---
title: Azure SQL und Microsoft SQL Server Graph Connector für Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Richten Sie den Azure SQL- und Microsoft SQL Graph-Connector für Microsoft Search ein.
ms.openlocfilehash: ae953d55de4a4f5e8afc32cc6b55f6e0b32e2811
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701435"
---
<!---Previous ms.author: vivg --->

# <a name="azure-sql-and-microsoft-sql-server-graph-connectors"></a>Azure SQL- und Microsoft SQL Server Graph-Connectors

Der Microsoft SQL Server- oder Azure SQL Graph-Connector ermöglicht Ihrer Organisation das Ermitteln und Indizieren von Daten aus einer lokalen SQL Server-Datenbank oder einer Datenbank, die in Ihrer Azure SQL Instanz in der Cloud gehostet wird.
Der Graph Connector indiziert den angegebenen Inhalt in Microsoft Search. Um den Index mit Quelldaten auf dem neuesten Stand zu halten, unterstützt er regelmäßige vollständige und inkrementelle Durchforstungen. Mit diesen SQL Connectors können Sie auch den Zugriff auf Suchergebnisse für bestimmte Benutzer einschränken.

> [!NOTE]
> Lesen Sie den Artikel [**"Setup Your Graph connector",**](configure-connector.md) um die allgemeinen Anweisungen zum Einrichten von Connectors Graph zu verstehen.

Dieser Artikel richtet sich an alle Personen, die einen Azure SQL und einen Microsoft SQL Server Graph Connector konfigurieren, ausführen und überwachen. Es ergänzt den allgemeinen Setupprozess und zeigt Anweisungen, die nur für den Azure SQL und microsoft SQL Server Graph Connector gelten. Dieser Artikel enthält auch Informationen zu [Einschränkungen](#limitations) für den Microsoft SQL-Server und Azure SQL Connectors.

## <a name="before-you-get-started"></a>Bevor Sie beginnen

### <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a>Installieren Sie den Graph Connector-Agent (nur für lokale Microsoft SQL Server Connector erforderlich)

Um auf Ihre lokalen Drittanbieterdaten zugreifen zu können, müssen Sie den Graph Connector-Agent installieren und konfigurieren. Weitere Informationen finden Sie unter [Installieren des Graph Connector-Agents.](graph-connector-agent.md)

>[!NOTE]
>Wenn Sie beim Konfigurieren des Microsoft SQL Server Graph Connectors Windows Authentifizierung verwenden, muss der Benutzer, mit dem Sie sich anmelden möchten, über interaktive Anmelderechte für den Computer verfügen, auf dem Graph Connector-Agent installiert ist. Informationen zur Überprüfung der Anmelderechte finden Sie in der Dokumentation zur Verwaltung von [Anmelderichtlinien.](/windows/security/threat-protection/security-policy-settings/allow-log-on-locally#policy-management)

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph Connectors in der Microsoft 365 Admin Center

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

### <a name="register-an-app-for-azure-sql-connector-only"></a>Registrieren einer App (nur für Azure SQL Connector)

Für Azure SQL Connector müssen Sie eine App in Azure Active Directory registrieren, damit Microsoft Search App auf Daten für die Indizierung zugreifen kann. Weitere Informationen zum Registrieren einer App finden Sie in der Microsoft Graph Dokumentation zum [Registrieren einer App.](/graph/auth-register-app-v2)

Nachdem Sie die App-Registrierung abgeschlossen und den App-Namen, die Anwendungs-ID (Client-ID) und die Mandanten-ID notieren, müssen Sie [einen neuen geheimen Clientschlüssel generieren.](/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret) Der geheime Clientschlüssel wird nur einmal angezeigt. Beachten Sie, & den geheimen Clientschlüssel sicher speichern. Verwenden Sie die Client-ID und den geheimen Clientschlüssel, während Sie eine neue Verbindung in Microsoft Search konfigurieren.

Zum Hinzufügen der registrierten App zu Ihrem Azure SQL-Datenbank müssen Sie Folgendes ausführen:

- Melden Sie sich bei Ihrer Azure SQL DB an.
- Öffnen eines neuen Abfragefensters
- Erstellen Sie einen neuen Benutzer, indem Sie den Befehl "CREATE USER [app name] FROM EXTERNAL PROVIDER" ausführen.
- Fügen Sie der Rolle einen Benutzer hinzu, indem Sie den Befehl 'exec sp_addrolemember 'db_datareader', [App-Name]' oder 'ALTER ROLE db_datareader ADD MEMBER [App-Name]' ausführen.

>[!NOTE]
>Informationen zum Widerrufen des Zugriffs auf alle in Azure Active Directory registrierten Apps finden Sie in der Azure-Dokumentation zum [Entfernen einer registrierten App.](/azure/active-directory/develop/quickstart-remove-app)

### <a name="connection-settings"></a>Verbindungseinstellungen

Um den Microsoft SQL Server Connector mit einer Datenquelle zu verbinden, müssen Sie den Datenbankserver konfigurieren, den Sie durchforsten möchten, und den lokalen Agent. Anschließend können Sie mit der erforderlichen Authentifizierungsmethode eine Verbindung mit der Datenbank herstellen.

> [!NOTE]
> - Ihre Datenbank muss SQL Server Version 2008 oder höher ausgeführt werden, damit der Microsoft SQL Server Connector eine Verbindung herstellen kann.
> - Der Azure SQL Graph-Connector ermöglicht nur die Aufnahme von einer Azure SQL Instanz im selben [Mandanten](/azure/active-directory/develop/quickstart-create-new-tenant) wie Microsoft 365. Der mandantenübergreifende Datenfluss wird nicht unterstützt.

Für den Azure SQL-Connector müssen Sie nur den Servernamen oder die IP-Adresse angeben, mit der Bzw. der Sie eine Verbindung herstellen möchten. Azure SQL Connector unterstützt nur Azure Active Directory Open ID Connect (OIDC)-Authentifizierung, um eine Verbindung mit der Datenbank herzustellen.

Für zusätzliche Sicherheit können Sie IP-Firewallregeln für Ihre Azure-SQL Server oder -Datenbank konfigurieren. Weitere Informationen zum Einrichten von IP-Firewallregeln finden Sie in der Dokumentation zu [IP-Firewallregeln.](/azure/azure-sql/database/firewall-configure) Fügen Sie die folgenden Client-IP-Bereiche in den Firewalleinstellungen hinzu.

| Region | IP-Bereich |
| ------------ | ------------ |
| NAM | 52.250.92.252/30, 52.224.250.216/30 |
| EUR | 20.54.41.208/30, 51.105.159.88/30 |
| APC | 52.139.188.212/30, 20.43.146.44/30 |

Zum Durchsuchen der Datenbankinhalte müssen Sie beim Konfigurieren des Connectors SQL Abfragen angeben. Diese SQL Abfragen müssen alle Datenbankspalten benennen, die Indiziert werden sollen (d. h. Quelleigenschaften), einschließlich aller SQL Verknüpfungen, die ausgeführt werden müssen, um alle Spalten abzurufen. Um den Zugriff auf Suchergebnisse einzuschränken, müssen Sie zugriffssteuerungslisten (Access Control Lists, ACLs) innerhalb SQL Abfragen angeben, wenn Sie den Connector konfigurieren.

## <a name="step-3a-full-crawl-required"></a>Schritt 3a: Vollständige Durchforstung (erforderlich)

In diesem Schritt konfigurieren Sie die SQL Abfrage, die eine vollständige Durchforstung der Datenbank ausführt. Die vollständige Durchforstung wählt alle Spalten oder Eigenschaften aus, in denen Sie die Optionen **Abfrage,** **Suche** oder **Abrufen** auswählen möchten. Sie können auch ACL-Spalten angeben, um den Zugriff auf Suchergebnisse auf bestimmte Benutzer oder Gruppen einzuschränken.

> [!Tip]
> Um alle benötigten Spalten abzurufen, können Sie mehrere Tabellen verknüpfen.

![Skript, in dem orderTable und AclTable mit Beispieleigenschaften angezeigt werden.](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Auswählen von Datenspalten (erforderlich) und ACL-Spalten (optional)

Das Beispiel zeigt eine Auswahl von fünf Datenspalten, die die Daten für die Suche enthalten: OrderId, OrderTitle, OrderDesc, CreatedDateTime und IsDeleted. Um Ansichtsberechtigungen für jede Datenzeile festzulegen, können Sie optional diese ACL-Spalten auswählen: AllowedUsers, AllowedGroups, DeniedUsers und DeniedGroups. All these data columns also have the options to **Query**, **Search**, or **Retrieve**.

Wählen Sie Datenspalten aus, wie in dieser Beispielabfrage gezeigt: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Beachten Sie, dass die SQL Connectors keine Spaltennamen mit nicht alphanumerischen Zeichen in der SELECT-Klausel zulassen. Entfernen Sie alle nicht alphanumerischen Zeichen aus Spaltennamen mithilfe eines Alias. Beispiel : SELECT *column_name* AS *columnName*

Um den Zugriff auf die Suchergebnisse zu verwalten, können Sie eine oder mehrere ACL-Spalten in der Abfrage angeben. Mit dem SQL Connector können Sie den Zugriff pro Datensatzebene steuern. Sie können die gleiche Zugriffssteuerung für alle Datensätze in einer Tabelle verwenden. Wenn die ACL-Informationen in einer separaten Tabelle gespeichert sind, müssen Sie möglicherweise eine Verknüpfung mit diesen Tabellen in Ihrer Abfrage durchführen.

Die Verwendung der einzelnen ACL-Spalten in der obigen Abfrage wird unten beschrieben. In der folgenden Liste werden die vier **Zugriffssteuerungsmechanismen** erläutert.

- **AllowedUsers:** Diese Spalte gibt die Liste der Benutzer-IDs an, die auf die Suchergebnisse zugreifen können. Im folgenden Beispiel würde die Liste der Benutzer: john@contoso.com, keith@contoso.com und lisa@contoso.com nur Zugriff auf einen Datensatz mit OrderId = 12 haben.
- **AllowedGroups:** Diese Spalte gibt die Gruppe von Benutzern an, die auf die Suchergebnisse zugreifen können. Im folgenden Beispiel hätten Gruppen-sales-team@contoso.com nur Zugriff auf den Datensatz mit OrderId = 12.
- **DeniedUsers**: Diese Spalte gibt die Liste der Benutzer an, die **keinen** Zugriff auf die Suchergebnisse haben. Im folgenden Beispiel haben Benutzer john@contoso.com und keith@contoso.com keinen Zugriff auf datensätze mit OrderId = 13, während alle anderen Benutzer Zugriff auf diesen Datensatz haben.
- **DeniedGroups:** Diese Spalte gibt die Gruppe von Benutzern an, die **keinen** Zugriff auf die Suchergebnisse haben. Im folgenden Beispiel haben Gruppen engg-team@contoso.com und pm-team@contoso.com keinen Zugriff auf datensätze mit OrderId = 15, während alle anderen Zugriff auf diesen Datensatz haben.  

![Beispieldaten, die OrderTable und AclTable mit Beispieleigenschaften anzeigen.](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Unterstützte Datentypen

In der folgenden Tabelle sind die SQL Datentypen zusammengefasst, die in den MS-SQL- und Azure SQL-Connectors unterstützt werden. In der Tabelle wird auch der Indizierungsdatentyp für den unterstützten SQL Datentyp zusammengefasst. Weitere Informationen zu von Microsoft Graph Connectors unterstützten Datentypen für die Indizierung finden Sie in der Dokumentation zu [Eigenschaftsressourcentypen.](/graph/api/resources/property?preserve-view=true&view=graph-rest-beta#properties)

| Kategorie | Quelldatentyp | Datentyp der Indizierung |
| ------------ | ------------ | ------------ |
| Datum und Uhrzeit | date <br> Datum/Uhrzeit <br> datetime2 <br> Smalldatetime | Datum/Uhrzeit |
| Exakt numerisch | Bigint <br> int <br> Smallint <br> Tinyint | int64 |
| Exakt numerisch | Bit | boolean |
| Ungefährer numerischer Wert | Gleitkommazahl <br> Real | double |
| Zeichenfolge | Char <br> Varchar <br> text | string |
| Unicode-Zeichenzeichenfolgen | Nchar <br> Nvarchar <br> Ntext | string |
| Andere Datentypen | Uniqueidentifier | string |

Für alle anderen Datentypen, die derzeit nicht direkt unterstützt werden, muss die Spalte explizit in einen unterstützten Datentyp umgewandelt werden.

### <a name="watermark-required"></a>Wasserzeichen (erforderlich)

Um eine Überladung der Datenbank zu verhindern, stapelt der Konnektor Vollständige Durchforstungsabfragen mit einer Vollständigdurchforstungs-Wasserzeichenspalte und setzt sie fort. Mithilfe des Werts der Wasserzeichenspalte wird jeder nachfolgende Batch abgerufen und die Abfrage vom letzten Prüfpunkt fortgesetzt. Im Wesentlichen steuert dieser Mechanismus die Datenaktualisierung für vollständige Durchforstungen.

Erstellen Sie Abfrageausschnitte für Wasserzeichen, wie in diesen Beispielen gezeigt:

- `WHERE (CreatedDateTime > @watermark)`. Geben Sie den Namen der Wasserzeichenspalte mit dem reservierten Schlüsselwort `@watermark` an. Wenn die Sortierreihenfolge der Wasserzeichenspalte aufsteigend ist, verwenden Sie `>` ; andernfalls verwenden Sie `<` .
- `ORDER BY CreatedDateTime ASC`. Sortieren Sie die Wasserzeichenspalte in aufsteigender oder absteigender Reihenfolge.

In der in der folgenden Abbildung gezeigten Konfiguration `CreatedDateTime` befindet sich die ausgewählte Wasserzeichenspalte. Um den ersten Zeilenbatch abzurufen, geben Sie den Datentyp der Wasserzeichenspalte an. In diesem Fall lautet der Datentyp `DateTime` .

![Konfiguration der Wasserzeichenspalte.](media/MSSQL-watermark.png)

Die erste Abfrage ruft die erste **N-Anzahl** von Zeilen mithilfe der folgenden Methode ab: "CreatedDateTime > 1. Januar 1753 00:00:00" (Min. Wert des DateTime-Datentyps). Nachdem der erste Batch abgerufen wurde, wird der höchste im Batch zurückgegebene Wert `CreatedDateTime` als Prüfpunkt gespeichert, wenn die Zeilen in aufsteigender Reihenfolge sortiert sind. Ein Beispiel ist der 1. März 2019 03:00:00. Anschließend wird der nächste Batch von **N-Zeilen** mithilfe von "CreatedDateTime > 1. März 2019 03:00:00" in der Abfrage abgerufen.

### <a name="skipping-soft-deleted-rows-optional"></a>Überspringen vorläufig gelöschter Zeilen (optional)

Um zeilenweise gelöschte Zeilen in Ihrer Datenbank von der Indizierung auszuschließen, geben Sie den Namen und den Wert für das vorläufige Löschen der Spalte an, der angibt, dass die Zeile gelöscht wird.

![Einstellungen für vorläufiges Löschen: "Spalte vorläufig löschen" und "Wert der Spalte für vorläufiges Löschen, die eine gelöschte Zeile angibt".](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Vollständige Durchforstung: Verwalten von Suchberechtigungen

Wählen Sie **"Berechtigungen verwalten"** aus, um die verschiedenen Zugriffssteuerungsspalten (Access Control, ACL) auszuwählen, die den Zugriffsteuerungsmechanismus angeben. Wählen Sie den Spaltennamen aus, den Sie in der vollständigen Durchforstung SQL Abfrage angegeben haben.

Es wird erwartet, dass jede der ACL-Spalten eine mehrwertige Spalte ist. Diese mehreren ID-Werte können durch Trennzeichen wie Semikolon (;), Komma (,) usw. getrennt werden. Sie müssen dieses Trennzeichen im **Werttrennzeichenfeld** angeben.

Die folgenden ID-Typen werden für die Verwendung als ACLs unterstützt:

- **Benutzerprinzipalname (USER Principal Name, UPN):** Ein Benutzerprinzipalname (User Principal Name, UPN) ist der Name eines Systembenutzers im E-Mail-Adressformat. Ein UPN (z. B. john.doe@domain.com) besteht aus dem Benutzernamen (Anmeldename), dem Trennzeichen (dem @-Symbol) und dem Domänennamen (UPN-Suffix).
- **Azure Active Directory (AAD)-ID:** In Azure AD verfügt jeder Benutzer oder jede Gruppe über eine Objekt-ID, die etwa wie "e0d3ad3d-0000-1111-2222-3c5f5c52ab9b" aussieht.
- **Active Directory (AD)-Sicherheits-ID:** Bei einem lokalen AD-Setup verfügen alle Benutzer und Gruppen über einen unveränderlichen, eindeutigen Sicherheitsbezeichner, der etwa wie "S-1-5-21-3878594291-211595936-132693609-65242" aussieht.

![Suchberechtigungseinstellungen zum Konfigurieren von Zugriffssteuerungslisten.](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Schritt 3b: Inkrementelle Durchforstung (optional)

Stellen Sie in diesem optionalen Schritt eine SQL Abfrage bereit, um eine inkrementelle Durchforstung der Datenbank auszuführen. Bei dieser Abfrage ermittelt der SQL Connector alle Änderungen an den Daten seit der letzten inkrementellen Durchforstung. Wählen Sie wie bei der vollständigen Durchforstung alle Spalten aus, in denen Sie die Optionen **Abfrage,** **Suche** oder **Abrufen** auswählen möchten. Geben Sie den gleichen Satz von ACL-Spalten an, den Sie in der vollständigen Durchforstungsabfrage angegeben haben.

Die Komponenten in der folgenden Abbildung ähneln den vollständigen Durchforstungskomponenten mit einer Ausnahme. In diesem Fall ist "ModifiedDateTime" die ausgewählte Wasserzeichenspalte. Überprüfen Sie die [vollständigen Durchforstungsschritte,](#step-3a-full-crawl-required) um zu erfahren, wie Sie die inkrementelle Durchforstungsabfrage schreiben und das folgende Bild als Beispiel anzeigen.

![Inkrementelles Durchforstungsskript mit ordertable-, AclTable- und Beispieleigenschaften, die verwendet werden können.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Schritt 4: Zuweisen von Eigenschaftenbeschriftungen

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-5-manage-schema"></a>Schritt 5: Verwalten des Schemas

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-6-manage-search-permissions"></a>Schritt 6: Verwalten von Suchberechtigungen

Sie können die [im vollständigen Durchforstungsbildschirm angegebenen ACLs](#full-crawl-manage-search-permissions) verwenden oder sie überschreiben, um Ihre Inhalte für alle sichtbar zu machen.

## <a name="step-7-choose-refresh-settings"></a>Schritt 7: Auswählen von Aktualisierungseinstellungen

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).-->

## <a name="troubleshooting"></a>Problembehandlung

Es folgt ein häufiger Fehler beim Konfigurieren des Connectors und sein möglicher Grund.

| Konfigurationsschritt | Fehlermeldung | Mögliche Gründe |
| ------------ | ------------ | ------------ |
| Vollständige Durchforstung | `Error from database server: A transport level error has occurred when receiving results from the server.` | Dieser Fehler tritt aufgrund von Netzwerkproblemen auf. Es wird empfohlen, Netzwerkprotokolle mithilfe des [Microsoft-Netzwerkmonitors](https://www.microsoft.com/download/details.aspx?id=4865) zu überprüfen und sich an den Microsoft-Kundensupport zu wenden. |
| Vollständige Durchforstung | `Column column_name returned from full crawl SQL query contains non-alphanumeric character` | Nicht alphanumerische Zeichen (wie Unterstriche) sind in Spaltennamen in DER SELECT-Klausel nicht zulässig. Verwenden Sie Aliase, um Spalten umzubenennen und nicht alphanumerische Zeichen zu entfernen (Beispiel: SELECT column_name AS columnName). |

## <a name="limitations"></a>Einschränkungen

Für die SQL Connectors gelten die folgenden Einschränkungen in der Vorschauversion:

- Microsoft SQL Server Connector: Die lokale Datenbank muss SQL Server Version 2008 oder höher ausgeführt werden.
- Das Microsoft 365-Abonnement und das Azure-Abonnement (Hosten der Azure SQL-Datenbank) müssen sich innerhalb desselben Azure Active Directory befinden.
- ACLs werden nur mithilfe eines Benutzerprinzipalnamens (User Principal Name, UPN), Azure Active Directory (Azure AD) oder Active Directory Security unterstützt.
- Das Indizieren von umfangreichen Inhalten in Datenbankspalten wird nicht unterstützt. Beispiele für solche Inhalte sind HTML, JSON, XML, Blobs und Dokumentparsings, die als Links in den Datenbankspalten vorhanden sind.
