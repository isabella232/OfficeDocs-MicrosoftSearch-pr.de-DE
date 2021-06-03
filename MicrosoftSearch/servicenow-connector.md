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
description: Einrichten des ServiceNow-Graph Connectors für Microsoft Search
ms.openlocfilehash: 08947381dff7cd06007c68a7f1614b23c53f7510
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720965"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a>ServiceNow Graph Connector

Der ServiceNow-Graph-Connector ermöglicht Es Ihrer Organisation, wissensbasierte Artikel zu indizieren, die für Benutzer gemäß den Benutzerkriterienberechtigungen in Ihrer Organisation sichtbar sind. Nachdem Sie den Connector und den Indexinhalt von ServiceNow konfiguriert haben, können Benutzer in jedem Microsoft Search-Client nach den Artikeln suchen.

> [!NOTE]
> Lesen Sie [**den Artikel Setup für Graph Connector,**](configure-connector.md) um die Allgemeinen Anweisungen Graph Connectors zu verstehen.

Dieser Artikel ist für jeden benutzer, der einen ServiceNow-Graph konfiguriert, ausgeführt und überwacht. Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen an, die nur für den ServiceNow-Graph gelten. Dieser Artikel enthält auch Informationen zur [Problembehandlung und](#troubleshooting) [Einschränkungen](#limitations).

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph im Microsoft 365 Admin Center

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a>Schritt 3: Verbindungs Einstellungen

Um eine Verbindung mit Ihren ServiceNow-Daten herzustellen, verwenden Sie die **DienstNow-Instanz-URL-Anmeldeinformationen** Ihrer Organisation für dieses Konto, die Client-ID und den Geheimen Clientgeheimnis für die OAuth-Authentifizierung.  

Die **ServiceNow-Instanz-URL** Ihrer Organisation sieht in der Regel wie **https:// &lt; Ihrer-Organisation-Domäne>.service-now.com** aus. Zusammen mit dieser URL benötigen Sie ein Konto zum Einrichten der Verbindung zu ServiceNow und zum Zulassen, dass Microsoft Search die Artikel von ServiceNow basierend auf dem Aktualisierungszeitplan aktualisiert. Das Konto sollte mindestens über eine <em>Wissensrolle</em> verfügen. [Erfahren Sie, wie Sie Rollen für ServiceNow-Konten zuweisen.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

>[!NOTE]
>Wenn Sie Benutzer- und Gruppenidentitäten durchforsten möchten, um Zugriffsberechtigungen von Wissensartikeln in Microsoft Search-Ergebnissen zu berücksichtigen, sollte das Konto Zugriff auf die folgenden Tabelleneinträge in ServiceNow haben:
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

Wählen Sie eine der drei unterstützten Methoden aus, um Inhalte von ServiceNow zu authentifizieren **und** zu synchronisieren:

1. Standardauthentifizierung
1. ServiceNow OAuth (empfohlen)
1. Azure AD OpenID Verbinden

### <a name="basic-authentication"></a>Standardauthentifizierung

Geben Sie den Benutzernamen und das Kennwort des ServiceNow-Kontos mit **der Wissensrolle** ein, um sich bei Ihrer Instanz zu authentifizieren.

### <a name="servicenow-oauth"></a>ServiceNow OAuth

Um ServiceNow OAuth für die Authentifizierung zu verwenden, müssen Sie einen Endpunkt in Ihrer ServiceNow-Instanz bereitstellen. Die Microsoft Search-App verwendet sie, um auf die Instanz zu zugreifen. Weitere Informationen finden Sie unter [Erstellen eines Endpunkts](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) für Clients für den Zugriff auf die Instanz in der ServiceNow-Dokumentation.

Die folgende Tabelle enthält Anleitungen zum Ausfüllen des Endpunkterstellungsformulars:

Feld | Beschreibung | Empfohlener Wert 
--- | --- | ---
Name | Eindeutiger Wert, der die Anwendung identifiziert, für die Sie OAuth-Zugriff benötigen. | Microsoft Search
Client-ID | Eine schreibgeschützte, automatisch generierte eindeutige ID für die Anwendung. Die Instanz verwendet die Client-ID, wenn sie ein Zugriffstoken anfordert. | NA
Geheimer Clientgeheimnis | Mit dieser gemeinsamen geheimen Zeichenfolge autorisieren die ServiceNow-Instanz und Microsoft Search die Kommunikation miteinander. | Befolgen Sie die bewährten Methoden für die Sicherheit, indem Sie den geheimen Schlüssel als Kennwort behandeln.
Umleitungs-URL | Eine erforderliche Rückruf-URL, an die der Autorisierungsserver umleite. | https://gcs.office.com/v1.0/admin/oauth/callback
Logo-URL | Eine URL, die das Bild für das Anwendungslogo enthält. | NA
Aktiv | Aktivieren Sie das Kontrollkästchen, um die Anwendungsregistrierung aktiv zu machen. | Auf aktiv festgelegt
Aktualisieren der Tokenlebensdauer | Die Anzahl der Sekunden, die ein Aktualisierungstoken gültig ist. Aktualisierungstoken laufen standardmäßig in 100 Tagen (8.640.000 Sekunden) ab. | 31.536.000 (1 Jahr)
Lebensdauer des Zugriffstokens | Die Anzahl der Sekunden, die ein Zugriffstoken gültig ist. | 43.200 (12 Stunden)

Geben Sie die Client-ID und den geheimen Clientgeheimnis ein, um eine Verbindung mit Ihrer Instanz herzustellen. Verwenden Sie nach der Verbindung die Anmeldeinformationen eines ServiceNow-Kontos, um die Berechtigung zum Crawlen zu authentifizieren. Das Konto sollte mindestens über eine **Wissensrolle** verfügen.

### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Verbinden

Führen Sie die folgenden Schritte aus, um Azure AD OpenID Verbinden für die Authentifizierung zu verwenden.

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a>Schritt 3.a: Registrieren einer neuen Anwendung in Azure Active Directory

Weitere Informationen zum Registrieren einer neuen Anwendung in Azure Active Directory finden Sie [unter Registrieren einer Anwendung](/azure/active-directory/develop/quickstart-register-app#register-an-application). Wählen Sie Ein-Mandanten-Organisationsverzeichnis aus. Umleitungs-URI ist nicht erforderlich. Notieren Sie sich nach der Registrierung die Anwendungs-ID (Client)-ID und die Verzeichnis-ID (Mandant).

## <a name="step-3b-create-a-client-secret"></a>Schritt 3.b: Erstellen eines geheimen Clientgeheimnis

Weitere Informationen zum Erstellen eines geheimen Clientgeheimnis finden Sie unter [Creating a client secret](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret). Notieren Sie sich den geheimen Clientgeheimnis.

## <a name="step-3c-retrieve-service-principal-object-identifier"></a>Schritt 3.c: Abrufen der Dienstprinzipalobjekt-ID

Führen Sie die Schritte zum Abrufen der Dienstprinzipalobjekt-ID aus.

1. Führen Sie PowerShell aus.

2. Installieren Azure PowerShell mithilfe des folgenden Befehls.

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Verbinden azure.

   ```powershell
   Connect-AzAccount
   ```

4. Bezeichner des Dienstprinzipalobjekts.

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   Ersetzen Sie "Application-ID" durch Anwendungs-ID (Client-ID) (ohne Anführungszeichen) der Anwendung, die Sie in Schritt 3.a registriert haben. Beachten Sie den Wert des ID-Objekts aus der PowerShell-Ausgabe. Es ist die Dienstprinzipal-ID.

Jetzt verfügen Sie über alle erforderlichen Informationen aus dem Azure-Portal. Eine kurze Zusammenfassung der Informationen finden Sie in der folgenden Tabelle.

Eigenschaft | Beschreibung 
--- | ---
Verzeichnis-ID (Mandanten-ID) | Eindeutige ID des Azure Active Directory Mandanten aus Schritt 3.a.
Anwendungs-ID (Client-ID) | Eindeutige ID der in Schritt 3.a registrierten Anwendung.
Geheimer Clientschlüssel | Der geheime Schlüssel der Anwendung (aus Schritt 3.b). Behandeln Sie es wie ein Kennwort.
Dienstprinzipal-ID | Eine Identität für die Anwendung, die als Dienst ausgeführt wird. (ab Schritt 3.c)

## <a name="step-3d-register-servicenow-application"></a>Schritt 3.d: Registrieren der ServiceNow-Anwendung

Die ServiceNow-Instanz benötigt die folgende Konfiguration:

1. Registrieren Sie eine neue OAuth OIDC-Entität. Weitere Informationen finden Sie unter [Create an OAuth OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).

2. Die folgende Tabelle enthält Anleitungen zum Ausfüllen des OIDC-Anbieterregistrierungsformulars

   Feld | Beschreibung | Empfohlener Wert
   --- | --- | ---
   Name | Ein eindeutiger Name, der die OAuth OIDC-Entität identifiziert. | Azure AD
   Client-ID | Die Client-ID der Anwendung, die auf dem OAuth OIDC-Server eines Drittanbieters registriert ist. Die Instanz verwendet die Client-ID beim Anfordern eines Zugriffstokens. | Anwendungs-ID (Client)-ID aus Schritt 3.a
   Geheimer Clientschlüssel | Der Clientgeheimnis der Anwendung, die auf dem OAuth OIDC-Server eines Drittanbieters registriert ist. | Geheimer Clientgeheimnis aus Schritt 3.b

   Alle anderen Werte können standardmäßig verwendet werden.

3. Im OIDC-Anbieterregistrierungsformular müssen Sie eine neue Konfiguration des OIDC-Anbieters hinzufügen. Wählen Sie das Suchsymbol für *das Feld OAuth OIDC Provider Configuration* aus, um die Datensätze von OIDC-Konfigurationen zu öffnen. Wählen Sie Neu aus.

4. In der folgenden Tabelle finden Sie Anleitungen zum Ausfüllen des OIDC-Anbieterkonfigurationsformulars

   Feld | Empfohlener Wert
   --- | ---
   OIDC-Anbieter |  Azure AD
   OIDC-Metadaten-URL | Die URL muss im Format https \: /login.microsoftonline.com/<tenandId">/.well-known/openid-configuration sein. <br/>Ersetzen Sie "tenantID" durch Verzeichnis-ID (Mandant) aus Schritt 3.a.
   Lebensdauer des OIDC-Konfigurationscaches |  120
   Application | Global
   Benutzeranspruch | sub
   Benutzerfeld | Benutzer-ID
   Aktivieren der Überprüfung von JTI-Anspruchsforderungen | Deaktiviert

5. Wählen Sie Senden und Aktualisieren des OAuth OIDC-Entitätsformulars aus.

## <a name="step-3e-create-a-servicenow-account"></a>Schritt 3.e: Erstellen eines ServiceNow-Kontos

Lesen Sie die Anweisungen zum Erstellen eines ServiceNow-Kontos, [erstellen Sie einen Benutzer in ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

Die folgende Tabelle enthält Anleitungen zum Ausfüllen der Registrierung des ServiceNow-Benutzerkontos.

Feld | Empfohlener Wert
--- | ---
Benutzer-ID | Dienstprinzipal-ID aus Schritt 3.c
Nur Webdienstzugriff | Checked

Alle anderen Werte können standardmäßig bleiben.

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a>Schritt 3.f: Aktivieren der Rolle "Wissen" für das ServiceNow-Konto

Greifen Sie auf das ServiceNow-Konto zu, das Sie mit der ServiceNow-Prinzipal-ID als Benutzer-ID erstellt haben, und weisen Sie die Wissensrolle zu. Anweisungen zum Zuweisen einer Rolle zu einem ServiceNow-Konto finden Sie hier: Zuweisen einer Rolle [zu einem Benutzer](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

Verwenden Sie Anwendungs-ID als Client-ID aus Schritt 3.a und Geheimer Clientgeheimnis aus Schritt 3.b, um sich bei Ihrer ServiceNow-Instanz mithilfe von Azure AD OpenID Verbinden.

## <a name="step-4-select-properties-and-filter-data"></a>Schritt 4: Auswählen von Eigenschaften und Filtern von Daten

In diesem Schritt können Sie verfügbare Eigenschaften aus Ihrer ServiceNow-Datenquelle hinzufügen oder entfernen. Microsoft 365 hat standardmäßig bereits einige Eigenschaften ausgewählt.

Mit einer ServiceNow-Abfragezeichenfolge können Sie Bedingungen für die Synchronisierung von Artikeln angeben. Es ist wie eine **Where-Klausel** in einer **SQL Select-Anweisung.** Sie können z. B. nur veröffentlichte und aktive Artikel indizieren. Weitere Informationen zum Erstellen einer eigenen Abfragezeichenfolge finden Sie unter Generieren einer [codierten Abfragezeichenfolge mithilfe eines Filters.](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)

Verwenden Sie die Schaltfläche Vorschauergebnisse, um die Beispielwerte der ausgewählten Eigenschaften und des Abfragefilters zu überprüfen.

## <a name="step-5-manage-search-permissions"></a>Schritt 5: Verwalten von Suchberechtigungen

Der ServiceNow-Connector unterstützt Suchberechtigungen, die für **Jeder** oder nur Personen mit **Zugriff auf diese Datenquelle sichtbar sind.** Indizierte Daten werden in den Suchergebnissen angezeigt und sind für Benutzer in der Organisation sichtbar, die auf diese zugreifen können. ServiceNow Connector unterstützt standardmäßige Benutzerkriterienberechtigungen ohne erweiterte Skripts. Wenn der Connector ein Benutzerkriterium mit erweitertem Skript findet, werden alle Daten, die diese Benutzerkriterien verwenden, nicht in den Suchergebnissen angezeigt.

Wenn Sie **Nur** Personen mit Zugriff auf diese Datenquelle auswählen, müssen Sie weiter auswählen, ob Ihre ServiceNow-Instanz über Azure Active Directory (AAD) bereitgestellte Benutzer oder Nicht-AAD-Benutzer verfügt.

>[!NOTE]
>Der ServiceNow-Connector befindet sich in **der Vorschau,** wenn Sie Nur Personen mit **Zugriff auf diese Datenquelle auswählen.**

>[!NOTE]
>Wenn Sie AAD als Typ der Identitätsquelle auswählen, stellen Sie sicher, dass Sie die UPN-Quelleigenschaft der E-Mail-Zieleigenschaft in ServiceNow zuweisen. Informationen zum Überprüfen oder Ändern der Zuordnungen finden Sie unter [Customizing user provisioning attribute-mappings for SaaS applications in Azure Active Directory](/azure/active-directory/app-provisioning/customize-application-attributes).

Wenn Sie eine ACL aus Ihrer ServiceNow-Instanz aufgenommen und "Nicht-AAD" für den Identitätstyp ausgewählt haben, finden Sie unter [Map your non-Azure AD Identities](map-non-aad.md) Anweisungen zum Zuordnen der Identitäten.

### <a name="managing-search-permissions-in-microsoft-search"></a>Verwalten von Suchberechtigungen in Microsoft Search

Im folgenden Video können Sie sehen, wie Sie den Servicenow-Connector verwenden, um Wissensartikel zu indizieren, Benutzerkriterienberechtigungen zu definieren und die Änderungen zwischen ServiceNow und Microsoft Search Index nahtlos zu synchronisieren.

> [!VIDEO https://www.youtube.com/watch?v=TVSkJpk1RiE]

## <a name="step-6-assign-property-labels"></a>Schritt 6: Zuweisen von Eigenschaftsbezeichnungen

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a>Schritt 7: Verwalten des Schemas

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a>Schritt 8: Auswählen von Aktualisierungseinstellungen

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
>Bei Identitäten wird nur der vollständige durchforstungsterminiert angewendet.

## <a name="step-9-review-connection"></a>Schritt 9: Überprüfen der Verbindung

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>Problembehandlung

Nachdem Sie Ihre Verbindung veröffentlicht haben und die Ergebnisseite angepasst haben, können Sie den Status unter der Registerkarte **Connectors** im [Admin Center überprüfen.](https://admin.microsoft.com) Informationen zum Erstellen von Aktualisierungen und Löschungen finden Sie unter [Manage your connector](manage-connector.md).

## <a name="limitations"></a>Einschränkungen

ServiceNow Graph Connector hat in seiner neuesten Version die folgenden Einschränkungen:

- Die Indizierung von Wissensartikeln, die für alle Indizierungsartikel in einer Organisation verfügbar sind, ist ein allgemein verfügbares Feature.
- *Nur Personen mit Zugriff auf dieses Datenquellenfeature* unter Schritt Suchberechtigungen verwalten befindet sich in der Vorschau und verarbeitet nur [Benutzerkriterienberechtigungen.](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) Alle anderen Arten von Zugriffsberechtigungen werden in den Suchergebnissen nicht angewendet.
- Benutzerkriterien mit erweiterten Skripts werden in der aktuellen Vorschauversion nicht unterstützt. Wissensartikel mit zugriffseinschränkungen werden indiziert, ohne dass jedem Zugriff verweigert wird, und werden erst dann in suchergebnissen angezeigt, wenn wir sie unterstützen.