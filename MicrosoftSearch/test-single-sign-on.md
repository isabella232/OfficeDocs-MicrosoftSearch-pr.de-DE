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
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508929"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="58403-103">Testen des einmaliges Anmeldens</span><span class="sxs-lookup"><span data-stu-id="58403-103">Test single sign-on</span></span>

<span data-ttu-id="58403-p101">Reduzieren Sie die Anzahl, die Benutzer zur Anmeldung aufgefordert werden. Wenn Sie das einmalige Anmelden an einer kleinen Gruppe von Benutzern testen, können Sie Konfigurationsprobleme identifizieren, die zu Sperrungen führen.</span><span class="sxs-lookup"><span data-stu-id="58403-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="58403-106">Für Benutzer von Chrome unter Windows 10 funktioniert das einmalige Anmelden nur, wenn die Windows 10- und die AAD-Anmeldeerweiterung für Chrome installiert ist.</span><span class="sxs-lookup"><span data-stu-id="58403-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="58403-107">Herunterladen der Windows 10- und AAD-Anmeldeerweiterung für Chrome</span><span class="sxs-lookup"><span data-stu-id="58403-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="58403-108">Es wird empfohlen, dass Sie eine Gruppenrichtlinie erstelle, um diese Erweiterung automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="58403-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="58403-109">Wechseln zum Microsoft Search-Verwaltungsportal</span><span class="sxs-lookup"><span data-stu-id="58403-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="58403-110">Klicken Sie im Navigationsbereich auf **Tools**.</span><span class="sxs-lookup"><span data-stu-id="58403-110">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="58403-111">Laden Sie in der Toolsliste die **Windows 10- und AAD-Anmeldeerweiterung für Chrome herunter**.</span><span class="sxs-lookup"><span data-stu-id="58403-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="58403-112">Freigeben der Erweiterung für Chrome Benutzer unter Windows 10</span><span class="sxs-lookup"><span data-stu-id="58403-112">Share the extension with Chrome users on Windows 10</span></span>

  

