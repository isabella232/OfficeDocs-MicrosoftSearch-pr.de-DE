---
title: Confluence Cloud Graph Connector für Microsoft Search
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Confluence Cloud Graph-Connectors für Microsoft Search
ms.openlocfilehash: baf6139257c8bf8e40bc997e2a408efb4fc2549f
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973444"
---
<!---Previous ms.author: kam1 --->

# <a name="confluence-cloud-graph-connector-preview"></a>Confluence Cloud Graph Connector (Vorschau)

Confluence Cloud Graph Connector ermöglicht Es Ihrer Organisation, Confluence-Inhalte zu indizieren. Nachdem Sie den Connector und die Indexdaten von der Confluence-Website konfiguriert haben, können Endbenutzer in Microsoft Search nach diesen Inhalten suchen.

>[!NOTE]
>Confluence Cloud Graph Connector befindet sich in der Vorschau. Wenn Sie frühzeitigen Zugriff erhalten möchten, um es auszuprobieren, registrieren Sie sich mit [<b>diesem Formular. </b>](https://forms.office.com/r/duLxv8Nf8U)  

Dieser Artikel richtet sich an Microsoft 365 Administratoren oder alle Personen, die einen Confluence Cloud Graph Connector konfigurieren, ausführen und überwachen. Er ergänzt die allgemeinen Anweisungen im Artikel ["Einrichten Ihres Graph Connectors".](configure-connector.md) Wenn Sie dies noch nicht getan haben, lesen Sie den gesamten Artikel zum Einrichten ihres Graph Connectors, um den allgemeinen Einrichtungsprozess zu verstehen.

Jeder Schritt im Setupprozess wird unten zusammen mit einem Hinweis aufgeführt, der angibt, dass Sie die allgemeinen Setupanweisungen oder andere Anweisungen befolgen sollten, die nur für Confluence Cloud Graph Connector gelten, einschließlich Informationen zur [Problembehandlung](#troubleshooting) und [Einschränkungen.](#limitations)


## <a name="before-you-get-started"></a>Bevor Sie beginnen
Sie müssen der Administrator für den M365-Mandanten Ihrer Organisation sowie der Administrator für die Confluence-Website Ihrer Organisation sein.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph Connectors im Microsoft 365 Admin Center
Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung
Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen
Verwenden Sie ihre Website-URL, um eine Verbindung mit Ihrer Confluence-Website herzustellen. Die URL einer Confluence-Cloudwebsite sieht in der Regel wie *https://<organization_name>.atlassian.net/* aus. Sie können entweder Standardauthentifizierung oder OAuth 2.0 (empfohlen) auswählen, um sich bei Ihrer Confluence-Website zu authentifizieren.

### <a name="basic-auth"></a>Standardauthentifizierung
Geben Sie den Benutzernamen Ihres Kontos (in der Regel E-Mail-ID) und das API-Token ein, um sich mit der einfachen Authentifizierung zu authentifizieren. Weitere Informationen zum Generieren eines API-Tokens finden Sie in der Dokumentation von Atlassian zum [Verwalten von API-Token für Ihr Atlassian-Konto.](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

### <a name="oauth-20"></a>OAuth 2.0
Registrieren Sie eine App in der Confluence Cloud, damit die Microsoft Search-App auf die Instanz zugreifen kann. Weitere Informationen finden Sie in der Dokumentation zum Atlassian-Support zum Aktivieren von [OAuth 2.0.](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)

Die folgenden Schritte enthalten Anleitungen zum Registrieren der App:

1. Melden Sie sich mit Ihrem Atlassian Confluence-Administratorkonto bei [der Atlassian Developer-Konsole](https://developer.atlassian.com/console/myapps/) an.
2. Klicken Sie auf `Create` und wählen Sie `OAuth 2.0 integration`
3. Geben Sie einen geeigneten Namen für die Anwendung an, und erstellen Sie die neue App.
4. Navigieren Sie `Permissions` vom Navigationsbereich auf der linken Seite zu. Klicken Sie `Add` auf `Confluence API` für . Klicken Sie nach dem Hinzufügen auf die folgenden Bereiche , , , , und fügen Sie sie `Configure` `Read Confluence space summary` `Read Confluence content properties` `Read Confluence detailed content` `Read Confluence content summary` `Read content permission in Confluence` `Read user` `Read user groups` `Search Confluence content and space summaries` hinzu.
5. Navigieren Sie `Authorization` vom Navigationsbereich auf der linken Seite zu. Fügen Sie die Rückruf-URL `https://gcs.office.com/v1.0/admin/oauth/callback` hinzu, und speichern Sie die Änderungen.
6. Navigieren Sie `Settings` vom Navigationsbereich auf der linken Seite zu. Sie erhalten das `Client ID` und `Secret` von dieser Seite.

Beim Registrieren der App mit den oben genannten Details erhalten Sie die **Client-ID** und den **geheimen Schlüssel.** Führen Sie den Schritt mit den Verbindungseinstellungen mithilfe dieser Schritte aus.

## <a name="step-4-select-properties-and-filter-data"></a>Schritt 4: Auswählen von Eigenschaften und Filtern von Daten

In diesem Schritt können Sie der Confluence-Datenquelle verfügbare Eigenschaften hinzufügen oder daraus entfernen. Microsoft 365 einige Eigenschaften standardmäßig bereits ausgewählt hat.

Mit einer CQL-Zeichenfolge (Confluence Query Language) können Sie Bedingungen für die Synchronisierung von Seiten angeben. Es ist wie eine **Where-Klausel** in einer **SQL Select-Anweisung.** Sie können z. B. nur die Seiten indizieren, die in den letzten zwei Jahren geändert wurden. Informationen zum Erstellen einer eigenen Abfragezeichenfolge finden Sie unter ["Erweiterte Suche mit CQL".](https://developer.atlassian.com/server/confluence/advanced-searching-using-cql/) Standardmäßig werden alle Blogs und Seiten vom Connector indiziert.

Verwenden Sie die Schaltfläche "Vorschauergebnisse", um die Beispielwerte der ausgewählten Eigenschaften und der CQL-Zeichenfolge zu überprüfen.

## <a name="step-5-manage-search-permissions"></a>Schritt 5: Verwalten von Suchberechtigungen

Confluence Cloud Graph Connector unterstützt Suchberechtigungen, die für  **alle** oder **nur Personen mit Zugriff auf diese Datenquelle** sichtbar sind. Wenn Sie **"Jeder"** auswählen, werden indizierte Daten in den Suchergebnissen für alle Benutzer angezeigt. Wenn Sie **nur Personen mit Zugriff auf diese Datenquelle** auswählen, werden indizierte Daten in den Suchergebnissen für Benutzer angezeigt, die Zugriff darauf haben.

In confluence Cloud werden Sicherheitsberechtigungen für Benutzer und Gruppen mithilfe von Platzberechtigungen und Seiteneinschränkungen definiert. Confluence Cloud Graph Connector wendet Platzberechtigungen an, wenn keine Seiteneinschränkungen bestehen. Einschränkungen auf Seitenebene haben, sofern vorhanden, Vorrang vor Platzberechtigungen.

Wenn Sie **nur Personen mit Zugriff auf diese Datenquelle** auswählen, müssen Sie weiter auswählen, ob Ihre Confluence-Website über Azure Active Directory (AAD) bereitgestellte Benutzer oder Nicht-AAD-Benutzer verfügt.

So ermitteln Sie, welche Option für Ihre Organisation geeignet ist:

1. Wählen Sie die **AAD-Option** aus, wenn die E-Mail-ID von Confluence-Benutzern mit dem UserPrincipalName (UPN) von Benutzern in AAD **identisch** ist.
2. Wählen Sie die **Option "Nicht-AAD",** wenn sich die E-Mail-ID von "Confluence"-Benutzern vom UserPrincipalName (UPN) der Benutzer in AAD **unterscheidet.** 

>[!NOTE]
> * Wenn Sie AAD als Typ der Identitätsquelle auswählen, ordnet der Connector die E-Mail-IDs von Benutzern, die von Confluence abgerufen wurden, direkt der UPN-Eigenschaft von AAD zu.
> * Wenn Sie "Nicht-AAD" für den Identitätstyp ausgewählt haben, finden Sie unter ["Zuordnen Ihrer Nicht-Azure AD-Identitäten"](map-non-aad.md) Anweisungen zum Zuordnen der Identitäten. Sie können diese Option verwenden, um den regulären Zuordnungsausdruck von der E-Mail-ID zum UPN bereitzustellen.

## <a name="step-6-assign-property-labels"></a>Schritt 6: Zuweisen von Eigenschaftenbeschriftungen

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

## <a name="step-7-manage-schema"></a>Schritt 7: Verwalten des Schemas

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

## <a name="step-8-choose-refresh-settings"></a>Schritt 8: Auswählen von Aktualisierungseinstellungen

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

>[!NOTE]
>Für Zugriffsberechtigungsupdates wird nur die geplante vollständige Durchforstung angewendet.

## <a name="step-9-review-connection"></a>Schritt 9: Überprüfen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

Nach der Veröffentlichung der Verbindung müssen Sie die Suchergebnisseite anpassen. Informationen zum Anpassen von Suchergebnissen finden Sie unter [Anpassen der Suchergebnisseite.](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)

## <a name="troubleshooting"></a>Problembehandlung
Darunter finden Sie eine Liste der häufigsten Fehler, die beim Konfigurieren des Connectors auftreten, und deren mögliche Ursachen.

| Konfigurationsschritt | Fehlermeldung | Mögliche Gründe |
| ------------ | ------------ | ------------ |
| Verbindungseinstellungen | Die Anforderung ist fehlerhaft oder falsch. | Falsche Url der Confluence-Website |
| Verbindungseinstellungen | Der Confluence-Clouddienst für Ihre Confluence-Website kann nicht erreicht werden. | Falsche Url der Confluence-Website |
| Verbindungseinstellungen | Der Client verfügt nicht über die Berechtigung zum Ausführen der Aktion. | Ungültiges API-Token, das für die Standardauthentifizierung bereitgestellt wird |
| Auswählen von Eigenschaften | Keine Fehlermeldung und keine Vorschauergebnisse | Überprüfen Ihrer CQL-Abfrage, ob sie gültig ist |

## <a name="limitations"></a>Einschränkungen
Confluence Cloud Graph Connector weist die folgenden bekannten Einschränkungen in seiner neuesten Version auf:

- Confluence Cloud Connector indiziert keine Anlagendateien und Kommentare.
- Bereitstellungen von Indizierungsservern und Rechenzentren werden als separater Connector freigegeben.