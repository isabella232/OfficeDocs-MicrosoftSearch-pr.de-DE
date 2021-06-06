---
title: ServiceNow Graph Connector für Microsoft Search
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
description: Einrichten des ServiceNow Graph Connectors für Microsoft Search
ms.openlocfilehash: 31b581af2c51a5c26b161e778b242e396afe91fd
ms.sourcegitcommit: 6cffa2d29448be9a22514e7b4c3009c522af0860
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52774080"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a>ServiceNow Graph Connector

Der ServiceNow Graph Connector ermöglicht Es Ihrer Organisation, wissensbasierte Artikel, die für Benutzer sichtbar sind, gemäß den Benutzerkriterienberechtigungen in Ihrer Organisation zu indizieren. Nachdem Sie den Connector konfiguriert und Inhalte von ServiceNow indiziert haben, können Benutzer von einem beliebigen Microsoft Search-Client nach den Artikeln suchen.

> [!NOTE]
> Lesen Sie den Artikel [**"Setup for your Graph connector",**](configure-connector.md) um die allgemeinen Anweisungen zum Einrichten Graph Connectors zu verstehen.

Dieser Artikel richtet sich an alle Personen, die einen ServiceNow Graph Connector konfigurieren, ausführen und überwachen. Es ergänzt den allgemeinen Setupprozess und zeigt Anweisungen, die nur für den ServiceNow Graph Connector gelten. Dieser Artikel enthält auch Informationen zur [Problembehandlung](#troubleshooting) und [zu Einschränkungen.](#limitations)

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph Connectors im Microsoft 365 Admin Center

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a>Schritt 3: Verbindungs-Einstellungen

Um eine Verbindung mit Ihren ServiceNow-Daten herzustellen, verwenden Sie die Url-Anmeldeinformationen ihrer Organisation für **die ServiceNow-Instanz** für dieses Konto, die Client-ID und den geheimen Clientschlüssel für die OAuth-Authentifizierung.  

Die **ServiceNow-Instanz-URL** Ihrer Organisation sieht in der Regel wie **https:// &lt; Ihre-Organisation-Domäne>.service-now.com** aus. Zusammen mit dieser URL benötigen Sie ein Konto zum Einrichten der Verbindung mit ServiceNow und zum Zulassen, dass Microsoft Search die Artikel von ServiceNow basierend auf dem Aktualisierungszeitplan aktualisieren kann. Das Konto sollte mindestens über <em>eine Wissensrolle</em> verfügen. [Erfahren Sie, wie Sie eine Rolle für ServiceNow-Konten zuweisen.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

>[!NOTE]
>Wenn Sie Benutzer- und Gruppenidentitäten durchforsten möchten, um Zugriffsberechtigungen von Wissensartikeln in Microsoft Search-Ergebnissen zu berücksichtigen, sollte das Konto Zugriff haben, um die folgenden Tabelleneinträge in ServiceNow zu lesen:
>* kb_uc_can_contribute_mtom
>* kb_uc_can_read_mtom
>* kb_uc_cannot_read_mtom
>* kb_uc_cannot_contribute_mtom
>* sys_user
>* sys_user_has_role
>* sys_user_grmember
>* user_criteria
>* kb_knowledge_base  
> Sie können eine Rolle für das Konto erstellen und zuweisen, das Sie zum Herstellen einer Verbindung mit Microsoft Search verwenden. Lesezugriff auf die Tabellen kann dieser Rolle zugewiesen werden. Informationen zum Festlegen des Lesezugriffs auf Tabellendatensätze finden Sie unter [Schützen von Tabellendatensätzen.](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)

Wählen Sie **eine von drei** unterstützten Methoden aus, um Inhalte von ServiceNow zu authentifizieren und zu synchronisieren:

1. Standardauthentifizierung
1. ServiceNow OAuth (empfohlen)
1. Azure AD OpenID Verbinden

### <a name="basic-authentication"></a>Standardauthentifizierung

Geben Sie den Benutzernamen und das Kennwort des ServiceNow-Kontos mit **der Wissensrolle** ein, um sich bei Ihrer Instanz zu authentifizieren.

### <a name="servicenow-oauth"></a>ServiceNow OAuth

Um ServiceNow OAuth für die Authentifizierung zu verwenden, stellen Sie einen Endpunkt in Ihrer ServiceNow-Instanz bereit. Die Microsoft Search-App verwendet sie, um auf die Instanz zuzugreifen. Weitere Informationen finden Sie unter ["Erstellen eines Endpunkts für Clients für den Zugriff auf die Instanz"](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in der ServiceNow-Dokumentation.

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

Geben Sie die Client-ID und den geheimen Clientschlüssel ein, um eine Verbindung mit Ihrer Instanz herzustellen. Verwenden Sie nach der Verbindung die Anmeldeinformationen eines ServiceNow-Kontos, um die Berechtigung zum Durchforsten zu authentifizieren. Das Konto sollte mindestens über **eine Wissensrolle** verfügen.

### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Verbinden

Führen Sie die folgenden Schritte aus, um Azure AD OpenID Verbinden für die Authentifizierung zu verwenden.

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a>Schritt 3.a: Registrieren einer neuen Anwendung in Azure Active Directory

Informationen zum Registrieren einer neuen Anwendung in Azure Active Directory finden Sie unter [Registrieren einer Anwendung.](/azure/active-directory/develop/quickstart-register-app#register-an-application) Wählen Sie ein Organisationsverzeichnis mit einem einzelnen Mandanten aus. Umleitungs-URI ist nicht erforderlich. Notieren Sie sich nach der Registrierung die Anwendungs-ID (Client-)ID und die Verzeichnis-ID (Mandanten-ID).

## <a name="step-3b-create-a-client-secret"></a>Schritt 3.b: Erstellen eines geheimen Clientschlüssels

Informationen zum Erstellen eines geheimen Clientschlüssels finden Sie unter [Erstellen eines geheimen Clientschlüssels.](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) Notieren Sie sich den geheimen Clientschlüssel.

## <a name="step-3c-retrieve-service-principal-object-identifier"></a>Schritt 3.c: Abrufen des Dienstprinzipalobjektbezeichners

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
Geheimer Clientschlüssel | Der geheime Schlüssel der Anwendung (aus Schritt 3.b). Behandeln Sie es wie ein Kennwort.
Dienstprinzipal-ID | Eine Identität für die Anwendung, die als Dienst ausgeführt wird. (aus Schritt 3.c)

## <a name="step-3d-register-servicenow-application"></a>Schritt 3.d: Registrieren der ServiceNow-Anwendung

Die ServiceNow-Instanz benötigt die folgende Konfiguration:

1. Registrieren Sie eine neue OAuth OIDC-Entität. Weitere Informationen finden Sie unter [Erstellen eines OAuth OIDC-Anbieters.](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)

2. Die folgende Tabelle enthält Anleitungen zum Ausfüllen des OIDC-Anbieterregistrierungsformulars.

   Feld | Beschreibung | Empfohlener Wert
   --- | --- | ---
   Name | Ein eindeutiger Name, der die OAuth OIDC-Entität identifiziert. | Azure AD
   Client-ID | Die Client-ID der Anwendung, die auf dem OAuth OIDC-Server eines Drittanbieters registriert ist. Die Instanz verwendet die Client-ID beim Anfordern eines Zugriffstokens. | Anwendungs-ID (Client) aus Schritt 3.a
   Geheimer Clientschlüssel | Der geheime Clientschlüssel der Anwendung, die auf dem OAuth OIDC-Server eines Drittanbieters registriert ist. | Geheimer Clientschlüssel aus Schritt 3.b

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

## <a name="step-3e-create-a-servicenow-account"></a>Schritt 3.e: Erstellen eines ServiceNow-Kontos

Lesen Sie die Anweisungen, um ein ServiceNow-Konto zu erstellen und [einen Benutzer in ServiceNow zu erstellen.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)

Die folgende Tabelle enthält Anleitungen zum Ausfüllen der Registrierung des ServiceNow-Benutzerkontos.

Feld | Empfohlener Wert
--- | ---
Benutzer-ID | Dienstprinzipal-ID aus Schritt 3.c
Nur Webdienstzugriff | Checked

Alle anderen Werte können auf den Standardwert festgelegt werden.

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a>Schritt 3.f: Aktivieren der Wissensrolle für das ServiceNow-Konto

Greifen Sie auf das ServiceNow-Konto zu, das Sie mit der ServiceNow-Prinzipal-ID als Benutzer-ID erstellt haben, und weisen Sie die Wissensrolle zu. Anweisungen zum Zuweisen einer Rolle zu einem ServiceNow-Konto finden Sie hier: [Zuweisen einer Rolle zu einem Benutzer.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

Verwenden Sie die Anwendungs-ID als Client-ID aus Schritt 3.a und den geheimen Clientschlüssel aus Schritt 3.b, um sich mithilfe von Azure AD OpenID Verbinden bei Ihrer ServiceNow-Instanz zu authentifizieren.

## <a name="step-4-select-properties-and-filter-data"></a>Schritt 4: Auswählen von Eigenschaften und Filtern von Daten

In diesem Schritt können Sie der ServiceNow-Datenquelle verfügbare Eigenschaften hinzufügen oder daraus entfernen. Microsoft 365 hat standardmäßig bereits einige Eigenschaften ausgewählt.

Mit einer ServiceNow-Abfragezeichenfolge können Sie Bedingungen für die Synchronisierung von Artikeln angeben. Es ist wie eine **Where-Klausel** in einer **SQL Select-Anweisung.** Sie können z. B. festlegen, dass nur Artikel indiziert werden, die veröffentlicht und aktiv sind. Informationen zum Erstellen einer eigenen Abfragezeichenfolge finden Sie unter [Generieren einer codierten Abfragezeichenfolge mithilfe eines Filters.](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)

Verwenden Sie die Schaltfläche "Vorschauergebnisse", um die Beispielwerte der ausgewählten Eigenschaften und des Abfragefilters zu überprüfen.

## <a name="step-5-manage-search-permissions"></a>Schritt 5: Verwalten von Suchberechtigungen

Der ServiceNow-Connector unterstützt Suchberechtigungen, die **für alle** oder nur Personen mit Zugriff auf **diese Datenquelle** sichtbar sind. Indizierte Daten werden in den Suchergebnissen angezeigt und sind für Benutzer in der Organisation sichtbar, die Zugriff darauf haben. ServiceNow Connector unterstützt standardmäßige Berechtigungen für Benutzerkriterien ohne erweiterte Skripts. Wenn der Connector ein Benutzerkriterium mit erweitertem Skript findet, werden nicht alle Daten, die diese Benutzerkriterien verwenden, in den Suchergebnissen angezeigt.

Wenn Sie **nur Personen mit Zugriff auf diese Datenquelle** auswählen, müssen Sie weiter auswählen, ob Ihre ServiceNow-Instanz über Azure Active Directory (AAD) bereitgestellte Benutzer oder Nicht-AAD-Benutzer verfügt.

>[!NOTE]
>Der ServiceNow-Connector befindet sich in der **Vorschau,** wenn Sie **nur Personen mit Zugriff auf diese Datenquelle** auswählen.

>[!NOTE]
>Wenn Sie AAD als Typ der Identitätsquelle auswählen, stellen Sie sicher, dass Sie die UPN-Quelleigenschaft E-Mail-Zieleigenschaft in ServiceNow zuweisen. Informationen zum Überprüfen oder Ändern Ihrer Zuordnungen finden Sie unter [Customizing user provisioning attribute-mappings for SaaS applications in Azure Active Directory](/azure/active-directory/app-provisioning/customize-application-attributes).

Wenn Sie sich entschieden haben, eine ACL aus Ihrer ServiceNow-Instanz zu erfassen, und "nicht-AAD" für den Identitätstyp ausgewählt haben, finden Sie anweisungen zum Zuordnen der Identitäten zu [Ihren Nicht-Azure AD-Identitäten.](map-non-aad.md)

### <a name="managing-search-permissions-in-microsoft-search"></a>Verwalten von Suchberechtigungen in Microsoft Search

Im folgenden Video sehen Sie, wie Sie den Servicenow-Connector verwenden, um Wissensartikel zu indizieren, Benutzerkriterienberechtigungen zu definieren und die Änderungen zwischen ServiceNow und Microsoft Search-Index nahtlos zu synchronisieren.

> [!VIDEO https://www.youtube-nocookie.com/embed/TVSkJpk1RiE]

## <a name="step-6-assign-property-labels"></a>Schritt 6: Zuweisen von Eigenschaftenbeschriftungen

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a>Schritt 7: Verwalten des Schemas

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a>Schritt 8: Auswählen von Aktualisierungseinstellungen

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
>Für Identitäten wird nur die geplante vollständige Durchforstung angewendet.

## <a name="step-9-review-connection"></a>Schritt 9: Überprüfen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>Problembehandlung

Nachdem Sie Ihre Verbindung veröffentlicht und die Ergebnisseite angepasst haben, können Sie den Status auf der Registerkarte **"Connectors"** im [Admin Center](https://admin.microsoft.com)überprüfen. Informationen zum Vornehmen von Aktualisierungen und Löschungen finden Sie unter [Verwalten des Connectors.](manage-connector.md)

## <a name="limitations"></a>Einschränkungen

ServiceNow Graph Connector hat die folgenden Einschränkungen in seiner neuesten Version:

- Die Indizierung von Wissensartikeln, die für alle Personen in einer Organisation verfügbar sind, ist ein allgemein verfügbares Feature.
- *Nur Personen mit Zugriff auf dieses Datenquellenfeature* im Schritt "Suchberechtigungen verwalten" befinden sich in der Vorschau und verarbeiten nur [Benutzerkriterienberechtigungen.](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) Andere Zugriffsberechtigungstypen werden in den Suchergebnissen nicht angewendet.
- Benutzerkriterien mit erweiterten Skripts werden in der aktuellen Vorschauversion nicht unterstützt. Wissensartikel mit einer Zugriffseinschränkung werden indiziert, wobei jeder Zugriff verweigert wird, und werden erst dann in suchergebnissen angezeigt, wenn wir sie unterstützen.