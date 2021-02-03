---
title: Ergebniscluster für Connectors
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
description: Details zur Connectorergebnisclustererfahrung
ms.openlocfilehash: fb29fb9c14811698fb7c5d043853b57231c76a0b
ms.sourcegitcommit: d1bc6c41ecf47584373ce57543502bed55753d0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080837"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="c6b58-103">Ergebniscluster für Graph connectors</span><span class="sxs-lookup"><span data-stu-id="c6b58-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="c6b58-104">Übersicht über den Ergebniscluster "Graph Connectors" (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c6b58-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="c6b58-105">Mit Ergebnisclustern für Graph Connectors können Unternehmen in ihrer Standardansicht, auf der Registerkarte "Alle", in SharePoint, Office.com und Microsoft Search in Bing nach Inhalten aus Drittanbieterdatenquellen suchen. </span><span class="sxs-lookup"><span data-stu-id="c6b58-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="c6b58-106">Ergebniscluster helfen Benutzern, alle Inhalte von Drittanbietern an einem Ort zu finden.</span><span class="sxs-lookup"><span data-stu-id="c6b58-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="c6b58-107">Die in einem Ergebniscluster angezeigten Ergebnisse werden basierend auf der Suchkonfiguration gruppiert.</span><span class="sxs-lookup"><span data-stu-id="c6b58-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="c6b58-108">Auswahl und Anzeige von Connectorergebnissen</span><span class="sxs-lookup"><span data-stu-id="c6b58-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="c6b58-109">Die im Ergebniscluster bereitgestellten Konnektorergebnisse werden von einzelnen Such vertikal mit Connectorinhalt abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="c6b58-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="c6b58-110">Jede Such vertikal stellt eine Reihe relevanter Ergebnisse zur Wahl eines Ergebnisclusters zur Wahl.</span><span class="sxs-lookup"><span data-stu-id="c6b58-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="c6b58-111">Relevante Ergebnisse werden basierend auf der "title"-Eigenschaft und der "content"-Eigenschaft jedes Elements ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="c6b58-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="c6b58-112">Die Inhaltseigenschaft ist im Schema *als "isContent=true"* gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="c6b58-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="c6b58-113">Um die Suche nach Inhalten aus den Such vertikal sicherzustellen, wird empfohlen, aussagekräftige Titel für Ihre Elemente zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="c6b58-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="c6b58-114">Dies wirkt sich positiv auf die Vermittlung von Ergebnisclusterkandidaten und die Wahrscheinlichkeit aus, dass Ihre Inhalte in einem Ergebniscluster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6b58-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="c6b58-115">Vermeiden Sie beispielsweise die Verwendung von IDs als Werte für die Eigenschaft "title", es sei denn, Ihre Benutzer verwenden IDs, um nach Inhalten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c6b58-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="c6b58-116">Wie oft ein Ergebniscluster angezeigt wird, hängt von Faktoren ab, z. B. von der Anzahl der konfigurierten Such vertikaler Suchressourcen und vom Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="c6b58-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="c6b58-117">Durch die Interaktion oder das Ignorieren eines Ergebnisclusters stellen Benutzer implizit Hinweise zur Verfügung, mit denen die Auslösung im Laufe der Zeit angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="c6b58-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="c6b58-118">Die Suchergebniserfahrung für Connectorelemente, die in Ihrem Ergebniscluster angezeigt werden, verwendet [von](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) Ihnen definierte Ergebnistypen.</span><span class="sxs-lookup"><span data-stu-id="c6b58-118">The search result experience for connector items shown in your result cluster uses [result types](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="c6b58-119">Wenn kein Ergebnistyp konfiguriert ist, wird ein vom System [generiertes](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) Layout verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6b58-119">If no result type is configured, a [system generated layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="c6b58-120">Es wird empfohlen, die Eigenschaft "title" als Suchergebnistitel und die Eigenschaft "content" als Suchbeschreibung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6b58-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="c6b58-121">Dies bietet den Benutzern die beste Benutzererfahrung durch genaues Auslösen des Ergebnisclusters und relevanteste Ergebnisse im Cluster.</span><span class="sxs-lookup"><span data-stu-id="c6b58-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="c6b58-122">Aktivieren von Ergebnisclustern</span><span class="sxs-lookup"><span data-stu-id="c6b58-122">Enable result clusters</span></span>
  
<span data-ttu-id="c6b58-123">Die Ergebnisclustererfahrung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c6b58-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="c6b58-124">Führen Sie die folgenden Schritte aus, um die Benutzererfahrung auf Organisationsebene zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="c6b58-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="c6b58-125">Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**"Vertikal".**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)</span><span class="sxs-lookup"><span data-stu-id="c6b58-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="c6b58-126">Wählen Sie die **Vertikale "Alle"** aus, und aktivieren **Sie dann "Connectorergebnisse anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="c6b58-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="c6b58-127">Führen Sie die folgenden Schritte aus, um die Benutzererfahrung auf der Ebene der SharePoint-Website zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="c6b58-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="c6b58-128">Wechseln Sie auf der SharePoint-Website, auf der Sie die Ergebnisclustererfahrung wünschen, zu **"Einstellungen".**</span><span class="sxs-lookup"><span data-stu-id="c6b58-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="c6b58-129">Wechseln Sie zu **Websiteinformationen** > **Anzeigen aller Websiteeinstellungen.**</span><span class="sxs-lookup"><span data-stu-id="c6b58-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="c6b58-130">Wechseln Sie zum Microsoft Search-Abschnitt, und wählen Sie dann **"Microsoft Search für diese Websitesammlung konfigurieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="c6b58-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="c6b58-131">Wechseln Sie im Navigationsbereich zu **"Benutzerdefiniert",** und wählen Sie dann **"Vertikal" aus.**</span><span class="sxs-lookup"><span data-stu-id="c6b58-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="c6b58-132">Wählen Sie die **Vertikale "Alle"** aus, und aktivieren **Sie dann "Connectorergebnisse anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="c6b58-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="c6b58-133">Anzeigen der Ergebnisclustererfahrung nach der Aktivierung</span><span class="sxs-lookup"><span data-stu-id="c6b58-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="c6b58-134">Nachdem Sie die Ergebnisclustererfahrung aktivieren, kann es bis zu 12 Stunden dauern, bis Sie sie anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="c6b58-134">After you turn on the result cluster experience, it can take up to 12 hours before you can view it.</span></span> <span data-ttu-id="c6b58-135">Wenn sie sofort angezeigt werden soll, können Sie *cacheClear=true* an die URL in SharePoint und Office anfügen.</span><span class="sxs-lookup"><span data-stu-id="c6b58-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
