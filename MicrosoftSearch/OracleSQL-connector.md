---
title: Oracle SQL Graph Connector für Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Richten Sie den Oracle SQL Graph Connector für Microsoft Search ein.
ms.openlocfilehash: 901b772def7585606a090d8a7696a32ff028e2a0
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508895"
---
<!---Previous ms.author:vivg --->

# <a name="oracle-sql-graph-connector"></a>Oracle SQL Graph Connector

Mit dem Oracle SQL Graph-Connector kann Ihre Organisation Daten aus einer lokalen Oracle-Datenbank ermitteln und indizieren. Der Connector indiziert den angegebenen Inhalt in Microsoft Search. Um den Index mit Quelldaten auf dem neuesten Stand zu halten, werden regelmäßige vollständige und inkrementelle Durchforstungen unterstützt. Mit dem Oracle SQL können Sie auch den Zugriff auf Suchergebnisse für bestimmte Benutzer einschränken.

> [!NOTE]
> Lesen Sie [**den Artikel Setup für Ihren Graph-Connector,**](configure-connector.md) um die allgemeinen Anweisungen zum Einrichten von Graph Connectors zu verstehen.

Dieser Artikel ist für alle Personen verfügbar, die einen Oracle SQL Graph-Connector konfigurieren, ausgeführt und überwachen. Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Oracle SQL Graph-Connector gelten. Dieser Artikel enthält auch Informationen zur [Problembehandlung und](#troubleshooting) [Einschränkungen](#limitations).

## <a name="before-you-get-started"></a>Bevor Sie beginnen

### <a name="install-the-graph-connector-agent"></a>Installieren des Graph-Connector-Agents

Um auf Ihre lokalen Drittanbieterdaten zugreifen zu können, müssen Sie den Graph-Connector-Agent installieren und konfigurieren. Weitere Informationen finden Sie unter [Installieren des Graph-Connector-Agents.](on-prem-agent.md)  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center

Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Um Ihren Oracle SQL-Connector mit einer Datenquelle zu verbinden, müssen Sie den Datenbankserver, den Sie durchforsten möchten, und den lokalen Graph-Connector-Agent konfigurieren. Anschließend können Sie eine Verbindung mit der Datenbank mit der erforderlichen Authentifizierungsmethode herstellen.

Für oracle SQL müssen Sie den Namen Hostname, Port und Dienst (Datenbank) zusammen mit der bevorzugten Authentifizierungsmethode, dem Benutzernamen und dem Kennwort angeben.

> [!NOTE]
> Ihre Datenbank muss Die Version 11g oder höher der Oracle-Datenbank ausführen, damit der Connector eine Verbindung herstellen kann. Der Connector unterstützt die Auf Windows-, Linux- und Azure-VM-Plattformen gehostete Oracle-Datenbank.

Zum Durchsuchen des Datenbankinhalts müssen Sie beim Konfigurieren des Connectors SQL Abfragen angeben. Diese SQL müssen alle Datenbankspalten benennen, die Sie indizieren möchten (d. h. Quelleigenschaften), einschließlich aller SQL-Verknüpfungen, die ausgeführt werden müssen, um alle Spalten zu erhalten. Um den Zugriff auf Suchergebnisse einzuschränken, müssen Sie Zugriffssteuerungslisten (Access Control Lists, ACLs) in SQL angeben, wenn Sie den Connector konfigurieren.

## <a name="step-3a-full-crawl-required"></a>Schritt 3a: Vollständige Durchforstung (erforderlich)

In diesem Schritt konfigurieren Sie die SQL, die eine vollständige Durchforstung der Datenbank ausgeführt wird. Bei der vollständigen Durchforstung werden alle Spalten oder Eigenschaften ausgewählt, in denen Sie die Optionen **Query,** **Search** oder **Retrieve auswählen möchten.** Sie können auch ACL-Spalten angeben, um den Zugriff auf Suchergebnisse auf bestimmte Benutzer oder Gruppen einzuschränken.

> [!Tip]
> Um alle benötigten Spalten zu erhalten, können Sie mehrere Tabellen verbinden.

![Skript mit den Beispieleigenschaften OrderTable und AclTable](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Auswählen von Datenspalten (erforderlich) und ACL-Spalten (Optional)

Das Beispiel veranschaulicht die Auswahl von fünf Datenspalten, die die Daten für die Suche enthalten: OrderId, OrderTitle, OrderDesc, CreatedDateTime und IsDeleted. Zum Festlegen von Ansichtsberechtigungen für jede Datenzeile können Sie optional die folgenden ACL-Spalten auswählen: AllowedUsers, AllowedGroups, DeniedUsers und DeniedGroups. Für alle diese Datenspalten können Sie die Optionen für **Query,** **Search** oder **Retrieve auswählen.**

Wählen Sie Datenspalten wie in dieser Beispielabfrage dargestellt aus: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Zum Verwalten des Zugriffs auf die Suchergebnisse können Sie eine oder mehrere ACL-Spalten in der Abfrage angeben. Der SQL ermöglicht es Ihnen, den Zugriff auf Datensatzebene zu steuern. Sie können dieselbe Zugriffssteuerung für alle Datensätze in einer Tabelle auswählen. Wenn die ACL-Informationen in einer separaten Tabelle gespeichert sind, müssen Sie möglicherweise eine Verknüpfung mit diesen Tabellen in Ihrer Abfrage ausführen.

Die Verwendung der einzelnen ACL-Spalten in der obigen Abfrage wird unten beschrieben. In der folgenden Liste werden die vier **Zugriffssteuerungsmechanismen erläutert.**

* **AllowedUsers**: Diese Option gibt die Liste der Benutzer-IDs an, die auf die Suchergebnisse zugreifen können. Im folgenden Beispiel hat die Liste der Benutzer: john@contoso.com, keith@contoso.com und lisa@contoso.com nur zugriff auf einen Datensatz mit OrderId = 12.
* **AllowedGroups**: Diese Option gibt die Gruppe von Benutzern an, die auf die Suchergebnisse zugreifen können. Im folgenden Beispiel haben gruppen sales-team@contoso.com nur Zugriff auf Aufzeichnungen mit OrderId = 12.
* **DeniedUsers**: Diese Option gibt die Liste der Benutzer an, die **keinen** Zugriff auf die Suchergebnisse haben. Im folgenden Beispiel haben Benutzer john@contoso.com und keith@contoso.com keinen Zugriff auf Aufzeichnungen mit OrderId = 13, während alle anderen Benutzer Zugriff auf diesen Datensatz haben.
* **DeniedGroups**: Diese Option gibt die Gruppe von Benutzern an, die **keinen** Zugriff auf die Suchergebnisse haben. Im folgenden Beispiel haben Gruppen engg-team@contoso.com und pm-team@contoso.com keinen Zugriff auf Die Aufzeichnung mit OrderId = 15, während alle anderen Benutzer Zugriff auf diesen Datensatz haben.  

![Beispieldaten mit den Beispieleigenschaften OrderTable und AclTable](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Unterstützte Datentypen

In der folgenden Tabelle sind die Datentypen zusammengefasst, die vom Oracle-SQL werden. In der Tabelle wird auch der Indizierungsdatentyp für den unterstützten SQL zusammengefasst. Weitere Informationen zu von Microsoft Graph Connectors unterstützten Datentypen für die Indizierung finden Sie in der Dokumentation zu [Eigenschaftenressourcentypen](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true).

| Kategorie | Quelldatentyp | Indizierungsdatentyp |
| ------------ | ------------ | ------------ |
| Zahlendatentyp | NUMBER(p,0) | int64 (für p <= 18) <br> double (für P > 18) |
| Datentyp für Gleitkommazahlen | NUMBER(p,s) <br> FLOAT(p) | double |
| Datumsdatentyp | DATE <br> TIMESTAMP <br> TIMESTAMP(n) | Datum/Uhrzeit |
| Zeichendatentyp | CHAR(n) <br> VARCHAR <br> VARCHAR2 <br> LONG <br> CLOB <br> NCLOB | Zeichenfolge |
| Unicode-Zeichendatentyp | NCHAR <br> NVARCHAR | Zeichenfolge |
| RowID-Datentyp | ROWID <br> UROWID | Zeichenfolge |

Für alle anderen Datentypen, die derzeit nicht direkt unterstützt werden, muss die Spalte explizit in einen unterstützten Datentyp umg castt werden.

### <a name="watermark-required"></a>Wasserzeichen (erforderlich)

Um zu verhindern, dass die Datenbank überlastet wird, stapelt und setzt der Connector vollständige Durchforstungsabfragen mit einer Vollständigdurchforstungswasserzeichenspalte fort. Mithilfe des Werts der Wasserzeichenspalte wird jeder nachfolgende Batch abgerufen, und die Abfrage wird vom letzten Prüfpunkt fortgesetzt. Im Wesentlichen handelt es sich dabei um einen Mechanismus zum Steuern der Datenaktualisierung für vollständige Durchforstungen.

Erstellen Sie Abfrageausschnitte für Wasserzeichen, wie in den folgenden Beispielen gezeigt:

* `WHERE (CreatedDateTime > @watermark)`. Geben Sie den Namen der Wasserzeichenspalte mit dem reservierten Schlüsselwort `@watermark` an. Sie können die Wasserzeichenspalte nur in aufsteigender Reihenfolge sortieren.
* `ORDER BY CreatedDateTime ASC`. Sortieren Sie nach der Wasserzeichenspalte in aufsteigender Reihenfolge.

In der in der folgenden Abbildung gezeigten Konfiguration `CreatedDateTime` befindet sich die ausgewählte Wasserzeichenspalte. Geben Sie zum Abrufen des ersten Zeilenbatches den Datentyp der Wasserzeichenspalte an. In diesem Fall ist der Datentyp `DateTime` .

![Konfiguration von Wasserzeichenspalten](media/MSSQL-watermark.png)

Die erste Abfrage ruft die erste **N-Anzahl** von Zeilen mithilfe von ab: "CreatedDateTime > January 1, 1753 00:00:00" (min value of DateTime data type). Nachdem der erste Batch abgerufen wurde, wird der höchste Wert, der im Batch zurückgegeben wird, als Prüfpunkt gespeichert, wenn die Zeilen in aufsteigender `CreatedDateTime` Reihenfolge sortiert sind. Ein Beispiel ist der 1. März 2019 03:00:00. Anschließend wird der nächste Batch **von N-Zeilen** mithilfe von "CreatedDateTime > March 1, 2019 03:00:00" in der Abfrage abgerufen.

### <a name="skipping-soft-deleted-rows-optional"></a>Überspringen weich gelöschter Zeilen (Optional)

Geben Sie den Namen und Wert der Spalte "Soft-Delete" an, der angibt, dass die Zeile gelöscht wird, um die Indizierung weich gelöschter Zeilen in Ihrer Datenbank auszuschließen.

![Einstellungen für "Soft Delete": "Spalte "Soft delete" und "Wert der Spalte "Soft Delete", die eine gelöschte Zeile angibt.](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Vollständiger Crawl: Verwalten von Suchberechtigungen

Wählen **Sie Berechtigungen verwalten** aus, um die verschiedenen Zugriffssteuerungsspalten (Access Control, ACL) auszuwählen, die den Zugriffskontrollesmechanismus angeben. Wählen Sie den Spaltennamen aus, den Sie in der vollständigen Durchforstungsabfrage SQL haben.

Jede der ACL-Spalten wird als mehrwertige Spalte erwartet. Diese werte mit mehreren IDs können durch Trennzeichen wie Semikolon (;), Komma (,) und so weiter getrennt werden. Sie müssen dieses Trennzeichen im **Werttrennfeld** angeben.

Die folgenden ID-Typen werden für die Verwendung als ACLs unterstützt:

* **Benutzerprinzipalname (User Principal Name, UPN):** Ein Benutzerprinzipalname (User Principal Name, UPN) ist der Name eines Systembenutzers in einem E-Mail-Adressformat. Ein UPN (z. B. john.doe@domain.com) besteht aus dem Benutzernamen (Anmeldename), dem Trennzeichen (dem @-Symbol) und dem Domänennamen (UPN-Suffix).
* **Azure Active Directory (AAD)-ID:** In Azure AD verfügt jeder Benutzer oder jede Gruppe über eine Objekt-ID, die etwa wie "e0d3ad3d-0000-1111-2222-3c5f5c52ab9b" aussieht.
* **Active Directory (AD)-Sicherheits-ID:** In einem lokalen AD-Setup verfügen alle Benutzer und Gruppen über einen unveränderlichen, eindeutigen Sicherheitsbezeichner, der etwa "S-1-5-21-3878594291-2115959936-132693609-65242" aussieht.

![Suchberechtigungseinstellungen zum Konfigurieren von Zugriffssteuerungslisten](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Schritt 3b: Inkrementelle Durchforstung (Optional)

Geben Sie in diesem optionalen Schritt eine SQL, um eine inkrementelle Durchforstung der Datenbank ausführen. Bei dieser Abfrage bestimmt der SQL alle Änderungen an den Daten seit der letzten inkrementellen Durchforstung. Wählen Sie wie bei der vollständigen Durchforstung zwischen den Optionen **Query,** **Search** oder **Retrieve aus.** Geben Sie den gleichen Satz von ACL-Spalten an, den Sie in der vollständigen Durchforstungsabfrage angegeben haben.

Die Komponenten in der folgenden Abbildung ähneln den vollständigen Durchforstungskomponenten mit einer Ausnahme. In diesem Fall ist "ModifiedDateTime" die ausgewählte Wasserzeichenspalte. Überprüfen Sie [die vollständigen Durchforstungsschritte,](#step-3a-full-crawl-required) um zu erfahren, wie Sie Ihre inkrementelle Durchforstungsabfrage schreiben, und sehen Sie sich das folgende Bild als Beispiel an.

![Inkrementelles Durchforstungsskript mit OrderTable-, AclTable- und Beispieleigenschaften, die verwendet werden können.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Schritt 4: Zuweisen von Eigenschaftsbezeichnungen

Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-5-manage-schema"></a>Schritt 5: Verwalten des Schemas

Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-search-permissions"></a>Schritt 6: Verwalten von Suchberechtigungen

Sie können die im vollständigen Durchforstungsbildschirm angegebenen [ACLs](#full-crawl-manage-search-permissions) verwenden, oder Sie können sie außer Kraft setzen, um Ihre Inhalte für jeden sichtbar zu machen.

## <a name="step-7-choose-refresh-settings"></a>Schritt 7: Auswählen von Aktualisierungseinstellungen

Der Oracle SQL unterstützt Aktualisierungszeitpläne für vollständige und inkrementelle Durchforstungen. Es wird empfohlen, beides zu setzen.

Ein vollständiger Durchforstungszeitplan findet gelöschte Zeilen, die zuvor mit dem Microsoft Search-Index synchronisiert wurden, sowie alle Zeilen, die aus dem Synchronisierungsfilter verschoben wurden. Wenn Sie zum ersten Mal eine Verbindung mit der Datenbank herstellen, wird eine vollständige Durchforstung ausgeführt, um alle von der vollständigen Durchforstungsabfrage abgerufenen Zeilen zu synchronisieren. Um neue Zeilen zu synchronisieren und Updates zu erstellen, müssen Sie inkrementelle Durchforstungen planen.

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!--- ## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md). -->

## <a name="troubleshooting"></a>Problembehandlung

Darunter finden Sie eine Liste der häufigen Fehler, die beim Konfigurieren des Connectors und deren mögliche Gründe festgestellt wurden.

| Konfigurationsschritt | Fehlermeldung | Mögliche Gründe |
| ------------ | ------------ | ------------ |
| Datenbankeinstellungen | Fehler vom Datenbankserver: Zeitfehler bei Verbindungsanforderung | Ungültiger Hostname <br> Host nicht erreichbar |
| Datenbankeinstellungen | Fehler vom Datenbankserver: ORA-12541: TNS: Kein Listener | Ungültiger Port |
| Datenbankeinstellungen | Fehler vom Datenbankserver: ORA-12514: TNS: Listener weiß derzeit nicht, welche Dienste in connector descriptor angefordert werden | Ungültiger Dienstname (Datenbank) |
| Datenbankeinstellungen | Fehler vom Datenbankserver: Fehler bei der Anmeldung für Benutzer ' `user` '. | Ungültiger Benutzername oder Kennwort |

## <a name="limitations"></a>Einschränkungen

Der Oracle SQL hat in der Vorschauversion die folgenden Einschränkungen:

* In der lokalen Datenbank muss Oracle Database Version 11g oder höher ausgeführt werden.
* ACLs werden nur mithilfe eines Benutzerprinzipalnamens (User Principal Name, UPN), Azure Active Directory (Azure AD) oder Active Directory Security unterstützt.
* Die Indizierung von Rich Content in Datenbankspalten wird nicht unterstützt. Beispiele für solche Inhalte sind HTML, JSON, XML, Blobs und Dokument parsings, die als Links in den Datenbankspalten vorhanden sind.
