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
ms.openlocfilehash: 256cf9748aa3050aacf48c3562f6f84b4ba2e460
ms.sourcegitcommit: 5151bcd8fd929ef37239b7c229e2fa33b1e0e0b7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235924"
---
# <a name="manage-custom-filters"></a>Verwalten benutzerdefinierter Filter

Sie können Filter verwenden, um die Microsoft Search Anzupassen. Mithilfe von Filtern können Benutzer die Ergebnisse ihrer Suchabfrage schnell verfeinern.

Ein benutzerdefinierter Filter kann in einer Vertikalen basierend auf einer Verbindungseigenschaft erstellt werden. Sie können z. B. einen **Filter "Veröffentlicht auf"** für die ServiceNow-Verbindung innerhalb einer Vertikalen erstellen.

> [!NOTE]
> Benutzerdefinierte Filter befinden sich derzeit in der Vorschau für Administratoren und Endbenutzer in targeted Release. Weitere Informationen zur Vorschau finden Sie unter [Connectors Preview Features](connectors-overview.md#what-are-the-preview-features).

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>Erstellen eines Filters auf vertikaler Ebene auf Organisationsebene

Gehen Sie folgendermaßen vor, um einen Filter für Microsoft Search zu erstellen:

1. Wechseln Sie im Microsoft 365 Admin Center zu ["Vertikalen".](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
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

1. Derzeit können Sie Filter nur für zeichenfolgenbasierte & verwalteten Eigenschaften des Datumstyps erstellen.
1. Sie können keine hierarchischen Filter erstellen.

## <a name="resources"></a>Ressourcen

[Branchen und Ergebnistypen verwalten](customize-search-page.md)
