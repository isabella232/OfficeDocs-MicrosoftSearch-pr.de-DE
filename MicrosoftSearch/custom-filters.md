---
title: Verwalten benutzerdefinierter Filter
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
description: Verwalten benutzerdefinierter Filter
ms.openlocfilehash: 339c7e96a00860a044a4e1af7382932f8e440e01b8b6d12445c24c1ea9b8cad0
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533128"
---
# <a name="manage-custom-filters"></a>Verwalten benutzerdefinierter Filter

Sie können Filter verwenden, um die Microsoft Search Anzupassen. Mithilfe von Filtern können Benutzer die Ergebnisse ihrer Suchabfrage schnell verfeinern.

Ein benutzerdefinierter Filter kann in einer Vertikalen basierend auf einer Verbindungseigenschaft erstellt werden. Sie können z. B. einen **Filter "Veröffentlicht auf"** für die ServiceNow-Verbindung innerhalb einer Vertikalen erstellen.

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>Erstellen eines Filters auf vertikaler Ebene auf Organisationsebene

Gehen Sie folgendermaßen vor, um einen Filter für Microsoft Search zu erstellen:

1. Wechseln Sie im Microsoft 365 Admin Center zu ["Verticals".](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
1. Erstellen/Bearbeiten der Vertikalen, in der Sie den Filter erstellen möchten
1. Navigieren Sie im Assistenten zum Schritt "Filter".
1. Klicken Sie auf "Filter hinzufügen" und erste Schritte
1. Nach dem Hinzufügen von Filtern können Sie die Vertikale überprüfen und speichern.

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte

1. Für Verbindungsinhalte sind zusätzliche Filterfunktionen vorhanden.

    - Sie können auch einen Filter für einen Alias erstellen, um Die Quelleigenschaften des Connectors zu verwenden.
    - Wenn eine Vertikale über mehrere Verbindungen verfügt, können Sie einen gemeinsamen Filter für diese Verbindungen erstellen. Dies kann durch Erstellen des Filters für einen gemeinsamen Alias erfolgen, der Quelleigenschaften über die verschiedenen Verbindungen hinweg aliast. Sie können z. **B.** einen Author-Filter für eine ServiceNow- und eine Jira-Verbindung erstellen, indem Sie wie folgt Aliase erstellen:

    | Verbindung | Eigenschaft | Alias |
    | --- | --- | --- |
    | Jetzt dienst | Besitzer | Ursprung |
    | Jira | Publisher | Ursprung |

1. Filter befinden sich innerhalb des Bereichs einer vertikalen.

    - Wenn ein Filter in einer Vertikalen erstellt wird, die sich auf Organisationsebene befindet, ist der Filter nur auf Organisationsebene sichtbar.
    - Wenn ein Filter in einer Vertikalen erstellt wird, die sich auf Standortebene befindet, ist der Filter nur auf Websiteebene sichtbar.

## <a name="known-limitations"></a>Bekannte Einschränkungen

1. Derzeit können Sie Filter nur für Zeichenfolgen & verwalteten Eigenschaften des Datumstyps erstellen.
1. Sie können keine hierarchischen Filter erstellen.

## <a name="resources"></a>Ressourcen

[Branchen und Ergebnistypen verwalten](customize-search-page.md)
