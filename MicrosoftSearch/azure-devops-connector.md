---
title: Azure DevOps Graph Connector für Microsoft Search
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
description: Einrichten des Azure DevOps Graph Connectors für Microsoft Search
ms.openlocfilehash: fcf381a92ef397f900b300ca667fa80067a6672a
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701390"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Azure DevOps Graph Connector (Vorschau)

Der Azure DevOps Graph Connector ermöglicht Es Ihrer Organisation, Arbeitselemente in ihrer Instanz des Azure DevOps Diensts zu indizieren. Nachdem Sie den Connector konfiguriert und Inhalte aus Azure DevOps indiziert haben, können Endbenutzer in Microsoft Search nach diesen Elementen suchen.

> [!NOTE]
> Lesen Sie den Artikel [**"Setup for your Graph connector",**](configure-connector.md) um die allgemeinen Anweisungen zum Einrichten Graph Connectors zu verstehen.

Dieser Artikel richtet sich an alle Personen, die einen Azure DevOps Graph Connector konfigurieren, ausführen und überwachen. Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Azure DevOps Graph Connector gelten.

>[!IMPORTANT]
>Der Azure DevOps Connector unterstützt nur den Azure DevOps Clouddienst. Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 und TFS 2013 werden von diesem Connector nicht unterstützt.

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph Connectors in der Microsoft 365 Admin Center

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Um eine Verbindung mit Ihrer Azure DevOps Instanz herzustellen, benötigen Sie ihren Azure DevOps [Organisationsnamen,](/azure/devops/organizations/accounts/create-organization) dessen App-ID und den geheimen Clientschlüssel für die OAuth-Authentifizierung.

### <a name="register-an-app"></a>Registrieren einer App

Registrieren Sie eine App in Azure DevOps, damit die Microsoft Search-App auf die Instanz zugreifen kann. Weitere Informationen finden Sie in Azure DevOps Dokumentation zum [Registrieren einer App.](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)

Die folgende Tabelle enthält Anleitungen zum Ausfüllen des App-Registrierungsformulars:

Pflichtfelder | Beschreibung | Empfohlener Wert
--- | --- | ---
| Firmenname         | Der Name Ihres Unternehmens. | Verwenden eines geeigneten Werts   |
| Name der Anwendung     | Ein eindeutiger Wert, der die Anwendung identifiziert, die Sie autorisieren.    | Microsoft Search     |
| Anwendungswebsite  | Die URL der Anwendung, die während der Connectoreinrichtung Zugriff auf Ihre Azure DevOps Instanz anfordert. (Erforderlich).  | https://<span>gcs.office.</span> com/
| Autorisierungsrückruf-URL        | Eine erforderliche Rückruf-URL, an die der Autorisierungsserver umleitet. | https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback|
| Autorisierte Bereiche | Der Umfang des Zugriffs für die Anwendung | Wählen Sie die folgenden Bereiche aus: Identität (lesen), Arbeitsaufgaben (lesen), Variablengruppen (lesen), Project und Team (lesen), Graph (lesen), Analyse (lesen)|

>[!IMPORTANT]
>Die autorisierten Bereiche, die Sie für die App auswählen, sollten genau wie oben aufgeführt mit den Bereichen übereinstimmen. Wenn Sie einen der autorisierten Bereiche in der Liste weglassen oder einen anderen Bereich hinzufügen, schlägt die Autorisierung fehl.

Beim Registrieren der App mit den oben genannten Details erhalten Sie die **App-ID** und den **geheimen Clientschlüssel,** die zum Konfigurieren des Connectors verwendet werden.

>[!NOTE]
>Um den Zugriff auf alle in Azure DevOps registrierten Apps zu widerrufen, wechseln Sie zu Benutzereinstellungen rechts oben in Ihrer Azure DevOps Instanz. Wählen Sie "Profil" und dann "Autorisierungen" im Abschnitt "Sicherheit" des Seitenbereichs aus. Zeigen Sie auf eine autorisierte OAuth-App, um die Schaltfläche "Widerrufen" in der Ecke der App-Details anzuzeigen.

### <a name="connection-settings"></a>Verbindungseinstellungen

Nachdem Sie die Microsoft Search-App bei Azure DevOps registriert haben, können Sie den Verbindungseinstellungsschritt ausführen. Geben Sie den Namen Ihrer Organisation, Die App-ID und den geheimen Clientschlüssel ein.

![Verbindungsanwendung Einstellungen.](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>Konfigurieren von Daten: Auswählen von Projekten und Feldern

Sie können auswählen, ob die Verbindung entweder die gesamte Organisation oder bestimmte Projekte indiziert.

Wenn Sie die gesamte Organisation indiziert, werden Elemente in allen Projekten in der Organisation indiziert. Neue Projekte und Elemente werden bei der nächsten Durchforstung indiziert, nachdem sie erstellt wurden.

Wenn Sie einzelne Projekte auswählen, werden nur Arbeitsaufgaben in diesen Projekten indiziert.

![Konfigurieren sie Daten.](media/ADO_Configure_data.png)

Wählen Sie als Nächstes aus, welche Felder die Verbindung für die Indizierung und Vorschau von Daten in diesen Feldern verwenden soll, bevor Sie fortfahren.

![Wählen Sie Eigenschaften aus.](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen

Der Azure DevOps Connector unterstützt Suchberechtigungen, die  **nur personen mit Zugriff auf diese Datenquelle** oder **"Jeder"** angezeigt werden. Wenn Sie **nur Personen mit Zugriff auf diese Datenquelle** auswählen, werden indizierte Daten in den Suchergebnissen für Benutzer angezeigt, die basierend auf Berechtigungen für Benutzer oder Gruppen in der Organisation, Project oder Bereichspfadebene in Azure DevOps Zugriff auf sie haben. Wenn Sie **"Jeder"** auswählen, werden indizierte Daten in den Suchergebnissen für alle Benutzer angezeigt.

## <a name="step-5-assign-property-labels"></a>Schritt 5: Zuweisen von Eigenschaftenbeschriftungen

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

## <a name="step-6-manage-schema"></a>Schritt 6: Verwalten des Schemas

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

## <a name="step-7-choose-refresh-settings"></a>Schritt 7: Auswählen von Aktualisierungseinstellungen

Der Azure DevOps Connector unterstützt Aktualisierungszeitpläne für vollständige und inkrementelle Durchforstungen.
Der empfohlene Zeitplan ist eine Stunde für eine inkrementelle Durchforstung und ein Tag für eine vollständige Durchforstung.

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)

>[!TIP]
>**Standardergebnistyp**
>* Der Azure DevOps Connector registriert automatisch einen [Ergebnistyp,](./customize-search-page.md#step-2-create-result-types) sobald der Connector veröffentlicht wurde. Der Ergebnistyp verwendet ein dynamisch generiertes [Ergebnislayout](./customize-results-layout.md) basierend auf den in Schritt 3 ausgewählten Feldern. 
>* Sie können den Ergebnistyp verwalten, indem Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Ergebnistypen**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) navigieren. Der Standardergebnistyp wird als `ConnectionId` "Standard" bezeichnet. Wenn ihre Verbindungs-ID beispielsweise `AzureDevOps` lautet, wird ihr Ergebnislayout wie folgt benannt: "AzureDevOpsDefault"
>* Sie können bei Bedarf auch einen eigenen Ergebnistyp erstellen.

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="troubleshooting"></a>Problembehandlung
Es folgt ein häufiger Fehler beim Konfigurieren des Connectors und sein möglicher Grund.

| Konfigurationsschritt | Fehlermeldung | Mögliche Gründe |
| ------------ | ------------ | ------------ |
|  | `The account associated with the connector doesn't have permission to access the item.` | Die registrierte App verfügt nicht über einen der erforderlichen OAuth-Bereiche. (Hinweis : Am 31.08.2021 wurde eine neue OAuth-Bereichsanforderung "Analytics:read" eingeführt.)  |

<!---## Limitations-->
<!---Insert limitations for this data source-->