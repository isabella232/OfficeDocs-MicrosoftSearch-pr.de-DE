---
title: Integration von PowerApps
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
description: Beziehen Sie browserbasierte Apps in Lesezeichenergebnisse für Microsoft Search ein.
ms.openlocfilehash: 96b409274e3fa06cef7dcc6f1c43360a3e6b9d34
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968378"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="1b221-103">Integration von PowerApps</span><span class="sxs-lookup"><span data-stu-id="1b221-103">Integrate PowerApps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b221-104">Die Einstellungen für Microsoft Search in Bing sind nun im Microsoft 365 Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1b221-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1b221-105">Beginnen Sie, indem Sie [Suchadministratoren](https://docs.microsoft.com/de-DE/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in Ihrem Admin Center zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1b221-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="1b221-106">Helfen Sie Ihren Benutzern beim Ausführen von Aufgaben, z. B. der Eingabe von Urlaubszeiten oder dem Erstellen von Spesenabrechnungen, indem Sie in Ihre Lesezeichen PowerApps integrieren.</span><span class="sxs-lookup"><span data-stu-id="1b221-106">Help your users complete tasks, such as entering vacation time or reporting expenses, by adding existing PowerApps to your bookmarks.</span></span> <span data-ttu-id="1b221-107">Integrierte PowerApps werden in einem Lesezeichenergebnis angezeigt, sodass es nicht mehr erforderlich ist, zu einer anderen Website zu wechseln oder ein separates Tool zu öffnen. Das spart Zeit und Aufwand.</span><span class="sxs-lookup"><span data-stu-id="1b221-107">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="1b221-108">Was sind PowerApps?</span><span class="sxs-lookup"><span data-stu-id="1b221-108">What are PowerApps?</span></span>

<span data-ttu-id="1b221-109">PowerApps ist ein Dienst, mit dem Sie Geschäfts-Apps erstellen können, die in einem Browser oder auf einem Smartphone oder Tablet ausgeführt werden, ohne dass eine Codierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1b221-109">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="1b221-110">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="1b221-110">Learn more:</span></span>
  
- <span data-ttu-id="1b221-111">
  [Interaktives Lernen](https://docs.microsoft.com/de-DE/learn/browse/?products=powerapps)</span><span class="sxs-lookup"><span data-stu-id="1b221-111">[Guided Learning](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)</span></span>
    
- <span data-ttu-id="1b221-112">
  [Dokumentation](https://docs.microsoft.com/de-DE/powerapps/)</span><span class="sxs-lookup"><span data-stu-id="1b221-112">[Documentation](https://docs.microsoft.com/en-us/powerapps/)</span></span>
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="1b221-113">Hinzufügen einer PowerApp zu einem Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="1b221-113">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="1b221-114">PowerApps funktionieren in jedem beliebigen Browser und auf jedem beliebigen Gerät und können in weniger als einer Minute hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1b221-114">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="1b221-115">
  [Suchen der App-ID für die PowerApp](https://docs.microsoft.com/de-DE/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id), die Sie integrieren möchten</span><span class="sxs-lookup"><span data-stu-id="1b221-115">Find the [App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) that you want to add.</span></span> 
    
2. <span data-ttu-id="1b221-116">Navigieren Sie im Microsoft Search Verwaltungsportal zu **Lesezeichen**.</span><span class="sxs-lookup"><span data-stu-id="1b221-116">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="1b221-117">Hinzufügen eines Lesezeichens oder Suchen eines vorhandenen Lesezeichens, dem Sie eine PowerApp hinzufügen möchten</span><span class="sxs-lookup"><span data-stu-id="1b221-117">Add a bookmark or find an existing bookmark that you want to add a PowerApp to.</span></span>
    
4. <span data-ttu-id="1b221-118">Klicken Sie in den Einstellungen des Lesezeichens auf **PowerApp** und dann auf **PowerApp hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1b221-118">In Bookmark settings, select Power App, and then Add a Power App.</span></span>
    
5. <span data-ttu-id="1b221-119">Geben oder fügen Sie die App-ID ein.</span><span class="sxs-lookup"><span data-stu-id="1b221-119">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="1b221-120">Die Höhe und Breite werden automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1b221-120">The height and width are automatically adjusted.</span></span> <span data-ttu-id="1b221-121">Lesezeichen können Hoch- und Querformat unterstützen, die Größe kann derzeit aber nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1b221-121">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="1b221-122">Die Vorschau des Lesezeichens zeigt, wie die PowerApp im Lesezeichenergebnis aussehen wird.</span><span class="sxs-lookup"><span data-stu-id="1b221-122">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="1b221-123">Die PowerApp ist in der Vorschau voll funktionsfähig, damit sie einfach zu testen und zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="1b221-123">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="1b221-124">Klicken Sie auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="1b221-124">Click **Publish**.</span></span>
    
<span data-ttu-id="1b221-125">Wenn ein autorisierter Microsoft Search-Benutzer in Bing nach einem der Schlüsselwörter des Lesezeichens oder nach reservierten Schlüsselwörtern sucht, wird die PowerApp im Lesezeichenergebnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b221-125">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

