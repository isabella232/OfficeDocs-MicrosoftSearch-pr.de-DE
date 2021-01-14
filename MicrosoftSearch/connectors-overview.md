---
title: Übersicht über Connectors
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
ms.openlocfilehash: 677c91f121185faa6dc96f80c517917f429a3ab0
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847519"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="bb4ba-103">Übersicht über Microsoft Graph Connectors</span><span class="sxs-lookup"><span data-stu-id="bb4ba-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="bb4ba-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indiziert alle [Ihre Microsoft 365-Daten,](https://www.microsoft.com/microsoft-365) um sie für Benutzer durchsuchbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="bb4ba-105">Mit Microsoft Graph Connectors kann Ihre Organisation Drittanbieterdaten indizieren, sodass sie in den Microsoft Search-Ergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="bb4ba-106">Dadurch werden die Typen von Inhaltsquellen erweitert, die in Ihren Microsoft 365-Produktivitäts-Apps und dem umfassenderen Microsoft-Ökosystem durchsuchbar sind.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="bb4ba-107">Die Drittanbieterdaten können lokal oder in öffentlichen oder privaten Clouds gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="bb4ba-108">Der Rest dieses Artikels soll Microsoft 365-Administratoren dabei helfen, die verfügbaren Ressourcen für die Beantwortung der folgenden Fragen zu finden:</span><span class="sxs-lookup"><span data-stu-id="bb4ba-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="bb4ba-109">Welche Datenquellen können mit Microsoft Search verbunden werden?</span><span class="sxs-lookup"><span data-stu-id="bb4ba-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="bb4ba-110">Wie verwalte ich meine Verbindungen?</span><span class="sxs-lookup"><span data-stu-id="bb4ba-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="bb4ba-111">Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Graph-Connectors?</span><span class="sxs-lookup"><span data-stu-id="bb4ba-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="bb4ba-112">Wie kann ich Suchergebnisse anpassen und konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="bb4ba-112">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="bb4ba-113">Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?</span><span class="sxs-lookup"><span data-stu-id="bb4ba-113">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> <span data-ttu-id="bb4ba-114">Microsoft Graph Connectors und Microsoft Search-APIs sind jetzt allgemein verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-114">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="bb4ba-115">Die ersten Rollouts sind für Kunden, die für die gezielte Veröffentlichung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-115">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="bb4ba-116">Wenn Sie einen Graph Connector in Ihrem Mandanten verwenden möchten, müssen Sich Benutzer und Administratoren für die [Zielversion entscheiden.](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="bb4ba-116">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="bb4ba-117">Welche Datenquellen können mit Microsoft Search verbunden werden?</span><span class="sxs-lookup"><span data-stu-id="bb4ba-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="bb4ba-118">Microsoft bietet zehn Graph-Connectors, und unsere Ökosystempartner haben mehr als 100 zusätzliche Graph Connectors erstellt.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-118">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="bb4ba-119">Sie können auch einen eigenen Graph-Connector erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-119">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="bb4ba-120">Microsoft Graph-Connectors</span><span class="sxs-lookup"><span data-stu-id="bb4ba-120">Graph connectors by Microsoft</span></span>

<span data-ttu-id="bb4ba-121">Sie können mithilfe von von Microsoft erstellten Graph-Connectors eine Verbindung mit den folgenden Datenquellen herstellen:</span><span class="sxs-lookup"><span data-stu-id="bb4ba-121">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="bb4ba-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="bb4ba-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="bb4ba-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="bb4ba-123">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="bb4ba-124">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="bb4ba-124">Azure SQL</span></span>
* [<span data-ttu-id="bb4ba-125">Unternehmenswebsites</span><span class="sxs-lookup"><span data-stu-id="bb4ba-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="bb4ba-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="bb4ba-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="bb4ba-127">Microsoft SQL Server </span><span class="sxs-lookup"><span data-stu-id="bb4ba-127">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="bb4ba-128">Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="bb4ba-128">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="bb4ba-129">Oracle (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="bb4ba-129">Oracle (preview)</span></span>
* [<span data-ttu-id="bb4ba-130">Salesforce (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="bb4ba-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="bb4ba-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="bb4ba-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="bb4ba-132">Der [Graph Connectors Gallery](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen Graph-Connectors.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="bb4ba-133">Wenn Sie bereit sind, eine dieser Datenquellen mit Ihrem [](configure-connector.md) Mandanten zu verbinden, lesen Sie unbedingt die Setupübersicht und alle anderen Artikel im Abschnitt "Setupconnectors von Microsoft", die für Ihre Datenquelle gelten.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-133">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="bb4ba-134">Graph connectors von unseren Partnern</span><span class="sxs-lookup"><span data-stu-id="bb4ba-134">Graph connectors by our partners</span></span>

<span data-ttu-id="bb4ba-135">Der [Microsoft Graph Connectors Gallery](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen graph-Connectors, die von unseren Partnern erstellt wurden, sowie einen Link zur Website der einzelnen Partner.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="bb4ba-136">Wenden Sie sich direkt an jeden Partner, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-136">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="bb4ba-137">Erstellen Eines eigenen Graph-Connectors</span><span class="sxs-lookup"><span data-stu-id="bb4ba-137">Build your own Graph connector</span></span>

<span data-ttu-id="bb4ba-138">Wenn Sie einen eigenen Graph-Connector erstellen möchten, finden Sie weitere Informationen in der Übersicht über die [Microsoft Search-API in Microsoft Graph.](https://docs.microsoft.com/graph/search-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="bb4ba-138">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="bb4ba-139">Wie verwalte ich meine Verbindungen?</span><span class="sxs-lookup"><span data-stu-id="bb4ba-139">How do I manage my connections?</span></span>

<span data-ttu-id="bb4ba-140">Sie können Ihre Verbindungen über die Registerkarte ["Connectors"](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) im [Microsoft 365 Admin Center verwalten.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="bb4ba-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="bb4ba-141">Weitere [Informationen finden Sie unter "Verwalten](manage-connector.md) Ihrer Verbindungen".</span><span class="sxs-lookup"><span data-stu-id="bb4ba-141">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="bb4ba-142">Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Graph-Connectors?</span><span class="sxs-lookup"><span data-stu-id="bb4ba-142">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="bb4ba-143">Sie benötigen eine gültige Microsoft 365- oder Office 365-Lizenz und ein ausreichendes Graph Connectors-Kontingent, damit Benutzer in Ihrer Organisation Daten von Connectors in ihren Suchergebnissen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-143">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="bb4ba-144">Weitere Informationen finden Sie unter [Lizenzanforderungen, Preise](licensing.md) und [Nutzungsbedingungen.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="bb4ba-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="bb4ba-145">Wie kann ich Suchergebnisse anpassen und konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="bb4ba-145">How do I customize and configure search results?</span></span>

<span data-ttu-id="bb4ba-146">Es gibt eine Reihe von Möglichkeiten zum Anpassen und Konfigurieren von Suchergebnissen.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-146">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="bb4ba-147">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="bb4ba-147">See the following articles to learn more:</span></span>

* [<span data-ttu-id="bb4ba-148">Branchen und Ergebnistypen verwalten</span><span class="sxs-lookup"><span data-stu-id="bb4ba-148">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="bb4ba-149">Verwalten von Layouts für Suchergebnisse</span><span class="sxs-lookup"><span data-stu-id="bb4ba-149">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="bb4ba-150">Verwalten von Ergebnisclusters</span><span class="sxs-lookup"><span data-stu-id="bb4ba-150">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="bb4ba-151">Verwalten benutzerdefinierter Filter</span><span class="sxs-lookup"><span data-stu-id="bb4ba-151">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="bb4ba-152">Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?</span><span class="sxs-lookup"><span data-stu-id="bb4ba-152">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="bb4ba-153">Nachdem benutzerdefinierte Daten indiziert wurden, können Entwickler [diese Daten abfragen.](https://docs.microsoft.com/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="bb4ba-153">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="bb4ba-154">Sie können Ihre Daten in jeder Anwendung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-154">You can view your data in any application.</span></span> <span data-ttu-id="bb4ba-155">Weitere Informationen finden Sie in der [Übersicht über die Microsoft Search-API in Microsoft Graph.](https://docs.microsoft.com/graph/search-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="bb4ba-155">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="limitations"></a><span data-ttu-id="bb4ba-156">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="bb4ba-156">Limitations</span></span>

* <span data-ttu-id="bb4ba-157">Wenn Sie **einen** von Microsoft erstellten Connector veröffentlichen, kann es einige Minuten dauern, bis die Verbindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-157">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="bb4ba-158">Während dieser Zeit zeigt die Verbindung ihren Status als ausstehend an.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-158">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="bb4ba-159">Das [Microsoft 365 Admin Center](https://admin.microsoft.com) unterstützt  die Bearbeitung des Suchschemas nach der Veröffentlichung einer Verbindung nicht.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-159">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="bb4ba-160">Um das Suchschema zu bearbeiten, löschen Sie Ihre Verbindung, und erstellen Sie dann eine neue.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-160">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="bb4ba-161">Der Erfassungsdurchsatz wird bei etwa vier Elementen pro Sekunde gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-161">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="bb4ba-162">Schemaupdates werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-162">There is no support for schema updates.</span></span> <span data-ttu-id="bb4ba-163">Nachdem Sie eine Verbindungseinrichtung erstellt haben, gibt es keine Möglichkeit, das Schema zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-163">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="bb4ba-164">Sie können die Verbindung nur löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-164">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="bb4ba-165">Es gibt ein Verbindungslimit.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-165">There is a connections limit.</span></span> <span data-ttu-id="bb4ba-166">Jeder Mandant kann bis zu 10 Verbindungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-166">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="bb4ba-167">Die Bearbeitungsunterstützung für die Verbindung ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-167">Edit support for connection is not available.</span></span> <span data-ttu-id="bb4ba-168">Nachdem die Verbindung erstellt wurde, können Sie sie nicht mehr bearbeiten oder ändern.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-168">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="bb4ba-169">Wenn Sie Details ändern müssen, müssen Sie die Verbindung löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb4ba-169">If you need to change any details, you must delete and recreate the connection.</span></span>
