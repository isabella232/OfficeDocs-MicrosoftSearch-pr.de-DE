---
title: Salesforce Graph Connector für Microsoft Search
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
description: Einrichten des Salesforce Graph-Connectors für Microsoft Search
ms.openlocfilehash: 86140a4650593e08188f171be54f1753b73ecf7a
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508823"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a>Salesforce Graph Connector (Vorschau)

Der Salesforce Graph-Connector ermöglicht Ihrer Organisation das Indizieren von Contacts-, Opportunities-, Leads- und Accounts-Objekten in Ihrer Salesforce-Instanz. Nachdem Sie den Connector und den Indexinhalt aus Salesforce konfiguriert haben, können Endbenutzer in jedem Microsoft Search-Client nach diesen Elementen suchen.

> [!NOTE]
> Lesen Sie [**den Artikel Setup für Ihren Graph-Connector,**](configure-connector.md) um die allgemeinen Anweisungen zum Einrichten von Graph Connectors zu verstehen.

Dieser Artikel ist für alle Benutzer verfügbar, die einen Salesforce Graph-Connector konfigurieren, ausgeführt und überwachen. Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Salesforce Graph-Connector gelten. Dieser Artikel enthält auch Informationen zu [Einschränkungen](#limitations).

>[!IMPORTANT]
>Der Salesforce Graph-Connector unterstützt derzeit Sommer '19 oder höher.

## <a name="before-you-get-started"></a>Bevor Sie beginnen

Zum Herstellen einer Verbindung mit Ihrer Salesforce-Instanz benötigen Sie die Salesforce-Instanz-URL, die Client-ID und den geheimen Client für die OAuth-Authentifizierung. In den folgenden Schritten wird erläutert, wie Sie oder Ihr Salesforce-Administrator diese Informationen aus Ihrem Salesforce-Konto erhalten können:

- Melden Sie sich bei Ihrer Salesforce-Instanz an, und wechseln Sie zu Setup

- Navigieren Sie zu Apps -> App Manager.

- Wählen **Sie Neue verbundene App aus.**

- Führen Sie den Abschnitt API wie folgt aus:

    - Aktivieren Sie das Kontrollkästchen **Oauth-Einstellungen aktivieren.**

    - Geben Sie die Rückruf-URL wie folgt an: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)

    - Wählen Sie diese erforderlichen OAuth-Bereiche aus.

        - Zugreifen und Verwalten Ihrer Daten (API)

        - Durchführen von Anforderungen in Ihrem Namen jederzeit (refresh_token, offline_access)

    - Aktivieren Sie das Kontrollkästchen Schlüssel **für Webserverfluss erforderlich.**

    - Speichern Sie die App.
    
      > [!div class="mx-imgBorder"]
      > ![API-Abschnitt in der Salesforce-Instanz, nachdem der Administrator alle oben aufgeführten erforderlichen Konfigurationen eingegeben hat.](media/salesforce-connector/sf1.png)

- Kopieren Sie den Verbraucherschlüssel und den Verbraucherschlüssel. Diese Informationen werden als Client-ID und geheimer Clientgeheimnis verwendet, wenn Sie die Verbindungseinstellungen für Ihren Graph Connector im Microsoft 365-Verwaltungsportal konfigurieren.

  > [!div class="mx-imgBorder"]
  > ![Ergebnisse, die vom API-Abschnitt in der Salesforce-Instanz zurückgegeben werden, nachdem der Administrator alle erforderlichen Konfigurationen übermittelt hat. Der Verbraucherschlüssel befindet sich oben in der linken Spalte, und der Geheime Verbraucherschlüssel befindet sich oben in der rechten Spalte.](media/salesforce-connector/clientsecret.png)
  
- Führen Sie vor dem Schließen Ihrer Salesforce-Instanz die folgenden Schritte aus, um sicherzustellen, dass Aktualisierungstoken nicht ablaufen:
    - Wechseln sie zu Apps -> App Manager
    - Suchen Sie die app, die Sie erstellt haben, und wählen Sie die Dropdownliste auf der rechten Seite aus. Wählen Sie **Verwalten aus**
    - Auswählen **von Bearbeitungsrichtlinien**
    - Wählen Sie für aktualisierungstokenrichtlinie die Option **Aktualisierungstoken ist gültig, bis sie widerrufen wurde.**

  > [!div class="mx-imgBorder"]
  > ![Wählen Sie die Aktualisierungstokenrichtlinie mit dem Namen "Aktualisierungstoken ist gültig, bis widerrufen" aus.](media/salesforce-connector/oauthpolicies.png)

Sie können nun das [M365 Admin Center](https://admin.microsoft.com/) verwenden, um den restlichen Setupvorgang für Ihren Graph-Connector abzuschließen.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center

Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Verwenden Sie für die Instanz-URL https://[domain].my.salesforce.com, wobei Domäne die #A0 für Ihre Organisation wäre.

Geben Sie die Client-ID und den geheimen Clientgeheimnis ein, die Sie von Ihrer Salesforce-Instanz erhalten haben, und wählen Sie Anmelden aus.

Wenn Sie sich zum ersten Mal mit diesen Einstellungen anmelden möchten, erhalten Sie ein Popup, in dem Sie aufgefordert werden, sich mit Ihrem Administratorbenutzernamen und Kennwort bei Salesforce zu anmelden. Der folgende Screenshot zeigt das Popup. Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie "Anmelden" aus.

  ![Login pop up asking for Username and password.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  >Wenn das Popup nicht angezeigt wird, wird es möglicherweise in Ihrem Browser blockiert, sodass Sie Popups und Umleitungen zulassen müssen.

Überprüfen Sie, ob die Verbindung erfolgreich war, indem Sie nach einem grünen Banner suchen, das "Verbindung erfolgreich" heißt, wie im screenshot unten gezeigt.

  > [!div class="mx-imgBorder"]
  > ![Screenshot der erfolgreichen Anmeldung. Das grüne Banner mit dem Namen "Verbindung erfolgreich" befindet sich unter dem Feld für Ihre Salesforce-Instanz-URL.](media/salesforce-connector/sf5.png)

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen

Sie müssen auswählen, welche Benutzer Suchergebnisse aus dieser Datenquelle sehen. Wenn Sie nur bestimmten Azure Active Directory (Azure AD) oder Nicht-Azure AD-Benutzern erlauben, die Suchergebnisse anzuzeigen, stellen Sie sicher, dass Sie die Identitäten zuordnungen.

## <a name="step-4a-select-permissions"></a>Schritt 4a: Auswählen von Berechtigungen

Sie können zugriffssteuerungslisten (Access Control Lists, ACLs) aus Ihrer Salesforce-Instanz ingesten oder jedem Benutzer in Ihrer Organisation erlauben, Suchergebnisse aus dieser Datenquelle zu sehen. AcLs können Azure Active Directory (AAD)-Identitäten (Benutzer, die von Azure AD zu Salesforce partneriert sind), Nicht-Azure AD-Identitäten (systemeigene Salesforce-Benutzer, die über entsprechende Identitäten in Azure AD verfügen) oder beides umfassen.

>[!NOTE]
>Wenn Sie einen Identitätsanbieter eines Drittanbieters wie Ping ID oder secureAuth verwenden, sollten Sie "Nicht-AAD" als Identitätstyp auswählen.

> [!div class="mx-imgBorder"]
> ![Wählen Sie den Berechtigungsbildschirm aus, der von einem Administrator abgeschlossen wurde. Der Administrator hat die Option "Nur Personen mit Zugriff auf diese Datenquelle" ausgewählt und auch "AAD" aus einem Dropdownmenü mit Identitätstypen ausgewählt.](media/salesforce-connector/sf6.png)

Wenn Sie eine ACL aus Ihrer Salesforce-Instanz aufgenommen und "Nicht-AAD" für den Identitätstyp ausgewählt haben, finden Sie unter [Map your non-Azure AD Identities](map-non-aad.md) Anweisungen zum Zuordnen der Identitäten.

## <a name="step-4b-map-aad-identities"></a>Schritt 4b: Zuordnung von AAD-Identitäten

Wenn Sie eine ACL aus Ihrer Salesforce-Instanz aufgenommen und "AAD" für den Identitätstyp ausgewählt haben, finden Sie unter [Map your Azure AD Identities](map-aad.md) Anweisungen zum Zuordnen der Identitäten. Informationen zum Einrichten von Azure AD SSO für Salesforce finden Sie in diesem [Lernprogramm](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial).

## <a name="step-5-assign-property-labels"></a>Schritt 5: Zuweisen von Eigenschaftsbezeichnungen

Sie können jeder Bezeichnung eine Quelleigenschaft zuweisen, indem Sie aus einem Menü mit Optionen auswählen. Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaftsbezeichnungen verbessern die Suchrelevanz und sorgen für bessere Suchergebnisse für Endbenutzer. Standardmäßig wurden einigen Bezeichnungen wie "Title", "URL", "CreatedBy" und "LastModifiedBy" bereits Quelleigenschaften zugewiesen.

## <a name="step-6-manage-schema"></a>Schritt 6: Verwalten des Schemas

Sie können auswählen, welche Quelleigenschaften indiziert werden sollen, damit sie in den Suchergebnissen angezeigt werden. Der Verbindungs-Assistent wählt standardmäßig ein Suchschema basierend auf einer Reihe von Quelleigenschaften aus. Sie können dies ändern, indem Sie die Kontrollkästchen für jede Eigenschaft und jedes Attribut auf der Suchschemaseite aktivieren. Suchschemaattribute sind Search, Query, Retrieve und Refine.
Mit Einschränkungen können Sie die Eigenschaften definieren, die später als benutzerdefinierte Einschränkungen oder Filter in der Sucherfahrung verwendet werden können.  

> [!div class="mx-imgBorder"]
> ![Wählen Sie das Schema für jede Quelleigenschaft aus. Die Optionen sind Query, Search, Retrieve und Refine.](media/salesforce-connector/sf9.png)

## <a name="step-7-set-the-refresh-schedule"></a>Schritt 7: Festlegen des Aktualisierungszeitplans

Der Salesforce-Connector unterstützt derzeit nur Aktualisierungszeitpläne für vollständige Durchforstungen.

>[!IMPORTANT]
>Bei einer vollständigen Durchforstung werden gelöschte Objekte und Benutzer gefunden, die zuvor mit dem Microsoft Search-Index synchronisiert wurden.

Der empfohlene Zeitplan ist eine Woche für eine vollständige Durchforstung.

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Einschränkungen

- Der Graph-Connector unterstützt derzeit keine Apex-basierte, gebietsbasierte Freigabe und Freigabe mithilfe persönlicher Gruppen aus Salesforce.
- Es gibt einen bekannten Fehler in der Salesforce-API, die der Graph-Connector verwendet, wobei die privaten organisationsweiten Standardwerte für Leads derzeit nicht berücksichtigt werden.  
- Wenn für ein Feld die Sicherheit auf Feldebene (Field Level Security, FLS) für ein Profil festgelegt ist, wird dieses Feld vom Graph-Connector nicht für Profile in dieser Salesforce-Organisation aufgenommen. Daher können Benutzer nicht nach Werten für diese Felder suchen, und sie werden auch nicht in den Ergebnissen angezeigt.  
- Im Bildschirm Schema verwalten werden diese allgemeinen Standardeigenschaftsnamen einmal aufgelistet, die Optionen **sind Query,** **Search,** **Retrieve** und **Refine** und gelten für alle oder keine.
    - Name
    - Url
    - Beschreibung
    - Fax
    - Phone
    - MobilePhone
    - E-Mail senden
    - Typ
    - Titel
    - AccountId
    - AccountName
    - AccountUrl
    - AccountOwner
    - AccountOwnerUrl
    - Besitzer
    - OwnerUrl
    - CreatedBy
    - CreatedByUrl
    - LastModifiedBy
    - LastModifiedByUrl
    - LastModifiedDate
    - ObjectName
