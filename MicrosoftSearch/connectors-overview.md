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
description: Übersicht über Microsoft Graph Connectors für Microsoft Search
ms.openlocfilehash: 87645e32e274eb166d6ba008c4ac720667105a1f
ms.sourcegitcommit: 52129e0129a201ec056903b2461d012fda6d3636
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383483"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="939fa-103">Übersicht über Microsoft Graph-Connectors</span><span class="sxs-lookup"><span data-stu-id="939fa-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="939fa-104">[Microsoft Search](./overview-microsoft-search.md) indiziert alle [Microsoft 365](https://www.microsoft.com/microsoft-365) Daten, damit sie für Benutzer durchsucht werden können.</span><span class="sxs-lookup"><span data-stu-id="939fa-104">[Microsoft Search](./overview-microsoft-search.md) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="939fa-105">Mit Microsoft Graph Connectors kann Ihre Organisation Drittanbieterdaten so indizieren, dass sie in Microsoft Search Ergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="939fa-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="939fa-106">Dieses Feature erweitert die Arten von Inhaltsquellen, die in Ihren Microsoft 365-Produktivitäts-Apps und im breiteren Microsoft-Ökosystem durchsuchbar sind.</span><span class="sxs-lookup"><span data-stu-id="939fa-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="939fa-107">Die Drittanbieterdaten können lokal oder in den öffentlichen oder privaten Clouds gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="939fa-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="939fa-108">Dieser Artikel soll Microsoft 365 Administratoren dabei helfen, die Ressourcen zu finden, die für die Beantwortung der folgenden Fragen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="939fa-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="939fa-109">Welche Datenquellen können mit Microsoft Search verbunden werden?</span><span class="sxs-lookup"><span data-stu-id="939fa-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="939fa-110">Wie verwalte ich meine Verbindungen?</span><span class="sxs-lookup"><span data-stu-id="939fa-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="939fa-111">Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Microsoft Graph Connectors?</span><span class="sxs-lookup"><span data-stu-id="939fa-111">What are the license requirements and terms of use for Microsoft Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [<span data-ttu-id="939fa-112">Was sind die Vorschaufeatures?</span><span class="sxs-lookup"><span data-stu-id="939fa-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="939fa-113">Wie kann ich Suchergebnisse anpassen und konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="939fa-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="939fa-114">Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?</span><span class="sxs-lookup"><span data-stu-id="939fa-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)
* [<span data-ttu-id="939fa-115">Wie kann ich Suchergebnisse anpassen?</span><span class="sxs-lookup"><span data-stu-id="939fa-115">How do I customize search results?</span></span>](#how-do-i-customize-search-results)
* [<span data-ttu-id="939fa-116">Was sind die Connectoreinschränkungen?</span><span class="sxs-lookup"><span data-stu-id="939fa-116">What are the connector limitations</span></span>](#what-are-the-connector-limitations)

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="939fa-117">Welche Datenquellen können mit Microsoft Search verbunden werden?</span><span class="sxs-lookup"><span data-stu-id="939fa-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="939fa-118">Microsoft bietet 9 Connectors an, und unsere Ökosystempartner haben über 100 weitere Connectors erstellt.</span><span class="sxs-lookup"><span data-stu-id="939fa-118">Microsoft provides 9 connectors and our ecosystem partners have created over 100 more connectors.</span></span> <span data-ttu-id="939fa-119">Sie können auch einen eigenen Connector erstellen.</span><span class="sxs-lookup"><span data-stu-id="939fa-119">You can also build your own connector.</span></span>

### <a name="microsoft-graph-connectors-by-microsoft"></a><span data-ttu-id="939fa-120">Microsoft Graph Connectors von Microsoft</span><span class="sxs-lookup"><span data-stu-id="939fa-120">Microsoft Graph connectors by Microsoft</span></span>

<span data-ttu-id="939fa-121">Sie können über von Microsoft erstellte Connectors eine Verbindung mit den folgenden Datenquellen herstellen:</span><span class="sxs-lookup"><span data-stu-id="939fa-121">You can connect to the following data sources using connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="939fa-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="939fa-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="939fa-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="939fa-123">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="939fa-124">Azure SQL und Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="939fa-124">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="939fa-125">Unternehmenswebsites</span><span class="sxs-lookup"><span data-stu-id="939fa-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="939fa-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="939fa-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="939fa-127">Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="939fa-127">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="939fa-128">Oracle SQL</span><span class="sxs-lookup"><span data-stu-id="939fa-128">Oracle SQL</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="939fa-129">Salesforce (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="939fa-129">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="939fa-130">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="939fa-130">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="939fa-131">Der [Microsoft Graph Connectors-Katalog](https://www.microsoft.com/microsoft-search/connectors) enthält eine kurze Beschreibung dieser Connectors.</span><span class="sxs-lookup"><span data-stu-id="939fa-131">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) contains a brief description of each of these connectors.</span></span> <span data-ttu-id="939fa-132">Wenn Sie bereit sind, eine dieser Datenquellen mit Ihrem Mandanten zu verbinden, lesen Sie unbedingt die [Setupübersicht](configure-connector.md) und alle anderen Artikel in den Setupconnectors von Microsoft, die für Ihre Datenquelle gelten.</span><span class="sxs-lookup"><span data-stu-id="939fa-132">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="microsoft-graph-connectors-by-our-partners"></a><span data-ttu-id="939fa-133">Microsoft Graph Connectors von unseren Partnern</span><span class="sxs-lookup"><span data-stu-id="939fa-133">Microsoft Graph connectors by our partners</span></span>

<span data-ttu-id="939fa-134">Der [Connectorkatalog](https://www.microsoft.com/microsoft-search/connectors) von Microsoft Graph enthält eine kurze Beschreibung der einzelnen Connectors, die von unseren Partnern erstellt wurden, sowie einen Link zur Website jedes Partners.</span><span class="sxs-lookup"><span data-stu-id="939fa-134">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) includes a brief description of each of the connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="939fa-135">Um mehr zu erfahren, wenden Sie sich direkt an jeden Partner.</span><span class="sxs-lookup"><span data-stu-id="939fa-135">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-microsoft-graph-connector"></a><span data-ttu-id="939fa-136">Erstellen Eines eigenen Microsoft Graph Connectors</span><span class="sxs-lookup"><span data-stu-id="939fa-136">Build your own Microsoft Graph connector</span></span>

<span data-ttu-id="939fa-137">Sie können bei Bedarf einen eigenen Connector erstellen.</span><span class="sxs-lookup"><span data-stu-id="939fa-137">You can build your own connector if you prefer.</span></span> <span data-ttu-id="939fa-138">Weitere Informationen zum Erstellen von Connectors finden Sie unter [Erstellen Ihres ersten benutzerdefinierten Microsoft Graph Connectors.](/graph/connecting-external-content-build-quickstart)</span><span class="sxs-lookup"><span data-stu-id="939fa-138">For more information on building connectors, see  [Build your first custom Microsoft Graph connector](/graph/connecting-external-content-build-quickstart).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="939fa-139">Wie verwalte ich meine Verbindungen?</span><span class="sxs-lookup"><span data-stu-id="939fa-139">How do I manage my connections?</span></span>

<span data-ttu-id="939fa-140">Sie können Ihre Verbindungen über die [Registerkarte Connectors](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) im [Microsoft 365 Admin Center](https://admin.microsoft.com/)verwalten.</span><span class="sxs-lookup"><span data-stu-id="939fa-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="939fa-141">Weitere Informationen zum Verwalten von Verbindungen finden Sie unter: [Verwalten Ihrer Verbindungen.](manage-connector.md)</span><span class="sxs-lookup"><span data-stu-id="939fa-141">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a><span data-ttu-id="939fa-142">Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Connectors?</span><span class="sxs-lookup"><span data-stu-id="939fa-142">What are the license requirements and terms of use for connectors?</span></span>

<span data-ttu-id="939fa-143">Sie benötigen eine gültige Microsoft 365- oder Office 365-Lizenz und ein ausreichendes Connectors-Kontingent für Benutzer in Ihrer Organisation, um Daten aus Connectors in ihren Suchergebnissen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="939fa-143">You need a valid Microsoft 365 or Office 365 license and sufficient connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="939fa-144">Weitere Informationen finden Sie unter [Lizenzanforderungen, Preise](licensing.md) und [Nutzungsbedingungen.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="939fa-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="939fa-145">Was sind die Vorschaufeatures?</span><span class="sxs-lookup"><span data-stu-id="939fa-145">What are the preview features?</span></span>

<span data-ttu-id="939fa-146">Obwohl Microsoft Graph Connectors und Microsoft Search-APIs jetzt allgemein verfügbar sind, gibt es mehrere Features, die sich in der Vorschau befinden.</span><span class="sxs-lookup"><span data-stu-id="939fa-146">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="939fa-147">Zu den Konnektoren und Features in der Vorschau gehören:</span><span class="sxs-lookup"><span data-stu-id="939fa-147">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="939fa-148">Azure DevOps-Connector</span><span class="sxs-lookup"><span data-stu-id="939fa-148">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="939fa-149">Salesforce-Connector</span><span class="sxs-lookup"><span data-stu-id="939fa-149">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="939fa-150">[ServiceNow-Connector](servicenow-connector.md) mit Suchberechtigungen, die Quell-ACLs verwenden</span><span class="sxs-lookup"><span data-stu-id="939fa-150">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="939fa-151">Verwalten von Ergebnisclusters</span><span class="sxs-lookup"><span data-stu-id="939fa-151">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="939fa-152">Mehrere Verbindungen in einer vertikalen</span><span class="sxs-lookup"><span data-stu-id="939fa-152">Multiple connections in a vertical</span></span>](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="939fa-153">Wie kann ich Suchergebnisse anpassen und konfigurieren?</span><span class="sxs-lookup"><span data-stu-id="939fa-153">How do I customize and configure search results?</span></span>

<span data-ttu-id="939fa-154">Es gibt viele Möglichkeiten zum Anpassen und Konfigurieren von Suchergebnissen.</span><span class="sxs-lookup"><span data-stu-id="939fa-154">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="939fa-155">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="939fa-155">See the following articles to learn more:</span></span>

* [<span data-ttu-id="939fa-156">Branchen und Ergebnistypen verwalten</span><span class="sxs-lookup"><span data-stu-id="939fa-156">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="939fa-157">Verwalten von Layouts für Suchergebnisse</span><span class="sxs-lookup"><span data-stu-id="939fa-157">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="939fa-158">Verwalten von Ergebnisclusters</span><span class="sxs-lookup"><span data-stu-id="939fa-158">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="939fa-159">Verwalten benutzerdefinierter Filter</span><span class="sxs-lookup"><span data-stu-id="939fa-159">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="939fa-160">Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?</span><span class="sxs-lookup"><span data-stu-id="939fa-160">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="939fa-161">Nachdem benutzerdefinierte Daten indiziert wurden, können Entwickler [diese Daten abfragen.](/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="939fa-161">After custom data is indexed, developers can [query this data](/graph/search-concept-custom-types).</span></span> <span data-ttu-id="939fa-162">Sie können Ihre Daten in einer beliebigen Anwendung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="939fa-162">You can view your data in any application.</span></span> <span data-ttu-id="939fa-163">Weitere Informationen finden Sie [in der Übersicht über die Microsoft Search-API in Microsoft Graph.](/graph/search-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="939fa-163">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-customize-search-results"></a><span data-ttu-id="939fa-164">Wie kann ich Suchergebnisse anpassen?</span><span class="sxs-lookup"><span data-stu-id="939fa-164">How do I customize search results?</span></span>

<span data-ttu-id="939fa-165">Der nächste Schritt besteht darin, die Suchergebnisse wie in diesem Artikel empfohlen [anzupassen. Wie kann ich Suchergebnisse anpassen und konfigurieren?](#how-do-i-customize-and-configure-search-results).</span><span class="sxs-lookup"><span data-stu-id="939fa-165">The next step is to customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="939fa-166">Weitere Informationen zum Anpassen von Suchergebnissen finden Sie unter [Anpassen der Suchergebnisseite.](customize-search-page.md)</span><span class="sxs-lookup"><span data-stu-id="939fa-166">To learn more about customizing search results, see [Customize the search results page](customize-search-page.md).</span></span>

## <a name="what-are-the-connector-limitations"></a><span data-ttu-id="939fa-167">Was sind die Connectoreinschränkungen?</span><span class="sxs-lookup"><span data-stu-id="939fa-167">What are the connector limitations?</span></span>

* <span data-ttu-id="939fa-168">Wenn Sie einen von Microsoft erstellten Connector **veröffentlichen,** kann es einige Minuten dauern, bis die Verbindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="939fa-168">When you **publish** a Microsoft-built connector, it can take a few minutes for the connection to be created.</span></span> <span data-ttu-id="939fa-169">Während dieser Zeit zeigt die Verbindung ihren Status als ausstehend an.</span><span class="sxs-lookup"><span data-stu-id="939fa-169">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="939fa-170">Der Aufnahmedurchsatz wird bei etwa vier Elementen pro Sekunde gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="939fa-170">Ingestion throughput is throttled at approximately four items per second.</span></span>

* <span data-ttu-id="939fa-171">Schemaupdates werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="939fa-171">There is no support for schema updates.</span></span> <span data-ttu-id="939fa-172">Nachdem Sie eine Verbindungseinrichtung erstellt haben, gibt es keine Möglichkeit, das Schema zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="939fa-172">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="939fa-173">Sie können die Verbindung nur löschen und erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="939fa-173">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="939fa-174">Es gibt einen Verbindungsgrenzwert.</span><span class="sxs-lookup"><span data-stu-id="939fa-174">There is a connection limit.</span></span> <span data-ttu-id="939fa-175">Jeder Mandant kann bis zu 10 Verbindungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="939fa-175">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="939fa-176">Sie können eine Verbindung nicht bearbeiten oder ändern, nachdem sie erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="939fa-176">You cannot edit or change a connection after it has been created.</span></span> <span data-ttu-id="939fa-177">Wenn Sie Details ändern müssen, müssen Sie die Verbindung löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="939fa-177">If you need to change any details, you must delete and recreate the connection.</span></span>
