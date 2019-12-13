---
title: Integrieren von Power apps
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
description: Einschließen von browserbasierten apps in Lesezeichen Ergebnisse für Microsoft-Suche
ms.openlocfilehash: 7d3dd21758c63da14bbd3896ece1ce67a19c80a2
ms.sourcegitcommit: f4cb37fdf85b895337caee827fb72b5b7fcaa8ad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2019
ms.locfileid: "39995023"
---
# <a name="integrate-power-apps-in-microsoft-search-bookmarks"></a><span data-ttu-id="278a0-103">Integrieren von Power apps in Microsoft Search-Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="278a0-103">Integrate Power Apps in Microsoft Search bookmarks</span></span>
   
<span data-ttu-id="278a0-104">Helfen Sie Ihren Benutzern, Aufgaben wie das Eingeben von Urlaubszeiten oder Berichtsausgaben zu erledigen, indem Sie vorhandene [Microsoft Power-apps](https://products.office.com/business/microsoft-powerapps) in Ihre Microsoft-Such-Lesezeichen integrieren.</span><span class="sxs-lookup"><span data-stu-id="278a0-104">Help your users complete tasks, like entering vacation time or reporting expenses, by integrating existing [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) into your Microsoft Search bookmarks.</span></span> <span data-ttu-id="278a0-105">Integrierte Power apps werden in einem Lesezeichen Ergebnis angezeigt, wodurch die Notwendigkeit vermieden wird, zu einer anderen Website zu wechseln oder ein separates Tool zu öffnen, was Zeit und Aufwand spart.</span><span class="sxs-lookup"><span data-stu-id="278a0-105">Integrated Power Apps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-power-apps"></a><span data-ttu-id="278a0-106">Was sind Power-apps?</span><span class="sxs-lookup"><span data-stu-id="278a0-106">What are Power Apps?</span></span>

<span data-ttu-id="278a0-107">[Power apps](https://products.office.com/business/microsoft-powerapps) ist ein Dienst, mit dem Sie Geschäftsanwendungen erstellen können, die in einem Browser oder auf einem Telefon oder Tablet ausgeführt werden, ohne dass eine Programmiererfahrung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="278a0-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="278a0-108">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="278a0-108">Learn more:</span></span>
  
- [<span data-ttu-id="278a0-109">Interaktives Lernen</span><span class="sxs-lookup"><span data-stu-id="278a0-109">Guided Learning</span></span>](https://docs.microsoft.com/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="278a0-110">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="278a0-110">Documentation</span></span>](https://docs.microsoft.com/powerapps/)
    
## <a name="add-a-power-app-to-a-bookmark"></a><span data-ttu-id="278a0-111">Hinzufügen einer Power-APP zu einer Textmarke</span><span class="sxs-lookup"><span data-stu-id="278a0-111">Add a Power App to a bookmark</span></span>

<span data-ttu-id="278a0-112">[Power Apps (https://products.office.com/business/microsoft-powerapps) arbeiten Sie in einem beliebigen Browser und auf einem beliebigen Gerät und nehmen Sie weniger als eine Minute Zeit in Anspruch.</span><span class="sxs-lookup"><span data-stu-id="278a0-112">[Power Apps(https://products.office.com/business/microsoft-powerapps) work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="278a0-113">[Suchen Sie die APP-ID für die Power-App](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) , die Sie integrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="278a0-113">[Find the App ID for the Power App](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate.</span></span>
    
2. <span data-ttu-id="278a0-114">Wechseln Sie im Microsoft 365 [Admin Center](https://admin.microsoft.com)zu **Lesezeichen**.</span><span class="sxs-lookup"><span data-stu-id="278a0-114">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Bookmarks**.</span></span>
    
3. <span data-ttu-id="278a0-115">Fügen Sie eine Textmarke hinzu, oder suchen Sie nach einer vorhandenen Textmarke, der Sie eine Power-app hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="278a0-115">Add a bookmark or find an existing bookmark that you want to add a Power App to.</span></span>
    
4. <span data-ttu-id="278a0-116">Wählen Sie in den Lesezeichen Einstellungen die Option **Power App**aus, und wählen Sie dann **Power app hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="278a0-116">In the bookmark settings, select **Power App**, and then select **Add a Power App**.</span></span>
    
5. <span data-ttu-id="278a0-117">Geben oder fügen Sie die App-ID ein.</span><span class="sxs-lookup"><span data-stu-id="278a0-117">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="278a0-118">Die Höhe und Breite werden automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="278a0-118">The height and width are automatically added.</span></span> <span data-ttu-id="278a0-119">Lesezeichen können Hoch- und Querformat unterstützen, die Größe kann derzeit aber nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="278a0-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="278a0-120">Die Lesezeichen Vorschau zeigt, wie die Power-App im Lesezeichen Ergebnis angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="278a0-120">The bookmark preview shows how the Power App will appear in the bookmark result.</span></span>
    
    <span data-ttu-id="278a0-121">Die Power-app in der Vorschau ist voll funktionsfähig, damit Sie einfach getestet und verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="278a0-121">The Power App in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="278a0-122">Wählen Sie **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="278a0-122">Select **Publish**.</span></span>
    
<span data-ttu-id="278a0-123">Wenn ein autorisierter Microsoft Search-Benutzer nach [Bing](https://Bing.com) nach einem der Schlüsselwörter oder reservierten Schlüsselwörter des Lesezeichens sucht, wird die Power-App im Lesezeichen Ergebnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="278a0-123">When an authorized Microsoft Search user searches on [Bing](https://Bing.com) for any of the bookmark's keywords or reserved keywords, the Power App will appear in the bookmark result.</span></span>
