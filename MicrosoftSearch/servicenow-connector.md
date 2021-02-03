---
title: ServiceNow Graph Connector für Microsoft Search
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
description: Einrichten des ServiceNow -Graph-Connectors für Microsoft Search
ms.openlocfilehash: d1fdfb5f1aec5091fd526152de2bdc86932cfdb9
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084893"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a>ServiceNow Graph Connector

Mit dem ServiceNow Graph-Connector kann Ihre Organisation wissensbasierte Artikel indizieren, die für Benutzer gemäß den Benutzerkriterienberechtigungen in Ihrer Organisation sichtbar sind. Nachdem Sie den Connector und den Indexinhalt von ServiceNow konfiguriert haben, können Benutzer von einem beliebigen Microsoft Search-Client aus nach den Artikeln suchen.

> [!NOTE]
> Lesen Sie [**den Artikel "Setup für Ihren Graph-Connector",**](configure-connector.md) um den allgemeinen Einrichtungsprozess für Graph Connectors zu verstehen.

Dieser Artikel ist für jeden benutzer, der einen ServiceNow Graph Connector konfiguriert, ausgeführt und überwacht. Sie ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den ServiceNow Graph-Connector gelten. Dieser Artikel enthält auch Informationen zur [Problembehandlung und](#troubleshooting) [Einschränkungen.](#limitations)
  
## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a>Schritt 3: Verbindungseinstellungen

Um eine Verbindung mit Ihren ServiceNow-Daten herzustellen, verwenden Sie die Anmeldeinformationen der **ServiceNow-Instanz-URL** Ihrer Organisation für dieses Konto, die Client-ID und den geheimen Clientgeheimnis für die OAuth-Authentifizierung.  

Die **ServiceNow-Instanz-URL** Ihrer Organisation sieht in der Regel wie https:// **&lt; Ihrer-Organisation-Domäne>.service-now.com.** Zusammen mit dieser URL benötigen Sie ein Konto zum Einrichten der Verbindung mit ServiceNow und zum Zulassen, dass Microsoft Search die Artikel aus ServiceNow basierend auf dem Aktualisierungszeitplan aktualisiert. Das Konto sollte mindestens über eine <em>Wissensrolle</em> verfügen. [Erfahren Sie, wie Sie Rollen für ServiceNow-Konten zuweisen.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

>[!NOTE]
>Wenn Sie Benutzer- und Gruppenidentitäten durchforsten möchten, um Zugriffsberechtigungen von Wissensdatenbankartikeln in Microsoft Search-Ergebnissen zu berücksichtigen, sollte das Konto Zugriff auf die folgenden Tabelleneinträge in ServiceNow haben:
>* kb_uc_can_contribute_mtom
>* kb_uc_can_read_mtom
>* kb_uc_cannot_read_mtom
>* kb_uc_cannot_contribute_mtom
>* sys_user
>* sys_user_has_role
>* sys_user_grmember
>* user_criteria
>* kb_knowledge_base  
> Sie können eine Rolle für das Konto erstellen und zuweisen, das Sie zum Herstellen einer Verbindung mit Microsoft Search verwenden. Lesezugriff auf die Tabellen kann für diese Rolle zugewiesen werden. Informationen zum Festlegen des Lesezugriffs auf Tabellendatensätze finden Sie unter [Securing Table Records](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls).

Wählen Sie eine der drei unterstützten Methoden aus, um Inhalte aus ServiceNow zu authentifizieren **und** zu synchronisieren:

1. Standardauthentifizierung
1. ServiceNow OAuth (empfohlen)
1. Azure AD OpenID Connect

### <a name="basic-authentication"></a>Standardauthentifizierung

Geben Sie den Benutzernamen und das Kennwort des ServiceNow-Kontos mit **der Wissenrolle** ein, um sich bei Ihrer Instanz zu authentifizieren.

### <a name="servicenow-oauth"></a>ServiceNow OAuth

Um ServiceNow OAuth für die Authentifizierung zu verwenden, müssen Sie einen Endpunkt in Ihrer "ServiceNow"-Instanz bereitstellen. Die Microsoft Search-App verwendet sie für den Zugriff auf die Instanz. Weitere Informationen finden Sie unter [Erstellen eines Endpunkts für Clients für den Zugriff auf die Instanz](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in der ServiceNow-Dokumentation.

Die folgende Tabelle enthält Anleitungen zum Ausfüllen des Endpunkterstellungsformulars:

Feld | Beschreibung | Empfohlener Wert 
--- | --- | ---
Name | Eindeutiger Wert, der die Anwendung identifiziert, für die Sie den Zugriff auf OAuth benötigen. | Microsoft Search
Client-ID | Eine schreibgeschützte, automatisch generierte eindeutige ID für die Anwendung. Die Instanz verwendet die Client-ID, wenn sie ein Zugriffstoken anfordert. | NA
Geheimer Clientgeheimnis | Mit dieser gemeinsamen geheimen Zeichenfolge autorisieren die Instanz "ServiceNow" und Microsoft Search die Kommunikation miteinander. | Befolgen Sie die bewährten Sicherheitsmethoden, indem Sie den geheimen Schlüssel als Kennwort behandeln.
Umleitungs-URL | Eine erforderliche Rückruf-URL, an die der Autorisierungsserver umleite. | https://gcs.office.com/v1.0/admin/oauth/callback
Logo-URL | Eine URL, die das Bild für das Anwendungslogo enthält. | NA
Aktiv | Aktivieren Sie das Kontrollkästchen, um die Anwendungsregistrierung zu aktivieren. | Auf "Aktiv" festgelegt
Aktualisierungstokenlebensdauer | Die Anzahl der Sekunden, die ein Aktualisierungstoken gültig ist. Aktualisierungstoken laufen standardmäßig in 100 Tagen (8.640.000 Sekunden) ab. | 31.536.000 (1 Jahr)
Lebensdauer des Zugriffstokens | Die Anzahl der Sekunden, die ein Zugriffstoken gültig ist. | 43.200 (12 Stunden)

Geben Sie die Client-ID und den geheimen Clientgeheimnis ein, um eine Verbindung mit Ihrer Instanz herzustellen. Verwenden Sie nach dem Herstellen der Verbindung die Anmeldeinformationen eines ServiceNow-Kontos, um die Berechtigung zum Crawlen zu authentifizieren. Das Konto sollte mindestens über eine **Wissensrolle** verfügen.

### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

Führen Sie die folgenden Schritte aus, um Azure AD OpenID Connect für die Authentifizierung zu verwenden.

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a>Schritt 3.a: Registrieren einer neuen Anwendung in Azure Active Directory

Informationen zum Registrieren einer neuen Anwendung in Azure Active Directory finden Sie unter [Registrieren einer Anwendung.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application) Wählen Sie das Organisationsverzeichnis eines einzelnen Mandanten aus. Umleitungs-URI ist nicht erforderlich. Notieren Sie sich nach der Registrierung die Anwendungs-ID (Client-ID) und die Verzeichnis-ID (Mandanten-ID).

## <a name="step-3b-create-a-client-secret"></a>Schritt 3.b: Erstellen eines geheimen Clientgeheimnis

Weitere Informationen zum Erstellen eines geheimen Clientgeheimnis finden Sie unter [Erstellen eines geheimen Clientgeheimnis.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) Notieren Sie sich den geheimen Client-Schlüssel.

## <a name="step-3c-retrieve-service-principal-object-identifier"></a>Schritt 3.c: Abrufen der Dienstprinzipalobjekt-ID

Führen Sie die Schritte zum Abrufen des Dienstprinzipalobjektbezeichners aus.

1. Führen Sie PowerShell aus.

2. Installieren Sie Azure PowerShell mit dem folgenden Befehl.

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Stellen Sie eine Verbindung mit Azure bereit.

   ```powershell
   Connect-AzAccount
   ```

4. Dienstprinzipalobjektbezeichner erhalten.

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   Ersetzen Sie "Application-ID" durch die Anwendungs-ID (Client-ID) (ohne Anführungszeichen) der Anwendung, die Sie in Schritt 3.a registriert haben. Notieren Sie sich den Wert des ID-Objekts aus der PowerShell-Ausgabe. Es ist die Dienstprinzipal-ID.

Jetzt verfügen Sie über alle erforderlichen Informationen aus dem Azure-Portal. Eine kurze Zusammenfassung der Informationen finden Sie in der folgenden Tabelle.

Eigenschaft | Beschreibung 
--- | ---
Verzeichnis-ID (Mandanten-ID) | Eindeutige ID des Azure Active Directory-Mandanten, aus Schritt 3.a.
Anwendungs-ID (Client-ID) | Eindeutige ID der in Schritt 3.a registrierten Anwendung.
Geheimer Clientschlüssel | Der geheime Schlüssel der Anwendung (aus Schritt 3.b). Behandeln Sie es wie ein Kennwort.
Dienstprinzipal-ID | Eine Identität für die Anwendung, die als Dienst ausgeführt wird. (aus Schritt 3.c)

## <a name="step-3d-register-servicenow-application"></a>Schritt 3.d: Registrieren der Dienstnowanwendung

Die Instanz "ServiceNow" benötigt die folgende Konfiguration:

1. Registrieren Sie eine neue OAuth OIDC-Entität. Weitere Informationen finden Sie unter [Erstellen eines OAuth OIDC-Anbieters.](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)

2. Die folgende Tabelle enthält Anleitungen zum Ausfüllen des Formulars für die Registrierung des OIDC-Anbieters.

   Feld | Beschreibung | Empfohlener Wert
   --- | --- | ---
   Name | Ein eindeutiger Name, der die OAuth-OIDC-Entität identifiziert. | Azure AD
   Client-ID | Die Client-ID der Anwendung, die auf dem OAuth-OIDC-Server eines Drittanbieters registriert ist. Die Instanz verwendet die Client-ID beim Anfordern eines Zugriffstokens. | Anwendungs-ID (Client) aus Schritt 3.a
   Geheimer Clientschlüssel | Der geheime Clientgeheimnis der Anwendung, die auf dem OAuth-OIDC-Server eines Drittanbieters registriert ist. | Geheimer Clientgeheimnis aus Schritt 3.b

   Alle anderen Werte können standard sein.

3. Im Formular zur Registrierung des OIDC-Anbieters müssen Sie eine neue Konfiguration des OIDC-Anbieters hinzufügen. Wählen Sie das Suchsymbol für das *Feld "OAuth OIDC-Anbieterkonfiguration"* aus, um die Datensätze der OIDC-Konfigurationen zu öffnen. Wählen Sie "Neu" aus.

4. Die folgende Tabelle enthält Anleitungen zum Ausfüllen des Formulars zur Konfiguration des OIDC-Anbieters.

   Feld | Empfohlener Wert
   --- | ---
   OIDC Provider |  Azure AD
   OIDC-Metadaten-URL | Die URL muss das Format https \: /login.microsoftonline.com/<tenandId">/.well-known/openid-configuration haben. <br/>Ersetzen Sie "tenantID" durch Verzeichnis-ID (Mandanten-ID) aus Schritt 3.a.
   Lebensdauer des OIDC-Konfigurationscaches |  120
   Anwendung | Global
   Benutzeranspruch | sub
   Benutzerfeld | Benutzer-ID
   Aktivieren der Überprüfung des JTI-Anspruchs | Deaktiviert

5. Wählen Sie "Absenden und Aktualisieren des OAuth OIDC-Entitätsformulars" aus.

## <a name="step-3e-create-a-servicenow-account"></a>Schritt 3.e: Erstellen eines ServiceNow-Kontos

Lesen Sie die Anweisungen zum Erstellen eines ServiceNow-Kontos, [erstellen Sie einen Benutzer in ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

Die folgende Tabelle enthält Anleitungen zum Ausfüllen der Registrierung des ServiceNow-Benutzerkontos.

Feld | Empfohlener Wert
--- | ---
Benutzer-ID | Dienstprinzipal-ID aus Schritt 3.c
Nur Webdienstzugriff | Checked

Alle anderen Werte können auf die Standardeinstellung festgelegt werden.

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a>Schritt 3.f: Aktivieren der Rolle "Knowledge" für das Konto "ServiceNow"

Greifen Sie auf das ServiceNow-Konto zu, das Sie mit der ServiceNow-Prinzipal-ID als Benutzer-ID erstellt haben, und weisen Sie die Wissensrolle zu. Anweisungen zum Zuweisen einer Rolle zu einem ServiceNow-Konto finden Sie hier: Zuweisen einer Rolle [zu einem Benutzer.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

Verwenden Sie die Anwendungs-ID als Client-ID aus Schritt 3.a und den geheimen Clientgeheimnis aus Schritt 3.b, um sich mit Azure AD OpenID Connect bei Ihrer "ServiceNow"-Instanz zu authentifizieren.

## <a name="step-4-select-properties-and-filter-data"></a>Schritt 4: Auswählen von Eigenschaften und Filtern von Daten

In diesem Schritt können Sie der Datenquelle "ServiceNow" verfügbare Eigenschaften hinzufügen oder aus ihr entfernen. Microsoft 365 hat standardmäßig bereits einige Eigenschaften ausgewählt.

Mit einer ServiceNow-Abfragezeichenfolge können Sie Bedingungen für die Synchronisierung von Artikeln angeben. Es ist wie eine **Where-Klausel** in einer **SQL Select-Anweisung.** Sie können beispielsweise festlegen, dass nur Artikel indiziert werden sollen, die veröffentlicht und aktiv sind. Informationen zum Erstellen einer eigenen Abfragezeichenfolge finden Sie unter [Generieren einer codierten Abfragezeichenfolge mithilfe eines Filters.](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)

Verwenden Sie die Schaltfläche "Vorschauergebnisse", um die Beispielwerte der ausgewählten Eigenschaften und des Abfragefilters zu überprüfen.

## <a name="step-5-manage-search-permissions"></a>Schritt 5: Verwalten von Suchberechtigungen

Der ServiceNow Connector unterstützt Suchberechtigungen, die für **alle** oder nur Personen mit Zugriff **auf diese Datenquelle sichtbar sind.** Indizierte Daten werden in den Suchergebnissen angezeigt und sind für Benutzer in der Organisation sichtbar, die jeweils Zugriff darauf haben. ServiceNow Connector unterstützt standardmäßige Benutzerkriterienberechtigungen ohne erweiterte Skripts. Wenn der Connector ein Benutzerkriterium mit erweitertem Skript findet, werden nicht alle Daten, die diese Benutzerkriterien verwenden, in den Suchergebnissen angezeigt.

Wenn Sie **"Nur** Personen mit Zugriff auf diese Datenquelle" auswählen, müssen Sie weiter auswählen, ob ihre "ServiceNow"-Instanz benutzer oder Nicht-AAD-Benutzer in Azure Active Directory (AAD) bereitgestellt hat.

>[!NOTE]
>Der ServiceNow Connector befindet sich in **der Vorschau,** wenn Sie "Nur Personen **mit Zugriff auf diese Datenquelle" auswählen.**

>[!NOTE]
>Wenn Sie AAD als Typ der Identitätsquelle auswählen, stellen Sie sicher, dass Sie der E-Mail-Zieleigenschaft in ServiceNow die Eigenschaft "UPN-Quelle" zuweisen. Informationen zum Überprüfen oder Ändern Ihrer Zuordnungen finden Sie unter Anpassen von Attributzuordnungen für die Benutzerbereitstellung für [SaaS-Anwendungen in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes)

Wenn Sie eine ACL aus Ihrer "ServiceNow"-Instanz aufgenommen und "Nicht-AAD" für den Identitätstyp ausgewählt haben, finden Sie unter "Zuordnen ihrer [Nicht-Azure AD-Identitäten"](map-non-aad.md) Anweisungen zum Zuordnen der Identitäten.

## <a name="step-6-assign-property-labels"></a>Schritt 6: Zuweisen von Eigenschaftsbezeichnungen

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a>Schritt 7: Verwalten des Schemas

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a>Schritt 8: Auswählen von Aktualisierungseinstellungen

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
>Bei Identitäten wird nur eine vollständige Durchforstung angewendet, die geplant ist.

## <a name="step-9-review-connection"></a>Schritt 9: Überprüfen der Verbindung

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>Problembehandlung

Nachdem Sie Ihre Verbindung veröffentlicht und die Ergebnisseite angepasst haben, können Sie den Status auf der Registerkarte **"Connectors"** im [Admin Center überprüfen.](https://admin.microsoft.com) Informationen zum Aktualisieren und Löschen finden Sie unter ["Verwalten des Connectors".](manage-connector.md)

## <a name="limitations"></a>Einschränkungen

Der ServiceNow Graph Connector hat in seiner neuesten Version die folgenden Einschränkungen:

- Die Indizierung von Wissensdatenbankartikeln, die für jeden in einer Organisation verfügbar sind, ist ein allgemein verfügbares Feature.
- *Nur Personen mit Zugriff auf dieses* Datenquellenfeature unter dem Schritt "Suchberechtigungen verwalten" befindet sich in der Vorschau und verarbeitet nur [Benutzerkriterienberechtigungen.](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) Alle anderen Arten von Zugriffsberechtigungen werden in den Suchergebnissen nicht angewendet.
- Benutzerkriterien mit erweiterten Skripts werden in der aktuellen Vorschauversion nicht unterstützt. Wissensdatenbankartikel mit Zugriffseinschränkung werden indiziert, um allen Benutzern den Zugriff zu verweigern, und werden erst dann in den Suchergebnissen angezeigt, wenn sie von uns unterstützt werden.
