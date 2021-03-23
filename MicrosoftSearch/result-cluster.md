---
title: Connectors-Ergebniscluster
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
description: Details zur Connector-Ergebniscluster-Erfahrung
ms.openlocfilehash: ae5528f2e12c9e331b66e821f2a9c03947d788df
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031773"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="2cc98-103">Ergebniscluster für Graphconnectors</span><span class="sxs-lookup"><span data-stu-id="2cc98-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="2cc98-104">Übersicht über den Graph Connectors-Ergebniscluster (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="2cc98-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="2cc98-105">Mit Ergebnisclustern von Graph Connectors können Unternehmen in ihrer Standardansicht, auf der Registerkarte **Alle,** in SharePoint, Office.com und Microsoft Search in Bing nach Inhalten aus Datenquellen von Drittanbietern suchen.</span><span class="sxs-lookup"><span data-stu-id="2cc98-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="2cc98-106">Ergebniscluster helfen Benutzern, alle Inhalte von Drittanbietern an einem Ort zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="2cc98-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="2cc98-107">Die in einem Ergebniscluster angezeigten Ergebnisse werden basierend auf der vertikalen Suchkonfiguration gruppiert.</span><span class="sxs-lookup"><span data-stu-id="2cc98-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="2cc98-108">Auswahl und Anzeige von Connectorergebnissen</span><span class="sxs-lookup"><span data-stu-id="2cc98-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="2cc98-109">Im Ergebniscluster bereitgestellte Connectorergebnisse werden von einzelnen Such vertikal mit Connectorinhalt abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="2cc98-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="2cc98-110">Jede Such vertikal bietet eine Reihe relevanter Ergebnisse, die zu einem Kandidatenergebniscluster werden.</span><span class="sxs-lookup"><span data-stu-id="2cc98-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="2cc98-111">Relevante Ergebnisse werden basierend auf der "title"-Eigenschaft und der "content"-Eigenschaft jedes Elements ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="2cc98-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="2cc98-112">Die Content-Eigenschaft wird im *Schema als isContent=true* markiert.</span><span class="sxs-lookup"><span data-stu-id="2cc98-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="2cc98-113">Um sicherzustellen, dass Inhalte aus den Such vertikal gefunden werden, wird empfohlen, aussagekräftige Titel für Ihre Elemente zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="2cc98-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="2cc98-114">Dies wirkt sich positiv auf die Vermittlung von Ergebnisclusterkandidaten und die Wahrscheinlichkeit aus, dass Ihre Inhalte in einem Ergebniscluster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2cc98-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="2cc98-115">Vermeiden Sie beispielsweise die Verwendung von IDs als Werte für die Eigenschaft "title", es sei denn, Ihre Benutzer verwenden IDs, um nach Inhalten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="2cc98-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="2cc98-116">Wie oft ein Ergebniscluster angezeigt wird, hängt von Faktoren ab, z. B. von der Anzahl der konfigurierten Such vertikaler Suchtypen und dem Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="2cc98-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="2cc98-117">Durch die Interaktion oder das Ignorieren eines Ergebnisclusters geben Benutzer implizit Hinweise, die ihre Auslösung im Laufe der Zeit anpassen.</span><span class="sxs-lookup"><span data-stu-id="2cc98-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="2cc98-118">Die Suchergebniserfahrung für Connectorelemente, die in Ihrem Ergebniscluster angezeigt werden, verwendet [von](./customize-search-page.md#create-your-own-result-type) Ihnen definierte Ergebnistypen.</span><span class="sxs-lookup"><span data-stu-id="2cc98-118">The search result experience for connector items shown in your result cluster uses [result types](./customize-search-page.md#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="2cc98-119">Wenn kein Ergebnistyp konfiguriert ist, wird [ein vom System generiertes Layout](./customize-search-page.md#default-search-result-layout) verwendet.</span><span class="sxs-lookup"><span data-stu-id="2cc98-119">If no result type is configured, a [system generated layout](./customize-search-page.md#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="2cc98-120">Es wird empfohlen, die "title"-Eigenschaft als Suchergebnistitel und die "content"-Eigenschaft als Suchbeschreibung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2cc98-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="2cc98-121">Dies bietet den Benutzern die beste Erfahrung durch genaues Auslösen des Ergebnisclusters und der relevantesten Ergebnisse im Cluster.</span><span class="sxs-lookup"><span data-stu-id="2cc98-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="2cc98-122">Aktivieren von Ergebnisclustern</span><span class="sxs-lookup"><span data-stu-id="2cc98-122">Enable result clusters</span></span>
  
<span data-ttu-id="2cc98-123">Die Ergebnisclustererfahrung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2cc98-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="2cc98-124">Führen Sie die folgenden Schritte aus, um die Benutzererfahrung auf Organisationsebene zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2cc98-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="2cc98-125">Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="2cc98-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="2cc98-126">Wählen Sie die **Vertikale Alle** aus, und aktivieren Sie **dann Konnektorergebnisse anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="2cc98-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="2cc98-127">Führen Sie die folgenden Schritte aus, um die Benutzererfahrung auf SharePoint-Websiteebene zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2cc98-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="2cc98-128">Wechseln Sie auf der SharePoint-Website, auf der Sie die Ergebnisclustererfahrung wünschen, zu **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="2cc98-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="2cc98-129">Wechseln Sie zu **Websiteinformationen** > **Alle Websiteeinstellungen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2cc98-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="2cc98-130">Wechseln Sie zum Abschnitt Microsoft Search, und wählen Sie **Dann Konfigurieren von Microsoft Search für diese Websitesammlung aus.**</span><span class="sxs-lookup"><span data-stu-id="2cc98-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="2cc98-131">Wechseln Sie im Navigationsbereich zu **Benutzerdefinierte Benutzerdefinierte Benutzererfahrung,** und wählen Sie **dann Vertikal aus.**</span><span class="sxs-lookup"><span data-stu-id="2cc98-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="2cc98-132">Wählen Sie die **Vertikale Alle** aus, und aktivieren Sie **dann Konnektorergebnisse anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="2cc98-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="2cc98-133">Anzeigen der Ergebnisclustererfahrung nach der Aktivierung</span><span class="sxs-lookup"><span data-stu-id="2cc98-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="2cc98-134">Nachdem Sie die Ergebnisclustererfahrung aktivieren, kann es bis zu 12 Stunden dauern, bis Sie sie anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="2cc98-134">After you turn on the result cluster experience, it can take up to 12 hours before you can view it.</span></span> <span data-ttu-id="2cc98-135">Wenn Sie die Erfahrung sofort wünschen, können Sie *cacheClear=true* an die URL in SharePoint und Office anhängen.</span><span class="sxs-lookup"><span data-stu-id="2cc98-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>