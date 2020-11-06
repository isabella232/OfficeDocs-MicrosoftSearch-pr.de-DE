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
# <a name="create-custom-filters"></a><span data-ttu-id="372ef-103">Erstellen von benutzerdefinierten Filtern</span><span class="sxs-lookup"><span data-stu-id="372ef-103">Create custom Filters</span></span>

<span data-ttu-id="372ef-104">Sie können Filter erstellen, um die Suchumgebung anzupassen, die Benutzern bei der Suche in Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com)und Microsoft Search in [Bing](https://bing.com)angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="372ef-104">You can create filters to customize the search experience that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="372ef-105">Mithilfe von Filtern können Benutzer die Ergebnisse Ihrer Suchabfrage schnell verfeinern.</span><span class="sxs-lookup"><span data-stu-id="372ef-105">Filters lets users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="372ef-106">Ein benutzerdefinierter Filter kann in einer vertikalen basierend auf einer Connection-Eigenschaft erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="372ef-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="372ef-107">Sie können beispielsweise einen **veröffentlichten on** -Filter für ServiceNow-Verbindung in einer benutzerdefinierten vertikalen erstellen.</span><span class="sxs-lookup"><span data-stu-id="372ef-107">For example, you can create a **Published On** filter for ServiceNow connection inside a custom vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="372ef-108">Zu berücksichtigende Aspekte</span><span class="sxs-lookup"><span data-stu-id="372ef-108">Things to consider</span></span>

1. <span data-ttu-id="372ef-109">Zum Erstellen eines benutzerdefinierten Filters für die Inhaltsquelle für Verbindungen werden einige zusätzliche Funktionen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="372ef-109">For creating custom filter on connection content source, some additional capabilities are provided:</span></span>
- <span data-ttu-id="372ef-110">Sie können auch Filter für einen Alias für die Eigenschaften von Connector Source erstellen.</span><span class="sxs-lookup"><span data-stu-id="372ef-110">You can also create filter on an alias to connector source properties</span></span>
- <span data-ttu-id="372ef-111">Wenn Ihre vertikale mehrere Verbindungen hat, können Sie einen allgemeinen Filter für diese Verbindungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="372ef-111">In case your vertical has multiple connections then you can create a common filter across these connections.</span></span> <span data-ttu-id="372ef-112">Dies kann durch Erstellen des Filters für einen gemeinsamen Alias erfolgen, der die Quelleigenschaften über verschiedene Verbindungen hinweg aliast.</span><span class="sxs-lookup"><span data-stu-id="372ef-112">This can be done by creating the filter on an common alias which aliases source properties across across different connections.</span></span> <span data-ttu-id="372ef-113">Sie können beispielsweise einen **Autor** Filter in einem ServiceNow & einer Jira-Verbindung erstellen, indem Sie wie folgt Aliase erstellen:</span><span class="sxs-lookup"><span data-stu-id="372ef-113">For example you can create an **Author** filter across a ServiceNow & a Jira connection by creating aliases as follows:</span></span>

| <span data-ttu-id="372ef-114">Verbindung</span><span class="sxs-lookup"><span data-stu-id="372ef-114">Connection</span></span> | <span data-ttu-id="372ef-115">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="372ef-115">Property</span></span> | <span data-ttu-id="372ef-116">Alias</span><span class="sxs-lookup"><span data-stu-id="372ef-116">Alias</span></span> |
| --- | --- | --- |
| <span data-ttu-id="372ef-117">Dienst jetzt</span><span class="sxs-lookup"><span data-stu-id="372ef-117">Service Now</span></span> | <span data-ttu-id="372ef-118">Besitzer</span><span class="sxs-lookup"><span data-stu-id="372ef-118">Owner</span></span> | <span data-ttu-id="372ef-119">Ursprung</span><span class="sxs-lookup"><span data-stu-id="372ef-119">Author</span></span> |
| <span data-ttu-id="372ef-120">Jira</span><span class="sxs-lookup"><span data-stu-id="372ef-120">Jira</span></span> | <span data-ttu-id="372ef-121">Publisher</span><span class="sxs-lookup"><span data-stu-id="372ef-121">Publisher</span></span> | <span data-ttu-id="372ef-122">Ursprung</span><span class="sxs-lookup"><span data-stu-id="372ef-122">Author</span></span> |

2. <span data-ttu-id="372ef-123">Filter sind im Bereich der vertikalen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="372ef-123">Filters exist within the scope of the vertical.</span></span> <span data-ttu-id="372ef-124">Daher</span><span class="sxs-lookup"><span data-stu-id="372ef-124">Hence,</span></span>  
- <span data-ttu-id="372ef-125">Wenn ein Filter in einer vertikalen erstellt wird, die auf Organisationsebene liegt, wird der Filter nur auf Organisationsebene angezeigt.</span><span class="sxs-lookup"><span data-stu-id="372ef-125">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
- <span data-ttu-id="372ef-126">Wenn ein Filter in einer vertikalen erstellt wird, die auf Standortebene liegt, wird der Filter nur auf Websiteebene angezeigt.</span><span class="sxs-lookup"><span data-stu-id="372ef-126">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="steps-to-create-custom-filter"></a><span data-ttu-id="372ef-127">Schritte zum Erstellen eines benutzerdefinierten Filters</span><span class="sxs-lookup"><span data-stu-id="372ef-127">Steps to Create custom filter</span></span>

### <a name="create-filter-in-organizational-level-vertical"></a><span data-ttu-id="372ef-128">Filter in der Organisationsebene vertikal erstellen:</span><span class="sxs-lookup"><span data-stu-id="372ef-128">Create filter in organizational level vertical:</span></span>

<span data-ttu-id="372ef-129">Führen Sie die folgenden Schritte aus, um einen Filter für Microsoft Search zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="372ef-129">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="372ef-130">Wechseln Sie im Microsoft 365 Admin Center zur Seite [vertikal](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) .</span><span class="sxs-lookup"><span data-stu-id="372ef-130">In the Microsoft 365 admin center, go to the [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) page.</span></span>
2. <span data-ttu-id="372ef-131">Erstellen/Bearbeiten der vertikalen, in der Sie den Filter erstellen möchten</span><span class="sxs-lookup"><span data-stu-id="372ef-131">Create/Edit the vertical in which you want to create the filter</span></span>
3. <span data-ttu-id="372ef-132">Navigieren Sie zum Schritt "Filter" im Assistenten.</span><span class="sxs-lookup"><span data-stu-id="372ef-132">Navigate to the 'Filters' step in the wizard</span></span>
4. <span data-ttu-id="372ef-133">Klicken Sie auf "Filter hinzufügen" und erste Schritte nach dem Hinzufügen von Filtern können Sie die vertikale überprüfen und speichern.</span><span class="sxs-lookup"><span data-stu-id="372ef-133">Click on 'Add Filter' and get started After adding filters, you can review and save the vertical.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="372ef-134">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="372ef-134">Known Limitations</span></span>

1. <span data-ttu-id="372ef-135">Sie können derzeit nur Filter für & Datentyp verwaltete Eigenschaften von Zeichenfolgen erstellen.</span><span class="sxs-lookup"><span data-stu-id="372ef-135">You can currently create filters only on String & Date type managed properties.</span></span>
2. <span data-ttu-id="372ef-136">Sie können keine hierarchischen Filter erstellen</span><span class="sxs-lookup"><span data-stu-id="372ef-136">You cannot create hierarchical filters</span></span>

## <a name="resources"></a><span data-ttu-id="372ef-137">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="372ef-137">Resources</span></span>

[<span data-ttu-id="372ef-138">Anpassen der Suchergebnisseite</span><span class="sxs-lookup"><span data-stu-id="372ef-138">Customize search result page</span></span>](customize-search-page.md)