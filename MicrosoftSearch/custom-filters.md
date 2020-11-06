---
title: Verwalten von benutzerdefinierten Filtern
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Verwalten von benutzerdefinierten Filtern
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927382"
---
# <a name="create-custom-filters"></a>Erstellen von benutzerdefinierten Filtern

Sie können Filter erstellen, um die Suchumgebung anzupassen, die Benutzern bei der Suche in Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com)und Microsoft Search in [Bing](https://bing.com)angezeigt wird. Mithilfe von Filtern können Benutzer die Ergebnisse Ihrer Suchabfrage schnell verfeinern.

Ein benutzerdefinierter Filter kann in einer vertikalen basierend auf einer Connection-Eigenschaft erstellt werden. Sie können beispielsweise einen **veröffentlichten on** -Filter für ServiceNow-Verbindung in einer benutzerdefinierten vertikalen erstellen.

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte

1. Zum Erstellen eines benutzerdefinierten Filters für die Inhaltsquelle für Verbindungen werden einige zusätzliche Funktionen bereitgestellt:
- Sie können auch Filter für einen Alias für die Eigenschaften von Connector Source erstellen.
- Wenn Ihre vertikale mehrere Verbindungen hat, können Sie einen allgemeinen Filter für diese Verbindungen erstellen. Dies kann durch Erstellen des Filters für einen gemeinsamen Alias erfolgen, der die Quelleigenschaften über verschiedene Verbindungen hinweg aliast. Sie können beispielsweise einen **Autor** Filter in einem ServiceNow & einer Jira-Verbindung erstellen, indem Sie wie folgt Aliase erstellen:

| Verbindung | Eigenschaft | Alias |
| --- | --- | --- |
| Dienst jetzt | Besitzer | Ursprung |
| Jira | Publisher | Ursprung |

2. Filter sind im Bereich der vertikalen vorhanden. Daher  
- Wenn ein Filter in einer vertikalen erstellt wird, die auf Organisationsebene liegt, wird der Filter nur auf Organisationsebene angezeigt.
- Wenn ein Filter in einer vertikalen erstellt wird, die auf Standortebene liegt, wird der Filter nur auf Websiteebene angezeigt.

## <a name="steps-to-create-custom-filter"></a>Schritte zum Erstellen eines benutzerdefinierten Filters

### <a name="create-filter-in-organizational-level-vertical"></a>Filter in der Organisationsebene vertikal erstellen:

Führen Sie die folgenden Schritte aus, um einen Filter für Microsoft Search zu erstellen:

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite [vertikal](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) .
2. Erstellen/Bearbeiten der vertikalen, in der Sie den Filter erstellen möchten
3. Navigieren Sie zum Schritt "Filter" im Assistenten.
4. Klicken Sie auf "Filter hinzufügen" und erste Schritte nach dem Hinzufügen von Filtern können Sie die vertikale überprüfen und speichern.

## <a name="known-limitations"></a>Bekannte Einschränkungen

1. Sie können derzeit nur Filter für & Datentyp verwaltete Eigenschaften von Zeichenfolgen erstellen.
2. Sie können keine hierarchischen Filter erstellen

## <a name="resources"></a>Ressourcen

[Anpassen der Suchergebnisseite](customize-search-page.md)