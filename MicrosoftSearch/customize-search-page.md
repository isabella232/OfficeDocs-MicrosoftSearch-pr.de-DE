---
title: Anpassen der Seite "Microsoft-Suche"
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Hinzufügen von Such vertikalen und Anpassen von Suchergebnissen
ms.openlocfilehash: 87b394847281e43683f2ed9dfd42d19aa103d3e2
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949808"
---
# <a name="customize-the-microsoft-search-page"></a><span data-ttu-id="a5142-103">Anpassen der Seite "Microsoft-Suche"</span><span class="sxs-lookup"><span data-stu-id="a5142-103">Customize the Microsoft Search page</span></span>

<span data-ttu-id="a5142-104">Durch das Erstellen von Such vertikalen und Ergebnistypen können Sie die Suchergebnisse anpassen, die Benutzern angezeigt werden, wenn Sie in Bing nach **SharePoint**, **Office.com** und **Microsoft Search** suchen.</span><span class="sxs-lookup"><span data-stu-id="a5142-104">By creating search verticals and result types you can customize the search results that are shown to users when they search in **SharePoint**, **Office.com** and **Microsoft Search in Bing** .</span></span> <span data-ttu-id="a5142-105">Vertikals erleichtern Benutzern die Suche nach Informationen, für die Sie die Berechtigung erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="a5142-105">Verticals make it easier for users to find the information they’ve got permission to see.</span></span>  <span data-ttu-id="a5142-106">Sie können beispielsweise eine Such Sparte für Marketing Analyse Daten aus Drittanbietersoftware für Ihre Benutzer in der Marketingabteilung erstellen.</span><span class="sxs-lookup"><span data-stu-id="a5142-106">For example, you can create a search vertical for marketing analysis data from third-party software for your users in the marketing department.</span></span> <span data-ttu-id="a5142-107">Sie können auch Ergebnistypen definieren und das Layout für diese Daten anpassen.</span><span class="sxs-lookup"><span data-stu-id="a5142-107">You can also define result types and customize the layout for this data.</span></span>  

<span data-ttu-id="a5142-108">Sie können vertikale und Ergebnistypen auf diesen Ebenen erstellen:</span><span class="sxs-lookup"><span data-stu-id="a5142-108">You can create verticals and result types  at these levels:</span></span> 

- <span data-ttu-id="a5142-109">Organisationsebene – Wenn Sie eine vertikale auf Organisationsebene hinzufügen, wird Sie auf der Suchergebnisseite angezeigt, wenn Benutzer auf Ihrer SharePoint-Startseite, auf Office.com und auf Bing.com suchen.</span><span class="sxs-lookup"><span data-stu-id="a5142-109">Organization level – When you add a vertical at the organization level, it appears on the search results page when users search from their SharePoint start page, on Office.com and on Bing.com.</span></span> 
- <span data-ttu-id="a5142-110">Websiteebene – Sie möchten beispielsweise Ihren Kundendienstmitarbeitern die Suche nach "Severity 1"-Vorfällen direkt über die SharePoint-Website Ihrer Abteilung gestatten.</span><span class="sxs-lookup"><span data-stu-id="a5142-110">Site level – For example, you might want to allow your customer service employees to search for “Severity 1” incidents directly from their department’s SharePoint site.</span></span> 

## <a name="whats-a-search-vertical"></a><span data-ttu-id="a5142-111">Was ist eine vertikale Suche?</span><span class="sxs-lookup"><span data-stu-id="a5142-111">What’s a search vertical?</span></span>

<span data-ttu-id="a5142-112">Oben auf der Microsoft-Suchergebnisseite befindet sich eine Zeile mit Registerkarten, wobei es sich um vertikale Suchergebnisse handelt.</span><span class="sxs-lookup"><span data-stu-id="a5142-112">At the top of the Microsoft search results page there is a row of tabs, these are search verticals.</span></span> <span data-ttu-id="a5142-113">Bei einer Such vertikalen werden nur Ergebnisse eines bestimmten Typs oder bestimmter Inhalte angezeigt, beispielsweise nur Dateien oder Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a5142-113">A search vertical only shows results of a certain type or from certain content, for example only files or news.</span></span> <span data-ttu-id="a5142-114">Standardmäßig werden in der Microsoft-Suche die vertikalen alle, Personen, Dateien, Websites und Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5142-114">By default Microsoft Search shows the verticals All, People, Files, Sites, and News.</span></span>  

<span data-ttu-id="a5142-115">Sie können Such vertikale hinzufügen, die für Ihre Organisation relevant sind.</span><span class="sxs-lookup"><span data-stu-id="a5142-115">You can add search verticals that are relevant to your organization.</span></span> <span data-ttu-id="a5142-116">Diese werden auf der Microsoft-Suchergebnisseite in SharePoint, Office.com und Bing angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5142-116">These will appear on the Microsoft search results page in SharePoint, Office.com, and Bing.</span></span>  <span data-ttu-id="a5142-117">Sie können beispielsweise eine vertikale für marketingbezogene Inhalte und eine weitere für den Vertrieb erstellen, basierend auf der Art der Informationen, die jede Gruppe erhalten möchte.</span><span class="sxs-lookup"><span data-stu-id="a5142-117">For example, you could create one vertical for  marketing related content and another for sales, based on the type of information that each group would want to have.</span></span> <span data-ttu-id="a5142-118">Sie können vertikale Werte hinzufügen, um Ergebnisse nur aus Inhalten anzuzeigen, die über Connectors indiziert sind.</span><span class="sxs-lookup"><span data-stu-id="a5142-118">You can add verticals to show results only from content indexed via Connectors.</span></span>  

<span data-ttu-id="a5142-119">**Haftungsausschluss:** Vertikale und Ergebnistypen befinden sich derzeit in der Vorschau als Teil der Microsoft Connectors-Vorschau.</span><span class="sxs-lookup"><span data-stu-id="a5142-119">**DISCLAIMER:** Verticals and result types are currently in preview as a part of Microsoft Connectors preview.</span></span> <span data-ttu-id="a5142-120">Sie können keinen vertikalen Inhalt für Inhalte erstellen, die sich in SharePoint befinden, oder aus Inhalten, die durch den FileShare-Konnektor indiziert sind.</span><span class="sxs-lookup"><span data-stu-id="a5142-120">You cannot create a vertical for content residing in SharePoint or from content indexed by the FileShare connector.</span></span> <span data-ttu-id="a5142-121">Weitere Informationen zur Vorschau finden Sie unter [Connectors Preview](connectors-preview.md).</span><span class="sxs-lookup"><span data-stu-id="a5142-121">To find out more about the preview, see [Connectors Preview](connectors-preview.md).</span></span> <span data-ttu-id="a5142-122">Um an der Vorschau teilzunehmen, müssen Sie zuerst das [Anmeldeformular für Microsoft Graph Connectors Preview](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)einreichen.</span><span class="sxs-lookup"><span data-stu-id="a5142-122">To participate in the preview, you must first submit the [Microsoft Graph Connectors Preview Signup form](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="a5142-123">Dinge, die Sie beachten sollten...</span><span class="sxs-lookup"><span data-stu-id="a5142-123">Things to consider...</span></span>

<span data-ttu-id="a5142-124">Bevor Sie beginnen, stellen Sie sicher, dass der Connector indiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="a5142-124">Before you start, make sure the connector has been indexed.</span></span> <span data-ttu-id="a5142-125">Je nach Dateigröße kann es bis zu 48 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="a5142-125">It can take up to 48 hours, depending on the file size.</span></span>

<span data-ttu-id="a5142-126">Sie können keine vertikale für Inhalte erstellen, die sich in SharePoint befinden, oder aus Inhalten, die durch den FileShare-Konnektor indiziert sind.</span><span class="sxs-lookup"><span data-stu-id="a5142-126">You can’t create a vertical for content residing in SharePoint or from content indexed by the FileShare connector .</span></span> <span data-ttu-id="a5142-127">Hier erfahren Sie, wie Sie Inhalte indizieren (Link zur Connector-Dokumentation).</span><span class="sxs-lookup"><span data-stu-id="a5142-127">Learn how to index content(Link to Connector documentation).</span></span>

<span data-ttu-id="a5142-128">Auf einer allgemeinen Ebene gibt es drei Hauptschritte zum Hinzufügen eines vertikalen.</span><span class="sxs-lookup"><span data-stu-id="a5142-128">At a high-level, there are three main steps for adding a vertical.</span></span> 

1. <span data-ttu-id="a5142-129">Erstellen der vertikalen – in diesem Schritt definieren Sie den vertikalen Namen, die Inhaltsquelle und den Umfang der zu suchenden Inhalte.</span><span class="sxs-lookup"><span data-stu-id="a5142-129">Create the vertical – In this step you will define the vertical’s name, content source, and scope of the content to search.</span></span> 
2. <span data-ttu-id="a5142-130">Legen Sie fest, wie die Ergebnisse für diese vertikale aussehen sollen.</span><span class="sxs-lookup"><span data-stu-id="a5142-130">Define what the results for this vertical will look like.</span></span>  
3. <span data-ttu-id="a5142-131">Aktivieren Sie die vertikale (anzuzeigende Anzeige) auf der vertikalen Listenseite.</span><span class="sxs-lookup"><span data-stu-id="a5142-131">Enable the vertical (to be displayed) from the vertical list page.</span></span>   

## <a name="step-1-create-the-search-vertical"></a><span data-ttu-id="a5142-132">Schritt 1: Erstellen der vertikalen Suche</span><span class="sxs-lookup"><span data-stu-id="a5142-132">STEP 1: Create the search vertical</span></span>

<span data-ttu-id="a5142-133">Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte zur Definition des vertikalen namens, der Inhaltsquelle und des Bereichs der Inhalte geführt, die durchsucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a5142-133">Once you start the wizard, you'll be guided through the steps to define the vertical's name, content source and scope of the content that it will search.</span></span> <span data-ttu-id="a5142-134">Die vertikale wird im deaktivierten Zustand erstellt.</span><span class="sxs-lookup"><span data-stu-id="a5142-134">The vertical is created in a disabled state.</span></span> <span data-ttu-id="a5142-135">Die vertikale wird später aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a5142-135">You will enable the vertical later.</span></span>

<span data-ttu-id="a5142-136">Sie können eine begrenzte Menge von [KQL (Keyword Query Language)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) verwenden, um den Bereich einzuschränken, und auf der Seite werden die verfügbaren Eigenschaften aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a5142-136">You can use a limited set of the [Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) to narrow down the scope, and the page shows lists the properties available to you.</span></span> <span data-ttu-id="a5142-137">Es wird empfohlen, freie Textschlüssel Wörter und Eigenschafteneinschränkungen mit booleschen Operatoren zum Erstellen der KQL zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5142-137">We recommend using free text-keywords and property restrictions with boolean operators for creating the KQL</span></span> 

### <a name="create-a-vertical-at-the-organization-level"></a><span data-ttu-id="a5142-138">Erstellen eines vertikalen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="a5142-138">Create a vertical at the organization level</span></span>

<span data-ttu-id="a5142-139">Führen Sie die folgenden Schritte aus, um die vertikale unter Microsoft Search in SharePoint Home, Bing oder Office.com zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a5142-139">To create the vertical on Microsoft Search in SharePoint home, Bing or Office.com, follow these steps:</span></span>

1. <span data-ttu-id="a5142-140">Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Microsoft Search** > **Verticals**.</span><span class="sxs-lookup"><span data-stu-id="a5142-140">In the Microsoft 365 admin center go to **Settings** > **Microsoft Search** > **Verticals**.</span></span>
1. <span data-ttu-id="a5142-141">Wählen Sie **Add** to Get Started aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-141">Select **Add** to get started.</span></span>  

### <a name="create-a-vertical-at-the-site-level"></a><span data-ttu-id="a5142-142">Erstellen eines vertikalen auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="a5142-142">Create a vertical at the site level</span></span>

1. <span data-ttu-id="a5142-143">Wechseln Sie auf der SharePoint-Website, auf der Sie die vertikale erstellen möchten, zu **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="a5142-143">On the SharePoint site where you want to create the vertical, go to **Settings**.</span></span>
1. <span data-ttu-id="a5142-144">Wählen Sie **Website Informationen**aus, und zeigen Sie dann **Alle Websiteeinstellungen**an.</span><span class="sxs-lookup"><span data-stu-id="a5142-144">Select **Site information**, and then **View all site settings**.</span></span>
1. <span data-ttu-id="a5142-145">Suchen Sie nach dem Abschnitt **Microsoft-Suche** , und wählen Sie dann **Microsoft-Suche für diese Websitesammlung konfigurieren**aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-145">Look for the **Microsoft Search** section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="a5142-146">Wechseln Sie im Navigationsbereich zu **benutzerdefiniertes Erlebnis**, und wählen Sie dann die Registerkarte **vertikal** aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-146">In the navigation pane, go to **Custom experience**, and then select the **Verticals** tab.</span></span>
1. <span data-ttu-id="a5142-147">Um eine vertikale hinzuzufügen, wählen Sie **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-147">To add a vertical, select **Add**.</span></span> <br>
<span data-ttu-id="a5142-148">ODER</span><span class="sxs-lookup"><span data-stu-id="a5142-148">OR</span></span> <br><span data-ttu-id="a5142-149">Um eine vertikale zu bearbeiten, wählen Sie Sie in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-149">To edit a vertical, select it in the list.</span></span>

<span data-ttu-id="a5142-150">Beachten Sie, dass vertikale im deaktivierten Zustand erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a5142-150">Remember, verticals are created in a disabled state.</span></span> <span data-ttu-id="a5142-151">Sie müssen Sie dennoch aktivieren, damit Benutzer die vertikalen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="a5142-151">You'll still need to enable them before users can see the verticals.</span></span>

## <a name="step-2-create-the-result-types"></a><span data-ttu-id="a5142-152">Schritt 2: Erstellen der Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="a5142-152">STEP 2: Create the result types</span></span>

<span data-ttu-id="a5142-153">Sie können definieren, wie die Ergebnisse in der vertikalen angezeigt werden, indem Sie das Layout mithilfe von Ergebnistypen entwerfen.</span><span class="sxs-lookup"><span data-stu-id="a5142-153">You can define how results are displayed in the vertical by designing the layout using result types.</span></span> <span data-ttu-id="a5142-154">Mit dem Ergebnis Layout können Sie wichtige Informationen direkt in den Suchergebnissen anzeigen, damit Benutzer nicht auf jedes Ergebnis klicken müssen, um zu sehen, ob Sie gefunden haben, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="a5142-154">The result layout let you show important information directly in the search results, so that users don't have to click on each result to see if they've found what they're looking for.</span></span>

<span data-ttu-id="a5142-p111">Ein Ergebnistyp einer Suche ist eine Regel, die bewirkt, dass unterschiedliche Arten von Suchergebnissen auf verschiedene Weisen angezeigt werden. Ein Ergebnistyp hat folgende Bestandteile:</span><span class="sxs-lookup"><span data-stu-id="a5142-p111">A search result type is a rule that causes distinct kinds of search results to be displayed in different ways. It consists of the following:</span></span>

- <span data-ttu-id="a5142-157">*Eine oder mehrere Bedingungen* zum Vergleichen der einzelnen Suchergebnisse, beispielsweise die Inhaltsquelle des Suchergebnisses.</span><span class="sxs-lookup"><span data-stu-id="a5142-157">*One or more conditions* to compare each search result against, such as the content source of the search result.</span></span>  
- <span data-ttu-id="a5142-158">Ein *Ergebnis Layout* , das für Suchergebnisse verwendet wird, die die Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a5142-158">A *result layout* to use for search results that meet the conditions.</span></span> <span data-ttu-id="a5142-159">Das Ergebnis Layout steuert die Art und Weise, in der alle Ergebnisse, die die Bedingungen erfüllen, auf einer Suchergebnisseite angezeigt werden und sich Verhalten.</span><span class="sxs-lookup"><span data-stu-id="a5142-159">The result layout controls the way in which all results that meet the conditions appear and behave on a search results page.</span></span>

<span data-ttu-id="a5142-160">**Sie müssen mindestens einen Ergebnistyp erstellen, damit die Ergebnisse in der vertikalen angezeigt werden.**</span><span class="sxs-lookup"><span data-stu-id="a5142-160">**You must create at least one result type for results to display on the vertical.**</span></span> <span data-ttu-id="a5142-161">Sie können mehrere Ergebnistypen für jede vertikale erstellen, sodass Sie unterschiedliche Layouts für unterschiedliche Ergebnistypen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a5142-161">You can create multiple result types for each vertical, this allows you to use different layouts for different type of results.</span></span> <span data-ttu-id="a5142-162">Sie können beispielsweise "Schweregrad 1"-Vorfälle so anpassen, dass Sie mehr prominente Farben und eine größere Schriftart im Vergleich zu "Schweregrad 3" Vorfälle haben.</span><span class="sxs-lookup"><span data-stu-id="a5142-162">For example, you can customize “Severity 1” incidents to have more prominent colors and a larger font compared to “Severity 3” incidents.</span></span> 

 <span data-ttu-id="a5142-163">Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte zum Definieren des Namens, der Inhaltsquelle und der Bedingungen für den Ergebnistyp geführt.</span><span class="sxs-lookup"><span data-stu-id="a5142-163">Once you start the wizard, you will be guided through the steps to define the name, content source and conditions for the result type.</span></span> <span data-ttu-id="a5142-164">Sie können die Priorität des Ergebnistyps in der Listenansicht definieren.</span><span class="sxs-lookup"><span data-stu-id="a5142-164">You can define the priority of the result type from the list view.</span></span> 
  
### <a name="create-a-result-type-at-the-organization-level"></a><span data-ttu-id="a5142-165">Erstellen eines Ergebnistyps auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="a5142-165">Create a result type at the organization level</span></span>

1. <span data-ttu-id="a5142-166">Wechseln Sie im Microsoft 365 Admin Center zu **Einstellung** > der**Microsoft-Suche**, und wählen Sie dann **Ergebnistyp**aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-166">In the Microsoft 365 admin center, go to **Setting** > **Microsoft Search**, and then select **Result type**.</span></span>
1. <span data-ttu-id="a5142-167">Zum Hinzufügen eines **Ergebnistyps**wählen Sie **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-167">To add a **Result type**, select **Add**.</span></span> <span data-ttu-id="a5142-168">Zum Bearbeiten eines Ergebnistyps wählen Sie den Ergebnistyp in der entsprechenden Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-168">To edit a result type, select the result type in the relevant list.</span></span>
 
### <a name="create-a-results-type-at-the-site-level"></a><span data-ttu-id="a5142-169">Erstellen eines Ergebnistyps auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="a5142-169">Create a results type at the site level</span></span>

1. <span data-ttu-id="a5142-170">Wechseln Sie auf der SharePoint-Website, auf der Sie den Ergebnistyp erstellen möchten, zu **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="a5142-170">On the SharePoint site where you want to create the result type, go to **Settings**.</span></span>
1. <span data-ttu-id="a5142-171">Wählen Sie **Website Informationen**aus, und zeigen Sie dann **Alle Websiteeinstellungen**an.</span><span class="sxs-lookup"><span data-stu-id="a5142-171">Select **Site information**, and then **View all site settings**.</span></span> 
1. <span data-ttu-id="a5142-172">Suchen Sie nach dem Abschnitt Microsoft-Suche, und wählen Sie dann **Microsoft-Suche für diese Websitesammlung konfigurieren**aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-172">Look for the Microsoft Search section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="a5142-173">Wechseln Sie im Navigationsbereich zu **benutzerdefiniertes Verhalten**, und wählen Sie dann Registerkarte Ergebnistyp aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-173">In the navigation pane, go to **Custom experience**, and then select Result type tab.</span></span>
1. <span data-ttu-id="a5142-174">Zum Hinzufügen eines Ergebnistyps wählen Sie **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-174">To add a result type, select **Add**.</span></span> <br> <span data-ttu-id="a5142-175">ODER</span><span class="sxs-lookup"><span data-stu-id="a5142-175">OR</span></span> <br><span data-ttu-id="a5142-176">Zum Bearbeiten eines Ergebnistyps wählen Sie den Ergebnistyp in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a5142-176">To edit a result type, select the result type in the list.</span></span>

### <a name="view-the-vertical-after-enabling"></a><span data-ttu-id="a5142-177">Anzeigen der vertikalen nach Aktivierung</span><span class="sxs-lookup"><span data-stu-id="a5142-177">View the vertical after enabling</span></span>

<span data-ttu-id="a5142-178">Nachdem Sie die vertikale aktiviert haben, kann es eine Weile dauern, bis Sie Sie anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="a5142-178">After you enable the vertical, it might take a while before you can view it.</span></span>
<span data-ttu-id="a5142-179">Wenn Sie nach dem Aktivieren warten möchten, können Sie *cacheClear = true* an die URL in SharePoint und Office.com anfügen, um die vertikale sofort anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a5142-179">If you want to wait after enabling it, you can append *cacheClear=true* to the URL in SharePoint and Office.com to view the vertical immediately.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a5142-180">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="a5142-180">Troubleshooting</span></span>

<span data-ttu-id="a5142-181">Im folgenden finden Sie eine Liste mit häufig auftretenden Problemen und Aktionen zur Behebung dieser Probleme.</span><span class="sxs-lookup"><span data-stu-id="a5142-181">Here's a list of common issues you might encounter and actions for fixing them.</span></span>


|<span data-ttu-id="a5142-182">Fehler</span><span class="sxs-lookup"><span data-stu-id="a5142-182">Error</span></span>  |<span data-ttu-id="a5142-183">Aktion</span><span class="sxs-lookup"><span data-stu-id="a5142-183">Action</span></span>  |
|---------|---------|
|<span data-ttu-id="a5142-184">Ich sehe einen Fehler "etwas ist falsch gelaufen" auf der vertikalen</span><span class="sxs-lookup"><span data-stu-id="a5142-184">I see a 'Something went wrong' error on the vertical</span></span>|   <span data-ttu-id="a5142-185">Zum Abschließen des Setups sind sowohl vertikale als auch Ergebnistypen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a5142-185">Both vertical and result types are needed to complete the setup.</span></span> <span data-ttu-id="a5142-186">Stellen Sie sicher, dass Sie beide für dieselbe Inhaltsquelle erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a5142-186">Make sure you have created both for the same content source.</span></span>      |
|<span data-ttu-id="a5142-187">Warum wird mein Ergebnis Layout nicht angezeigt, obwohl ich ein erstellt habe?</span><span class="sxs-lookup"><span data-stu-id="a5142-187">Why don't I see my result layout although I have created one?</span></span> | <span data-ttu-id="a5142-188">Es dauert ein paar Minuten, bis die Ergebnistypen verwendet werden, da diese Einstellungen im allgemeinen zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a5142-188">It takes a few minutes for result types to be used as these settings are generally cached.</span></span> <span data-ttu-id="a5142-189">Warten Sie einige Minuten, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="a5142-189">Wait for a few minutes and try again</span></span>        |
|<span data-ttu-id="a5142-190">Es werden keine Inhaltsquellen auf der Seite "vertikal" oder "Ergebnistyp" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5142-190">I don't see any content sources on the vertical or result type page</span></span>     |      <span data-ttu-id="a5142-191">Stellen Sie sicher, dass Sie Connectors und indizierte Daten konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="a5142-191">Make sure you have configured connectors and indexed data</span></span>   |



## <a name="next-steps"></a><span data-ttu-id="a5142-192">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a5142-192">Next steps</span></span>
[<span data-ttu-id="a5142-193">Schritt 3: Anpassen des Ergebnis Layouts</span><span class="sxs-lookup"><span data-stu-id="a5142-193">STEP 3: Customize the results layout</span></span>](customize-results-layout.md)