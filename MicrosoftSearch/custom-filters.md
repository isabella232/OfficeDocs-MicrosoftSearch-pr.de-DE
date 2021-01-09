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
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790330"
---
# <a name="manage-custom-filters"></a>Verwalten benutzerdefinierter Filter

Mithilfe von Filtern können Sie die Microsoft Search-Erfahrung anpassen. Mithilfe von Filtern können Benutzer den Satz von Ergebnissen aus ihrer Suchabfrage schnell verfeinern.

Ein benutzerdefinierter Filter kann basierend auf einer Verbindungseigenschaft in einer Vertikalen erstellt werden. Sie können z. B. eine **"Veröffentlicht am"-Filter** für eine "ServiceNow"-Verbindung innerhalb einer vertikalen Verbindung erstellen.

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>Erstellen eines Filters in einer Organisationsebene

Führen Sie die folgenden Schritte aus, um einen Filter in Microsoft Search zu erstellen:

1. Wechseln Sie im Microsoft 365 Admin Center zu ["Verticals".](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
1. Erstellen/Bearbeiten der Vertikalen, in der Sie den Filter erstellen möchten
1. Navigieren Sie im Assistenten zum Schritt "Filter".
1. Klicken Sie auf "Filter hinzufügen" und beginnen Sie.
1. Nach dem Hinzufügen von Filtern können Sie die Vertikale überprüfen und speichern.

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte

1. Für Verbindungsinhalte sind zusätzliche Filterfunktionen vorhanden.

    - Sie können auch einen Filter für einen Alias für Connectorquelleneigenschaften erstellen.
    - Wenn eine Vertikale mehrere Verbindungen hat, können Sie einen gemeinsamen Filter für diese Verbindungen erstellen. Dies kann durch Erstellen des Filters nach einem allgemeinen Alias durchgeführt werden, der Quelleigenschaften über die verschiedenen Verbindungen hinweg aliasiert. Sie können beispielsweise  einen Autorenfilter über eine ServiceNow- und eine Jira-Verbindung hinweg erstellen, indem Sie aliase wie folgt erstellen:

    | Verbindung | Eigenschaft | Alias |
    | --- | --- | --- |
    | Service Now | Besitzer | Ursprung |
    | Jira | Publisher | Ursprung |

1. Filter sind innerhalb des Bereichs einer Vertikalen vorhanden.

    - Wenn ein Filter in einer Vertikalen erstellt wird, die sich auf Organisationsebene befindet, wäre der Filter nur auf Organisationsebene sichtbar.
    - Wenn ein Filter in einer vertikalen Ebene erstellt wird, die sich auf Standortebene befindet, wäre der Filter nur auf Standortebene sichtbar.

## <a name="known-limitations"></a>Bekannte Einschränkungen

1. Derzeit können Sie Filter nur für Zeichenfolgen erstellen, & verwaltete Eigenschaften des Datumstyps enthalten.
1. Sie können keine hierarchischen Filter erstellen.

## <a name="resources"></a>Ressourcen

[Branchen und Ergebnistypen verwalten](customize-search-page.md)
