---
title: ServiceNow Graph Connector für Microsoft Search
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des ServiceNow Graph-Connectors für Microsoft Search
ms.openlocfilehash: fccae6c2a007470eb9ef56130cb952158c01610c
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701912"
---
<!---Previous ms.author: kam1 --->


# <a name="servicenow-graph-connector"></a>ServiceNow Graph Connector

Mit dem Microsoft Graph Connector für ServiceNow kann Ihre Organisation Knowledge Base-Artikel indizieren, die für alle Benutzer sichtbar oder mit Benutzerkriterienberechtigungen innerhalb Ihrer Organisation eingeschränkt sind. Nachdem Sie den Connector konfiguriert und Inhalte von ServiceNow indiziert haben, können Endbenutzer von einem beliebigen Microsoft Search Client nach diesen Artikeln suchen.  

Sie können auch [das folgende Video](https://www.youtube.com/watch?v=TVSkJpk1RiE) lesen, um mehr über Graph Connector-Funktion zum Verwalten von Suchberechtigungen zu erfahren.

[![Verwalten von Suchberechtigungen in Microsoft Graph Connector für ServiceNow.](https://img.youtube.com/vi/TVSkJpk1RiE/hqdefault.jpg)](https://www.youtube.com/watch?v=TVSkJpk1RiE)

Dieser Artikel richtet sich an Microsoft 365 Administratoren oder alle Personen, die einen ServiceNow Graph Connector konfigurieren, ausführen und überwachen. Er ergänzt die allgemeinen Anweisungen im Artikel ["Einrichten Ihres Graph Connectors".](configure-connector.md) Wenn sie dies noch nicht getan haben, lesen Sie den gesamten Artikel zum Einrichten ihres Graph Connectors, um den allgemeinen Einrichtungsprozess zu verstehen.

Jeder Schritt im Setupprozess wird unten zusammen mit einem Hinweis aufgeführt, der angibt, dass Sie die allgemeinen Setupanweisungen oder andere Anweisungen befolgen sollten, die nur für ServiceNow Graph Connector gelten, einschließlich Informationen zur [Problembehandlung](#troubleshooting) und [Einschränkungen.](#limitations)  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Fügen Sie einen Graph Connector im Microsoft 365 Admin Center hinzu.
Befolgen Sie die allgemeinen Setupanweisungen.

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen Sie die Verbindung.
Befolgen Sie die allgemeinen Setupanweisungen.


## <a name="step-3-connection-settings"></a>Schritt 3: Verbindungs-Einstellungen
Um eine Verbindung mit Ihren ServiceNow-Daten herzustellen, benötigen Sie die **ServiceNow-Instanz-URL** Ihrer Organisation. Die ServiceNow-Instanz-URL Ihrer Organisation sieht in der Regel wie **https:// &lt; Ihrer Organisation-Domäne>.service-now.com** aus. 

Zusammen mit dieser URL benötigen Sie ein **Dienstkonto** zum Einrichten der Verbindung mit ServiceNow sowie zum Zulassen, dass Microsoft Search die Wissensartikel regelmäßig basierend auf dem Aktualisierungszeitplan aktualisieren können. Das Dienstkonto benötigt Lesezugriff auf die folgenden **ServiceNow-Tabelleneinträge,** um verschiedene Entitäten erfolgreich durchforsten zu können.

**Feature** | **Erforderliche Tabellen für den Lesezugriff** | **Beschreibung**
--- | --- | ---
Index knowledge articles available to <em>Everyone</em> | kb_knowledge | Informationen zum Durchforsten von Wissensartikeln
Index- und Supportberechtigungen für Benutzerkriterien | kb_uc_can_read_mtom | Wer diese Knowledge Base lesen können
| | kb_uc_can_contribute_mtom | Wer können zu dieser Wissensbasis beitragen
| | kb_uc_cannot_read_mtom | Wer diese Knowledge Base nicht lesen können
| | kb_uc_cannot_contribute_mtom | Wer können nicht zu dieser Wissensbasis beitragen
| | sys_user | Benutzertabelle lesen
| | sys_user_has_role | Lesen von Rolleninformationen von Benutzern
| | sys_user_grmember | Lesen der Gruppenmitgliedschaft von Benutzern
| | user_criteria | Benutzerkriterienberechtigungen lesen
| | kb_knowledge_base | Lesen von Knowledge Base-Informationen

Sie können eine Rolle für das Dienstkonto **erstellen und zuweisen,** das Sie zum Herstellen einer Verbindung mit Microsoft Search verwenden. [Erfahren Sie, wie Sie eine Rolle für ServiceNow-Konten zuweisen.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html) Lesezugriff auf die Tabellen kann der erstellten Rolle zugewiesen werden. Informationen zum Festlegen des Lesezugriffs auf Tabellendatensätze finden Sie unter [Schützen von Tabellendatensätzen.](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls) 


>[!NOTE]
> ServiceNow Graph Connector kann Wissensartikel und Benutzerkriterienberechtigungen ohne erweiterte Skripts indizen. Wenn ein Benutzerkriterium ein erweitertes Skript enthält, werden alle zugehörigen Wissensartikel in suchergebnissen ausgeblendet.

Wählen Sie **eine von drei** unterstützten Methoden aus, um Inhalte von ServiceNow zu authentifizieren und zu synchronisieren: 
 
- Standardauthentifizierung 
- ServiceNow OAuth (empfohlen)
- Azure AD OpenID Verbinden

## <a name="step-31-basic-authentication"></a>Schritt 3.1: Standardauthentifizierung

Geben Sie den Benutzernamen und das Kennwort des ServiceNow-Kontos mit **der Wissensrolle** ein, um sich bei Ihrer Instanz zu authentifizieren.

## <a name="step-32-servicenow-oauth"></a>Schritt 3.2: ServiceNow OAuth

Um ServiceNow OAuth für die Authentifizierung zu verwenden, muss ein ServiceNow-Administrator einen Endpunkt in Ihrer ServiceNow-Instanz bereitstellen, damit die Microsoft Search App darauf zugreifen kann. Weitere Informationen finden Sie unter ["Erstellen eines Endpunkts für Clients für den Zugriff auf die Instanz"](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in der ServiceNow-Dokumentation.

Die folgende Tabelle enthält Anleitungen zum Ausfüllen des Formulars für die Endpunkterstellung:

Feld | Beschreibung | Empfohlener Wert 
--- | --- | ---
Name | Eindeutiger Wert, der die Anwendung identifiziert, für die Sie OAuth-Zugriff benötigen. | Microsoft Search
Client-ID | Eine schreibgeschützte, automatisch generierte eindeutige ID für die Anwendung. Die Instanz verwendet die Client-ID, wenn sie ein Zugriffstoken anfordert. | NA
Geheimer Clientschlüssel | Mit dieser freigegebenen geheimen Zeichenfolge autorisieren die ServiceNow-Instanz und Microsoft Search die Kommunikation miteinander. | Befolgen Sie bewährte Methoden für die Sicherheit, indem Sie den geheimen Schlüssel als Kennwort behandeln.
Umleitungs-URL | Eine erforderliche Rückruf-URL, an die der Autorisierungsserver umleitet. | https://gcs.office.com/v1.0/admin/oauth/callback
Logo-URL | Eine URL, die das Bild für das Anwendungslogo enthält. | NA
Aktiv | Aktivieren Sie das Kontrollkästchen, um die Anwendungsregistrierung zu aktivieren. | Auf "Aktiv" festgelegt
Aktualisierung der Tokenlebensdauer | Die Anzahl der Sekunden, für die ein Aktualisierungstoken gültig ist. Standardmäßig laufen Aktualisierungstoken in 100 Tagen ab (8.640.000 Sekunden). | 31.536.000 (1 Jahr)
Lebensdauer des Zugriffstokens | Die Anzahl der Sekunden, für die ein Zugriffstoken gültig ist. | 43.200 (12 Stunden)

Geben Sie die Client-ID und den geheimen Clientschlüssel ein, um eine Verbindung mit Ihrer Instanz herzustellen. Verwenden Sie nach der Verbindung die Anmeldeinformationen eines ServiceNow-Kontos, um die Berechtigung zum Durchforsten zu authentifizieren. Das Konto sollte mindestens über **eine Wissensrolle** verfügen. Lesen Sie die Tabelle am Anfang von [Schritt 3: Verbindungseinstellungen,](#step-3-connection-settings) um Lesezugriff auf weitere ServiceNow-Tabelleneinträge und Berechtigungen für Indexbenutzerkriterien bereitzustellen.

## <a name="step-33-azure-ad-openid-connect"></a>Schritt 3.3: Azure AD OpenID Verbinden

Führen Sie die folgenden Schritte aus, um Azure AD OpenID Verbinden für die Authentifizierung zu verwenden.

### <a name="step-331-register-a-new-application-in-azure-active-directory"></a>Schritt 3.3.1: Registrieren einer neuen Anwendung in Azure Active Directory

Informationen zum Registrieren einer neuen Anwendung in Azure Active Directory finden Sie unter [Registrieren einer Anwendung.](/azure/active-directory/develop/quickstart-register-app#register-an-application) Wählen Sie ein Organisationsverzeichnis mit einem einzelnen Mandanten aus. Umleitungs-URI ist nicht erforderlich. Notieren Sie sich nach der Registrierung die Anwendungs-ID (Client-)ID und die Verzeichnis-ID (Mandanten-ID).

### <a name="step-332-create-a-client-secret"></a>Schritt 3.3.2: Erstellen eines geheimen Clientschlüssels

Informationen zum Erstellen eines geheimen Clientschlüssels finden Sie unter [Erstellen eines geheimen Clientschlüssels.](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) Notieren Sie sich den geheimen Clientschlüssel.

### <a name="step-333-retrieve-service-principal-object-identifier"></a>Schritt 3.3.3: Abrufen des Dienstprinzipalobjektbezeichners

Führen Sie die Schritte zum Abrufen des Dienstprinzipalobjektbezeichners aus.

1. Führen Sie PowerShell aus.

2. Installieren Sie Azure PowerShell mit dem folgenden Befehl.

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Verbinden zu Azure.

   ```powershell
   Connect-AzAccount
   ```

4. Dient zum Abrufen des Dienstprinzipalobjektbezeichners.

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   Ersetzen Sie "Application-ID" durch die Anwendungs-ID (Client)-ID (ohne Anführungszeichen) der Anwendung, die Sie in Schritt 3.a registriert haben. Beachten Sie den Wert des ID-Objekts aus der PowerShell-Ausgabe. Dies ist die Dienstprinzipal-ID.

Jetzt verfügen Sie über alle erforderlichen Informationen aus dem Azure-Portal. Eine kurze Zusammenfassung der Informationen finden Sie in der folgenden Tabelle.

Eigenschaft | Beschreibung 
--- | ---
Verzeichnis-ID (Mandanten-ID) | Eindeutige ID des Azure Active Directory Mandanten aus Schritt 3.a.
Anwendungs-ID (Client-ID) | Eindeutige ID der in Schritt 3.a registrierten Anwendung.
Client Secret | Der geheime Schlüssel der Anwendung (aus Schritt 3.b). Behandeln Sie es wie ein Kennwort.
Dienstprinzipal-ID | Eine Identität für die Anwendung, die als Dienst ausgeführt wird. (aus Schritt 3.c)

### <a name="step-334-register-servicenow-application"></a>Schritt 3.3.4: Registrieren der ServiceNow-Anwendung

Die ServiceNow-Instanz benötigt die folgende Konfiguration:

1. Registrieren Sie eine neue OAuth OIDC-Entität. Weitere Informationen finden Sie unter [Erstellen eines OAuth OIDC-Anbieters.](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)

2. Die folgende Tabelle enthält Anleitungen zum Ausfüllen des OIDC-Anbieterregistrierungsformulars.

   Feld | Beschreibung | Empfohlener Wert
   --- | --- | ---
   Name | Ein eindeutiger Name, der die OAuth OIDC-Entität identifiziert. | Azure AD
   Client-ID | Die Client-ID der Anwendung, die auf dem OAuth OIDC-Server eines Drittanbieters registriert ist. Die Instanz verwendet die Client-ID beim Anfordern eines Zugriffstokens. | Anwendungs-ID (Client) aus Schritt 3.a
   Client Secret | Der geheime Clientschlüssel der Anwendung, die auf dem OAuth OIDC-Server eines Drittanbieters registriert ist. | Geheimer Clientschlüssel aus Schritt 3.b

   Alle anderen Werte können standard sein.

3. Im OIDC-Anbieterregistrierungsformular müssen Sie eine neue OIDC-Anbieterkonfiguration hinzufügen. Wählen Sie das Suchsymbol für das *OAuth OIDC-Anbieterkonfigurationsfeld* aus, um die Datensätze der OIDC-Konfigurationen zu öffnen. Wählen Sie "Neu" aus.

4. Die folgende Tabelle enthält Anleitungen zum Ausfüllen des OIDC-Anbieterkonfigurationsformulars.

   Feld | Empfohlener Wert
   --- | ---
   OIDC-Anbieter |  Azure AD
   OIDC-Metadaten-URL | Die URL muss das Format https \: ://login.microsoftonline.com/<tenandId">/.well-known/openid-configuration aufweisen. <br/>Ersetzen Sie "tenantID" durch die Verzeichnis-ID (Mandanten-ID) aus Schritt 3.a.
   Lebensdauer des OIDC-Konfigurationscaches |  120
   Anwendung | Global
   Benutzeranspruch | Sub
   Benutzerfeld | Benutzer-ID
   Aktivieren der JTI-Anspruchsüberprüfung | Deaktiviert

5. Wählen Sie "Absenden und Aktualisieren des OAuth OIDC-Entitätsformulars" aus.

### <a name="step-335-create-a-servicenow-account"></a>Schritt 3.3.5: Erstellen eines ServiceNow-Kontos

Lesen Sie die Anweisungen, um ein ServiceNow-Konto zu erstellen und [einen Benutzer in ServiceNow zu erstellen.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)

Die folgende Tabelle enthält Anleitungen zum Ausfüllen der Registrierung des ServiceNow-Benutzerkontos.

Feld | Empfohlener Wert
--- | ---
Benutzer-ID | Dienstprinzipal-ID aus Schritt 3.c
Nur Webdienstzugriff | Checked

Alle anderen Werte können auf den Standardwert festgelegt werden.

### <a name="step-336-enable-knowledge-role-for-the-servicenow-account"></a>Schritt 3.3.6: Aktivieren der Wissensrolle für das ServiceNow-Konto

Greifen Sie auf das ServiceNow-Konto zu, das Sie mit der ServiceNow-Prinzipal-ID als Benutzer-ID erstellt haben, und weisen Sie die Wissensrolle zu. Anweisungen zum Zuweisen einer Rolle zu einem ServiceNow-Konto finden Sie hier. [Weisen Sie einem Benutzer eine Rolle zu.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html) Lesen Sie die Tabelle am Anfang von [Schritt 3: Verbindungseinstellungen,](#step-3-connection-settings) um Lesezugriff auf weitere ServiceNow-Tabelleneinträge und Berechtigungen für Indexbenutzerkriterien bereitzustellen.

Verwenden Sie die Anwendungs-ID als Client-ID (aus Schritt 3.a) und den geheimen Clientschlüssel (aus Schritt 3.b) im Admin Center-Konfigurations-Assistenten, um sich mithilfe von Azure AD OpenID Verbinden bei Ihrer ServiceNow-Instanz zu authentifizieren.

## <a name="step-4-select-properties-and-filter-data"></a>Schritt 4: Auswählen von Eigenschaften und Filtern von Daten

In diesem Schritt können Sie der ServiceNow-Datenquelle verfügbare Eigenschaften hinzufügen oder daraus entfernen. Microsoft 365 hat bereits einige Eigenschaften standardmäßig ausgewählt.

Mit einer ServiceNow-Abfragezeichenfolge können Sie Bedingungen für die Synchronisierung von Artikeln angeben. Es ist wie eine **Where-Klausel** in einer **SQL Select-Anweisung.** Sie können z. B. festlegen, dass nur Artikel indiziert werden, die veröffentlicht und aktiv sind. Informationen zum Erstellen einer eigenen Abfragezeichenfolge finden Sie unter [Generieren einer codierten Abfragezeichenfolge mithilfe eines Filters.](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)

Verwenden Sie die Schaltfläche "Vorschauergebnisse", um die Beispielwerte der ausgewählten Eigenschaften und des Abfragefilters zu überprüfen.

## <a name="step-5-manage-search-permissions"></a>Schritt 5: Verwalten von Suchberechtigungen

Der ServiceNow-Connector unterstützt Suchberechtigungen, die **für alle** oder nur Personen mit Zugriff auf **diese Datenquelle** sichtbar sind. Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation bzw. für Benutzer sichtbar, die über die Berechtigung für Benutzerkriterien darauf zugreifen können. Wenn ein Wissensartikel nicht mit einem Benutzerkriterium aktiviert ist, wird er in den Suchergebnissen aller Benutzer in der Organisation angezeigt.

ServiceNow Graph Connector unterstützt standardmäßige Berechtigungen für Benutzerkriterien ohne erweiterte Skripts. Wenn der Connector auf ein Benutzerkriterium mit erweitertem Skript trifft, werden nicht alle Daten, die diese Benutzerkriterien verwenden, in den Suchergebnissen angezeigt.

Wenn Sie **nur Personen mit Zugriff auf diese Datenquelle** auswählen, müssen Sie weiter auswählen, ob Ihre ServiceNow-Instanz über Azure Active Directory (AAD) bereitgestellte Benutzer oder Nicht-AAD-Benutzer verfügt.

>[!NOTE]
>Wenn Sie AAD als Typ der Identitätsquelle auswählen, stellen Sie sicher, dass Sie userPrincipalName (UPN)-Quelleigenschaft E-Mail-Zieleigenschaft in ServiceNow zuweisen. Informationen zum Überprüfen oder Ändern Ihrer Zuordnungen finden Sie unter [Customizing user provisioning attribute-mappings for SaaS applications in Azure Active Directory](/azure/active-directory/app-provisioning/customize-application-attributes).

Wenn Sie "nicht-AAD" für den Identitätstyp gewählt haben, finden Sie anweisungen zum Zuordnen der Identitäten zu [Ihren Nicht-Azure AD-Identitäten.](map-non-aad.md) 


## <a name="step-6-assign-property-labels"></a>Schritt 6: Zuweisen von Eigenschaftenbeschriftungen

Befolgen Sie die allgemeinen Setupanweisungen.

## <a name="step-7-manage-schema"></a>Schritt 7: Verwalten des Schemas

Befolgen Sie die allgemeinen Setupanweisungen.

## <a name="step-8-choose-refresh-settings"></a>Schritt 8: Auswählen von Aktualisierungseinstellungen

Befolgen Sie die allgemeinen Setupanweisungen.

>[!NOTE]
>Für Identitäten wird nur die geplante vollständige Durchforstung angewendet.

## <a name="step-9-review-connection"></a>Schritt 9: Überprüfen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

ServiceNow Graph Connector hat die folgenden Einschränkungen in seiner neuesten Version:

Nach der Veröffentlichung der Verbindung müssen Sie die Suchergebnisseite anpassen. Informationen zum Anpassen von Suchergebnissen finden Sie unter [Anpassen der Suchergebnisseite.](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)

## <a name="limitations"></a>Einschränkungen
ServiceNow Graph Connector hat die folgenden Einschränkungen in seiner neuesten Version:
- Die Indizierung von Wissensartikeln, die für alle Personen in einer Organisation verfügbar sind, ist ein allgemein verfügbares Feature.
- *Nur Personen mit Zugriff auf dieses Datenquellenfeature* unter Schritt "Suchberechtigungen verwalten" befinden sich im kanal für die gezielte Freigabe und verarbeiten nur [Benutzerkriterienberechtigungen.](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) Andere Zugriffsberechtigungstypen werden in den Suchergebnissen nicht angewendet.
- Benutzerkriterien mit erweiterten Skripts werden in der aktuellen Version nicht unterstützt. Alle Wissensartikel mit einer solchen Zugriffseinschränkung werden indiziert, wobei jeder Zugriff verweigert wird, d. h. sie werden keinem Benutzer in den Suchergebnissen angezeigt, bis wir sie unterstützen.

## <a name="troubleshooting"></a>Problembehandlung
Nachdem Sie Ihre Verbindung veröffentlicht und die Ergebnisseite angepasst haben, können Sie den Status auf der Registerkarte **"Datenquellen"** im [Admin Center](https://admin.microsoft.com)überprüfen. Informationen zum Vornehmen von Aktualisierungen und Löschungen finden Sie unter [Verwalten des Connectors.](manage-connector.md)
Die Schritte zur Problembehandlung für häufig auftretende Probleme finden Sie weiter unten.
### <a name="1-unable-to-login-due-to-single-sign-on-enabled-servicenow-instance"></a>1. Anmeldung aufgrund einer einzelnen Sign-On aktivierten ServiceNow-Instanz nicht möglich

Wenn Ihre Organisation Single Sign-On (SSO) für ServiceNow aktiviert hat, haben Sie möglicherweise Probleme bei der Anmeldung mit dem Dienstkonto. Sie können benutzernamen- und kennwortbasierte <em> `login.do` </em> Anmeldungen aufrufen, indem Sie die Url der ServiceNow-Instanz hinzufügen. Beispiel. `https://<your-organization-domain>.service-now.com./login.do` 

### <a name="2-unauthorized-or-forbidden-response-to-api-request"></a>2. Nicht autorisierte oder unzulässige Antwort auf API-Anforderung

#### <a name="21-check-table-access-permissions"></a>2.1. Überprüfen von Tabellenzugriffsberechtigungen
Wenn im Verbindungsstatus eine unzulässige oder nicht autorisierte Antwort angezeigt wird, überprüfen Sie, ob das Dienstkonto Zugriff auf die in [Schritt 3: Verbindungseinstellungen](#step-3-connection-settings)erwähnten Tabellen benötigt. Überprüfen Sie, ob alle Spalten in den Tabellen Lesezugriff haben.

#### <a name="22-check-if-servicenow-instance-behind-firewall"></a>2.2. Überprüfen, ob die ServiceNow-Instanz hinter der Firewall liegt
Graph Der Connector kann Ihre ServiceNow-Instanz möglicherweise nicht erreichen, wenn er sich hinter einer Netzwerkfirewall befindet. Sie müssen den Zugriff auf Graph Connectordienst explizit zulassen. Sie finden den öffentlichen IP-Adressbereich Graph Connector-Diensts in der folgenden Tabelle. Fügen Sie sie basierend auf Ihrer Mandantenregion der Whitelist des ServiceNow-Instanznetzwerks hinzu.

**Umgebung** | **Region** | **Range**
--- | --- | ---
PROD | Nordamerika | 52.250.92.252/30, 52.224.250.216/30
PROD | Europa | 20.54.41.208/30, 51.105.159.88/30 
PROD | Asiatisch-pazifischer Raum | 52.139.188.212/30, 20.43.146.44/30 

#### <a name="23-access-permissions-not-working-as-expected"></a>2.3. Zugriffsberechtigungen funktionieren nicht wie erwartet
Wenn Sie Abweichungen bei den Zugriffsberechtigungen beobachten, die auf Suchergebnisse angewendet werden, überprüfen Sie das Zugriffsflussdiagramm auf Benutzerkriterien bei der [Verwaltung des Zugriffs auf Wissensdatenbanken und Artikel.](https://docs.servicenow.com/bundle/rome-servicenow-platform/page/product/knowledge-management/concept/user-access-knowledge.html)

Wenn Sie andere Probleme haben oder Feedback geben möchten, schreiben Sie uns [aka.ms/TalkToGraphConnectors](https://aka.ms/TalkToGraphConnectors)
