---
title: Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: Rufen Sie relevante Suchvorschläge ab, und suchen Sie schneller nach Arbeitsergebnissen, indem Sie Ihrer Intranetwebsite oder -seite ein Microsoft Search Suchfeld hinzufügen.
ms.openlocfilehash: 7d9ca4be8d3be27a7549ffb940d6dc55b3763baf
ms.sourcegitcommit: 38a0f09596c2bca0e12bf4cada7b4c64fd4c48e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53449061"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="37284-103">Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite</span><span class="sxs-lookup"><span data-stu-id="37284-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="37284-104">Um Ihren Benutzern einfachen Zugriff auf Ergebnisse aus Ihrer Organisation zu ermöglichen, fügen Sie einer Intranetwebsite oder -seite in Bing Suchfeld eine Microsoft Search hinzu.</span><span class="sxs-lookup"><span data-stu-id="37284-104">To provide your users with easy access to results from your organization, add a Microsoft Search in Bing search box to any intranet site or page.</span></span> <span data-ttu-id="37284-105">Dies sind einige der Vorteile:</span><span class="sxs-lookup"><span data-stu-id="37284-105">These are some of the benefits:</span></span>

- <span data-ttu-id="37284-106">Ein Suchfeld in Ihrem SharePoint oder Intranetportal bietet einen vertrauten, vertrauenswürdigen Einstiegspunkt, um mit der Suche zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="37284-106">A search box on your SharePoint or intranet portal provides a familiar, trusted entry point to start searching</span></span>
- <span data-ttu-id="37284-107">Unterstützt alle gängigen Webbrowser, einschließlich Google Chrome und Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="37284-107">Supports all major web browsers, including Google Chrome and Microsoft Edge</span></span>
- <span data-ttu-id="37284-108">Es werden nur Suchvorschläge aus Ihrer Organisation angezeigt, Webvorschläge werden nie eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="37284-108">Only search suggestions from your organization appear, web suggestions are never included</span></span>
- <span data-ttu-id="37284-109">Führt Benutzer zu einem Microsoft Search auf Bing Seite mit Arbeitsergebnissen, die Anzeigen und Webergebnisse ausschließt</span><span class="sxs-lookup"><span data-stu-id="37284-109">Takes users to a Microsoft Search in Bing work results page, which excludes ads and web results</span></span>
- <span data-ttu-id="37284-110">Sie steuern die Darstellung und das Verhalten des Suchfelds, einschließlich der Möglichkeit, Benutzer auf einer Standard-Vertikal oder einer benutzerdefinierten Vertikalen zu landen, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="37284-110">You control the appearance and behavior of the search box, including the ability to land users on a default vertical or a custom vertical you've created</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="37284-111">Hinzufügen eines Suchfelds zu einer Intranetseite</span><span class="sxs-lookup"><span data-stu-id="37284-111">Add a search box to an intranet page</span></span>

<span data-ttu-id="37284-112">Sie müssen der Seite zwei Elemente hinzfügen: ein Container für das Suchfeld und das zugrunde liegende Skript.</span><span class="sxs-lookup"><span data-stu-id="37284-112">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="37284-113">Fügen Sie auf einer klassischen SharePoint-Website ein Skript-Editor-Webpart hinzu, und platzieren Sie das Skript darin.</span><span class="sxs-lookup"><span data-stu-id="37284-113">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="37284-114">Aktivieren des Suchfelds für mobile Geräte</span><span class="sxs-lookup"><span data-stu-id="37284-114">Enable the search box for mobile</span></span>

<span data-ttu-id="37284-115">Fügen Sie für Intranetwebsites oder -seiten, die für mobile Benutzer verfügbar sind, „isMobile: true“ zum Einstellungsobjekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="37284-115">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox", 
        isMobile: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="37284-116">Setzen des Fokus auf das Suchfeld als Standardeinstellung</span><span class="sxs-lookup"><span data-stu-id="37284-116">Put focus on the search box by default</span></span>

<span data-ttu-id="37284-117">Damit Benutzer schneller suchen können, platzieren Sie, wenn die Seite oder Website geladen wird, den Cursor im Suchfeld, indem Sie dem Einstellungsobjekt „focus: true“ hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="37284-117">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        focus: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="37284-118">Anpassen des Erscheinungsbilds des Suchfelds</span><span class="sxs-lookup"><span data-stu-id="37284-118">Customize the appearance of the search box</span></span> 

<span data-ttu-id="37284-119">Sie können eine Vielzahl von Konfigurationsoptionen verwenden, um das Suchfeld an den Stil Ihres Intranets anzupassen.</span><span class="sxs-lookup"><span data-stu-id="37284-119">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="37284-120">Kombinieren Sie je nach Bedarf verschiedene Optionen.</span><span class="sxs-lookup"><span data-stu-id="37284-120">Mix and match options to suit your needs.</span></span>

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: false
        iconColor: "#067FA6",                   // default: #067FA6
        title: "Search box",                    // default: "Search box"
        vertical: "Person-people",              // default: not specified, search box directs to the All vertical on the WORK results page
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="direct-users-to-a-default-or-custom-vertical"></a><span data-ttu-id="37284-121">Weiterleiten von Benutzern zu einer Standard- oder benutzerdefinierten vertikalen Komponente</span><span class="sxs-lookup"><span data-stu-id="37284-121">Direct users to a default or custom vertical</span></span>

<span data-ttu-id="37284-122">Um eine einfache Integration zwischen Ihren Branchen-Apps oder Intranetwebsites und Ihren Arbeitsergebnissen zu ermöglichen, können Sie auch das Suchfeld anpassen, indem Sie eine Standard- oder benutzerdefinierte Vertikale angeben, auf der Benutzer landen sollten, wenn sie auf einen Suchvorschlag klicken.</span><span class="sxs-lookup"><span data-stu-id="37284-122">To provide easy integration between your line-of-business apps or intranet sites and your work results, you can also customize the search box by specifying a default or custom vertical that users should land on when they click a search suggestion.</span></span>

<span data-ttu-id="37284-123">Verwenden Sie die vertikale Option in bfbSearchBoxConfig, um die gewünschte Vertikale zu definieren.</span><span class="sxs-lookup"><span data-stu-id="37284-123">Use the vertical option in bfbSearchBoxConfig to define the vertical you want.</span></span> <span data-ttu-id="37284-124">Wenn Benutzer beispielsweise immer auf der vertikalen Website(einer der Standard-Vertikalen) landen sollen, verwenden Sie den Wert "Websitewebsites".</span><span class="sxs-lookup"><span data-stu-id="37284-124">For example, if you want users to always land on the Sites vertical, one of the default verticals, use the value "Site-sites".</span></span>

:::image type="content" alt-text="Screenshot der Seite &quot;Arbeitsergebnisse&quot; auf Microsoft Search in Bing mit den vertikalen Ergebnissen und der URL der Websites." source="media/sites-vertical-esb.png" lightbox="media/sites-vertical-esb.png":::

<span data-ttu-id="37284-126">Verwenden Sie für benutzerdefinierte Vertikale den Hash am Ende der URL.</span><span class="sxs-lookup"><span data-stu-id="37284-126">For custom verticals, use the hash at the end of the URL.</span></span> <span data-ttu-id="37284-127">Sie finden diese Werte, indem Sie auf der Arbeitsseite auf Bing suchen, auf eine vertikale Beschriftung klicken und den Wert nach dem Nummernzeichen (#) kopieren.</span><span class="sxs-lookup"><span data-stu-id="37284-127">You can find these values by searching from the work page on Bing, clicking a vertical label, and copying the value after the number sign (#).</span></span>

:::image type="content" alt-text="Screenshot der Seite &quot;Arbeitsergebnisse&quot; auf Microsoft Search in Bing, auf der die vertikalen Ergebnisse und die URL einer benutzerdefinierten Präsentation angezeigt werden." source="media/custom-vertical-esb.png" lightbox="media/custom-vertical-esb.png":::

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="37284-129">Verwenden eines iFrame zum Einbetten eines Suchfelds</span><span class="sxs-lookup"><span data-stu-id="37284-129">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="37284-130">Wenn das Einbetten eines Skripts keine Option für die Website ist, verwenden Sie einen iFrame, der dem Suchfeld hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="37284-130">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="37284-131">Sie können das Suchfeld nicht anpassen.</span><span class="sxs-lookup"><span data-stu-id="37284-131">You won't be able to customize the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```

## <a name="inprivate-mode-and-conditional-access"></a><span data-ttu-id="37284-132">InPrivate-Modus und bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="37284-132">InPrivate mode and Conditional Access</span></span>

<span data-ttu-id="37284-133">Ein eingebettetes Suchfeld wird deaktiviert, wenn die Seite oder Website in einem InPrivate-Fenster geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="37284-133">An embedded search box will be disabled if the page or site is opened in an InPrivate window.</span></span> <span data-ttu-id="37284-134">Darüber hinaus unterstützt Bing.com die AAD-Anmeldung bei Verwendung des InPrivate-Modus nicht, wenn azure AD conditional Access in Microsoft Edge unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="37284-134">Also, with Azure AD Conditional Access support in Microsoft Edge, Bing.com doesn't support AAD sign in when using InPrivate mode.</span></span> <span data-ttu-id="37284-135">Weitere Informationen zum bedingten Zugriff in Edge finden Sie unter [Microsoft Edge und bedingter Zugriff.](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge)</span><span class="sxs-lookup"><span data-stu-id="37284-135">For more information about Conditional Access in Edge, see [Microsoft Edge and Conditional Access](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge).</span></span> 
