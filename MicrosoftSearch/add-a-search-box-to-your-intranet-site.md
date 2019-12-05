---
title: Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
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
description: Erhalten Sie relevante Suchvorschläge und Arbeitsergebnisser schneller, indem Sie ein Microsoft Search-Suchfeld zu einer Intranetwebsite oder -seite hinzufügen.
ms.openlocfilehash: bcf1c6890415fdd9ae22f28cdf6d3dec1ffcaac4
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948906"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="516a1-103">Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite</span><span class="sxs-lookup"><span data-stu-id="516a1-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="516a1-104">Für schnellen Zugriff auf relevante Suchvorschläge und Arbeitsergebnisse, fügen Sie ein Microsoft Search-Suchfeld zu einer beliebigen Intranetwebsite oder -seite hinzu.</span><span class="sxs-lookup"><span data-stu-id="516a1-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="516a1-105">Hinzufügen eines Suchfelds zu einer Intranetseite</span><span class="sxs-lookup"><span data-stu-id="516a1-105">Add a search box to an intranet page</span></span>

<span data-ttu-id="516a1-106">Sie müssen der Seite zwei Elemente hinzfügen: ein Container für das Suchfeld und das zugrunde liegende Skript.</span><span class="sxs-lookup"><span data-stu-id="516a1-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="516a1-107">Fügen Sie auf einer klassischen SharePoint-Website ein Skript-Editor-Webpart hinzu, und platzieren Sie das Skript darin.</span><span class="sxs-lookup"><span data-stu-id="516a1-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="516a1-108">Aktivieren des Suchfelds für mobile Geräte</span><span class="sxs-lookup"><span data-stu-id="516a1-108">Enable the search box for mobile</span></span>

<span data-ttu-id="516a1-109">Fügen Sie für Intranetwebsites oder -seiten, die für mobile Benutzer verfügbar sind, „isMobile: true“ zum Einstellungsobjekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="516a1-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="516a1-110">Setzen des Fokus auf das Suchfeld als Standardeinstellung</span><span class="sxs-lookup"><span data-stu-id="516a1-110">Put focus on the search box by default</span></span>

<span data-ttu-id="516a1-111">Damit Benutzer schneller suchen können, platzieren Sie, wenn die Seite oder Website geladen wird, den Cursor im Suchfeld, indem Sie dem Einstellungsobjekt „focus: true“ hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="516a1-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="516a1-112">Anpassen des Erscheinungsbilds des Suchfelds</span><span class="sxs-lookup"><span data-stu-id="516a1-112">Customize the appearance of the search box</span></span> 

<span data-ttu-id="516a1-113">Sie können eine Vielzahl von Konfigurationsoptionen verwenden, um das Suchfeld an den Stil Ihres Intranets anzupassen.</span><span class="sxs-lookup"><span data-stu-id="516a1-113">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="516a1-114">Kombinieren Sie je nach Bedarf verschiedene Optionen.</span><span class="sxs-lookup"><span data-stu-id="516a1-114">Mix and match options to suit your needs.</span></span>

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: true
        iconColor: "#067FA6",                   // default: #067FA6
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work and the web"
                                                // when specified, text will be "Search the web and [Contoso]"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="516a1-115">Verwenden eines iFrame zum Einbetten eines Suchfelds</span><span class="sxs-lookup"><span data-stu-id="516a1-115">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="516a1-116">Wenn das Einbetten eines Skripts keine Option für die Website ist, verwenden Sie einen iFrame, der dem Suchfeld hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="516a1-116">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="516a1-117">Sie können das Erscheinungsbilds des Suchfelds nicht anpassen.</span><span class="sxs-lookup"><span data-stu-id="516a1-117">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```