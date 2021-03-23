---
title: Verwalten von Layouts für Suchergebnisse
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Erstellen Sie mithilfe adaptiver Karten ein Layout zum Anzeigen ihrer angepassten Suchergebnisse.
ms.openlocfilehash: d29b1a45f11079f4b71f71a387cf43cbf2f48e7d
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031737"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="53169-103">Erstellen eines Layouts zum Anpassen von Suchergebnissen</span><span class="sxs-lookup"><span data-stu-id="53169-103">Create a layout to customize search results</span></span>

<span data-ttu-id="53169-104">Sie können das Ergebnislayout für eine benutzerdefinierte Vertikale mithilfe des Suchlayout-Designers entwerfen.</span><span class="sxs-lookup"><span data-stu-id="53169-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="53169-105">Sie können mit dem Entwerfen des Layouts beginnen, indem Sie vorlagen auswählen, die im Layout-Designer angeboten werden, und diese verwenden, wenn sie Ihren Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="53169-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="53169-106">Sie können diese Vorlagen auch auf unterschiedliche Weise bearbeiten, um Ihren Anforderungen gerecht zu werden.</span><span class="sxs-lookup"><span data-stu-id="53169-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="53169-107">Beispiel: Hinzufügen/Entfernen von Bildern, Hinzufügen/Entfernen von Text und Ändern von Text.</span><span class="sxs-lookup"><span data-stu-id="53169-107">For example, add/remove images, add/remove text, and modify text.</span></span> <span data-ttu-id="53169-108">Wenn keine der Vorlagen Ihren Anforderungen entspricht, können Sie das Layout mithilfe einer leeren Vorlage entwerfen.</span><span class="sxs-lookup"><span data-stu-id="53169-108">If none of the templates meet your requirements, you can choose to start designing your layout using a blank template.</span></span>  

<span data-ttu-id="53169-109">Nachdem das Layout bereit ist, verwenden Sie die Vorlage für [adaptive](/adaptive-cards/templating/language) Karten, um ein Ergebnislayout-JSON zu erstellen, das zum Definieren eines Ergebnistyps verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="53169-109">After the layout is ready, use the [Adaptive Cards Template language](/adaptive-cards/templating/language) to create a result layout JSON that's used to define a result type.</span></span> <span data-ttu-id="53169-110">Sie ordnen die Ergebniseigenschaften dem Layout mithilfe des Zuordnungsschritts im Layout-Designer zu.</span><span class="sxs-lookup"><span data-stu-id="53169-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="53169-111">Eigenes Layout erstellen</span><span class="sxs-lookup"><span data-stu-id="53169-111">Create a layout on your own</span></span>

<span data-ttu-id="53169-112">Das Erstellen eines Layouts allein erfordert Kenntnisse der [adaptiven Karten und](/adaptive-cards/authoring-cards/getting-started) deren [Schema.](https://adaptivecards.io/explorer/)</span><span class="sxs-lookup"><span data-stu-id="53169-112">Creating a layout on your own requires knowledge of [adaptive cards](/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="53169-113">Das Suchergebnislayout verwendet eine Teilmenge der Elemente, die von adaptiven Karten angeboten werden, und Sie können den Layoutdesigner verwenden, um mehr über den unterstützten Satz von Elementen zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="53169-113">Search result layout uses a subset of the elements offered by adaptive cards, and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="53169-114">Erstellen Sie beim Erstellen Ihres eigenen Layouts das layout für adaptive Karten mithilfe von Daten aus Ihrem Connector, und finalisieren Sie das Layout.</span><span class="sxs-lookup"><span data-stu-id="53169-114">While creating your own layout, create the adaptive card layout using data from your connector, and then finalize the layout.</span></span>
<span data-ttu-id="53169-115">Es gibt zwei Hauptschritte beim Erstellen eines eigenen Layouts:</span><span class="sxs-lookup"><span data-stu-id="53169-115">There are two main steps in creating your own layout:</span></span>

- <span data-ttu-id="53169-116">Entwerfen Sie das Layout.</span><span class="sxs-lookup"><span data-stu-id="53169-116">Design the layout.</span></span>
- <span data-ttu-id="53169-117">Trennen Sie die Daten von der Vorlage.</span><span class="sxs-lookup"><span data-stu-id="53169-117">Separate the data from the template.</span></span>

### <a name="design-the-layout"></a><span data-ttu-id="53169-118">Entwerfen des Layouts</span><span class="sxs-lookup"><span data-stu-id="53169-118">Design the layout</span></span>

<span data-ttu-id="53169-119">In diesem Beispiel wird ein Layout mit einer Kopfzeile, einem Link und einem beschreibenden Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="53169-119">In this example, we show a layout with a header, link, and descriptive text.</span></span>

![Beispiel für ein Layout mit einer Kopfzeile, einem Link und einer Beschreibung.](media/Verts-ExampleLayout.png)

<span data-ttu-id="53169-121">Und hier ist die zugeordnete JSON-Datei des Layouts:</span><span class="sxs-lookup"><span data-stu-id="53169-121">And here's the layout's associated JSON file:</span></span>

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
     "body": [
{

            "type": "ColumnSet",
             "columns": [
                 {
                     "type": "Column",
                     "width": 8,
                     "items": [
                         {
                             "type": "TextBlock",
                             "text": "Contoso Marketing Analysis - Q3 FY18",
                             "color": "Accent",
                             "size": "Medium",
                             "spacing": "None",
                             "$when": "{title != \"\"}",
                             "weight": "Bolder"
                        },
                        {
                        "type": "TextBlock",  
                        "text": "https://contoso.com/hr/link",
                        "spacing": "None",  
                        "color": "Dark",
                        "weight": "Bolder"

                        },

                        {  
                        "type": "TextBlock",
                        "text": "Marketing team at Contoso.., and looking at the Contoso Marketing documents on the team site. This contains the data from FY20 and will taken over to FY21...Marketing Planning is ongoing for FY20..",  
                        "wrap": true,
                        "maxLines": 2,
                        "spacing": "Medium"
                        }
                        ],

                    "horizontalAlignment": "Center",
                    "spacing": "None"

                }

            ]

        }
        ],

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json"
}
```

### <a name="separate-the-data-from-the-layout"></a><span data-ttu-id="53169-122">Trennen der Daten vom Layout</span><span class="sxs-lookup"><span data-stu-id="53169-122">Separate the data from the layout</span></span>

<span data-ttu-id="53169-123">Sie können die Daten vom Layout trennen und die Daten binden.</span><span class="sxs-lookup"><span data-stu-id="53169-123">You can separate the data from the layout and bind the data.</span></span>

<span data-ttu-id="53169-124">Hier ist Layout JSON nach dem Binden der Daten:</span><span class="sxs-lookup"><span data-stu-id="53169-124">Here's Layout JSON after binding the data:</span></span>

```json
{

    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
    {
    "type": "ColumnSet",
"columns": [

                {
                "type": "Column",
                "width": 8,
                "items": [
                {
                "type": "TextBlock",
                "text": "[{title}]({titleUrl})",
                "color": "Accent",
                "size": "Medium",
                "spacing": "None",
                "weight": "Bolder"

                 },
                 {
                 "type": "TextBlock",
                 "text": "{link}",
                 "spacing": "None",
                 "color": "Dark",
                 "weight": "Bolder"
                 },
                 {
                 "type": "TextBlock",
                 "text": "{description}",
                 "wrap": true,
                 "maxLines": 2,
                 "spacing": "Medium"
                 }
                 ],
                 "horizontalAlignment": "Center",
                 "spacing": "None"
                 }
                 ]

        }

    ],

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json"
}
```

<span data-ttu-id="53169-125">Beispieldaten: Geben Sie Beispieldaten im **Beispieldaten-Editor an,** um die datengebundene Karte im **Vorschaumodus anzuzeigen.**</span><span class="sxs-lookup"><span data-stu-id="53169-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in **Preview Mode**.</span></span>

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="53169-126">Ordnen Sie das Layout den Ergebniseigenschaften zu.</span><span class="sxs-lookup"><span data-stu-id="53169-126">Map the layout to the result properties</span></span>

<span data-ttu-id="53169-127">Sie müssen jedes Feld des Layouts einer Ergebniseigenschaft oder einer Connectoreigenschaft zuordnungen, um das Ergebnislayout JSON zu generieren.</span><span class="sxs-lookup"><span data-stu-id="53169-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

![Bildschirmaufnahme eines Beispiellayouts auf der Seite Suchlayout-Designer, bei dem ein Feld ausgewählt und der Eigenschaftenbereich geöffnet ist.](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="53169-129">Wählen Sie ein Feld im Layout aus, um die Variablen zu markieren, die zugeordnet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="53169-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="53169-130">Sie können mehrere Variablen für ein einzelnes Feld verwenden, und alle Felder müssen den Ergebniseigenschaften zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="53169-130">You can use multiple variables for a single field, and all fields must be mapped to the result properties.</span></span>

### <a name="show-snippet-on-search-result"></a><span data-ttu-id="53169-131">Codeausschnitt im Suchergebnis anzeigen</span><span class="sxs-lookup"><span data-stu-id="53169-131">Show snippet on search result</span></span>  

<span data-ttu-id="53169-132">Dynamische Codeausschnitte, die in der **Inhaltseigenschaft** des Connectorergebniss generiert werden, können im Suchergebnis angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="53169-132">Dynamic snippets generated on the **content** property of the connector result can be shown on the search result.</span></span> <span data-ttu-id="53169-133">**ResultSnippet** ist die Systemeigenschaft, die als Platzhaltereigenschaft für die Codeausschnitte dient, die für jedes Connector-Ergebnis generiert werden.</span><span class="sxs-lookup"><span data-stu-id="53169-133">**ResultSnippet** is the system property that acts as a placeholder property for the snippets generated for each Connector result.</span></span> <span data-ttu-id="53169-134">Zum Anzeigen der Codeausschnitte im Ergebnislayout muss die **ResultSnippet-Systemeigenschaft** einem entsprechenden Feld zugeordnet werden, z. B. Beschreibung, im Suchergebnislayout.</span><span class="sxs-lookup"><span data-stu-id="53169-134">To show the snippets on the result layout, the **ResultSnippet** system property must be mapped to an appropriate field, for example Description, in the search result layout.</span></span> <span data-ttu-id="53169-135">Codeausschnitte, die für jedes Ergebnis generiert werden, markieren auch die Übereinstimmungen im Codeausschnitt mit dem vom Benutzer eingegebenen Abfragebegriff.</span><span class="sxs-lookup"><span data-stu-id="53169-135">Snippets generated on each result also highlight the matches in the Snippet with the query term entered by the user.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="53169-136">Zu berücksichtigende Aspekte</span><span class="sxs-lookup"><span data-stu-id="53169-136">Things to consider</span></span>

<span data-ttu-id="53169-137">Bevor Sie beginnen, sollten Sie einige Dinge tun und einige Dinge vermeiden, die Sie vermeiden sollten, um sicherzustellen, dass Ihre Layouts erfolgreich sind.</span><span class="sxs-lookup"><span data-stu-id="53169-137">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="53169-138">Dos</span><span class="sxs-lookup"><span data-stu-id="53169-138">Do</span></span>

- <span data-ttu-id="53169-139">Bearbeiten Sie eine Vorlage, um den Logolink im Layout zur Verfügung zu stellen, wenn Sie statische Links für Logos und keine Ergebniseigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="53169-139">Edit a template to provide the logo link in the layout if you're using static links for logos and not result properties.</span></span>
- <span data-ttu-id="53169-140">Überprüfen Sie das Ergebnislayout für Szenarien, in denen keine Daten für eine ergebniseigenschaft zurückgegeben werden, die im Ergebnis-JSON verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="53169-140">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="53169-141">Verwenden Sie `$when` die Bedingung, um ein Element auszublenden, wenn die Eigenschaft keine Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="53169-141">Use the `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="53169-142">Stellen Sie sicher, dass die Datentypen der `$when` Bedingung und der result-Eigenschaft übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="53169-142">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="53169-143">Vergleichen Sie z. B. nicht `Number` mit `Text` in der `$when` Bedingung.</span><span class="sxs-lookup"><span data-stu-id="53169-143">For example, don't compare `Number` with `Text` in the `$when` condition.</span></span>  
- <span data-ttu-id="53169-144">Denken Sie an Designanforderungen beim Entwerfen eines Ergebnislayouts.</span><span class="sxs-lookup"><span data-stu-id="53169-144">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="53169-145">Stellen Sie sicher, dass `Textblock`   das Element dynamische Inhalte verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="53169-145">Make sure that the `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="53169-146">Zu diesem Zweck können Sie `wrap` die Eigenschaften and element `maxLines` verwenden.</span><span class="sxs-lookup"><span data-stu-id="53169-146">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span>
- <span data-ttu-id="53169-147">Formatieren Sie das Datum bei Verwendung `{DATE()}` in Markdown ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="53169-147">Properly format the date when using `{DATE()}` in Markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="53169-148">Don’ts</span><span class="sxs-lookup"><span data-stu-id="53169-148">Don't</span></span>

- <span data-ttu-id="53169-149">Definieren Sie beim Binden von Werten keine ungültigen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="53169-149">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="53169-150">Weitere Informationen zu Datentypen finden Sie unter [Manage the Search schema](/sharepoint/search/manage-the-search-schema).</span><span class="sxs-lookup"><span data-stu-id="53169-150">For more information about data types, see [Manage the Search schema](/sharepoint/search/manage-the-search-schema).</span></span>
- <span data-ttu-id="53169-151">Vermeiden Sie das Zuschneiden des Ergebnisses auf der Ergebnisseite, indem Sie der maximalen Höhe des Ergebnislayouts JSON folgen.</span><span class="sxs-lookup"><span data-stu-id="53169-151">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="53169-152">Wenn Sie die maximale Höhe des Ergebnislayouts überschreiten, wird das Ergebnis auf der Ergebnisseite zugeschnitten.</span><span class="sxs-lookup"><span data-stu-id="53169-152">If you exceed the maximum height of the result layout, the result will be cropped on the result page.</span></span>
- <span data-ttu-id="53169-153">Verwenden Sie keine `px` Werte in Elementeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="53169-153">Don't use `px` values in element properties.</span></span>
- <span data-ttu-id="53169-154">Verwenden Sie markdown nicht mit der **ResultSnippet-Eigenschaft** im Ergebnislayout, um die Abfrage übereinstimmung im Suchergebnis zu markieren.</span><span class="sxs-lookup"><span data-stu-id="53169-154">Don't use markdown with the **ResultSnippet** property in the result layout to highlight query match in the search result.</span></span>

## <a name="resources"></a><span data-ttu-id="53169-155">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="53169-155">Resources</span></span>

[<span data-ttu-id="53169-156">Anpassen der Suchergebnisseite</span><span class="sxs-lookup"><span data-stu-id="53169-156">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="53169-157">Adaptive Karten</span><span class="sxs-lookup"><span data-stu-id="53169-157">Adaptive cards</span></span>](/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="53169-158">Vorlage für adaptive Karten</span><span class="sxs-lookup"><span data-stu-id="53169-158">Adaptive Cards Template language</span></span>](/adaptive-cards/templating/language)

[<span data-ttu-id="53169-159">Adaptives Kartenschema</span><span class="sxs-lookup"><span data-stu-id="53169-159">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)