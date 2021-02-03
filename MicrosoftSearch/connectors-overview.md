---
title: Übersicht über Microsoft Graph Connectors
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Übersicht über Microsoft Graph Connectors für Microsoft Search
ms.openlocfilehash: 13127d092fe4e624ed448037d83f16f83ddc560a
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084875"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="81d6a-103">Übersicht über Microsoft Graph Connectors</span><span class="sxs-lookup"><span data-stu-id="81d6a-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="81d6a-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indiziert alle [Ihre Microsoft 365-Daten,](https://www.microsoft.com/microsoft-365) um sie für Benutzer durchsuchbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="81d6a-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="81d6a-105">Mit Microsoft Graph Connectors kann Ihre Organisation Drittanbieterdaten indizieren, sodass sie in den Microsoft Search-Ergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="81d6a-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="81d6a-106">Dieses Feature erweitert die Typen von Inhaltsquellen, die in Ihren Microsoft 365-Produktivitäts-Apps und dem umfassenderen Microsoft-Ökosystem durchsuchbar sind.</span><span class="sxs-lookup"><span data-stu-id="81d6a-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="81d6a-107">Die Drittanbieterdaten können lokal oder in öffentlichen oder privaten Clouds gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="81d6a-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="81d6a-108">Dieser Artikel soll Microsoft 365-Administratoren dabei helfen, die verfügbaren Ressourcen für die Beantwortung der folgenden Fragen zu finden:</span><span class="sxs-lookup"><span data-stu-id="81d6a-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="81d6a-109">Welche Datenquellen können mit Microsoft Search verbunden werden?</span><span class="sxs-lookup"><span data-stu-id="81d6a-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="81d6a-110">Wie verwalte ich meine Verbindungen?</span><span class="sxs-lookup"><span data-stu-id="81d6a-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="81d6a-111">Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Graph-Connectors?</span><span class="sxs-lookup"><span data-stu-id="81d6a-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="81d6a-112">Was sind die Vorschaufeatures?</span><span class="sxs-lookup"><span data-stu-id="81d6a-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="81d6a-113">Wie kann ich Suchergebnisse anpassen und konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="81d6a-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="81d6a-114">Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?</span><span class="sxs-lookup"><span data-stu-id="81d6a-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="81d6a-115">Microsoft Graph Connectors und Microsoft Search-APIs sind jetzt allgemein verfügbar.</span><span class="sxs-lookup"><span data-stu-id="81d6a-115">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="81d6a-116">Die ersten Rollouts sind für Kunden, die für die gezielte Veröffentlichung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="81d6a-116">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="81d6a-117">Wenn Sie einen Graph Connector in Ihrem Mandanten verwenden möchten, müssen Sich Benutzer und Administratoren für die [Zielversion entscheiden.](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="81d6a-117">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).</span></span>

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="81d6a-118">Welche Datenquellen können mit Microsoft Search verbunden werden?</span><span class="sxs-lookup"><span data-stu-id="81d6a-118">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="81d6a-119">Microsoft bietet 9 Graph-Connectors, und unsere Ökosystempartner haben mehr als 100 weitere Graph Connectors erstellt.</span><span class="sxs-lookup"><span data-stu-id="81d6a-119">Microsoft provides 9 Graph connectors and our ecosystem partners have created over 100 more Graph connectors.</span></span> <span data-ttu-id="81d6a-120">Sie können auch einen eigenen Graph-Connector erstellen.</span><span class="sxs-lookup"><span data-stu-id="81d6a-120">You can also build your own Graph connector.</span></span>

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="81d6a-121">Microsoft Graph-Connectors</span><span class="sxs-lookup"><span data-stu-id="81d6a-121">Graph connectors by Microsoft</span></span>

<span data-ttu-id="81d6a-122">Sie können mithilfe von von Microsoft erstellten Graph-Connectors eine Verbindung mit den folgenden Datenquellen herstellen:</span><span class="sxs-lookup"><span data-stu-id="81d6a-122">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="81d6a-123">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="81d6a-123">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="81d6a-124">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="81d6a-124">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="81d6a-125">Azure SQL und Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="81d6a-125">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="81d6a-126">Unternehmenswebsites</span><span class="sxs-lookup"><span data-stu-id="81d6a-126">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="81d6a-127">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="81d6a-127">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="81d6a-128">Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="81d6a-128">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="81d6a-129">Oracle SQL (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="81d6a-129">Oracle SQL (preview)</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="81d6a-130">Salesforce (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="81d6a-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="81d6a-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="81d6a-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="81d6a-132">Der [Graph Connectors Gallery](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen Graph-Connectors.</span><span class="sxs-lookup"><span data-stu-id="81d6a-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="81d6a-133">Wenn Sie bereit sind, eine dieser Datenquellen mit Ihrem Mandanten [](configure-connector.md) zu verbinden, lesen Sie unbedingt die Setupübersicht und alle anderen Artikel im Abschnitt "Setupconnectors von Microsoft", die für Ihre Datenquelle gelten.</span><span class="sxs-lookup"><span data-stu-id="81d6a-133">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="81d6a-134">Graph connectors von unseren Partnern</span><span class="sxs-lookup"><span data-stu-id="81d6a-134">Graph connectors by our partners</span></span>

<span data-ttu-id="81d6a-135">Der [Microsoft Graph Connectors Gallery](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen von unseren Partnern erstellten Graph-Connectors sowie einen Link zur Website der einzelnen Partner.</span><span class="sxs-lookup"><span data-stu-id="81d6a-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief description of each of the Graph connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="81d6a-136">Um mehr zu erfahren, wenden Sie sich direkt an jeden Partner.</span><span class="sxs-lookup"><span data-stu-id="81d6a-136">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="81d6a-137">Erstellen Eines eigenen Graph-Connectors</span><span class="sxs-lookup"><span data-stu-id="81d6a-137">Build your own Graph connector</span></span>

<span data-ttu-id="81d6a-138">Sie können einen eigenen Graph-Connector erstellen, wenn Sie es vorziehen.</span><span class="sxs-lookup"><span data-stu-id="81d6a-138">You can build your own Graph connector if you prefer.</span></span> <span data-ttu-id="81d6a-139">Weitere Informationen zum Erstellen von Graph Connectors finden Sie in der Übersicht über die [Microsoft Search-API in Microsoft Graph.](https://docs.microsoft.com/graph/search-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="81d6a-139">For more information on building Graph connectors, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="81d6a-140">Wie verwalte ich meine Verbindungen?</span><span class="sxs-lookup"><span data-stu-id="81d6a-140">How do I manage my connections?</span></span>

<span data-ttu-id="81d6a-141">Sie können Ihre Verbindungen über die Registerkarte ["Connectors"](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) im [Microsoft 365 Admin Center verwalten.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="81d6a-141">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="81d6a-142">Weitere Informationen zum Verwalten von Verbindungen finden Sie unter: [Verwalten Ihrer Verbindungen.](manage-connector.md)</span><span class="sxs-lookup"><span data-stu-id="81d6a-142">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="81d6a-143">Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Graph-Connectors?</span><span class="sxs-lookup"><span data-stu-id="81d6a-143">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="81d6a-144">Sie benötigen eine gültige Microsoft 365- oder Office 365-Lizenz und ein ausreichendes Graph Connectors-Kontingent, damit Benutzer in Ihrer Organisation Daten von Connectors in ihren Suchergebnissen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="81d6a-144">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="81d6a-145">Weitere Informationen finden Sie unter [Lizenzanforderungen, Preise](licensing.md) und [Nutzungsbedingungen.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="81d6a-145">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="81d6a-146">Was sind die Vorschaufeatures?</span><span class="sxs-lookup"><span data-stu-id="81d6a-146">What are the preview features?</span></span>

<span data-ttu-id="81d6a-147">Obwohl Microsoft Graph Connectors und Microsoft Search-APIs jetzt allgemein verfügbar sind, gibt es mehrere Features, die sich in der Vorschau befinden.</span><span class="sxs-lookup"><span data-stu-id="81d6a-147">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="81d6a-148">Zu den Konnektoren und Features in der Vorschau gehören:</span><span class="sxs-lookup"><span data-stu-id="81d6a-148">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="81d6a-149">Azure DevOps Connector</span><span class="sxs-lookup"><span data-stu-id="81d6a-149">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="81d6a-150">Salesforce Connector</span><span class="sxs-lookup"><span data-stu-id="81d6a-150">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="81d6a-151">[ServiceNow Connector mit](servicenow-connector.md) Suchberechtigungen, die Quell-ACLs verwenden</span><span class="sxs-lookup"><span data-stu-id="81d6a-151">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="81d6a-152">Verwalten von Ergebnisclusters</span><span class="sxs-lookup"><span data-stu-id="81d6a-152">Manage result cluster</span></span>](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="81d6a-153">Wie kann ich Suchergebnisse anpassen und konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="81d6a-153">How do I customize and configure search results?</span></span>

<span data-ttu-id="81d6a-154">Es gibt viele Möglichkeiten zum Anpassen und Konfigurieren von Suchergebnissen.</span><span class="sxs-lookup"><span data-stu-id="81d6a-154">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="81d6a-155">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="81d6a-155">See the following articles to learn more:</span></span>

* [<span data-ttu-id="81d6a-156">Branchen und Ergebnistypen verwalten</span><span class="sxs-lookup"><span data-stu-id="81d6a-156">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="81d6a-157">Verwalten von Layouts für Suchergebnisse</span><span class="sxs-lookup"><span data-stu-id="81d6a-157">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="81d6a-158">Verwalten von Ergebnisclusters</span><span class="sxs-lookup"><span data-stu-id="81d6a-158">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="81d6a-159">Verwalten benutzerdefinierter Filter</span><span class="sxs-lookup"><span data-stu-id="81d6a-159">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="81d6a-160">Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?</span><span class="sxs-lookup"><span data-stu-id="81d6a-160">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="81d6a-161">Nachdem benutzerdefinierte Daten indiziert wurden, können Entwickler [diese Daten abfragen.](https://docs.microsoft.com/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="81d6a-161">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="81d6a-162">Sie können Ihre Daten in jeder Anwendung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="81d6a-162">You can view your data in any application.</span></span> <span data-ttu-id="81d6a-163">Weitere Informationen finden Sie in der [Übersicht über die Microsoft Search-API in Microsoft Graph.](https://docs.microsoft.com/graph/search-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="81d6a-163">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="next-steps"></a><span data-ttu-id="81d6a-164">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="81d6a-164">Next steps</span></span>

<span data-ttu-id="81d6a-165">Stellen Sie sicher, dass Sie die Suchergebnisse wie in diesem Artikel empfohlen anpassen. Wie kann ich [Suchergebnisse anpassen und konfigurieren?](#how-do-i-customize-and-configure-search-results)</span><span class="sxs-lookup"><span data-stu-id="81d6a-165">Make sure you customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="81d6a-166">Weitere Informationen zum Anpassen von Suchergebnissen finden Sie auf [der Seite "Suchergebnisse anpassen".](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)</span><span class="sxs-lookup"><span data-stu-id="81d6a-166">To learn more about customizing search results, see [Customize the search results page](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).</span></span>

## <a name="limitations"></a><span data-ttu-id="81d6a-167">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="81d6a-167">Limitations</span></span>

* <span data-ttu-id="81d6a-168">Wenn Sie **einen** von Microsoft erstellten Connector veröffentlichen, kann es einige Minuten dauern, bis die Verbindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="81d6a-168">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="81d6a-169">Während dieser Zeit zeigt die Verbindung ihren Status als ausstehend an.</span><span class="sxs-lookup"><span data-stu-id="81d6a-169">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="81d6a-170">Das [Microsoft 365 Admin Center](https://admin.microsoft.com) unterstützt  die Bearbeitung des Suchschemas nach der Veröffentlichung einer Verbindung nicht.</span><span class="sxs-lookup"><span data-stu-id="81d6a-170">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="81d6a-171">Um das Suchschema zu bearbeiten, löschen Sie Ihre Verbindung, und erstellen Sie dann eine neue.</span><span class="sxs-lookup"><span data-stu-id="81d6a-171">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="81d6a-172">Der Erfassungsdurchsatz wird bei etwa vier Elementen pro Sekunde gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="81d6a-172">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="81d6a-173">Schemaupdates werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="81d6a-173">There is no support for schema updates.</span></span> <span data-ttu-id="81d6a-174">Nachdem Sie eine Verbindungseinrichtung erstellt haben, gibt es keine Möglichkeit, das Schema zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="81d6a-174">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="81d6a-175">Sie können die Verbindung nur löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="81d6a-175">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="81d6a-176">Es gibt ein Verbindungslimit.</span><span class="sxs-lookup"><span data-stu-id="81d6a-176">There is a connections limit.</span></span> <span data-ttu-id="81d6a-177">Jeder Mandant kann bis zu 10 Verbindungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="81d6a-177">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="81d6a-178">Die Bearbeitungsunterstützung für die Verbindung ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="81d6a-178">Edit support for connection is not available.</span></span> <span data-ttu-id="81d6a-179">Nachdem die Verbindung erstellt wurde, können Sie sie nicht mehr bearbeiten oder ändern.</span><span class="sxs-lookup"><span data-stu-id="81d6a-179">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="81d6a-180">Wenn Sie Details ändern müssen, müssen Sie die Verbindung löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="81d6a-180">If you need to change any details, you must delete and recreate the connection.</span></span>
