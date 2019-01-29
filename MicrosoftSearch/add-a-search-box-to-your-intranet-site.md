---
title: Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
description: Möchten Sie relevante Suchvorschläge erhalten, und suchen Sie Arbeit Ergebnisse schneller, indem Sie ein Suchfeld Microsoft Search zu einer Intranet-Website oder Seite hinzufügen.
ms.openlocfilehash: 699cfd9c411c9b86f3a2f8742c425aaedef1ebc5
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612417"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="bd353-103">Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite</span><span class="sxs-lookup"><span data-stu-id="bd353-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="bd353-104">Fügen Sie ein Suchfeld Microsoft Search für schnellen Zugriff auf relevante Suchvorschläge und Arbeit Ergebnisse an einem beliebigen Intranet-Website oder Seite.</span><span class="sxs-lookup"><span data-stu-id="bd353-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="bd353-105">Fügen Sie ein Suchfeld hinzu, um eine Seite im intranet</span><span class="sxs-lookup"><span data-stu-id="bd353-105">Add a search box to an intranet page</span></span>

<span data-ttu-id="bd353-106">Sie müssen auf der Seite zwei Elemente hinzugefügt: ein Container für das Suchfeld und das Skript, das sie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bd353-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="bd353-107">Auf einer SharePoint-Website klassische ein Skript-Editor-Webpart hinzufügen, und das Skript einlassen.</span><span class="sxs-lookup"><span data-stu-id="bd353-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="bd353-108">Aktivieren Sie das Suchfeld für mobile</span><span class="sxs-lookup"><span data-stu-id="bd353-108">Enable the search box for mobile</span></span>

<span data-ttu-id="bd353-109">Fügen Sie für Intranetwebsites oder Seiten mobilen Benutzern zur Verfügung stehen, IsMobile: true, wenn das Objekt Settings:</span><span class="sxs-lookup"><span data-stu-id="bd353-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="bd353-110">Verschieben Sie den Fokus auf das Suchfeld in der Standardeinstellung</span><span class="sxs-lookup"><span data-stu-id="bd353-110">Put focus on the search box by default</span></span>

<span data-ttu-id="bd353-111">Damit Benutzer schneller, suchen Sie beim Laden der Seite oder einer Website durch Hinzufügen der Fokus den Cursor im Suchfeld platzieren: true, wenn das Objekt Settings:</span><span class="sxs-lookup"><span data-stu-id="bd353-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="bd353-112">Verwenden eines IFRAMEs ein Suchfeld einbetten</span><span class="sxs-lookup"><span data-stu-id="bd353-112">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="bd353-113">Wenn eine Option für die Website nicht Einbetten eines Skripts ist, verwenden Sie einen iFrame Suchfeld hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="bd353-113">If embedding a script isn't an option for the site, use an iFrame to add the search box:</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
