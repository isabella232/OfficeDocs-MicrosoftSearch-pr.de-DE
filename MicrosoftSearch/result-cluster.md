---
title: Ergebnis Cluster "Connectors"
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Details der Connectors result Cluster Experience
ms.openlocfilehash: f2355213a0b1821968c801153841c274e539d72e
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773027"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="b2176-103">Ergebnis Cluster "Graph Connectors"</span><span class="sxs-lookup"><span data-stu-id="b2176-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="b2176-104">Übersicht über den Ergebnis Cluster "Graph Connectors" (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="b2176-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="b2176-105">Mit Graph Connectors result Clusters können Unternehmen in Ihrer Standardansicht, der Registerkarte **alle** , in SharePoint, Office.com und Microsoft Search in Bing nach Inhalten von Drittanbieter-Datenquellen suchen.</span><span class="sxs-lookup"><span data-stu-id="b2176-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="b2176-106">Ergebnis Cluster helfen Benutzern, alle Inhalte von Drittanbietern an einer einzigen Stelle zu entdecken.</span><span class="sxs-lookup"><span data-stu-id="b2176-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="b2176-107">Die in einem Ergebnis Cluster angezeigten Ergebnisse werden basierend auf der Such vertikalen Konfiguration zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="b2176-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="b2176-108">Auswählen und Anzeigen von Verbindungs Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="b2176-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="b2176-109">Die im Ergebnis Cluster bereitgestellten Connector-Ergebnisse werden von einzelnen Such vertikalen mit Connector-Inhalten abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="b2176-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="b2176-110">Jede vertikale Suche enthält eine Reihe relevanter Ergebnisse, die zu einem Kandidaten Ergebnis Cluster werden.</span><span class="sxs-lookup"><span data-stu-id="b2176-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="b2176-111">Relevante Ergebnisse werden basierend auf der Eigenschaft "Title" und der Eigenschaft "Content" jedes Elements ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="b2176-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="b2176-112">Die Content-Eigenschaft wird im Schema als *iscontent = true* gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="b2176-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="b2176-113">Um sicherzustellen, dass Inhalte aus den Such vertikalen gefunden werden, wird empfohlen, aussagekräftige Titel für ihre Elemente bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b2176-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="b2176-114">Dies wirkt sich positiv auf das Schiedsverfahren von Ergebnis Cluster Kandidaten und die Wahrscheinlichkeit aus, dass Ihre Inhalte in einem Ergebnis Cluster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b2176-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="b2176-115">Vermeiden Sie beispielsweise die Verwendung von IDs als Werte für die Eigenschaft "Title", es sei denn, Ihre Benutzer verwenden IDs, um nach Inhalten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b2176-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="b2176-116">Wie oft ein Ergebnis Cluster angezeigt wird, hängt von Faktoren wie der Anzahl der von Ihnen konfigurierten Such vertikalen Elementen und dem Typ des Inhalts ab.</span><span class="sxs-lookup"><span data-stu-id="b2176-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="b2176-117">Durch Interaktion oder Ignorierung eines Ergebnis Clusters geben Benutzer implizit Hinweise an, mit denen die Auslösung im Laufe der Zeit angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="b2176-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="b2176-118">Die Suchergebnis Erfahrung für Konnektoren, die im Ergebnis Cluster angezeigt werden, verwendet [Ergebnistypen](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) , die von Ihnen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b2176-118">The search result experience for connector items shown in your result cluster uses [result types](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="b2176-119">Wenn kein Ergebnistyp konfiguriert ist, wird ein vom [System generiertes Layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2176-119">If no result type is configured, a [system generated layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="b2176-120">Es wird empfohlen, die Eigenschaft "Title" als Suchergebnis Titel und die Eigenschaft "Inhalt" als Such Beschreibung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2176-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="b2176-121">Dadurch erhalten Ihre Benutzer die beste Erfahrung durch eine genaue Auslösung des Ergebnis Clusters und der relevantesten Ergebnisse im Cluster.</span><span class="sxs-lookup"><span data-stu-id="b2176-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="b2176-122">Ergebnis Cluster aktivieren</span><span class="sxs-lookup"><span data-stu-id="b2176-122">Enable result clusters</span></span>
  
<span data-ttu-id="b2176-123">Die Ergebnis Cluster Erfahrung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b2176-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="b2176-124">Führen Sie die folgenden Schritte aus, um die Benutzeroberfläche auf Organisationsebene zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="b2176-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="b2176-125">Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**vertikal**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="b2176-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="b2176-126">Wählen Sie die Option **alle** vertikal aus, und aktivieren Sie dann **Show Connector results**.</span><span class="sxs-lookup"><span data-stu-id="b2176-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="b2176-127">Führen Sie die folgenden Schritte aus, um die Benutzerfreundlichkeit auf der SharePoint-Websiteebene zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="b2176-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="b2176-128">Wechseln Sie auf der SharePoint-Website, auf der Sie das Ergebnis-Cluster-Erlebnis wünschen, zu **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="b2176-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="b2176-129">Wechseln Sie zu **Website Informationen** > **Alle Websiteeinstellungen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="b2176-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="b2176-130">Wechseln Sie zum Abschnitt Microsoft-Suche, und wählen Sie dann **Microsoft-Suche für diese Websitesammlung konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="b2176-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="b2176-131">Wechseln Sie im Navigationsbereich zu **benutzerdefiniertes Erlebnis**, und wählen Sie dann **vertikal** aus.</span><span class="sxs-lookup"><span data-stu-id="b2176-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="b2176-132">Wählen Sie die Option **alle** vertikal aus, und aktivieren Sie dann **Show Connector results**.</span><span class="sxs-lookup"><span data-stu-id="b2176-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="b2176-133">Anzeigen der Ergebnis Cluster Erfahrung nach der Aktivierung</span><span class="sxs-lookup"><span data-stu-id="b2176-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="b2176-134">Nachdem Sie die Ergebnis Cluster Erfahrung aktiviert haben, kann es einige Minuten dauern, bis Sie Sie anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="b2176-134">After you turn on the result cluster experience, it might take a few minutes before you can view it.</span></span> <span data-ttu-id="b2176-135">Wenn Sie die Benutzeroberfläche sofort nutzen möchten, können Sie *cacheClear = true* an die URL in SharePoint und Office anfügen.</span><span class="sxs-lookup"><span data-stu-id="b2176-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
