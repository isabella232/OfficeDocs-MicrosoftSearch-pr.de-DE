---
title: Atlassian Jira Graph Connector für Microsoft Search
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
description: Einrichten des Atlassian Jira Graph Connectors für Microsoft Search
ms.openlocfilehash: 0b4b1dc0ed1f9e9d3ca57f98dc3878f63e68d510
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973778"
---
# <a name="atlassian-jira-graph-connector-preview"></a>Atlassian Jira Graph Connector (Vorschau)

Der Atlassian Jira Graph Connector ermöglicht Es Ihrer Organisation, Jira-Probleme zu indizieren. Nachdem Sie den Connector und den Indexinhalt von der Jira-Website konfiguriert haben, können Endbenutzer in Microsoft Search nach diesen Elementen suchen.

> [!NOTE]
> Lesen Sie den Artikel [**"Setup for your Graph connector",**](configure-connector.md) um die allgemeinen Anweisungen zum Einrichten Graph Connectors zu verstehen.

Dieser Artikel richtet sich an alle Personen, die einen Atlassian Jira Graph Connector konfigurieren, ausführen und überwachen. Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Atlassian Jira Graph Connector gelten.

>[!IMPORTANT]
>Der Atlassian Jira Graph Connector unterstützt nur in der Jira-Cloud gehostete Instanzen. Jira Server- und Jira Data Center-Versionen werden von diesem Connector nicht unterstützt.

## <a name="before-you-get-started"></a>Bevor Sie beginnen
Sie müssen der Administrator für den M365-Mandanten Ihrer Organisation sowie der Administrator für die Jira-Website Ihrer Organisation sein.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph Connectors im Microsoft 365 Admin Center
Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung
Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen
Um eine Verbindung mit Ihrer Jira-Website herzustellen, verwenden Sie die URL Ihrer Jira-Website. Eine URL einer Jira-Cloudwebsite sieht in der Regel wie *https://<organization_name>.atlassian.net/* aus. Sie können entweder Standardauthentifizierung oder OAuth 2.0 (empfohlen) auswählen, um sich bei Ihrer Jira-Website zu authentifizieren.

### <a name="basic-auth"></a>Standardauthentifizierung
Geben Sie den Benutzernamen Ihres Kontos (in der Regel E-Mail-ID) und das API-Token ein, um sich mit der einfachen Authentifizierung zu authentifizieren. Weitere Informationen zum Generieren eines API-Tokens finden Sie in der Dokumentation von Atlassian zum [Verwalten von API-Token für Ihr Atlassian-Konto.](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

### <a name="oauth-20"></a>OAuth 2.0
Registrieren Sie eine App in Atlassian Jira, damit die Microsoft Search App auf die Instanz zugreifen kann. Weitere Informationen finden Sie in der Dokumentation zum Atlassian-Support zum Aktivieren von [OAuth 2.0.](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)

Die folgenden Schritte enthalten Anleitungen zum Registrieren der App:

1. Melden Sie sich mit Ihrem Atlassian Jira-Administratorkonto bei [der Atlassian Developer-Konsole](https://developer.atlassian.com/console/myapps/) an.
2. Klicken Sie auf `Create` und wählen Sie `OAuth 2.0 integration`
3. Geben Sie einen geeigneten Namen für die Anwendung an, und erstellen Sie die neue App.
4. Navigieren Sie `Permissions` vom Navigationsbereich auf der linken Seite zu. Klicken Sie `Add` auf `Jira platform REST API` für . Klicken Sie nach dem Hinzufügen auf `Configure` die folgenden Bereiche – und fügen Sie sie `View Jira issue data` `Manage Jira global settings` `View user profiles` hinzu.
5. Navigieren Sie `Authorization` vom Navigationsbereich auf der linken Seite zu. Fügen Sie die Rückruf-URL `https://gcs.office.com/v1.0/admin/oauth/callback` hinzu, und speichern Sie die Änderungen.
6. Navigieren Sie `Settings` vom Navigationsbereich auf der linken Seite zu. Sie erhalten das `Client ID` und `Secret` von dieser Seite.

Beim Registrieren der App mit den oben genannten Details erhalten Sie die **Client-ID** und den **geheimen Schlüssel.** Führen Sie den Schritt mit den Verbindungseinstellungen mithilfe dieser Schritte aus.

### <a name="step-3a-configure-data-select-projects"></a>Schritt 3a: Konfigurieren von Daten: Auswählen von Projekten

Sie können auswählen, ob die Verbindung entweder die gesamte Jira-Website oder nur bestimmte Projekte indiziert.

* Wenn Sie die gesamte Jira-Website indizieren möchten, werden Jira-Probleme in allen Projekten auf der Website indiziert. Neue Projekte und Probleme werden während der nächsten Durchforstung indiziert, nachdem sie erstellt wurden.
* Wenn Sie einzelne Projekte auswählen, werden nur Jira-Probleme in diesen Projekten indiziert.

Sie können die Jira-Probleme weiter filtern, die auf zwei Arten indiziert werden.
* Geben Sie den Zeitraum für die **Änderung des Problems an.** Dadurch werden nur die Jira-Probleme indiziert, die in dem auf der aktuellen Durchforstung **basierenden** fortlaufend ausgewählten Zeitraum erstellt oder geändert werden.
* Geben Sie **JQL** an. Dadurch werden nur die Jira-Probleme indiziert, die nach der Filterung basierend auf der bereitgestellten Jira Query Language (JQL) zurückgegeben werden. Weitere Informationen zur Verwendung von JQL finden Sie in der Dokumentation zum Atlassian-Support zur [Verwendung der erweiterten Suche mit Jira Query Language](https://support.atlassian.com/jira-service-management-cloud/docs/use-advanced-search-with-jira-query-language-jql/)

> [!TIP]
> Sie können den JQL-Filter verwenden, um nur bestimmte Jira-Problemtypen mithilfe von "*issueType in (Bug, Improvement)*" zu indizieren.

### <a name="step-3b-configure-data-select-properties"></a>Schritt 3b: Konfigurieren von Daten: Auswählen von Eigenschaften

Wählen Sie aus, welche Felder die Verbindung zum Indizierungs- und Vorschaudaten in diesen Feldern verwenden soll, bevor Sie fortfahren. Einige Felder sind bereits standardmäßig ausgewählt und können nicht entfernt werden.

Der Atlassian Jira Graph Connector kann sowohl Standardproblemfelder als auch benutzerdefinierte erstellte Problemfelder indiziert.

> [!NOTE]
> Wenn ein ausgewähltes benutzerdefiniertes erstelltes Feld in einigen Jira-Problemtypen nicht vorhanden ist, wird das Feld als *NULL* (leer) aufgenommen.

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen

Der Atlassian Jira Graph Connector unterstützt Suchberechtigungen, die  **für alle** oder **nur Personen mit Zugriff auf diese Datenquelle** sichtbar sind. Wenn Sie **"Jeder"** auswählen, werden indizierte Daten in den Suchergebnissen für alle Benutzer angezeigt. Wenn Sie **nur Personen mit Zugriff auf diese Datenquelle** auswählen, werden indizierte Daten in den Suchergebnissen für Benutzer angezeigt, die Zugriff darauf haben. In Atlassian Jira werden Sicherheitsberechtigungen mithilfe von Projektberechtigungsschemas definiert, die Gruppen auf Websiteebene und Projektrollen enthalten. Die Sicherheit auf Problemebene kann auch mithilfe von Berechtigungsschemas auf Problemebene definiert werden.

Wenn Sie **nur Personen mit Zugriff auf diese Datenquelle** auswählen, müssen Sie weiter auswählen, ob Ihre Jira-Website über Azure Active Directory (AAD) bereitgestellte Benutzer oder Nicht-AAD-Benutzer verfügt.

So ermitteln Sie, welche Option für Ihre Organisation geeignet ist:

1. Wählen Sie die **AAD-Option** aus, wenn die E-Mail-ID von Jira-Benutzern mit dem UserPrincipalName (UPN) von Benutzern in AAD **identisch** ist.
2. Wählen Sie die **Option "Nicht-AAD",** wenn sich die E-Mail-ID von Jira-Benutzern vom UserPrincipalName (UPN) der Benutzer in AAD **unterscheidet.** 

>[!NOTE]
> * Wenn Sie AAD als Typ der Identitätsquelle auswählen, ordnet der Connector die E-Mail-IDs von Benutzern, die von Jira abgerufen wurden, direkt der UPN-Eigenschaft von AAD zu.
> * Wenn Sie "Nicht-AAD" für den Identitätstyp ausgewählt haben, finden Sie unter ["Zuordnen Ihrer Nicht-Azure AD-Identitäten"](map-non-aad.md) Anweisungen zum Zuordnen der Identitäten. Sie können diese Option verwenden, um den regulären Zuordnungsausdruck von der E-Mail-ID zum UPN bereitzustellen.

## <a name="step-5-assign-property-labels"></a>Schritt 5: Zuweisen von Eigenschaftenbeschriftungen

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

## <a name="step-6-manage-schema"></a>Schritt 6: Verwalten des Schemas

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

## <a name="step-7-choose-refresh-settings"></a>Schritt 7: Auswählen von Aktualisierungseinstellungen

Der Atlassian Jira Graph Connector unterstützt Aktualisierungszeitpläne für vollständige und inkrementelle Durchforstungen.
Der empfohlene Zeitplan ist eine Stunde für eine inkrementelle Durchforstung und ein Tag für eine vollständige Durchforstung.

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

## <a name="troubleshooting"></a>Problembehandlung
Darunter finden Sie eine Liste der häufigsten Fehler, die beim Konfigurieren des Connectors auftreten, und deren mögliche Ursachen.

| Konfigurationsschritt | Fehlermeldung | Mögliche Gründe |
| ------------ | ------------ | ------------ |
| Verbindungseinstellungen | Die Anforderung ist fehlerhaft oder falsch. | Falsche URL der Jira-Website |
| Verbindungseinstellungen | Der Jira-Clouddienst für Ihre Jira-Website kann nicht erreicht werden. | Falsche URL der Jira-Website |
| Verbindungseinstellungen | Der Client verfügt nicht über die Berechtigung zum Ausführen der Aktion. | Ungültiges API-Token, das für die Standardauthentifizierung bereitgestellt wird |


## <a name="limitations"></a>Einschränkungen
Es folgen bekannte Einschränkungen des Atlassian Jira Graph Connectors:
* Jira Server- und Data Center-Versionen werden nicht unterstützt.