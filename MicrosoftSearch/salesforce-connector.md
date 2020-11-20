---
title: Salesforce Connector für Microsoft Search
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten von Salesforce Connector für Microsoft Search
ms.openlocfilehash: 149d1d9a297e09e9b895aeb0947c7ff4a3cbdf84
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367649"
---
# <a name="salesforce-connector-preview"></a>Salesforce Connector (Vorschau)

Mit dem Salesforce Graph-Konnektor kann Ihre Organisation Kontakte, Verkaufschancen, Leads und Accounts-Objekte in ihrer Salesforce-Instanz indizieren. Nachdem Sie den Connector-und den Index Inhalt von Salesforce konfiguriert haben, können Endbenutzer nach diesen Elementen von einem beliebigen Microsoft Search-Client aus suchen.

Dieser Artikel richtet sich an [Microsoft 365](https://www.microsoft.com/microsoft-365) -Administratoren oder Personen, die einen Salesforce Connector konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.

>[!IMPORTANT]
>Der Salesforce Graph Connector unterstützt derzeit Sommer ' 19 oder höher.

## <a name="connection-settings"></a>Verbindungseinstellungen

Zum Herstellen einer Verbindung mit ihrer Salesforce-Instanz benötigen Sie die Salesforce-Instanz-URL, die Client-ID und den geheimen Client Schlüssel für die OAuth-Authentifizierung. In den folgenden Schritten wird erklärt, wie Sie oder Ihr Salesforce-Administrator diese Informationen von Ihrem Salesforce-Konto abrufen können:

- Melden Sie sich bei ihrer Salesforce-Instanz an, und wechseln Sie zu Setup

- Navigieren Sie zu apps-> App-Manager.

- Wählen Sie **neue verbundene App** aus.

- Schließen Sie den API-Abschnitt wie folgt ab:

    - Aktivieren Sie das Kontrollkästchen für **OAuth-Einstellungen aktivieren**.

    - Geben Sie die Rückruf-URL wie folgt an: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)

    - Wählen Sie diese erforderlichen OAuth-Bereiche aus. 

        - Zugreifen auf und Verwalten von Daten (API) 

        - Ausführen von Anforderungen in Ihrem Namen zu einem beliebigen Zeitpunkt (refresh_token, offline_access) 

    - Aktivieren Sie das Kontrollkästchen für **geheimen Webserver Fluss erforderlich**.

    - Speichern Sie die app.
    
      ![API-Abschnitt in Salesforce instance, nachdem Administrator alle oben aufgeführten erforderlichen Konfigurationen eingegeben hat.](media/salesforce-connector/sf1.png)

- Kopieren Sie den Consumer-Schlüssel und das Consumer-Geheimnis. Diese werden als Client-ID und den geheimen Client Schlüssel verwendet, wenn Sie die Verbindungseinstellungen für Ihren Graph-Konnektor im Microsoft 365-Verwaltungsportal konfigurieren.

  ![Vom API-Abschnitt zurückgegebene Ergebnisse in der Salesforce-Instanz, nachdem der Administrator alle erforderlichen Konfigurationen übermittelt hat. Consumer Key befindet sich oben in der linken Spalte, und Consumer Secret befindet sich oben rechts in der Spalte.](media/salesforce-connector/clientsecret.png)
- Führen Sie vor dem Schließen der Salesforce-Instanz die folgenden Schritte aus, um sicherzustellen, dass Aktualisierungstoken nicht ablaufen:
    - Wechseln Sie zu apps-> App-Manager
    - Suchen Sie die soeben erstellte APP, und wählen Sie die Dropdownliste rechts aus. Wählen Sie **Verwalten** aus.
    - Auswählen von **Richtlinien bearbeiten**
    - Wählen Sie für Aktualisierungstoken-Richtlinie **die Option Aktualisierungstoken gilt bis zum Widerruf** aus.

  ![Wählen Sie die Aktualisierungstoken-Richtlinie mit dem Namen "Aktualisierungstoken ist gültig bis Widerruf" aus.](media/salesforce-connector/oauthpolicies.png)

Sie können jetzt das [M365 Admin Center](https://admin.microsoft.com/) verwenden, um den restlichen Setupvorgang für Ihren Graph-Konnektor abzuschließen.  

Konfigurieren Sie die Verbindungseinstellungen für Ihren Graph-Konnektor wie folgt:

- Verwenden Sie für die Instanz-URL https://[Domäne]. My. salesforce. com, wobei Domäne die Salesforce-Domäne für Ihre Organisation wäre. 
- Geben Sie die von ihrer Salesforce-Instanz abgerufene Client-ID und den geheimen Client Schlüssel ein, und wählen Sie anmelden aus.
- Wenn Sie zum ersten Mal versucht haben, sich mit diesen Einstellungen anzumelden, erhalten Sie ein Popup, in dem Sie aufgefordert werden, sich mit Ihrem Administrator-Benutzernamen und-Kennwort bei Salesforce anzumelden. Das folgende Screenshot zeigt das Popup. Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie anmelden aus.

  ![Melden Sie sich an, und Fragen Sie nach Benutzername und Kennwort.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  >Wenn das Popup nicht angezeigt wird, wird es möglicherweise in Ihrem Browser blockiert, sodass Sie Popups und Umleitungen zulassen müssen.

  >[!NOTE]
  >Wenn Ihre Organisation einmaliges Anmelden (SSO) verwendet, können Sie in der unteren rechten Ecke der Anmelde Schnittstelle die Option **benutzerdefinierte Domäne verwenden** auswählen. Geben Sie die Domäne ein, und wählen Sie dann **weiter** aus. Sie wird auf Ihrer organisationsspezifischen Anmeldeseite angezeigt, auf der Sie eine Option zur Anmeldung bei SSO haben.

- Überprüfen Sie, ob die Verbindung erfolgreich war, indem Sie nach einem grünen Banner suchen, das besagt, dass die Verbindung erfolgreich verläuft, wie im Screenshot unten dargestellt.

  ![Screenshot der erfolgreichen Anmeldung. Das grüne Banner, das besagt, dass die Verbindung erfolgreich verläuft, befindet sich unter dem Feld für Ihre Salesforce-Instanz-URL.](media/salesforce-connector/sf5.png)

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen
Sie müssen auswählen, welche Benutzer Suchergebnisse aus dieser Datenquelle erhalten. Wenn Sie nur bestimmten Azure-Active Directory (Azure AD) oder nicht-Azure AD-Benutzern die Suchergebnisse anzeigen können, müssen Sie die Identitäten zuordnen.

### <a name="select-permissions"></a>Auswählen von Berechtigungen
Sie können Zugriffssteuerungslisten (Access Control Lists, ACLs) aus ihrer Salesforce-Instanz aufnehmen oder jedem in Ihrer Organisation die Möglichkeit geben, Suchergebnisse aus dieser Datenquelle anzuzeigen. ACLs können Azure Active Directory (AAD)-Identitäten (Benutzer, die von Azure AD zu Salesforce verbunden sind), nicht Azure AD Identitäten (Native Salesforce-Benutzer mit entsprechenden Identitäten in Azure AD) oder beides umfassen.

![Wählen Sie den Bildschirm Berechtigungen aus, der von einem Administrator abgeschlossen wurde. Der Administrator hat die Option "nur Personen mit Zugriff auf diese Datenquelle" ausgewählt und in einem Dropdownmenü mit Identitätstypen auch "Aad" ausgewählt.](media/salesforce-connector/sf6.png)

### <a name="map-non-aad-identities"></a>Zuordnen von nicht Aad Identitäten 
Wenn Sie eine ACL aus ihrer Salesforce-Instanz aufnehmen und "nicht-Aad" für den Identitätstyp ausgewählt haben, finden Sie Anweisungen zum Zuordnen der Identitäten unter [Zuordnen der nicht Azure AD Identitäten](map-non-aad.md) .

### <a name="map-aad-identities"></a>Zuordnen von Aad-Identitäten
Wenn Sie eine ACL aus ihrer Salesforce-Instanz aufnehmen und "Aad" für den Identitätstyp ausgewählt haben, finden Sie Anweisungen zum Zuordnen der Identitäten unter [Zuordnen der Azure AD Identitäten](map-aad.md) . Informationen zum Einrichten Azure AD SSO für Salesforce finden Sie in diesem [Lernprogramm](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/salesforce-tutorial).

## <a name="assign-property-labels"></a>Zuweisen von Eigenschaften Bezeichnungen 
Sie können jeder Beschriftung eine Source-Eigenschaft zuweisen, indem Sie in einem Menü mit Optionen auswählen. Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaften Bezeichnungen verbessern die Suchrelevanz und stellen genauere Suchergebnisse für Endbenutzer sicher. Standardmäßig wurden einigen Bezeichnungen wie "Title", "" URL "," "CreatedBy" und "LastModifiedBy" bereits Quelleigenschaften zugewiesen.

![Bildschirm Eigenschaften Bezeichnungen zuweisen mit Standard Quelleigenschaften.](media/salesforce-connector/sf8.png)

## <a name="manage-schema"></a>Verwalten des Schemas
Sie können auswählen, welche Quelleigenschaften indiziert werden sollen, damit Sie in den Suchergebnissen angezeigt werden können. Der Verbindungs-Assistent wählt standardmäßig ein Suchschema basierend auf einer Reihe von Quelleigenschaften aus. Sie können ihn ändern, indem Sie die Kontrollkästchen für jede Eigenschaft und jedes Attribut auf der Seite Suchschema aktivieren. Suchschema Attribute umfassen Suche, Abfrage, abrufen und verfeinern. Mit verfeinern können Sie die Eigenschaften definieren, die später als benutzerdefinierte Einschränkungen oder Filter in der Suchumgebung verwendet werden können.  

![Wählen Sie das Schema für jede Source-Eigenschaft aus. Die Optionen sind Abfrage, Suche, abrufen und verfeinern](media/salesforce-connector/sf9.png)

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans

Der Salesforce Connector unterstützt derzeit nur Aktualisierungs Zeitpläne für vollständige Durchforstungen.

>[!IMPORTANT]
>Bei einer vollständigen Durchforstung werden gelöschte Objekte und Benutzer gesucht, die zuvor mit dem Microsoft-Suchindex synchronisiert wurden.

Der empfohlene Zeitplan beträgt eine Woche für eine vollständige Durchforstung.

## <a name="limitations"></a>Einschränkungen

- Der Graph Connector unterstützt derzeit keine Apex-basierte, Gebiets basierte Freigabe und Freigabe mithilfe persönlicher Gruppen von salesforce.
- Es gibt einen bekannten Bug in der Salesforce-API, den der Grafik-Konnektor verwendet, wobei die privaten org Wide-Standardwerte für Leads derzeit nicht berücksichtigt werden.  
- Wenn ein Feld für ein Profil auf Field Level Security (FLS) festgelegt ist, nimmt der Graph Connector dieses Feld nicht für Profile in dieser Salesforce-Organisation auf. Benutzer können daher nicht nach Werten für diese Felder suchen, noch wird Sie in den Ergebnissen angezeigt.  
- Auf dem Bildschirm "Schema verwalten" werden diese allgemeinen Standardeigenschaften Namen einmal aufgeführt, und die Auswahl erfolgt, damit Sie abgefragt, durchsuchbar und abrufbar ist, für alle oder keine.
    - Name
    - Url 
    - Beschreibung
    - Fax
    - Phone
    - MobilePhone
    - E-Mails
    - Typ
    - Titel
    - AccountId
    - Accountname
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
