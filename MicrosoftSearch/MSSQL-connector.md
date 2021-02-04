---
title: Azure SQL und Microsoft SQL Server Graph Connector für Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Richten Sie den Azure SQL und Microsoft SQL Graph Connector für Microsoft Search ein.
ms.openlocfilehash: 9f0a0a617541c6e27196a183d3283e0f05163dec
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097439"
---
<!---Previous ms.author: vivg --->

# <a name="azure-sql-and-microsoft-sql-server-graph-connectors"></a>Azure SQL und Microsoft SQL Server Graph Connectors

Mit dem Microsoft SQL-Server oder Azure SQL -Graph-Connector kann Ihre Organisation Daten aus einer lokalen SQL Server-Datenbank oder einer datenbank, die in Ihrer Azure SQL-Instanz in der Cloud gehostet wird, ermitteln und indizieren.
Der Graph Connector indiziert den angegebenen Inhalt in Microsoft Search. Um den Index mit Quelldaten auf dem neuesten Stand zu halten, werden regelmäßige vollständige und inkrementelle Durchforstungen unterstützt. Mit diesen SQL Connectors können Sie auch den Zugriff auf Suchergebnisse für bestimmte Benutzer einschränken.

> [!NOTE]
> Lesen Sie den [**Artikel zum Einrichten ihres Graph-Connectors,**](configure-connector.md) um den allgemeinen Einrichtungsprozess für Graph Connectors zu verstehen.

Dieser Artikel ist für jeden benutzer, der einen Azure SQL und Microsoft SQL Graph Connector konfiguriert, ausgeführt und überwacht. Sie ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Azure SQL und Microsoft SQL Graph-Connector gelten. Dieser Artikel enthält auch Informationen zu Einschränkungen [für](#limitations) den Microsoft SQL server und Azure SQL Connectors.

## <a name="before-you-get-started"></a>Bevor Sie beginnen

### <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a>Installieren des Graph-Connector-Agents (nur für lokalen Microsoft SQL Serverconnector erforderlich)

Um auf Ihre lokalen Drittanbieterdaten zugreifen zu können, müssen Sie den Graph-Connector-Agent installieren und konfigurieren. Weitere [Informationen finden Sie unter "Installieren des Graph-Connector-Agents".](on-prem-agent.md)  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

### <a name="register-an-app-for-azure-sql-connector-only"></a>Registrieren einer App (nur für Azure SQL Connector)

Für Azure SQL Connector müssen Sie eine App in Azure Active Directory registrieren, damit die Microsoft Search-App auf Daten für die Indizierung zugreifen kann. Weitere Informationen zum Registrieren einer App finden Sie in der Microsoft Graph-Dokumentation zum Registrieren [einer App.](https://docs.microsoft.com/graph/auth-register-app-v2)

Nachdem Sie die Registrierung der App abgeschlossen und den App-Namen, die Anwendungs-ID (Client-ID) und die Mandanten-ID notiert haben, müssen Sie einen neuen geheimen [Clientgeheimnis generieren.](https://docs.microsoft.com/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret) Der geheime Client wird nur einmal angezeigt. Denken Sie daran, & den geheimen Clientgeheimnis sicher zu speichern. Verwenden Sie die Client-ID und den geheimen Clientgeheimnis beim Konfigurieren einer neuen Verbindung in Microsoft Search.

Zum Hinzufügen der registrierten App zu Ihrer Azure SQL-Datenbank müssen Sie:

- Melden Sie sich bei Ihrer Azure SQL DB an.
- Öffnen eines neuen Abfragefensters
- Erstellen Eines neuen Benutzers durch Ausführen des Befehls 'CREATE USER [app name] FROM EXTERNAL PROVIDER'
- Fügen Sie benutzer zur Rolle hinzu, indem Sie den Befehl 'exec sp_addrolemember 'db_datareader', [app name]' oder 'ALTER ROLE db_datareader ADD MEMBER [app name]' ausführen.

>[!NOTE]
>Informationen zum Widerrufen des Zugriffs auf alle in Azure Active Directory registrierten Apps finden Sie in der Azure-Dokumentation zum Entfernen [einer registrierten App.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-remove-app)

### <a name="connection-settings"></a>Verbindungseinstellungen

Um Ihren Microsoft SQL-Serverconnector mit einer Datenquelle zu verbinden, müssen Sie den Datenbankserver, den Sie durchforsten möchten, und den agent vor Ort konfigurieren. Anschließend können Sie mit der erforderlichen Authentifizierungsmethode eine Verbindung mit der Datenbank herstellen.

> [!NOTE] 
> Ihre Datenbank muss SQL Version 2008 oder höher ausgeführt werden, damit der Microsoft SQL Server Connector eine Verbindung herstellen kann.

Für den Azure SQL Connector müssen Sie nur den Servernamen oder die IP-Adresse angeben, mit dem Sie eine Verbindung herstellen möchten. Azure SQL Connector unterstützt nur die Azure Active Directory Open ID Connect (OIDC)-Authentifizierung, um eine Verbindung mit der Datenbank herzustellen.

Um zusätzliche Sicherheit zu gewährleisten, können Sie DIE-IP-Firewallregeln für Ihren Azure SQL server oder datenbank konfigurieren. Weitere Informationen zum Einrichten von IP-Firewallregeln finden Sie in der Dokumentation zu [IP-Firewallregeln.](https://docs.microsoft.com/azure/azure-sql/database/firewall-configure) Fügen Sie die folgenden Client-IP-Bereiche in den Firewalleinstellungen hinzu.

| Region | IP-Bereich |
| ------------ | ------------ |
| NAM | 52.250.92.252/30, 52.224.250.216/30 |
| EUR | 20.54.41.208/30, 51.105.159.88/30 |
| APC | 52.139.188.212/30, 20.43.146.44/30 |

Zum Durchsuchen des Datenbankinhalts müssen Sie SQL beim Konfigurieren des Connectors angeben. Diese SQL müssen alle Datenbankspalten benennen, die Sie indizieren möchten (d. h. Quelleigenschaften), einschließlich aller SQL-Verknüpfungen, die ausgeführt werden müssen, um alle Spalten zu erhalten. Um den Zugriff auf Suchergebnisse einzuschränken, müssen Sie zugriffssteuerungslisten (Access Control Lists, ACLs) in SQL angeben, wenn Sie den Connector konfigurieren.

## <a name="step-3a-full-crawl-required"></a>Schritt 3a: Vollständige Durchforstung (erforderlich)

In diesem Schritt konfigurieren Sie die SQL, mit der eine vollständige Durchforstung der Datenbank ausgeführt wird. Bei der vollständigen Durchforstung werden alle Spalten oder Eigenschaften ausgewählt, in denen Sie die Optionen **"Abfrage",** **"Suche"** oder **"Abrufen" auswählen möchten.** Sie können auch Zugriffssteuerungsspalten angeben, um den Zugriff auf Suchergebnisse auf bestimmte Benutzer oder Gruppen zu beschränken.

> [!Tip]
> Um alle benötigten Spalten zu erhalten, können Sie mehrere Tabellen verbinden.

![Skript mit OrderTable und AclTable mit Beispieleigenschaften](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Auswählen von Datenspalten (erforderlich) und ACL-Spalten (optional)

Das Beispiel veranschaulicht eine Auswahl von fünf Datenspalten, die die Daten für die Suche enthalten: OrderId, OrderTitle, OrderDesc, CreatedDateTime und IsDeleted. Zum Festlegen von Ansichtsberechtigungen für jede Datenzeile können Sie optional die folgenden Spalten für die Zugriffssteuerungsberechtigung auswählen: AllowedUsers, AllowedGroups, DeniedUsers und DeniedGroups. Alle diese Datenspalten verfügen auch über die Optionen **"Abfragen",** **"Suchen"** oder **"Abrufen".**

Wählen Sie Datenspalten wie in dieser Beispielabfrage dargestellt aus: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Um den Zugriff auf die Suchergebnisse zu verwalten, können Sie eine oder mehrere ACL-Spalten in der Abfrage angeben. Der SQL ermöglicht es Ihnen, den Zugriff auf Datensatzebene zu steuern. Sie können dieselbe Zugriffssteuerung für alle Datensätze in einer Tabelle auswählen. Wenn die Informationen zur ACL in einer separaten Tabelle gespeichert sind, müssen Sie möglicherweise eine Verknüpfung mit diesen Tabellen in Ihrer Abfrage ausführen.

Die Verwendung der einzelnen Spalten der ACL in der obigen Abfrage wird unten beschrieben. In der folgenden Liste werden die vier Mechanismen **für die Zugriffssteuerung erläutert.**

- **AllowedUsers:** Diese Spalte gibt die Liste der Benutzer-IDs an, die auf die Suchergebnisse zugreifen können. Im folgenden Beispiel hat die Liste der Benutzer: john@contoso.com, keith@contoso.com und lisa@contoso.com haben nur Zugriff auf einen Datensatz mit OrderId = 12.
- **AllowedGroups:** Diese Spalte gibt die Gruppe von Benutzern an, die auf die Suchergebnisse zugreifen können. Im folgenden Beispiel hat sales-team@contoso.com nur Zugriff auf einen Datensatz mit OrderId = 12.
- **DeniedUsers**: Diese Spalte gibt die Liste der Benutzer an, die **keinen** Zugriff auf die Suchergebnisse haben. Im folgenden Beispiel haben Benutzer john@contoso.com und keith@contoso.com keinen Zugriff auf die Aufzeichnung mit OrderId = 13, während alle anderen Benutzer Zugriff auf diesen Datensatz haben.
- **DeniedGroups:** Diese Spalte gibt die Gruppe von Benutzern an, die **keinen** Zugriff auf die Suchergebnisse haben. Im folgenden Beispiel haben Gruppen engg-team@contoso.com und pm-team@contoso.com keinen Zugriff auf einen Datensatz mit OrderId = 15, während alle anderen Personen Zugriff auf diesen Datensatz haben.  

![Beispieldaten mit OrderTable und AclTable mit Beispieleigenschaften](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Unterstützte Datentypen

In der folgenden Tabelle sind die SQL zusammengefasst, die in den MS-SQL- und Azure SQL unterstützt werden. In der Tabelle wird auch der Indizierungsdatentyp für den unterstützten SQL zusammengefasst. Weitere Informationen zu von Microsoft Graph Connectors unterstützten Datentypen für die Indizierung finden Sie in der Dokumentation zu [Eigenschaftsressourcentypen.](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true)

| Kategorie | Quelldatentyp | Indizierungsdatentyp |
| ------------ | ------------ | ------------ |
| Datum und Uhrzeit | date <br> Datum/Uhrzeit <br> datetime2 <br> smalldatetime | Datum/Uhrzeit |
| Exakt numerisch | bigint <br> int <br> smallint <br> tinyint | int64 |
| Exakt numerisch | bit | Boolescher Wert |
| Ungefähre numerische Werte | Gleitkommazahl <br> real | double |
| Zeichenfolge | char <br> varchar <br> text | string |
| Zeichenfolgen für Unicodezeichen | nchar <br> nvarchar <br> ntext | Zeichenfolge |
| Andere Datentypen | uniqueidentifier | Zeichenfolge |

Für alle anderen Datentypen, die derzeit nicht direkt unterstützt werden, muss die Spalte explizit in einen unterstützten Datentyp umgumart werden.

### <a name="watermark-required"></a>Wasserzeichen (erforderlich)

Um zu verhindern, dass die Datenbank überlastet wird, stapelt und nimmt der Connector vollständige Durchforstungsabfragen mit einer vollständig durchforsteten Wasserzeichenspalte wieder auf. Mithilfe des Werts der Wasserzeichenspalte wird jeder nachfolgende Batch abgerufen, und die Abfrage wird vom letzten Prüfpunkt fortgesetzt. Im Wesentlichen steuert dieser Mechanismus die Datenaktualisierung für vollständige Durchforstungen.

Erstellen Sie Abfrageausschnitte für Wasserzeichen, wie in den folgenden Beispielen gezeigt:

- `WHERE (CreatedDateTime > @watermark)`. Geben Sie den Namen der Wasserzeichenspalte mit dem reservierten Schlüsselwort `@watermark` an. Wenn die Sortierreihenfolge der Wasserzeichenspalte aufsteigend ist, verwenden Sie ; verwenden Sie `>` andernfalls `<` .
- `ORDER BY CreatedDateTime ASC`. Sortieren Nach der Wasserzeichenspalte in aufsteigender oder absteigender Reihenfolge.

In der in der folgenden Abbildung gezeigten Konfiguration befindet sich `CreatedDateTime` die ausgewählte Wasserzeichenspalte. Geben Sie zum Abrufen des ersten Zeilenbatches den Datentyp der Wasserzeichenspalte an. In diesem Fall ist der Datentyp `DateTime` .

![Konfiguration von Wasserzeichenspalten](media/MSSQL-watermark.png)

Die erste Abfrage ruft die erste **N** Anzahl von Zeilen mithilfe von: "CreatedDateTime > January 1, 1753 00:00:00" (min value of DateTime data type). Nachdem der erste Batch abgerufen wurde, wird der höchste Im Batch zurückgegebene Wert als Prüfpunkt gespeichert, wenn die Zeilen `CreatedDateTime` in aufsteigender Reihenfolge sortiert werden. Ein Beispiel ist der 1. März 2019 03:00:00. Anschließend wird der nächste Batch von **N** Zeilen mit "CreatedDateTime > March 1, 2019 03:00:00" in der Abfrage abgerufen.

### <a name="skipping-soft-deleted-rows-optional"></a>Überspringen von nicht gelöschten Zeilen (optional)

Wenn Sie die Indizierung für nicht gelöschte Zeilen in der Datenbank ausschließen möchten, geben Sie den Namen und Wert der Spalte zum löschen an, der angibt, dass die Zeile gelöscht wird.

![Soft delete settings: "Soft delete column" and "Value of soft delete column which indicates a deleted row"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Vollständige Durchforstung: Verwalten von Suchberechtigungen

Wählen **Sie "Berechtigungen verwalten"** aus, um die verschiedenen Zugriffssteuerungsspalten (Access Control, ACL) auszuwählen, die den Zugriffsteuerungsmechanismus angeben. Wählen Sie den Spaltennamen aus, den Sie in der vollständigen Durchforstungsabfrage SQL haben.

Es wird erwartet, dass es sich bei allen Spalten der ACL um eine mehrwertige Spalte handelt. Diese Mehrfach-ID-Werte können durch Trennzeichen wie Semikolon (;), Komma (,) und so weiter getrennt werden. Sie müssen dieses Trennzeichen im **Werttrennfeld** angeben.

Die folgenden ID-Typen werden für die Verwendung als ACLs unterstützt:

- **Benutzerprinzipalname (UPN):** Ein Benutzerprinzipalname (User Principal Name, UPN) ist der Name eines Systembenutzers in einem E-Mail-Adressformat. Ein UPN (z. B. john.doe@domain.com) besteht aus dem Benutzernamen (Anmeldename), dem Trennzeichen (dem @-Symbol) und dem Domänennamen (UPN-Suffix).
- **Azure Active Directory (AAD)-ID:** In Azure AD verfügt jeder Benutzer oder jede Gruppe über eine Objekt-ID, die etwa wie "e0d3ad3d-0000-1111-2222-3c5f5c52ab9b" aussieht.
- **Active Directory (AD)-Sicherheits-ID:** Bei einer lokalen Einrichtung von AD verfügen alle Benutzer und Gruppen über eine unveränderliche, eindeutige Sicherheits-ID, die etwa wie "S-1-5-21-3878594291-2115959936-132693609-65242" aussieht.

![Suchberechtigungseinstellungen zum Konfigurieren von Zugriffssteuerungslisten](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Schritt 3b: Inkrementelle Durchforstung (optional)

Stellen Sie in diesem optionalen Schritt eine SQL, um eine inkrementelle Durchforstung der Datenbank ausführen. Bei dieser Abfrage ermittelt der SQL alle Änderungen an den Daten seit der letzten inkrementellen Durchforstung. Wählen Sie wie bei der vollständigen Durchforstung alle Spalten aus, in denen Sie die Optionen **"Abfrage",** **"Suche"** oder **"Abrufen" auswählen möchten.** Geben Sie den gleichen Satz von ACL-Spalten an, den Sie in der vollständigen Durchforstungsabfrage angegeben haben.

Die Komponenten in der folgenden Abbildung ähneln den vollständigen Durchforstungskomponenten mit einer Ausnahme. In diesem Fall ist "ModifiedDateTime" die ausgewählte Wasserzeichenspalte. Überprüfen Sie [die vollständigen Durchforstungsschritte,](#step-3a-full-crawl-required) um zu erfahren, wie Sie ihre inkrementelle Durchforstungsabfrage schreiben, und sehen Sie sich die folgende Abbildung als Beispiel an.

![Inkrementelles Durchforstungsskript mit OrderTable-, AclTable- und Beispieleigenschaften, die verwendet werden können.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Schritt 4: Zuweisen von Eigenschaftsbezeichnungen

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-5-manage-schema"></a>Schritt 5: Verwalten des Schemas

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-6-manage-search-permissions"></a>Schritt 6: Verwalten von Suchberechtigungen

Sie können die im vollständigen Durchforstungsbildschirm angegebenen [ACLs](#full-crawl-manage-search-permissions) verwenden oder sie außer Kraft setzen, um Ihre Inhalte für jeden sichtbar zu machen.

## <a name="step-7-choose-refresh-settings"></a>Schritt 7: Auswählen von Aktualisierungseinstellungen

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="next-steps-customize-the-search-results-page"></a>Nächste Schritte: Anpassen der Suchergebnissetseite

Erstellen Sie ihre eigenen Vertikalen und Ergebnistypen, damit Endbenutzer Suchergebnisse aus neuen Verbindungen anzeigen können. Ohne diesen Schritt werden Daten aus Ihrer Verbindung nicht auf der Suchergebnissetseite angezeigt.

Weitere Informationen zum Erstellen ihrer Vertikalen und MRTs finden Sie unter [Anpassung der Suchergebnisseite.](customize-search-page.md)

<!---## Troubleshooting-->

<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Einschränkungen

Die SQL connectors haben diese Einschränkungen in der Vorschauversion:

- Microsoft SQL-Serverconnector: Die lokale Datenbank muss SQL Serverversion 2008 oder höher ausgeführt werden.
- Das M365-Abonnement und das Azure-Abonnement (Das Hosten der Azure SQL-Datenbank) müssen sich im selben Azure Active Directory befinden.
- ACLs werden nur unter Verwendung eines Benutzerprinzipalnamens (User Principal Name, UPN), Azure Active Directory (Azure AD) oder Active Directory Security unterstützt.
- Die Indizierung von umfangreichem Inhalt in Datenbankspalten wird nicht unterstützt. Beispiele für solche Inhalte sind HTML, JSON, XML, BLOBS und Dokumentparsings, die als Links innerhalb der Datenbankspalten vorhanden sind.
