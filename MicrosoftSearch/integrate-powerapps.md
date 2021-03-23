---
title: Integrieren von Power Apps
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
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
description: Einfügen browserbasierter Apps in Lesezeichenergebnisse für Microsoft Search
ms.openlocfilehash: 52fa78c54ab6db74ef1e3679d3d32151a3f5ac10
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031701"
---
# <a name="integrate-power-apps-in-microsoft-search-bookmarks"></a><span data-ttu-id="e0ef4-103">Integrieren von Power Apps in Microsoft Search-Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="e0ef4-103">Integrate Power Apps in Microsoft Search bookmarks</span></span>
   
<span data-ttu-id="e0ef4-104">Helfen Sie Ihren Benutzern beim Ausführen von Aufgaben, z. B. beim Eingeben von Urlaubs- oder Berichtskosten, indem Sie vorhandene [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) in Ihre Microsoft Search-Lesezeichen integrieren.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-104">Help your users complete tasks, like entering vacation time or reporting expenses, by integrating existing [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) into your Microsoft Search bookmarks.</span></span> <span data-ttu-id="e0ef4-105">Integrierte Power Apps werden in einem Lesezeichenergebnis angezeigt, sodass sie nicht zu einer anderen Website wechseln oder ein separates Tool öffnen müssen, was Zeit und Aufwand spart.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-105">Integrated Power Apps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-power-apps"></a><span data-ttu-id="e0ef4-106">Was sind Power Apps?</span><span class="sxs-lookup"><span data-stu-id="e0ef4-106">What are Power Apps?</span></span>

<span data-ttu-id="e0ef4-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) ist ein Dienst, mit dem Sie Geschäfts-Apps erstellen können, die in einem Browser oder auf einem Smartphone oder Tablet ohne Codierungserfahrung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="e0ef4-108">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="e0ef4-108">Learn more:</span></span>
  
- [<span data-ttu-id="e0ef4-109">Interaktives Lernen</span><span class="sxs-lookup"><span data-stu-id="e0ef4-109">Guided Learning</span></span>](/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="e0ef4-110">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="e0ef4-110">Documentation</span></span>](/powerapps/)
    
## <a name="add-a-power-app-to-a-bookmark"></a><span data-ttu-id="e0ef4-111">Hinzufügen einer Power App zu einer Textmarke</span><span class="sxs-lookup"><span data-stu-id="e0ef4-111">Add a Power App to a bookmark</span></span>

<span data-ttu-id="e0ef4-112">[Power Apps( funktioniert in jedem Browser und auf jedem Gerät und https://products.office.com/business/microsoft-powerapps) dauert weniger als eine Minute.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-112">[Power Apps(https://products.office.com/business/microsoft-powerapps) work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="e0ef4-113">[Suchen Sie die App-ID für die Power App,](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) die Sie integrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-113">[Find the App ID for the Power App](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate.</span></span>
    
2. <span data-ttu-id="e0ef4-114">Wechseln Sie im Microsoft 365 [Admin Center](https://admin.microsoft.com)zu **Lesezeichen**.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-114">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Bookmarks**.</span></span>
    
3. <span data-ttu-id="e0ef4-115">Fügen Sie ein Lesezeichen hinzu, oder suchen Sie nach einer vorhandenen Textmarke, der Sie eine Power App hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-115">Add a bookmark or find an existing bookmark that you want to add a Power App to.</span></span>
    
4. <span data-ttu-id="e0ef4-116">Wählen Sie in den Lesezeicheneinstellungen **Power App** aus, und wählen Sie dann Power App **hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="e0ef4-116">In the bookmark settings, select **Power App**, and then select **Add a Power App**.</span></span>
    
5. <span data-ttu-id="e0ef4-117">Geben oder fügen Sie die App-ID ein.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-117">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="e0ef4-118">Die Höhe und Breite werden automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-118">The height and width are automatically added.</span></span> <span data-ttu-id="e0ef4-119">Lesezeichen können Hoch- und Querformat unterstützen, die Größe kann derzeit aber nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="e0ef4-120">Die Lesezeichenvorschau zeigt, wie die Power App im Lesezeichenergebnis angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-120">The bookmark preview shows how the Power App will appear in the bookmark result.</span></span>
    
    <span data-ttu-id="e0ef4-121">Die Power App in der Vorschau ist voll funktionsfähig, damit sie einfach zu testen und zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-121">The Power App in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="e0ef4-122">Wählen Sie **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-122">Select **Publish**.</span></span>
    
<span data-ttu-id="e0ef4-123">Wenn ein autorisierter Microsoft Search-Benutzer in [Bing](https://Bing.com) nach schlüsselwörtern oder reservierten Schlüsselwörtern der Textmarke sucht, wird die Power App im Lesezeichenergebnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0ef4-123">When an authorized Microsoft Search user searches on [Bing](https://Bing.com) for any of the bookmark's keywords or reserved keywords, the Power App will appear in the bookmark result.</span></span>