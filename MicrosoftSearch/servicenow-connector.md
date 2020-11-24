---
title: ServiceNow Connector für Microsoft Search
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des ServiceNow Connectors für Microsoft Search
ms.openlocfilehash: 520232f8055d5432ccb96a840a9466ae6a4e3b1a
ms.sourcegitcommit: ac4e261c01262be747341f810d2d1faf220d3961
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2020
ms.locfileid: "49382560"
---
# <a name="servicenow-connector"></a>ServiceNow-Connector

Mit dem ServiceNow-Connector kann Ihre Organisation Knowledge Base-Artikel indizieren, die für alle Benutzer sichtbar sind oder mit Berechtigungen für benutzerkriterien in Ihrer Organisation eingeschränkt sind. Nachdem Sie den Connector-und den Index Inhalt von ServiceNow konfiguriert haben, können Endbenutzer nach diesen Artikeln von einem beliebigen Microsoft Search-Client aus suchen.  

Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen ServiceNow-Connector konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.

Informationen zum Zugriff auf von Microsoft erstellte Connectors finden Sie unter [Einrichten Ihres von Microsoft erstellten Connectors für Microsoft Search](https://docs.microsoft.com/microsoftsearch/configure-connector). ServiceNow Connector Specific Configuration wird im folgenden Artikel erläutert.

## <a name="connection-settings"></a>Verbindungseinstellungen
Zum Herstellen einer Verbindung mit ihren ServiceNow-Daten benötigen Sie die **ServiceNow-Instanz-URL** Ihrer Organisation, Anmeldeinformationen für dieses Konto sowie die Client-ID und den geheimen Client Schlüssel für die OAuth-Authentifizierung.  

Die ServiceNow- **Instanz-URL** Ihrer Organisation sieht in der Regel wie **https:// &lt; ihrer-Organisations-Domain>. Service-now.com** aus. Zusammen mit dieser URL benötigen Sie ein Konto zum Einrichten der Verbindung mit ServiceNow sowie dazu, dass Microsoft Search die Artikel aus ServiceNow regelmäßig basierend auf dem Aktualisierungszeitplan aktualisieren kann. Das Konto sollte mindestens über eine <em>Wissens</em> Rolle verfügen. [Erfahren Sie, wie Sie der Rolle für ServiceNow-Konten zuweisen](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

>[!NOTE]
>Wenn Sie Benutzer-und Gruppenidentitäten durchforsten möchten, um die Zugriffsberechtigungen von Knowledge Articles in Microsoft-Suchergebnissen zu honorieren, sollte das Konto über Zugriff verfügen, um die folgenden Tabelleneinträge in ServiceNow lesen zu können:
>* kb_uc_can_contribute_mtom
>* kb_uc_can_read_mtom
>* kb_uc_cannot_read_mtom
>* kb_uc_cannot_contribute_mtom
>* sys_user
>* sys_user_has_role
>* sys_user_grmember
>* user_criteria
>* kb_knowledge_base  
> Sie können eine Rolle für das Konto erstellen und zuweisen, das Sie für die Verbindung mit der Microsoft-Suche verwenden. Lesezugriff auf die Tabellen kann für diese Rolle zugewiesen werden. Informationen zum Festlegen des Lesezugriffs auf Tabellendatensätze finden Sie unter [Sichern von Tabellendatensätzen](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls).

Wählen Sie **eine der drei** unterstützten Methoden aus, um Inhalte von ServiceNow zu authentifizieren und zu synchronisieren: 
1. Standardauthentifizierung 
2. ServiceNow OAuth (empfohlen)
3. Azure AD OpenID Connect

#### <a name="basic-authentication"></a>Standardauthentifizierung

Geben Sie den Benutzernamen und das Kennwort des ServiceNow-Kontos mit der **Wissens** Rolle ein, die bei Ihrer Instanz authentifiziert werden soll.

#### <a name="servicenow-oauth"></a>ServiceNow OAuth

Um ServiceNow OAuth für die Authentifizierung zu verwenden, muss ein ServiceNow-Administrator einen Endpunkt in der ServiceNow-Instanz bereitstellen, damit die Microsoft Search-App auf die Instanz zugreifen kann. Weitere Informationen finden Sie unter [Erstellen eines Endpunkts für Clients für den Zugriff auf die Instanz](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in der ServiceNow-Dokumentation.

Die folgende Tabelle enthält Anleitungen zum Ausfüllen des Endpunkts-erstellungsformulars:

**Field** | **Beschreibung** | **Empfohlener Wert**
--- | --- | ---
Name | Dieser eindeutige Wert identifiziert die Anwendung, für die Sie OAuth-Zugriff benötigen. | Microsoft Search
Client-ID | Eine schreibgeschützte, automatisch generierte eindeutige ID für die Anwendung. Die Instanz verwendet die Client-ID, wenn Sie ein Zugriffstoken anfordert. | NA
Geheimer Client Schlüssel | Mit dieser freigegebenen geheimen Zeichenfolge autorisieren die ServiceNow-Instanz und die Microsoft Search die Kommunikation miteinander. | Beachten Sie bewährte Methoden für die Sicherheit, indem Sie dies als Kennwort behandeln.
Umleitungs-URL | Eine erforderliche Rückruf-URL, an die der autorisierungsserver umgeleitet wird. | https://gcs.office.com/v1.0/admin/oauth/callback
Logo-URL | Eine URL, die das Bild für das Anwendungslogo enthält. | NA
Aktiv | Aktivieren Sie das Kontrollkästchen, um die Anwendungsregistrierung aktiv zu machen. | Auf aktiv festlegen
Lebensdauer des Aktualisierungs Tokens | Die Anzahl der Sekunden, die ein Aktualisierungstoken gültig ist. Standardmäßig laufen Aktualisierungstoken in 100 Tagen (8640000 Sekunden) ab. | 31.536.000 (1 Jahr)
Lebensdauer des Zugriffstokens | Die Anzahl der Sekunden, die ein Zugriffstoken gültig ist. | 43.200 (12 Stunden)

Geben Sie die Client-ID und den geheimen Client Schlüssel für die Verbindung mit Ihrer Instanz ein. Verwenden Sie nach dem Herstellen einer Verbindung eine ServiceNow-Kontoanmeldeinformationen, um die Berechtigung zum durchforsten zu authentifizieren. Das Konto sollte mindestens über eine **Wissens** Rolle verfügen.

#### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

Führen Sie die folgenden Schritte aus, um Azure AD OpenID Connect für die Authentifizierung zu verwenden.

###### <a name="step-1-register-a-new-application-in-azure-active-directory"></a>Schritt 1: Registrieren einer neuen Anwendung in Azure Active Directory

Informationen zum Registrieren einer neuen Anwendung in Azure Active Directory finden Sie unter [Registrieren einer Anwendung](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application). Wählen Sie ein Organisations Verzeichnis für einzelne Mandanten aus. Umleitungs-URI ist nicht erforderlich. Notieren Sie nach der Registrierung die ID des Anwendungsclients (Client) und die Verzeichnis (Mandanten-ID).

###### <a name="step-2-create-a-client-secret"></a>Schritt 2: Erstellen eines geheimen Client Schlüssels

Informationen zum Erstellen eines geheimen Client Schlüssels finden Sie unter [Erstellen eines geheimen Client Schlüssels](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret). Notieren Sie sich den geheimen Client Schlüssel.

###### <a name="step-3-retrieve-service-principal-object-identifier"></a>Schritt 3: Abrufen der Dienstprinzipal Objekt-ID

Führen Sie die Schritte zum Abrufen der Dienstprinzipal Objekt-ID aus.

1. Ausführen von PowerShell
2. Installieren von Azure PowerShell mit dem folgenden Befehl
```<language>
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
```
3. Herstellen einer Verbindung mit Azure
```<language>
    Connect-AzAccount
```
4. Dienstprinzipal Objekt-ID abrufen
```<language>
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
```
Ersetzen Sie "Application-ID" durch die Application (Client)-ID (ohne Anführungszeichen) der Anwendung, die Sie in Schritt 1 registriert haben. Notieren Sie sich den Wert des ID-Objekts aus der PowerShell-Ausgabe. Es handelt sich um die Dienstprinzipal-ID.

Jetzt haben Sie alle erforderlichen Informationen aus dem Azure-Portal. Eine kurze Zusammenfassung der Informationen finden Sie in der folgenden Tabelle.

**Eigenschaft** | **Beschreibung**
--- | ---
Verzeichnis-ID (Mandanten-ID) | Dies ist eine eindeutige ID, die den Azure Active Directory-Mandanten (aus Schritt 1) verweist.
Anwendungs-ID (Client-ID) | Hierbei handelt es sich um eine eindeutige ID, die die in Schritt 1 registrierte Anwendung referenziert.
Geheimer Clientschlüssel | Dies ist der geheime Schlüssel der Anwendung (aus Schritt 2). Behandeln Sie es wie ein Kennwort.
Dienstprinzipal-ID | Eine Identität für die Anwendung, die als Dienst gestartet wird. (aus Schritt 3)

###### <a name="step-4-register-servicenow-application"></a>Schritt 4: Registrieren der ServiceNow-Anwendung

Die folgende Konfiguration muss in der ServiceNow-Instanz ausgeführt werden.

1. Registrieren einer neuen OAuth OIDC-Entität. Weitere Informationen finden Sie unter [Create an OAuth OIDC Provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).
2. In der folgenden Tabelle finden Sie Anleitungen zum Ausfüllen des OIDC-Anbieter Registrierungsformulars.

**Field** | **Beschreibung** | **Empfohlener Wert**
--- | --- | ---
Name | Ein eindeutiger Name, der die OAuth OIDC-Entität identifiziert. | Azure AD
Client-ID | Die Client-ID der Anwendung, die im OAuth OIDC-Server des Drittanbieters registriert ist. Die Instanz verwendet die Client-ID beim Anfordern eines Zugriffstokens. | Anwendungs-ID (Client) aus Schritt 1
Geheimer Clientschlüssel | Der geheime Client Schlüssel der Anwendung, die im OAuth OIDC-Server von Drittanbietern registriert ist. | Geheimer Client Schlüssel aus Schritt 2

Alle anderen Werte können Standard sein.

3. Im OIDC-Anbieter Registrierungsformular müssen Sie eine neue OIDC-Anbieterkonfiguration hinzufügen. Klicken Sie auf das Suchsymbol für *OAuth OIDC-Anbieter Konfigurations* Feld, um die Datensätze der OIDC-Konfigurationen zu öffnen. Klicken Sie auf Neu.
4. In der folgenden Tabelle finden Sie Anleitungen zum Ausfüllen des OIDC-Anbieter Konfigurations Formulars.

**Field** | **Empfohlener Wert**
--- | ---
OIDC-Anbieter |  Azure AD
OIDC-Metadaten-URL | Dies muss das Format https \: //Login.microsoftonline.com/"tenandId"/.well-known/OpenID-Configuration <br/>Ersetzen Sie "Mandantenkennung" durch die Verzeichnis (Mandanten-ID) aus Schritt 1 (ohne Anführungszeichen).
Lebensdauer des OIDC-Konfigurations Cache |  120
Anwendung | Global
Benutzer Forderung | sub
Benutzerfeld | Benutzer-ID
Aktivieren der Überprüfung der Überprüfung der Forderung | Deaktiviert

5. Klicken Sie auf Submit, und aktualisieren Sie das entitätsformular OAuth OIDC.

###### <a name="step-5-create-a-servicenow-account"></a>Schritt 5: Erstellen eines ServiceNow-Kontos

Lesen Sie die Anweisungen zum Erstellen eines ServiceNow-Kontos, [Erstellen Sie einen Benutzer in ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

Die folgende Tabelle enthält Anleitungen zum Ausfüllen der ServiceNow-Benutzerkonto Registrierung.

**Field** | **Empfohlener Wert**
--- | ---
Benutzer-ID | Dienstprinzipal-ID aus Schritt 3
Nur-Webdienstzugriff | Checked

Alle anderen Werte können als Standard beibehalten werden.

###### <a name="step-6-enable-knowledge-role-for-the-servicenow-account"></a>Schritt 6: Aktivieren der Wissens Rolle für das ServiceNow-Konto

Greifen Sie auf das ServiceNow-Konto zu, das Sie mit ServiceNow Principal ID als Benutzer-ID erstellt haben, und weisen Sie die Wissens Rolle zu. Anweisungen zum Zuweisen einer Rolle zu einem ServiceNow-Konto finden Sie hier, [Zuweisen einer Rolle zu einem Benutzer](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

Verwenden Sie die Anwendungs-ID als Client-ID (aus Schritt 1) und den geheimen Client Schlüssel (ab Schritt 2) im Admin Center-Konfigurations-Assistenten, um sich bei ihrer ServiceNow-Instanz mit Azure AD OpenID Connect zu authentifizieren.

## <a name="filter-data"></a>Filtern von Daten

Mit einer ServiceNow-Abfragezeichenfolge können Sie Bedingungen für die Synchronisierung von Artikeln angeben. Es ist wie eine **Where** -Klausel in einer **SQL-SELECT** -Anweisung. Beispielsweise können Sie auswählen, nur veröffentlichte und aktive Artikel zu indizieren. Weitere Informationen zum Erstellen einer eigenen Abfragezeichenfolge finden Sie unter [Generieren einer codierten Abfragezeichenfolge mithilfe eines Filters](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen

Der ServiceNow-Connector unterstützt Suchberechtigungen, die für **alle** Benutzer oder **nur für Personen mit Zugriff auf diese Datenquelle** sichtbar sind. Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation oder für Benutzer sichtbar, die Zugriff auf diese haben. ServiceNow Connector unterstützt Standardbenutzer Kriterien-Berechtigungen ohne erweiterte Skripts. Wenn der Connector auf ein Benutzer Kriterium mit erweitertem Skript stößt, werden alle Daten, die diese benutzerkriterien verwenden, nicht in den Suchergebnissen angezeigt.

Wenn Sie **nur Personen mit Zugriff auf diese Datenquelle** auswählen, müssen Sie entscheiden, ob Ihre ServiceNow-Instanz Azure-Active Directory (AAD)-Benutzer oder nicht-Aad-Benutzer enthält.

>[!NOTE]
>Der ServiceNow-Connector befindet sich in der **Vorschau** , wenn Sie **nur Personen mit Zugriff auf diese Datenquelle** auswählen.

>[!NOTE]
>Wenn Sie Aad als Typ der Identitäts Quelle auswählen, müssen Sie sicherstellen, dass Sie die UPN-Quelleigenschaft für die e-Mail-Zieleigenschaft in ServiceNow zuweisen. Informationen zum Überprüfen oder Ändern ihrer Zuordnungen finden Sie unter [Customizing User Provisioning Attribut-Mappings for Saas Applications in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes).

Wenn Sie eine ACL aus ihrer ServiceNow-Instanz aufnehmen und "nicht-Aad" für den Identitätstyp ausgewählt haben, finden Sie Anweisungen zum Zuordnen der Identitäten unter [Zuordnen der nicht Azure AD Identitäten](map-non-aad.md) .

## <a name="assign-property-labels"></a>Zuweisen von Eigenschaften Bezeichnungen

Sie können jeder Beschriftung eine Source-Eigenschaft zuweisen, indem Sie in einem Menü mit Optionen auswählen. Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaften Bezeichnungen verbessern die Suchrelevanz und stellen genauere Suchergebnisse für Endbenutzer sicher.

## <a name="manage-schema"></a>Schema verwalten

Auf dem Bildschirm " **Schema verwalten** " haben Sie die Möglichkeit, die den Eigenschaften zugeordneten Schema **Attribute (** abfragbar, **durchsuchbar**, **abrufbar** und **verfeinernd**) zu ändern, optionale Aliase hinzuzufügen und die **Content** -Eigenschaft auszuwählen.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans

Der ServiceNow-Connector unterstützt Aktualisierungs Zeitpläne für vollständige und inkrementelle Crawls. Es wird empfohlen, beides festzulegen.

Ein vollständiger durchforstungszeitplan findet gelöschte Artikel, die zuvor mit dem Microsoft-Suchindex synchronisiert wurden, sowie alle Artikel, die aus dem Synchronisierungsfilter verschoben wurden. Wenn Sie zum ersten Mal eine Verbindung mit ServiceNow herstellen, wird eine vollständige Durchforstung ausgeführt, um alle Knowledge Base-Artikel zu synchronisieren. Sie müssen inkrementelle Crawls planen, um neue Elemente zu synchronisieren und Aktualisierungen vorzunehmen.

Der empfohlene Standardwert ist ein Tag für eine vollständige Durchforstung und vier Stunden für eine inkrementelle Durchforstung.
>[!NOTE]
>Für Identitäten wird nur die vollständige Durchforstung geplant angewendet.

## <a name="review-and-publish"></a>Überprüfen und veröffentlichen

Nachdem Sie den Connector konfiguriert haben, können Sie die Verbindung überprüfen und veröffentlichen.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Verbindung veröffentlicht haben, müssen Sie die Suchergebnisseite anpassen. Informationen zum Anpassen von Suchergebnissen finden Sie unter [Anpassen der Suchergebnisseite](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).