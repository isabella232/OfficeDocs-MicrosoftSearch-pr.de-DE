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
ms.openlocfilehash: af12ce4d17c2695e196f8e4d79ccd515f002f238
ms.sourcegitcommit: 92206ea179ec00b22496f6fd2866b5406449cf40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44798225"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="e5dea-103">Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite</span><span class="sxs-lookup"><span data-stu-id="e5dea-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="e5dea-104">Um Ihren Benutzern einfachen Zugriff auf Ergebnisse aus Ihrer Organisation zu ermöglichen, fügen Sie eine Microsoft Search in Bing Suchfeld zu jeder Intranetsite oder Website hinzu.</span><span class="sxs-lookup"><span data-stu-id="e5dea-104">To provide your users with easy access to results from your organization, add a Microsoft Search in Bing search box to any intranet site or page.</span></span> <span data-ttu-id="e5dea-105">Dies sind einige der Vorteile:</span><span class="sxs-lookup"><span data-stu-id="e5dea-105">These are some of the benefits:</span></span>

- <span data-ttu-id="e5dea-106">Ein Suchfeld auf Ihrem SharePoint-oder Intranet-Portal stellt einen vertrauten, vertrauenswürdigen Einstiegspunkt zum Starten der Suche bereit.</span><span class="sxs-lookup"><span data-stu-id="e5dea-106">A search box on your SharePoint or intranet portal provides a familiar, trusted entry point to start searching</span></span>
- <span data-ttu-id="e5dea-107">Unterstützt alle wichtigen Webbrowser, einschließlich Google Chrome und Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e5dea-107">Supports all major web browsers, including Google Chrome and Microsoft Edge</span></span>
- <span data-ttu-id="e5dea-108">Nur Suchvorschläge aus Ihrer Organisation werden angezeigt, Webvorschläge werden nie berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e5dea-108">Only search suggestions from your organization appear, web suggestions are never included</span></span>
- <span data-ttu-id="e5dea-109">Führt Benutzer zu einer Microsoft-Suche auf der Seite Bing work results, die anzeigen und Webergebnisse ausschließt.</span><span class="sxs-lookup"><span data-stu-id="e5dea-109">Takes users to a Microsoft Search in Bing work results page, which excludes ads and web results</span></span>
- <span data-ttu-id="e5dea-110">Sie steuern die Darstellung und das Verhalten des Such Felds.</span><span class="sxs-lookup"><span data-stu-id="e5dea-110">You control the appearance and behavior of the search box</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="e5dea-111">Hinzufügen eines Suchfelds zu einer Intranetseite</span><span class="sxs-lookup"><span data-stu-id="e5dea-111">Add a search box to an intranet page</span></span>

<span data-ttu-id="e5dea-112">Sie müssen der Seite zwei Elemente hinzfügen: ein Container für das Suchfeld und das zugrunde liegende Skript.</span><span class="sxs-lookup"><span data-stu-id="e5dea-112">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="e5dea-113">Fügen Sie auf einer klassischen SharePoint-Website ein Skript-Editor-Webpart hinzu, und platzieren Sie das Skript darin.</span><span class="sxs-lookup"><span data-stu-id="e5dea-113">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="e5dea-114">Aktivieren des Suchfelds für mobile Geräte</span><span class="sxs-lookup"><span data-stu-id="e5dea-114">Enable the search box for mobile</span></span>

<span data-ttu-id="e5dea-115">Fügen Sie für Intranetwebsites oder -seiten, die für mobile Benutzer verfügbar sind, „isMobile: true“ zum Einstellungsobjekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="e5dea-115">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="e5dea-116">Setzen des Fokus auf das Suchfeld als Standardeinstellung</span><span class="sxs-lookup"><span data-stu-id="e5dea-116">Put focus on the search box by default</span></span>

<span data-ttu-id="e5dea-117">Damit Benutzer schneller suchen können, platzieren Sie, wenn die Seite oder Website geladen wird, den Cursor im Suchfeld, indem Sie dem Einstellungsobjekt „focus: true“ hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e5dea-117">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="e5dea-118">Anpassen des Erscheinungsbilds des Suchfelds</span><span class="sxs-lookup"><span data-stu-id="e5dea-118">Customize the appearance of the search box</span></span> 

<span data-ttu-id="e5dea-119">Sie können eine Vielzahl von Konfigurationsoptionen verwenden, um das Suchfeld an den Stil Ihres Intranets anzupassen.</span><span class="sxs-lookup"><span data-stu-id="e5dea-119">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="e5dea-120">Kombinieren Sie je nach Bedarf verschiedene Optionen.</span><span class="sxs-lookup"><span data-stu-id="e5dea-120">Mix and match options to suit your needs.</span></span>

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
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="e5dea-121">Verwenden eines iFrame zum Einbetten eines Suchfelds</span><span class="sxs-lookup"><span data-stu-id="e5dea-121">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="e5dea-122">Wenn das Einbetten eines Skripts keine Option für die Website ist, verwenden Sie einen iFrame, der dem Suchfeld hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e5dea-122">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="e5dea-123">Sie können das Erscheinungsbilds des Suchfelds nicht anpassen.</span><span class="sxs-lookup"><span data-stu-id="e5dea-123">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
