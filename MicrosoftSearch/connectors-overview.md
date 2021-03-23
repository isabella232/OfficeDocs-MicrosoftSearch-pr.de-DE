---
title: Übersicht über Microsoft Graph Connectors
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Übersicht über Microsoft Graph-Connectors für Microsoft Search
ms.openlocfilehash: 2d49471c703b765f6e99324f39dbe730f6dea814
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031656"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="7bf68-103">Übersicht über Microsoft Graph-Connectors</span><span class="sxs-lookup"><span data-stu-id="7bf68-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="7bf68-104">[Microsoft Search](./overview-microsoft-search.md) indiziert alle [Ihre Microsoft 365-Daten,](https://www.microsoft.com/microsoft-365) damit sie für Benutzer durchsucht werden können.</span><span class="sxs-lookup"><span data-stu-id="7bf68-104">[Microsoft Search](./overview-microsoft-search.md) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="7bf68-105">Mit Microsoft Graph-Connectors kann Ihre Organisation Drittanbieterdaten indizieren, sodass sie in den Microsoft-Suchergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7bf68-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="7bf68-106">Dieses Feature erweitert die Typen von Inhaltsquellen, die in Ihren Microsoft 365-Produktivitäts-Apps durchsucht werden können, und das umfassendere Microsoft-Ökosystem.</span><span class="sxs-lookup"><span data-stu-id="7bf68-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="7bf68-107">Die Drittanbieterdaten können lokal oder in öffentlichen oder privaten Clouds gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="7bf68-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="7bf68-108">Dieser Artikel soll Microsoft 365-Administratoren dabei helfen, die Ressourcen zu finden, die zur Beantwortung der folgenden Fragen zur Verfügung stehen:</span><span class="sxs-lookup"><span data-stu-id="7bf68-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="7bf68-109">Welche Datenquellen können mit Microsoft Search verbunden werden?</span><span class="sxs-lookup"><span data-stu-id="7bf68-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="7bf68-110">Wie verwalte ich meine Verbindungen?</span><span class="sxs-lookup"><span data-stu-id="7bf68-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="7bf68-111">Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Graph-Connectors?</span><span class="sxs-lookup"><span data-stu-id="7bf68-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="7bf68-112">Was sind die Vorschaufeatures?</span><span class="sxs-lookup"><span data-stu-id="7bf68-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="7bf68-113">Wie kann ich Suchergebnisse anpassen und konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="7bf68-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="7bf68-114">Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?</span><span class="sxs-lookup"><span data-stu-id="7bf68-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)
* [<span data-ttu-id="7bf68-115">Wie kann ich Suchergebnisse anpassen?</span><span class="sxs-lookup"><span data-stu-id="7bf68-115">How do I customize search results?</span></span>](#how-do-i-customize-search-results)
* [<span data-ttu-id="7bf68-116">Was sind die Connectoreinschränkungen?</span><span class="sxs-lookup"><span data-stu-id="7bf68-116">What are the connector limitations</span></span>](#what-are-the-connector-limitations)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="7bf68-117">Microsoft Graph-Connectors und Microsoft Search-APIs sind jetzt allgemein verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7bf68-117">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="7bf68-118">Die ersten Rollouts sind für Kunden, die für die gezielte Veröffentlichung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="7bf68-118">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="7bf68-119">Wenn Sie einen Graph-Connector in Ihrem Mandanten verwenden möchten, müssen Sich Benutzer und Administratoren für die gezielte [Version entscheiden.](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="7bf68-119">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide).</span></span>

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](./overview-microsoft-search.md) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="7bf68-120">Welche Datenquellen können mit Microsoft Search verbunden werden?</span><span class="sxs-lookup"><span data-stu-id="7bf68-120">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="7bf68-121">Microsoft stellt 9 Graph-Connectors zur Verfügung, und unsere Ökosystempartner haben mehr als 100 weitere Graph-Connectors erstellt.</span><span class="sxs-lookup"><span data-stu-id="7bf68-121">Microsoft provides 9 Graph connectors and our ecosystem partners have created over 100 more Graph connectors.</span></span> <span data-ttu-id="7bf68-122">Sie können auch einen eigenen Graph-Connector erstellen.</span><span class="sxs-lookup"><span data-stu-id="7bf68-122">You can also build your own Graph connector.</span></span>

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="7bf68-123">Microsoft Graph-Connectors</span><span class="sxs-lookup"><span data-stu-id="7bf68-123">Graph connectors by Microsoft</span></span>

<span data-ttu-id="7bf68-124">Sie können eine Verbindung mit den folgenden Datenquellen herstellen, indem Sie von Microsoft erstellte Graph-Connectors verwenden:</span><span class="sxs-lookup"><span data-stu-id="7bf68-124">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="7bf68-125">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="7bf68-125">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="7bf68-126">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="7bf68-126">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="7bf68-127">Azure SQL und Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="7bf68-127">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="7bf68-128">Unternehmenswebsites</span><span class="sxs-lookup"><span data-stu-id="7bf68-128">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="7bf68-129">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="7bf68-129">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="7bf68-130">Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="7bf68-130">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="7bf68-131">Oracle SQL (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="7bf68-131">Oracle SQL (preview)</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="7bf68-132">Salesforce (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="7bf68-132">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="7bf68-133">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7bf68-133">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="7bf68-134">Der [Graph-Connectors-Katalog](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen Graph-Connectors.</span><span class="sxs-lookup"><span data-stu-id="7bf68-134">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="7bf68-135">Wenn Sie bereit sind, eine dieser Datenquellen mit Ihrem Mandanten [](configure-connector.md) zu verbinden, lesen Sie unbedingt die Setupübersicht und alle anderen Artikel im Abschnitt Setup connectors by Microsoft, die für Ihre Datenquelle gelten.</span><span class="sxs-lookup"><span data-stu-id="7bf68-135">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="7bf68-136">Graph connectors by our partners</span><span class="sxs-lookup"><span data-stu-id="7bf68-136">Graph connectors by our partners</span></span>

<span data-ttu-id="7bf68-137">Der [Microsoft Graph-Connectorskatalog](connectors-gallery.md) enthält eine kurze Beschreibung der von unseren Partnern erstellten Graph-Connectors und einen Link zur Website jedes Partners.</span><span class="sxs-lookup"><span data-stu-id="7bf68-137">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief description of each of the Graph connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="7bf68-138">Um mehr zu erfahren, wenden Sie sich direkt an jeden Partner.</span><span class="sxs-lookup"><span data-stu-id="7bf68-138">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="7bf68-139">Erstellen Eines eigenen Graph-Connectors</span><span class="sxs-lookup"><span data-stu-id="7bf68-139">Build your own Graph connector</span></span>

<span data-ttu-id="7bf68-140">Sie können einen eigenen Graph-Connector erstellen, wenn Sie dies bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="7bf68-140">You can build your own Graph connector if you prefer.</span></span> <span data-ttu-id="7bf68-141">Weitere Informationen zum Erstellen von Graph-Connectors finden Sie unter Übersicht über die [Microsoft Search-API in Microsoft Graph](/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="7bf68-141">For more information on building Graph connectors, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="7bf68-142">Wie verwalte ich meine Verbindungen?</span><span class="sxs-lookup"><span data-stu-id="7bf68-142">How do I manage my connections?</span></span>

<span data-ttu-id="7bf68-143">Sie können Ihre Verbindungen über die Registerkarte [Connectors im](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) [Microsoft 365 Admin Center verwalten.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7bf68-143">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="7bf68-144">Weitere Informationen zum Verwalten von Verbindungen finden Sie unter: [Verwalten Ihrer Verbindungen](manage-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7bf68-144">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="7bf68-145">Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Graph-Connectors?</span><span class="sxs-lookup"><span data-stu-id="7bf68-145">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="7bf68-146">Sie benötigen eine gültige Microsoft 365- oder Office 365-Lizenz und ein ausreichendes Graph Connectors-Kontingent für Benutzer in Ihrer Organisation, um Daten von Connectors in ihren Suchergebnissen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7bf68-146">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="7bf68-147">Weitere Informationen finden Sie unter [Lizenzanforderungen und Preise](licensing.md) und [Nutzungsbedingungen](terms-of-use.md).</span><span class="sxs-lookup"><span data-stu-id="7bf68-147">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="7bf68-148">Was sind die Vorschaufeatures?</span><span class="sxs-lookup"><span data-stu-id="7bf68-148">What are the preview features?</span></span>

<span data-ttu-id="7bf68-149">Obwohl Microsoft Graph-Connectors und Microsoft Search-APIs jetzt allgemein verfügbar sind, stehen mehrere Features in der Vorschau zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7bf68-149">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="7bf68-150">Zu den Connectors und Features in der Vorschau gehören:</span><span class="sxs-lookup"><span data-stu-id="7bf68-150">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="7bf68-151">Azure DevOps Connector</span><span class="sxs-lookup"><span data-stu-id="7bf68-151">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="7bf68-152">Salesforce Connector</span><span class="sxs-lookup"><span data-stu-id="7bf68-152">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="7bf68-153">[ServiceNow-Connector](servicenow-connector.md) mit Suchberechtigungen, die Quell-ACLs verwenden</span><span class="sxs-lookup"><span data-stu-id="7bf68-153">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="7bf68-154">Verwalten von Ergebnisclusters</span><span class="sxs-lookup"><span data-stu-id="7bf68-154">Manage result cluster</span></span>](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="7bf68-155">Wie kann ich Suchergebnisse anpassen und konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="7bf68-155">How do I customize and configure search results?</span></span>

<span data-ttu-id="7bf68-156">Es gibt viele Möglichkeiten zum Anpassen und Konfigurieren von Suchergebnissen.</span><span class="sxs-lookup"><span data-stu-id="7bf68-156">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="7bf68-157">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="7bf68-157">See the following articles to learn more:</span></span>

* [<span data-ttu-id="7bf68-158">Branchen und Ergebnistypen verwalten</span><span class="sxs-lookup"><span data-stu-id="7bf68-158">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="7bf68-159">Verwalten von Layouts für Suchergebnisse</span><span class="sxs-lookup"><span data-stu-id="7bf68-159">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="7bf68-160">Verwalten von Ergebnisclusters</span><span class="sxs-lookup"><span data-stu-id="7bf68-160">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="7bf68-161">Verwalten benutzerdefinierter Filter</span><span class="sxs-lookup"><span data-stu-id="7bf68-161">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="7bf68-162">Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?</span><span class="sxs-lookup"><span data-stu-id="7bf68-162">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="7bf68-163">Nachdem benutzerdefinierte Daten indiziert wurden, können Entwickler [diese Daten abfragen.](/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="7bf68-163">After custom data is indexed, developers can [query this data](/graph/search-concept-custom-types).</span></span> <span data-ttu-id="7bf68-164">Sie können Ihre Daten in einer beliebigen Anwendung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7bf68-164">You can view your data in any application.</span></span> <span data-ttu-id="7bf68-165">Weitere Informationen finden Sie unter [Übersicht über die Microsoft Search-API in Microsoft Graph](/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="7bf68-165">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-customize-search-results"></a><span data-ttu-id="7bf68-166">Wie kann ich Suchergebnisse anpassen?</span><span class="sxs-lookup"><span data-stu-id="7bf68-166">How do I customize search results?</span></span>

<span data-ttu-id="7bf68-167">Der nächste Schritt besteht im Anpassen der Suchergebnisse wie in diesem Artikel empfohlen. Wie kann ich [Suchergebnisse anpassen und konfigurieren?](#how-do-i-customize-and-configure-search-results).</span><span class="sxs-lookup"><span data-stu-id="7bf68-167">The next step is to customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="7bf68-168">Weitere Informationen zum Anpassen von Suchergebnissen finden Sie unter [Customize the search results page](./configure-connector.md#next-steps-customize-the-search-results-page).</span><span class="sxs-lookup"><span data-stu-id="7bf68-168">To learn more about customizing search results, see [Customize the search results page](./configure-connector.md#next-steps-customize-the-search-results-page).</span></span>

## <a name="what-are-the-connector-limitations"></a><span data-ttu-id="7bf68-169">Was sind die Connectoreinschränkungen?</span><span class="sxs-lookup"><span data-stu-id="7bf68-169">What are the connector limitations?</span></span>

* <span data-ttu-id="7bf68-170">Wenn Sie **einen** von Microsoft erstellten Connector veröffentlichen, kann es einige Minuten dauern, bis die Verbindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7bf68-170">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="7bf68-171">Während dieser Zeit wird der Status der Verbindung als ausstehend angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bf68-171">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="7bf68-172">Das [Microsoft 365 Admin Center](https://admin.microsoft.com) unterstützt  die Bearbeitung des Suchschemas nach der Veröffentlichung einer Verbindung nicht.</span><span class="sxs-lookup"><span data-stu-id="7bf68-172">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="7bf68-173">Um das Suchschema zu bearbeiten, löschen Sie Ihre Verbindung, und erstellen Sie dann eine neue.</span><span class="sxs-lookup"><span data-stu-id="7bf68-173">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="7bf68-174">Der Erfassungsdurchsatz wird bei etwa vier Elementen pro Sekunde gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="7bf68-174">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="7bf68-175">Schemaupdates werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7bf68-175">There is no support for schema updates.</span></span> <span data-ttu-id="7bf68-176">Nachdem Sie eine Verbindungseinrichtung erstellt haben, gibt es keine Möglichkeit, das Schema zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7bf68-176">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="7bf68-177">Sie können die Verbindung nur löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7bf68-177">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="7bf68-178">Es gibt einen Verbindungsgrenzwert.</span><span class="sxs-lookup"><span data-stu-id="7bf68-178">There is a connection limit.</span></span> <span data-ttu-id="7bf68-179">Jeder Mandant kann bis zu 10 Verbindungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="7bf68-179">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="7bf68-180">Die Bearbeitungsunterstützung für die Verbindung ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7bf68-180">Edit support for connection is not available.</span></span> <span data-ttu-id="7bf68-181">Nachdem die Verbindung erstellt wurde, können Sie sie nicht bearbeiten oder ändern.</span><span class="sxs-lookup"><span data-stu-id="7bf68-181">Once the connection has been created, you can't edit or change it.</span></span> <span data-ttu-id="7bf68-182">Wenn Sie Details ändern müssen, müssen Sie die Verbindung löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7bf68-182">If you need to change any details, you must delete and recreate the connection.</span></span>