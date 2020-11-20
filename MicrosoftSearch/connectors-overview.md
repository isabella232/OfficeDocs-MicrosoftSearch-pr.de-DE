---
title: Connectors (Übersicht)
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Übersicht über Microsoft Graph Connectors für Microsoft Search
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367523"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="a9b14-103">Übersicht über Microsoft Graph-Connectors</span><span class="sxs-lookup"><span data-stu-id="a9b14-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="a9b14-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indiziert alle Ihre [Microsoft 365](https://www.microsoft.com/microsoft-365) -Daten, damit Sie für Benutzer durchsucht werden können.</span><span class="sxs-lookup"><span data-stu-id="a9b14-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="a9b14-105">Mit Microsoft Graph-Connectors kann Ihre Organisation Daten von Drittanbietern indizieren, damit diese in Microsoft-Suchergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a9b14-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="a9b14-106">Dadurch werden die Arten von Inhaltsquellen erweitert, die in Ihren Microsoft 365-Produktivitäts-apps und dem breiteren Microsoft-Ökosystem durchsucht werden können.</span><span class="sxs-lookup"><span data-stu-id="a9b14-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="a9b14-107">Die drittanbieterdaten können lokal oder in öffentlichen oder privaten Clouds gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="a9b14-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="a9b14-108">Der Rest dieses Artikels soll Microsoft 365 Administratoren dabei helfen, die Ressourcen zu finden, die für die Beantwortung der folgenden Fragen zur Verfügung stehen:</span><span class="sxs-lookup"><span data-stu-id="a9b14-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are avaiable to answer the following questions:</span></span>

* [<span data-ttu-id="a9b14-109">Welche Datenquellen können mit Microsoft Search verbunden werden?</span><span class="sxs-lookup"><span data-stu-id="a9b14-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="a9b14-110">Wie verwalte ich meine Verbindungen?</span><span class="sxs-lookup"><span data-stu-id="a9b14-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="a9b14-111">Was sind die Lizenzanforderungen und Nutzungsbedingungen für Graph Connectors?</span><span class="sxs-lookup"><span data-stu-id="a9b14-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="a9b14-112">Wie kann ich Suchergebnisse anpassen und konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="a9b14-112">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="a9b14-113">Wie kann ich meine connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?</span><span class="sxs-lookup"><span data-stu-id="a9b14-113">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> <span data-ttu-id="a9b14-114">Microsoft Graph-Connectors und Microsoft Search-APIs sind jetzt allgemein verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a9b14-114">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="a9b14-115">Die ersten Rollouts erfolgen für Kunden, die für eine gezielte Veröffentlichung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="a9b14-115">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="a9b14-116">Wenn Sie einen Graph-Konnektor in Ihrem Mandanten verwenden möchten, müssen sich Benutzer und Administratoren für eine [gezielte Veröffentlichung](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)entscheiden.</span><span class="sxs-lookup"><span data-stu-id="a9b14-116">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="a9b14-117">Welche Datenquellen können mit Microsoft Search verbunden werden?</span><span class="sxs-lookup"><span data-stu-id="a9b14-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="a9b14-118">Microsoft bietet zehn Graph-Konnektoren, und unsere Ökosystempartner haben mehr als 100 zusätzliche Graph-Konnektoren erstellt.</span><span class="sxs-lookup"><span data-stu-id="a9b14-118">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="a9b14-119">Sie können auch einen eigenen Graph-Konnektor erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9b14-119">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="a9b14-120">Graph-Konnektoren von Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9b14-120">Graph connectors by Microsoft</span></span>

<span data-ttu-id="a9b14-121">Sie können eine Verbindung mit den folgenden Datenquellen herstellen, indem Sie von Microsoft erstellte Graph-Konnektoren verwenden:</span><span class="sxs-lookup"><span data-stu-id="a9b14-121">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="a9b14-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="a9b14-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="a9b14-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="a9b14-123">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="a9b14-124">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="a9b14-124">Azure SQL</span></span>
* [<span data-ttu-id="a9b14-125">Unternehmenswebsites</span><span class="sxs-lookup"><span data-stu-id="a9b14-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="a9b14-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="a9b14-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="a9b14-127">Microsoft SQL Server </span><span class="sxs-lookup"><span data-stu-id="a9b14-127">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="a9b14-128">Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="a9b14-128">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="a9b14-129">Oracle (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="a9b14-129">Oracle (preview)</span></span>
* [<span data-ttu-id="a9b14-130">Salesforce (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="a9b14-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="a9b14-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="a9b14-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="a9b14-132">Der [Gallery Graph Connectors](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen Graph-Konnektoren.</span><span class="sxs-lookup"><span data-stu-id="a9b14-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="a9b14-133">Wenn Sie bereit sind, eine dieser Datenquellen mit Ihrem Mandanten zu verbinden, lesen Sie unbedingt die [Setup-Übersicht](configure-connector.md) und alle anderen Artikel im Abschnitt Setup Connectors by Microsoft, die für Ihre Datenquelle gelten.</span><span class="sxs-lookup"><span data-stu-id="a9b14-133">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="a9b14-134">Graph-Konnektoren von unseren Partnern</span><span class="sxs-lookup"><span data-stu-id="a9b14-134">Graph connectors by our partners</span></span>

<span data-ttu-id="a9b14-135">Der [Microsoft Graph Connectors-Katalog](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen Graph-Konnektoren, die von unseren Partnern erstellt wurden, sowie einen Link zu den Websites der einzelnen Partner.</span><span class="sxs-lookup"><span data-stu-id="a9b14-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="a9b14-136">Wenden Sie sich direkt an jeden Partner, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a9b14-136">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="a9b14-137">Erstellen eines eigenen Graph-Konnektors</span><span class="sxs-lookup"><span data-stu-id="a9b14-137">Build your own Graph connector</span></span>

<span data-ttu-id="a9b14-138">Wenn Sie einen eigenen Graph-Konnektor erstellen möchten, finden Sie weitere Informationen unter [Übersicht über die Microsoft-Such-API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) .</span><span class="sxs-lookup"><span data-stu-id="a9b14-138">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="a9b14-139">Wie verwalte ich meine Verbindungen?</span><span class="sxs-lookup"><span data-stu-id="a9b14-139">How do I manage my connections?</span></span>

<span data-ttu-id="a9b14-140">Sie können Ihre Verbindungen über die [Registerkarte Connectors](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) im [Microsoft 365 Admin Center](https://admin.microsoft.com/)verwalten.</span><span class="sxs-lookup"><span data-stu-id="a9b14-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="a9b14-141">Weitere Informationen finden Sie unter [Manage Your Connections](manage-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="a9b14-141">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="a9b14-142">Was sind die Lizenzanforderungen und Nutzungsbedingungen für Graph Connectors?</span><span class="sxs-lookup"><span data-stu-id="a9b14-142">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="a9b14-143">Für Benutzer in Ihrer Organisation benötigen Sie eine gültige Microsoft 365-oder Office 365-Lizenz sowie ausreichende Graph-Konnektoren, um Daten aus Konnektoren in ihren Suchergebnissen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9b14-143">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="a9b14-144">Weitere Informationen finden Sie unter [License Requirements and Pricing](licensing.md) and [Terms of use](terms-of-use.md).</span><span class="sxs-lookup"><span data-stu-id="a9b14-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="a9b14-145">Wie kann ich Suchergebnisse anpassen und konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="a9b14-145">How do I customize and configure search results?</span></span>

<span data-ttu-id="a9b14-146">Es gibt eine Reihe von Möglichkeiten zum Anpassen und Konfigurieren von Suchergebnissen.</span><span class="sxs-lookup"><span data-stu-id="a9b14-146">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="a9b14-147">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="a9b14-147">See the following articles to learn more:</span></span>

* [<span data-ttu-id="a9b14-148">Branchen und Ergebnistypen verwalten</span><span class="sxs-lookup"><span data-stu-id="a9b14-148">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="a9b14-149">Verwalten von Layouts für Suchergebnisse</span><span class="sxs-lookup"><span data-stu-id="a9b14-149">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="a9b14-150">Verwalten des Ergebnis Clusters</span><span class="sxs-lookup"><span data-stu-id="a9b14-150">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="a9b14-151">Verwalten von benutzerdefinierten Filtern</span><span class="sxs-lookup"><span data-stu-id="a9b14-151">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="a9b14-152">Wie kann ich meine connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?</span><span class="sxs-lookup"><span data-stu-id="a9b14-152">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="a9b14-153">Nachdem benutzerdefinierte Daten indiziert wurden, können Entwickler [diese Daten Abfragen](https://docs.microsoft.com/graph/search-concept-custom-types).</span><span class="sxs-lookup"><span data-stu-id="a9b14-153">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="a9b14-154">Sie können Ihre Daten in einer beliebigen Anwendung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9b14-154">You can view your data in any application.</span></span> <span data-ttu-id="a9b14-155">Weitere Informationen finden Sie in der [Übersicht über die Microsoft-Such-API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="a9b14-155">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>
