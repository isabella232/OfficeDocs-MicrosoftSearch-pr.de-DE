---
title: Testen des einmaliges Anmeldens
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: a220c1bf-7cee-448a-90a3-310284d03e81
ROBOTS: NOINDEX
description: Reduzieren Sie die Anzahl, die Windows 10-Benutzer zur Anmeldung bei Microsoft Search und Office 365 aufgefordert werden.
ms.openlocfilehash: c05a8ffcc973926add551bdbb20273b41ea23bc0
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591044"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="b026c-103">Testen des einmaliges Anmeldens</span><span class="sxs-lookup"><span data-stu-id="b026c-103">Test single sign-on</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b026c-104">Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal.</span><span class="sxs-lookup"><span data-stu-id="b026c-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="b026c-105">Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird es entfernt.</span><span class="sxs-lookup"><span data-stu-id="b026c-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="b026c-106">Es wird empfohlen, dass Sie zu Beginn das Microsoft 365 Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="b026c-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="b026c-107">[Übersicht über Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="b026c-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="b026c-p102">Reduzieren Sie die Anzahl, die Benutzer zur Anmeldung aufgefordert werden. Wenn Sie das einmalige Anmelden an einer kleinen Gruppe von Benutzern testen, können Sie Konfigurationsprobleme identifizieren, die zu Sperrungen führen.</span><span class="sxs-lookup"><span data-stu-id="b026c-p102">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="b026c-110">Für Benutzer von Chrome unter Windows 10 funktioniert das einmalige Anmelden nur, wenn die Windows 10- und die AAD-Anmeldeerweiterung für Chrome installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b026c-110">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="b026c-111">Herunterladen der Windows 10- und AAD-Anmeldeerweiterung für Chrome</span><span class="sxs-lookup"><span data-stu-id="b026c-111">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="b026c-112">Es wird empfohlen, dass Sie eine Gruppenrichtlinie erstelle, um diese Erweiterung automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b026c-112">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="b026c-113">Wechseln zum Microsoft Search-Verwaltungsportal</span><span class="sxs-lookup"><span data-stu-id="b026c-113">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="b026c-114">Klicken Sie im Navigationsbereich auf **Tools**.</span><span class="sxs-lookup"><span data-stu-id="b026c-114">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="b026c-115">Laden Sie in der Toolsliste die **Windows 10- und AAD-Anmeldeerweiterung für Chrome herunter**.</span><span class="sxs-lookup"><span data-stu-id="b026c-115">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="b026c-116">Freigeben der Erweiterung für Chrome Benutzer unter Windows 10</span><span class="sxs-lookup"><span data-stu-id="b026c-116">Share the extension with Chrome users on Windows 10</span></span>

  

