---
title: Oracle SQL Connector für Microsoft-Suche
ms.author: vivg
author: Vivek
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Richten Sie den Oracle SQL Connector für Microsoft Search ein.
ms.openlocfilehash: 794ba81778ae5acf30c539f78390872579ac5467
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408915"
---
# <a name="oracle-sql-connector"></a>Oracle SQL Connector

Mit dem Oracle SQL Connector kann Ihre Organisation Daten aus einer lokalen Oracle-Datenbank ermitteln und indizieren. Der Connector indiziert angegebene Inhalte in Microsoft Search. Um den Index mit den Quelldaten auf dem neuesten Stand zu halten, unterstützt er periodische vollständige und inkrementelle Crawls. Mit dem Oracle SQL Connector können Sie auch den Zugriff auf Suchergebnisse für bestimmte Benutzer einschränken.

Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen Oracle SQL Connector konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.

## <a name="install-the-graph-connector-agent"></a>Installieren des Graph Connector-Agents

Um auf Ihre lokalen drittanbieterdaten zugreifen zu können, müssen Sie den Graph Connector-Agent installieren und konfigurieren. Weitere Informationen finden Sie unter [install the graph Connector Agent](on-prem-agent.md) .  

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle

Um den Oracle SQL Connector mit einer Datenquelle zu verbinden, müssen Sie den Datenbankserver, den Sie durchforsten möchten, und den lokalen Graph Connector-Agent konfigurieren. Sie können dann mit der erforderlichen Authentifizierungsmethode eine Verbindung mit der Datenbank herstellen.

Für Oracle SQL Connector müssen Sie den Hostnamen, den Port und den Dienst (Daten Bank Name) zusammen mit der bevorzugten Authentifizierungsmethode, dem Benutzernamen und dem Kennwort angeben.

> [!NOTE]
> Für die Datenbank muss die Oracle-Datenbank Version 11g oder höher ausgeführt werden, damit der Connector eine Verbindung herstellen kann. Der Connector unterstützt die Oracle-Datenbank, die auf Windows-, Linux-und Azure VM-Plattformen gehostet wird.

Zum Durchsuchen des Datenbankinhalts müssen Sie beim Konfigurieren des Connectors SQL-Abfragen angeben. Diese SQL-Abfragen müssen alle Datenbankspalten benennen, die Sie indizieren möchten (also Quelleigenschaften), einschließlich aller SQL-Joins, die ausgeführt werden müssen, um alle Spalten abzurufen. Wenn Sie den Zugriff auf Suchergebnisse einschränken möchten, müssen Sie Zugriffssteuerungslisten (Access Control Lists, ACLs) in SQL-Abfragen angeben, wenn Sie den Connector konfigurieren.

## <a name="full-crawl-required"></a>Vollständige Durchforstung (erforderlich)

In diesem Schritt konfigurieren Sie die SQL-Abfrage, die eine vollständige Durchforstung der Datenbank ausführt. Bei der vollständigen Durchforstung werden alle Spalten oder Eigenschaften ausgewählt, die **abgefragt**, **durchsuchbar** oder **abrufbar** gemacht werden sollen. Sie können auch ACL-Spalten angeben, um den Zugriff auf Suchergebnisse auf bestimmte Benutzer oder Gruppen zu beschränken.

> [!Tip]
> Wenn Sie alle benötigten Spalten abrufen möchten, können Sie mehreren Tabellen beitreten.

![Skript, das die Sortier-und AclTable mit Beispiel Eigenschaften zeigt](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Auswählen von Datenspalten (erforderlich) und ACL-Spalten (optional)

Im Beispiel wird die Auswahl von fünf Datenspalten veranschaulicht, die die Daten für die Suche enthalten: OrderID, OrderTitle, OrderDesc, CreatedDateTime und IsDeleted. Um die Ansichtsberechtigungen für jede Datenzeile festzulegen, können Sie optional diese ACL-Spalten auswählen: AllowedUsers, AllowedGroups, DeniedUsers und DeniedGroups. Alle diese Datenspalten können **abgefragt**, **durchsuchbar** oder **abrufbar** gemacht werden.

Wählen Sie Datenspalten aus, wie in der folgenden Beispielabfrage gezeigt: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Um den Zugriff auf die Suchergebnisse zu verwalten, können Sie eine oder mehrere ACL-Spalten in der Abfrage angeben. Mit SQL Connector können Sie den Zugriff auf Datensatzebene steuern. Sie können auswählen, dass für alle Datensätze in einer Tabelle dieselbe Zugriffssteuerung gilt. Wenn die ACL-Informationen in einer separaten Tabelle gespeichert werden, müssen Sie möglicherweise eine Verknüpfung mit diesen Tabellen in Ihrer Abfrage durchführen.

Die Verwendung der einzelnen ACL-Spalten in der obigen Abfrage wird im folgenden beschrieben. In der folgenden Liste werden die vier **Zugriffssteuerungsmechanismen** erläutert.

* **AllowedUsers**: Hiermit wird die Liste der Benutzer-IDs angegeben, die auf die Suchergebnisse zugreifen können. Im folgenden Beispiel würde die Liste der Benutzer: John@contoso.com, Keith@contoso.com und Lisa@contoso.com nur Zugriff auf einen Datensatz mit OrderID = 12 haben.
* **AllowedGroups**: Hiermit wird die Benutzergruppe angegeben, die auf die Suchergebnisse zugreifen kann. Im folgenden Beispiel hätte Group Sales-Team@contoso.com nur Zugriff auf Record mit OrderID = 12.
* **DeniedUsers**: Dies gibt die Liste der Benutzer an, die **keinen** Zugriff auf die Suchergebnisse haben. Im folgenden Beispiel haben Benutzer John@contoso.com und Keith@contoso.com keinen Zugriff auf Record mit OrderID = 13, während alle anderen Zugriff auf diesen Datensatz haben.
* **DeniedGroups**: Hiermit wird die Gruppe von Benutzern angegeben, die **keinen** Zugriff auf die Suchergebnisse haben. Im folgenden Beispiel haben Gruppen Engg-Team@contoso.com und PM-Team@contoso.com keinen Zugriff auf Record mit OrderID = 15, während alle anderen Zugriff auf diesen Datensatz haben.  

![Beispieldaten, die die Sortier-und AclTable mit Beispiel Eigenschaften anzeigen](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Unterstützte Datentypen

In der folgenden Tabelle werden die Datentypen zusammengefasst, die vom Oracle SQL Connector unterstützt werden. Die Tabelle fasst auch den Indizierungs Datentyp für den unterstützten SQL-Datentyp zusammen. Weitere Informationen zu Microsoft Graph-Konnektoren, die unterstützte Datentypen für die Indizierung sind, finden Sie in der Dokumentation zu [Eigenschaften Ressourcentypen](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties).

| Kategorie | Source-Datentyp | Indizierungs Datentyp |
| ------------ | ------------ | ------------ |
| Datentyp "Number" | Zahl (p, 0) | Int64 (für p <= 18) <br> Double (für p > 18) |
| Datentyp für Gleitkommazahl | Zahl (p, s) <br> FLOAT (p) | double |
| Date-Datentyp | DATE <br> Timestamp <br> Zeitstempel (n) | Datum/Uhrzeit |
| Datentyp "Character" | CHAR (n) <br> VARCHAR <br> VARCHAR2 <br> Long <br> CLOB <br> NCLOB | string |
| Unicode-Zeichendatentyp | NCHAR <br> NVARCHAR | string |
| ROWID-Datentyp | ROWID <br> UROWID | string |

Für alle anderen Datentypen, die derzeit nicht direkt unterstützt werden, muss die Spalte explizit in einen unterstützten Datentyp umgewandelt werden.

### <a name="watermark-required"></a>Wasserzeichen (erforderlich)

Um zu verhindern, dass die Datenbank überladen wird, führt der Connector Batches aus und setzt vollständige Durchforstungs Abfragen mit einer Wasserzeichen Spalte vollständig Durchforstung fort. Durch Verwendung des Werts der Spalte Wasserzeichen wird jeder nachfolgende Batch abgerufen, und die Abfrage wird vom letzten Prüfpunkt fortgesetzt. Im Wesentlichen handelt es sich hierbei um einen Mechanismus zum Steuern der Datenaktualisierung für vollständige Durchforstungen.

Erstellen Sie Abfrage Ausschnitte für Wasserzeichen, wie in den folgenden Beispielen gezeigt:

* `WHERE (CreatedDateTime > @watermark)`. Zitieren Sie den Namen der Wasserzeichen Spalte mit dem reservierten Schlüsselwort `@watermark` . Sie können die Wasserzeichen Spalte nur in aufsteigender Reihenfolge sortieren.
* `ORDER BY CreatedDateTime ASC`. Sortieren Sie in aufsteigender Reihenfolge nach der Wasserzeichen Spalte.

In der in der folgenden Abbildung gezeigten Konfiguration `CreatedDateTime` befindet sich die ausgewählte Wasserzeichen Spalte. Um den ersten Zeilenbatch abzurufen, geben Sie den Datentyp der Spalte Wasserzeichen an. In diesem Fall ist der Datentyp `DateTime` .

![Konfiguration der Wasserzeichen Spalte](media/MSSQL-watermark.png)

Die erste Abfrage ruft die erste **N** -Anzahl von Zeilen mithilfe von: "CreatedDateTime > January 1, 1753 00:00:00" (min-Wert des datetime-Datentyps) ab. Nachdem der erste Batch abgerufen wurde, wird der höchste `CreatedDateTime` im Batch zurückgegebene Wert als Prüfpunkt gespeichert, wenn die Zeilen in aufsteigender Reihenfolge sortiert werden. Ein Beispiel ist der 1. März 2019 03:00:00. Anschließend wird der nächste Batch von **N** Zeilen mithilfe von "CreatedDateTime > March 1, 2019 03:00:00" in der Abfrage abgerufen.

### <a name="skipping-soft-deleted-rows-optional"></a>Überspringen von weich gelöschten Zeilen (optional)

Um vorläufig gelöschte Zeilen in Ihrer Datenbank von der Indizierung auszuschließen, geben Sie den Namen und den Wert der Soft-Delete-Spalte an, der angibt, dass die Zeile gelöscht wird.

![Einstellungen für "weiche Löschung": "weiche Löschspalte" und "Wert der Spalte" weiche Löschung ", die eine gelöschte Zeile angibt.](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Vollständige Durchforstung: Verwalten von Suchberechtigungen

Klicken Sie auf **Berechtigungen verwalten** , um die verschiedenen Spalten der Zugriffssteuerung (ACL) auszuwählen, die den Zugriffssteuerungsmechanismus angeben. Wählen Sie den Spaltennamen aus, den Sie in der vollständigen Durchforstungs-SQL-Abfrage angegeben haben.

Für jede der ACL-Spalten wird eine mehrwertige Spalte erwartet. Diese mehrere ID-Werte können durch Trennzeichen wie Semikolon (;), Komma (,) usw. getrennt werden. Sie müssen dieses Trennzeichen im Feld **Wert Trennzeichen** angeben.

Die folgenden ID-Typen werden für die Verwendung als ACLs unterstützt:

* **Benutzerprinzipalname (UPN)**: ein Benutzerprinzipalname (UPN) ist der Name eines Systembenutzers in einem e-Mail-Adressformat. Ein UPN (zum Beispiel: John.Doe@Domain.com) besteht aus dem Benutzernamen (Anmeldename), dem Trennzeichen (dem @-Symbol) und dem Domänennamen (UPN-Suffix).
* **Azure Active Directory (AAD) ID**: in Azure AD hat jeder Benutzer oder jede Gruppe eine Objekt-ID, die so aussieht wie "e0d3ad3d-0000-1111-2222-3c5f5c52ab9b".
* **Active Directory (AD)-Sicherheits-ID**: in einer lokalen AD-Einrichtung haben jeder Benutzer und jede Gruppe eine unveränderliche, eindeutige Sicherheits-ID, die ungefähr so aussieht, wie es-1-5-21-3878594291-2115959936-132693609-65242. "

![Berechtigungseinstellungen für die Suche zum Konfigurieren von Zugriffssteuerungslisten](media/MSSQL-ACL2.png)

## <a name="incremental-crawl-optional"></a>Inkrementelle Durchforstung (optional)

Geben Sie in diesem optionalen Schritt eine SQL-Abfrage ein, um einen inkrementellen Crawl der Datenbank auszuführen. Mit dieser Abfrage ermittelt der SQL Connector alle Änderungen an den Daten seit der letzten inkrementellen Durchforstung. Wählen Sie wie in der vollständigen Durchforstung alle Spalten aus, die **abgefragt**, **durchsuchbar** oder **abrufbar** gemacht werden sollen. Geben Sie dieselbe Gruppe von ACL-Spalten an, die Sie in der vollständigen Durchforstungs Abfrage angegeben haben.

Die Komponenten in der folgenden Abbildung ähneln den vollständigen Durchforstungskomponenten mit einer Ausnahme. In diesem Fall ist "ModifiedDateTime" die ausgewählte Wasserzeichen Spalte. Lesen Sie die [vollständigen Crawl Schritte](#full-crawl-required) , um zu erfahren, wie Sie Ihre inkrementelle Durchforstungs Abfrage schreiben und das folgende Bild als Beispiel betrachten.

![Inkrementelles Durchforstungs Skript mit Sortier-, AclTable-und Beispiel Eigenschaften, die verwendet werden können.](media/MSSQL-incrcrawl.png)

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen

Sie können die [im vollständigen Durchforstungs Bildschirm angegebenen ACLs](#full-crawl-manage-search-permissions) verwenden, oder Sie können Sie außer Kraft setzen, damit Ihre Inhalte für alle sichtbar sind.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans

Der Oracle SQL Connector unterstützt Aktualisierungs Zeitpläne für vollständige und inkrementelle Crawls. Es wird empfohlen, beides festzulegen.

Ein vollständiger durchforstungszeitplan sucht gelöschte Zeilen, die zuvor mit dem Microsoft-Suchindex synchronisiert wurden, sowie alle Zeilen, die aus dem Synchronisierungsfilter verschoben wurden. Wenn Sie zum ersten Mal eine Verbindung mit der Datenbank herstellen, wird eine vollständige Durchforstung ausgeführt, um alle von der vollständigen Durchforstungs Abfrage abgerufenen Zeilen zu synchronisieren. Um neue Zeilen zu synchronisieren und Aktualisierungen vorzunehmen, müssen Sie inkrementelle Durchforstungen planen.

## <a name="next-steps-customize-the-search-results-page"></a>Nächste Schritte: Anpassen der Suchergebnisseite

Erstellen Sie Ihre eigenen vertikalen und Ergebnistypen, sodass Endbenutzer Suchergebnisse aus neuen Verbindungen anzeigen können. Ohne diesen Schritt werden Daten aus ihrer Verbindung nicht auf der Suchergebnisseite angezeigt.

Weitere Informationen zum Erstellen von vertikalen und MRT finden Sie unter [Anpassen der Suchergebnisseite](customize-search-page.md).

## <a name="limitations"></a>Einschränkungen

Der Oracle SQL Connector weist diese Einschränkungen in der Vorschauversion auf:

* In der lokalen Datenbank muss die Oracle-Datenbank Version 11g oder höher ausgeführt werden.
* ACLs werden nur mit einem Benutzerprinzipalnamen (User Principal Name, UPN), Azure Active Directory (Azure AD) oder Active Directory Sicherheit unterstützt.
* Das Indizieren von umfangreichen Inhalten in Datenbankspalten wird nicht unterstützt. Beispiele für solche Inhalte sind HTML-, JSON-, XML-, BLOBs-und Dokumentanalysen, die als Links in den Datenbankspalten vorhanden sind.

## <a name="troubleshooting-guide"></a>Leitfaden zur Problembehandlung

Unten finden Sie eine Liste der häufigsten Fehler, die beim Konfigurieren des Connectors und ihrer möglichen Gründe beobachtet wurden.
| Konfigurationsschritt | Fehlermeldung | Mögliche Ursache (n) |
| ------------ | ------------ | ------------ |
| Datenbankeinstellungen | Fehler vom Datenbankserver: Timeout der Verbindungsanforderung | Ungültiger Hostname <br> Host nicht erreichbar |
| Datenbankeinstellungen | Fehler vom Datenbankserver: ORA-12541: TNS: No listner | Ungültiger Port |
| Datenbankeinstellungen | Fehler vom Datenbankserver: ORA-12514: TNS: listner kennt derzeit nicht den in Connector-Deskriptor angeforderten Dienst | Ungültiger Dienstname (Datenbank) |
| Datenbankeinstellungen | Fehler vom Datenbankserver: Fehler bei der Anmeldung für den Benutzer ' `user` '. | Ungültiger Benutzername oder Kennwort |
