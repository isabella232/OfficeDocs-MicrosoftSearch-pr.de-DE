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
# <a name="manage-custom-filters"></a><span data-ttu-id="083af-103">Verwalten benutzerdefinierter Filter</span><span class="sxs-lookup"><span data-stu-id="083af-103">Manage custom filters</span></span>

<span data-ttu-id="083af-104">Mithilfe von Filtern können Sie die Microsoft Search-Erfahrung anpassen.</span><span class="sxs-lookup"><span data-stu-id="083af-104">You can use filters to customize the Microsoft Search experience.</span></span> <span data-ttu-id="083af-105">Mithilfe von Filtern können Benutzer den Satz von Ergebnissen aus ihrer Suchabfrage schnell verfeinern.</span><span class="sxs-lookup"><span data-stu-id="083af-105">Filters let users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="083af-106">Ein benutzerdefinierter Filter kann basierend auf einer Verbindungseigenschaft in einer Vertikalen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="083af-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="083af-107">Sie können z. B. eine **"Veröffentlicht am"-Filter** für eine "ServiceNow"-Verbindung innerhalb einer vertikalen Verbindung erstellen.</span><span class="sxs-lookup"><span data-stu-id="083af-107">For example, you can create a **Published On** filter for ServiceNow connection inside a vertical.</span></span>

## <a name="create-a-filter-in-an-organizational-level-vertical"></a><span data-ttu-id="083af-108">Erstellen eines Filters in einer Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="083af-108">Create a filter in an organizational level vertical</span></span>

<span data-ttu-id="083af-109">Führen Sie die folgenden Schritte aus, um einen Filter in Microsoft Search zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="083af-109">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="083af-110">Wechseln Sie im Microsoft 365 Admin Center zu ["Verticals".](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)</span><span class="sxs-lookup"><span data-stu-id="083af-110">In the Microsoft 365 admin center, go to [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
1. <span data-ttu-id="083af-111">Erstellen/Bearbeiten der Vertikalen, in der Sie den Filter erstellen möchten</span><span class="sxs-lookup"><span data-stu-id="083af-111">Create/Edit the vertical in which you want to create the filter</span></span>
1. <span data-ttu-id="083af-112">Navigieren Sie im Assistenten zum Schritt "Filter".</span><span class="sxs-lookup"><span data-stu-id="083af-112">Navigate to the 'Filters' step in the wizard</span></span>
1. <span data-ttu-id="083af-113">Klicken Sie auf "Filter hinzufügen" und beginnen Sie.</span><span class="sxs-lookup"><span data-stu-id="083af-113">Click on 'Add Filter' and get started</span></span>
1. <span data-ttu-id="083af-114">Nach dem Hinzufügen von Filtern können Sie die Vertikale überprüfen und speichern.</span><span class="sxs-lookup"><span data-stu-id="083af-114">After adding filters, you can review and save the vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="083af-115">Zu berücksichtigende Aspekte</span><span class="sxs-lookup"><span data-stu-id="083af-115">Things to consider</span></span>

1. <span data-ttu-id="083af-116">Für Verbindungsinhalte sind zusätzliche Filterfunktionen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="083af-116">Additional filter capabilities exist on connection content.</span></span>

    - <span data-ttu-id="083af-117">Sie können auch einen Filter für einen Alias für Connectorquelleneigenschaften erstellen.</span><span class="sxs-lookup"><span data-stu-id="083af-117">You can also create filter on an alias to connector source properties</span></span>
    - <span data-ttu-id="083af-118">Wenn eine Vertikale mehrere Verbindungen hat, können Sie einen gemeinsamen Filter für diese Verbindungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="083af-118">If a vertical has multiple connections, you can create a common filter across these connections.</span></span> <span data-ttu-id="083af-119">Dies kann durch Erstellen des Filters nach einem allgemeinen Alias durchgeführt werden, der Quelleigenschaften über die verschiedenen Verbindungen hinweg aliasiert.</span><span class="sxs-lookup"><span data-stu-id="083af-119">This can be done by creating the filter on an common alias which aliases source properties across across the different connections.</span></span> <span data-ttu-id="083af-120">Sie können beispielsweise  einen Autorenfilter über eine ServiceNow- und eine Jira-Verbindung hinweg erstellen, indem Sie aliase wie folgt erstellen:</span><span class="sxs-lookup"><span data-stu-id="083af-120">For example you can create an **Author** filter across a ServiceNow and a Jira connection by creating aliases as follows:</span></span>

    | <span data-ttu-id="083af-121">Verbindung</span><span class="sxs-lookup"><span data-stu-id="083af-121">Connection</span></span> | <span data-ttu-id="083af-122">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="083af-122">Property</span></span> | <span data-ttu-id="083af-123">Alias</span><span class="sxs-lookup"><span data-stu-id="083af-123">Alias</span></span> |
    | --- | --- | --- |
    | <span data-ttu-id="083af-124">Service Now</span><span class="sxs-lookup"><span data-stu-id="083af-124">Service Now</span></span> | <span data-ttu-id="083af-125">Besitzer</span><span class="sxs-lookup"><span data-stu-id="083af-125">Owner</span></span> | <span data-ttu-id="083af-126">Ursprung</span><span class="sxs-lookup"><span data-stu-id="083af-126">Author</span></span> |
    | <span data-ttu-id="083af-127">Jira</span><span class="sxs-lookup"><span data-stu-id="083af-127">Jira</span></span> | <span data-ttu-id="083af-128">Publisher</span><span class="sxs-lookup"><span data-stu-id="083af-128">Publisher</span></span> | <span data-ttu-id="083af-129">Ursprung</span><span class="sxs-lookup"><span data-stu-id="083af-129">Author</span></span> |

1. <span data-ttu-id="083af-130">Filter sind innerhalb des Bereichs einer Vertikalen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="083af-130">Filters exist within the scope of a vertical.</span></span>

    - <span data-ttu-id="083af-131">Wenn ein Filter in einer Vertikalen erstellt wird, die sich auf Organisationsebene befindet, wäre der Filter nur auf Organisationsebene sichtbar.</span><span class="sxs-lookup"><span data-stu-id="083af-131">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
    - <span data-ttu-id="083af-132">Wenn ein Filter in einer vertikalen Ebene erstellt wird, die sich auf Standortebene befindet, wäre der Filter nur auf Standortebene sichtbar.</span><span class="sxs-lookup"><span data-stu-id="083af-132">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="083af-133">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="083af-133">Known Limitations</span></span>

1. <span data-ttu-id="083af-134">Derzeit können Sie Filter nur für Zeichenfolgen erstellen, & verwaltete Eigenschaften des Datumstyps enthalten.</span><span class="sxs-lookup"><span data-stu-id="083af-134">You can currently create filters only on string & date type managed properties.</span></span>
1. <span data-ttu-id="083af-135">Sie können keine hierarchischen Filter erstellen.</span><span class="sxs-lookup"><span data-stu-id="083af-135">You cannot create hierarchical filters.</span></span>

## <a name="resources"></a><span data-ttu-id="083af-136">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="083af-136">Resources</span></span>

[<span data-ttu-id="083af-137">Branchen und Ergebnistypen verwalten</span><span class="sxs-lookup"><span data-stu-id="083af-137">Manage verticals and result types</span></span>](customize-search-page.md)
