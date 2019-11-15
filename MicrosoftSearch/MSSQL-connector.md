---
title: Microsoft SQL Connector für Microsoft-Suche
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Richten Sie den Microsoft SQL Connector für Microsoft Search ein.
ms.openlocfilehash: a073a6d3f226e5f8b0ea297494a8889f1f50bab1
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626756"
---
# <a name="microsoft-sql-server-connector"></a>Microsoft SQL Server-Connector

Mit einem Microsoft SQL Server-Connector kann Ihre Organisation Daten aus einer lokalen SQL Server Datenbank ermitteln und indizieren. Der Connector indiziert angegebene Inhalte in Microsoft Search. Um den Index mit den Quelldaten auf dem neuesten Stand zu halten, unterstützt er periodische vollständige und inkrementelle Crawls. Mit dem SQL Server-Konnektor können Sie auch den Zugriff auf Suchergebnisse für bestimmte Benutzer einschränken.

Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen Microsoft SQL Server-Connector konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.

## <a name="install-a-data-gateway"></a>Installieren eines Datengateways
Um auf Ihre drittanbieterdaten zugreifen zu können, müssen Sie ein Microsoft Power BI-Gateway installieren und konfigurieren. Weitere Informationen finden Sie unter [Install and on-premises Gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) .  

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle
Um den Microsoft SQL Server-Connector mit einer Datenquelle zu verbinden, müssen Sie den Datenbankserver, den Sie durchforsten möchten, und das lokale Gateway konfigurieren. Sie können dann mit der erforderlichen Authentifizierungsmethode eine Verbindung mit der Datenbank herstellen.

> [!NOTE]
> In der Datenbank muss SQL Server Version 2008 oder höher ausgeführt werden.

Zum Durchsuchen des Datenbankinhalts müssen Sie beim Konfigurieren des Connectors SQL-Abfragen angeben. Diese SQL-Abfragen müssen alle Datenbankspalten benennen, die Sie indizieren möchten (also Quelleigenschaften), einschließlich aller SQL-Joins, die ausgeführt werden müssen, um alle Spalten abzurufen. Wenn Sie den Zugriff auf Suchergebnisse einschränken möchten, müssen Sie Zugriffssteuerungslisten (Access Control Lists, ACLs) mit SQL-Abfragen angeben, wenn Sie den Microsoft SQL Server-Connector konfigurieren.

## <a name="full-crawl-required"></a>Vollständige Durchforstung (erforderlich)
In diesem Schritt konfigurieren Sie die SQL-Abfrage, die eine vollständige Durchforstung der Datenbank ausführt. Bei der vollständigen Durchforstung werden alle Spalten oder Eigenschaften ausgewählt, die **abgefragt**, **durchsuchbar**oder **abrufbar**gemacht werden sollen. Sie können auch ACL-Spalten angeben, um den Zugriff auf Suchergebnisse auf bestimmte Benutzer oder Gruppen zu beschränken.

> [!Tip]
> Wenn Sie alle benötigten Spalten abrufen möchten, können Sie mehreren Tabellen beitreten.

![Skript, das die Sortier-und AclTable mit Beispiel Eigenschaften zeigt](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Auswählen von Datenspalten (erforderlich) und ACL-Spalten (optional)
Im Beispiel wird die Auswahl von fünf Datenspalten veranschaulicht, die die Daten für die Suche enthalten: OrderID, OrderTitle, OrderDesc, CreatedDateTime und IsDeleted. Um die Ansichtsberechtigungen für jede Datenzeile festzulegen, können Sie optional diese ACL-Spalten auswählen: AllowedUsers, AllowedGroups, DeniedUsers und DeniedGroups. Alle diese Datenspalten können **abgefragt**, **durchsuchbar**oder **abrufbar**gemacht werden.

Wählen Sie Datenspalten aus, wie in der folgenden Beispielabfrage gezeigt:`SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

### <a name="watermark-required"></a>Wasserzeichen (erforderlich)
Um zu verhindern, dass die Datenbank überladen wird, führt der Connector Batches aus und setzt vollständige Durchforstungs Abfragen mit einer Wasserzeichen Spalte vollständig Durchforstung fort. Durch Verwendung des Werts der Spalte Wasserzeichen wird jeder nachfolgende Batch abgerufen, und die Abfrage wird vom letzten Prüfpunkt fortgesetzt. Im Wesentlichen handelt es sich hierbei um einen Mechanismus zum Steuern der Datenaktualisierung für vollständige Durchforstungen.

Erstellen Sie Abfrage Ausschnitte für Wasserzeichen, wie in den folgenden Beispielen gezeigt:
* `WHERE (CreatedDateTime > @watermark)`. Zitieren Sie den Namen der Wasserzeichen Spalte `@watermark`mit dem reservierten Schlüsselwort. Wenn die Sortierreihenfolge der Wasserzeichen Spalte aufsteigend ist, verwenden Sie `>`; Andernfalls verwenden Sie `<`.
* `ORDER BY CreatedDateTime ASC`. Sortieren Sie in aufsteigender oder absteigender Reihenfolge nach der Wasserzeichen Spalte.

In der in der folgenden Abbildung gezeigten `CreatedDateTime` Konfiguration befindet sich die ausgewählte Wasserzeichen Spalte. Um den ersten Zeilenbatch abzurufen, geben Sie den Datentyp der Spalte Wasserzeichen an. In diesem Fall ist `DateTime`der Datentyp.

![](media/MSSQL-watermark.png)

Die erste Abfrage ruft die erste **N** -Menge von Zeilen mithilfe von: "CreatedDateTime #a0 January 1, 1753 00:00:00" (min-Wert des datetime-Datentyps) ab. Nachdem der erste Batch abgerufen wurde, wird der höchste im Batch `CreatedDateTime` zurückgegebene Wert als Prüfpunkt gespeichert, wenn die Zeilen in aufsteigender Reihenfolge sortiert werden. Ein Beispiel ist der 1. März 2019 03:00:00. Anschließend wird der nächste Batch von **N** Zeilen mithilfe von "CreatedDateTime #a0 March 1, 2019 03:00:00" in der Abfrage abgerufen.

### <a name="skipping-soft-deleted-rows-optional"></a>Überspringen von weich gelöschten Zeilen (optional)
Um vorläufig gelöschte Zeilen in Ihrer Datenbank von der Indizierung auszuschließen, geben Sie den Namen und den Wert der Soft-Delete-Spalte an, der angibt, dass die Zeile gelöscht wird.

![Einstellungen für "weiche Löschung": "weiche Löschspalte" und "Wert der Spalte" weiche Löschung ", die eine gelöschte Zeile angibt.](media/MSSQL-softdelete.png)

## <a name="incremental-crawl-optional"></a>Inkrementelle Durchforstung (optional)
Geben Sie in diesem optionalen Schritt eine SQL-Abfrage ein, um einen inkrementellen Crawl der Datenbank auszuführen. Mit dieser Abfrage nimmt der Microsoft SQL Server-Connector seit der letzten inkrementellen Durchforstung Änderungen an den Daten vor. Wählen Sie wie in der vollständigen Durchforstung alle Spalten aus, die **abgefragt**, **durchsuchbar**oder **abrufbar**gemacht werden sollen. Geben Sie dieselbe Gruppe von ACL-Spalten an, die Sie in der vollständigen Durchforstungs Abfrage angegeben haben.

Die Komponenten in der folgenden Abbildung ähneln den vollständigen Durchforstungskomponenten mit einer Ausnahme. In diesem Fall ist "ModifiedDateTime" die ausgewählte Wasserzeichen Spalte. Lesen Sie die [vollständigen Crawl Schritte](#full-crawl-required) , um zu erfahren, wie Sie Ihre inkrementelle Durchforstungs Abfrage schreiben und das folgende Bild als Beispiel betrachten.

![Inkrementelles Durchforstungs Skript mit Sortier-, AclTable-und Beispiel Eigenschaften, die verwendet werden können.](media/MSSQL-incrcrawl.png)

## <a name="limitations"></a>Einschränkungen
Der Microsoft SQL Server-Connector weist diese Einschränkungen in der Vorschauversion auf:
* In der lokalen Datenbank muss SQL Server Version 2008 oder höher ausgeführt werden.
* ACLs werden nur mit einem Benutzerprinzipalnamen (User Principal Name, UPN), Azure Active Directory (Azure AD) oder Active Directory Sicherheit unterstützt.
* Das Indizieren von umfangreichen Inhalten in Datenbankspalten wird nicht unterstützt. Beispiele für solche Inhalte sind HTML-, JSON-, XML-, BLOBs-und Dokumentanalysen, die als Links in den Datenbankspalten vorhanden sind.

