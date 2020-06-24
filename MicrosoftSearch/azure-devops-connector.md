---
title: Azure DevOps Connector für Microsoft Search
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Azure DevOps Connectors für Microsoft Search
ms.openlocfilehash: e2698d7d4a50c15bf765aa4eeada20fbc7328772
ms.sourcegitcommit: 7eda9b621def0659d7e7bc8b989f8adc929cce93
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "44861103"
---
# <a name="azure-devops-connector"></a>Azure DevOps-Connector

Mit dem Azure DevOps-Connector kann Ihre Organisation Arbeitsaufgaben in Ihrer Instanz des Azure DevOps-Diensts indizieren. Nachdem Sie den Connector-und den Index Inhalt aus Azure DevOps konfiguriert haben, können Endbenutzer nach diesen Elementen in der Microsoft-Suche suchen.

Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen Azure DevOps-Connector konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.

>[!IMPORTANT]
>Der Azure DevOps-Connector unterstützt nur den Azure DevOps Cloud Service. Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 und TFS 2013 werden von diesem Connector nicht unterstützt.

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle

Um eine Verbindung mit ihrer Azure DevOps-Instanz herzustellen, benötigen Sie Ihren Azure DevOps- [Organisations](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) Namen, die APP-ID und den geheimen Client Schlüssel für die OAuth-Authentifizierung.

### <a name="register-an-app"></a>Registrieren einer App

Sie müssen eine app in Azure DevOps registrieren, damit die Microsoft Search-App auf die Instanz zugreifen kann. Weitere Informationen finden Sie unter Azure DevOps-Dokumentation zum [Registrieren einer APP](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).

In der folgenden Tabelle finden Sie Anleitungen zum Ausfüllen des App-Registrierungsformulars:

 **Obligatorische Felder** | **Beschreibung**      | **Empfohlener Wert**
--- | --- | ---
| Firmenname         | Dies ist der Name Ihres Unternehmens. | Verwenden eines geeigneten Werts   |
| Anwendungsname     | Dieser eindeutige Wert identifiziert die Anwendung, die Sie zu autorisieren haben.    | Microsoft Search     |
| Anwendungswebsite  | Dieses erforderliche Feld ist die URL der Anwendung, die während des Connector-Setups Zugriff auf Ihre Azure DevOps-Instanz anfordert.  | <https://gcs.office.com/>                |
| Autorisierungs-Rückruf-URL        | Eine erforderliche Rückruf-URL, an die der autorisierungsserver umgeleitet wird. | <https://gcs.office.com/v1.0/admin/oauth/callback>|
| Autorisierte Bereiche | Dies ist der Umfang des Zugriffs für die Anwendung. | Wählen Sie die folgenden Bereiche aus: Identity (lesen), Arbeitsaufgaben (lesen), Variablen Gruppen (lesen), Projekt und Team (lesen)|

Beim Registrieren der APP mit den obigen Details erhalten Sie die **App-ID** und den **geheimen Client Schlüssel** , die zum Konfigurieren des Connectors verwendet werden.

>[!NOTE]
>Um den Zugriff auf alle in Azure DevOps registrierten apps aufzuheben, wechseln Sie zu Benutzereinstellungen rechts oben in ihrer Azure DevOps-Instanz. Klicken Sie auf Profil, und klicken Sie dann im Abschnitt Sicherheit des Seitenbereichs auf Berechtigungen. Zeigen Sie mit der Maus auf eine autorisierte OAuth-APP, um die Schaltfläche Widerrufen an der Ecke der App-Details anzuzeigen.

### <a name="connection-settings"></a>Verbindungseinstellungen

Nachdem Sie die Microsoft Search-App mit Azure DevOps registriert haben, können Sie den Schritt Verbindungseinstellungen durchführen. Geben Sie den Namen Ihrer Organisation, die APP-ID und den geheimen Client Schlüssel ein.

![Einstellungen für die Verbindungsanwendung](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a>Auswählen von Projekten und Feldern

Sie können auswählen, ob die Verbindung entweder die gesamte Organisation oder bestimmte Projekte indizieren soll.

Wenn Sie sich dafür entscheiden, die gesamte Organisation zu indizieren, werden Elemente in allen Projekten in der Organisation indiziert. Neue Projekte und Elemente werden während der nächsten Durchforstung indiziert, nachdem Sie erstellt wurden. Wenn Sie einzelne Projekte auswählen, werden nur Arbeitsaufgaben in diesen Projekten indiziert.

![Konfigurieren von Daten](media/ADO_Configure_data.png)

Wählen Sie als nächstes aus, welche Felder die Verbindung indizieren soll, und sehen Sie sich die Daten in diesen Feldern in der Vorschau an, bevor Sie fortfahren.

![Auswählen von Eigenschaften](media/ADO_choose_properties.png)

## <a name="manage-the-search-schema"></a>Verwalten des Suchschemas

Konfigurieren Sie die Zuordnung für das Suchschema. Sie können auswählen, welche Eigenschaften **abgefragt**, **durchsuchbar** und **abrufbar**gemacht werden sollen.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen

Der Azure DevOps-Connector unterstützt derzeit nur Suchberechtigungen **, die für alle sichtbar**sind. Indizierte Daten werden in den Suchergebnissen für alle Benutzer angezeigt.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans

Der Azure DevOps-Connector unterstützt Aktualisierungs Zeitpläne für vollständige und inkrementelle Crawls. Bei einer vollständigen Durchforstung werden gelöschte Arbeitsaufgaben gesucht, die zuvor mit dem Microsoft-Suchindex synchronisiert wurden. Eine vollständige Durchforstung wird ausgeführt, um alle Arbeitsaufgaben zu synchronisieren. Um neue Arbeitsaufgaben und Aktualisierungen an vorhandenen Arbeitsaufgaben zu synchronisieren, müssen Sie inkrementelle Durchforstungen planen.

Der empfohlene Zeitplan beträgt eine Stunde für eine inkrementelle Durchforstung und einen Tag für eine vollständige Durchforstung.
