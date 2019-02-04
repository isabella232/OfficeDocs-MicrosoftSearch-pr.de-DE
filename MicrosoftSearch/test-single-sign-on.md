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
description: Reduzieren Sie die Anzahl, die Windows 10-Benutzer zur Anmeldung bei Microsoft Search und Office 365 aufgefordert werden.
ms.openlocfilehash: 55d359edac36020ec8cf2aad6b64ca9737ee1066
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612353"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="b4d26-103">Testen des einmaliges Anmeldens</span><span class="sxs-lookup"><span data-stu-id="b4d26-103">Test single sign-on</span></span>

<span data-ttu-id="b4d26-p101">Reduzieren Sie die Anzahl, die Benutzer zur Anmeldung aufgefordert werden. Wenn Sie das einmalige Anmelden an einer kleinen Gruppe von Benutzern testen, können Sie Konfigurationsprobleme identifizieren, die zu Sperrungen führen.</span><span class="sxs-lookup"><span data-stu-id="b4d26-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="b4d26-106">Für Benutzer von Chrome unter Windows 10 funktioniert das einmalige Anmelden nur, wenn die Windows 10- und die AAD-Anmeldeerweiterung für Chrome installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b4d26-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="b4d26-107">Herunterladen der Windows 10- und AAD-Anmeldeerweiterung für Chrome</span><span class="sxs-lookup"><span data-stu-id="b4d26-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="b4d26-108">Es wird empfohlen, dass Sie eine Gruppenrichtlinie erstelle, um diese Erweiterung automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b4d26-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="b4d26-109">Wechseln zum Microsoft Search-Verwaltungsportal</span><span class="sxs-lookup"><span data-stu-id="b4d26-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="b4d26-110">Klicken Sie im Navigationsbereich auf **Tools**.</span><span class="sxs-lookup"><span data-stu-id="b4d26-110">In the navigation pane, click **ADSI Edit**.</span></span>
    
3. <span data-ttu-id="b4d26-111">Laden Sie in der Toolsliste die **Windows 10- und AAD-Anmeldeerweiterung für Chrome herunter**.</span><span class="sxs-lookup"><span data-stu-id="b4d26-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="b4d26-112">Freigeben der Erweiterung für Chrome Benutzer unter Windows 10</span><span class="sxs-lookup"><span data-stu-id="b4d26-112">Share the extension with Chrome users on Windows 10</span></span>

  

