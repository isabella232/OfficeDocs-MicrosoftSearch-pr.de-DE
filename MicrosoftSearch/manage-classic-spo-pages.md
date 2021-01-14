---
title: Klassische Seiten in SharePoint Online und Microsoft Search
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Verwenden von Microsoft Search auf klassischen SharePoint-Seiten
ms.openlocfilehash: 9a5aeb2e683297faccfb55d3407653c1791b3961
ms.sourcegitcommit: 7133d46ca9c3a5216ee9159db781febd17e5a831
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49863174"
---
# <a name="classic-pages-and-microsoft-search"></a><span data-ttu-id="5594c-103">Klassische Seiten und Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="5594c-103">Classic pages and Microsoft Search</span></span>

<span data-ttu-id="5594c-104">SharePoint-Websites, die vor modernen Websites erstellt wurden, verwenden ein klassisches Suchfeld und klassische Suchergebnisse.</span><span class="sxs-lookup"><span data-stu-id="5594c-104">SharePoint sites created prior to modern sites use a classic search box and classic search results experience.</span></span> <span data-ttu-id="5594c-105">Wir werden ein Feature zur Standardeinstellung klassischer Seiten für die Verwendung der modernen Suchfunktion mit Microsoft Search verwenden, die personalisierte Ergebnisse mit höherer Relevanz bietet.</span><span class="sxs-lookup"><span data-stu-id="5594c-105">We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.</span></span>

<span data-ttu-id="5594c-106">Die Verwendung von Microsoft Search wird für alle Websites empfohlen, einschließlich der klassischen, aber wenn Ihre klassischen Websites benutzerdefinierte Gestaltungsseiten verwenden und/oder Sie Ihre klassische Suchergebnisse angepasst haben, erkennen wir diese Anpassungen automatisch und wechseln nicht zu Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="5594c-106">Using Microsoft Search is recommended for all sites, including classic, but if your classic sites use custom master pages and/or you have customized your classic search results experience, we will auto-detect these customizations and not switch to Microsoft Search.</span></span>

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a><span data-ttu-id="5594c-107">Klassische Websites, die automatisch zu Microsoft Search wechseln</span><span class="sxs-lookup"><span data-stu-id="5594c-107">Classic sites that will automatically switch to Microsoft Search</span></span>

<span data-ttu-id="5594c-108">Klassische Websites beginnen mit der Verwendung von Microsoft Search, wenn alle folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="5594c-108">Classic sites will start using Microsoft Search if all of the following are true:</span></span>

* <span data-ttu-id="5594c-109">Die Website basiert auf der Teamwebsitevorlage (z. B. STS#0 und STS#1).</span><span class="sxs-lookup"><span data-stu-id="5594c-109">The site is based on the team site template (like STS#0 and STS#1).</span></span>
* <span data-ttu-id="5594c-110">Auf der Website ist das Veröffentlichungsfeature nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5594c-110">The site does not have the publishing feature turned on.</span></span>
* <span data-ttu-id="5594c-111">Die Website verwendet keine benutzerdefinierte Masterseite (eine andere Masterseite als oslo.master oder seattle.master).</span><span class="sxs-lookup"><span data-stu-id="5594c-111">The site does not use a custom master page (a different master page than oslo.master or seattle.master).</span></span>
* <span data-ttu-id="5594c-112">Es gibt keine aktiven Abfrageregeln, mit denen höhergestufte Ergebnisse für die Website, Websitesammlung oder den Mandanten in der Standardergebnisquelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5594c-112">There are no active query rules other than those adding promoted results for the site, site collection or tenant on the default result source.</span></span>
* <span data-ttu-id="5594c-113">Es gibt keine benutzerdefinierten Ergebnistypen für die Website oder die Websitesammlung in der Standardergebnisquelle.</span><span class="sxs-lookup"><span data-stu-id="5594c-113">There are no custom result types for the site or the site collection on the default result source.</span></span>
* <span data-ttu-id="5594c-114">Die Website oder die Websitesammlung wird mit der unten beschriebenen *Einstellung "SearchBoxInNavBar"* nicht von der Option ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5594c-114">The site or the site collection is not opted out of the switch using the *SearchBoxInNavBar* setting described below.</span></span>

<span data-ttu-id="5594c-115">Nach dem Wechsel zu Microsoft Search wird auf klassischen Seiten der Website das Suchfeld in der Suitenavigationsleiste angezeigt, und das klassische Suchfeld wird von der Seite entfernt.</span><span class="sxs-lookup"><span data-stu-id="5594c-115">After the switch to Microsoft Search, classic pages in the site will start to show the search box in the suite navigation bar and remove the classic search box from the page.</span></span> <span data-ttu-id="5594c-116">Wenn ein Benutzer dann nach einem Ausdruck sucht, werden die Ergebnisse mithilfe der modernen Suchfunktion von Microsoft Search angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5594c-116">Then, when a user searches for a term, the results will be displayed using the modern search experience of Microsoft Search.</span></span>

## <a name="staying-with-the-classic-search-experience"></a><span data-ttu-id="5594c-117">Mit der klassischen Sucherfahrung bleiben</span><span class="sxs-lookup"><span data-stu-id="5594c-117">Staying with the classic search experience</span></span>

<span data-ttu-id="5594c-118">Wenn Ihre Website die oben aufgeführten Kriterien erfüllt, Sie jedoch nicht möchten, dass sie zur Microsoft Search-Erfahrung wechselt, können Sie sich mit den folgenden Befehlen als Website- oder Websitesammlungsbesitzer abmelden.</span><span class="sxs-lookup"><span data-stu-id="5594c-118">If your site meets the criteria listed above, but you do not want it to switch to the Microsoft Search experience, you can opt out using the following commands, as the site or site collection owner.</span></span>

<span data-ttu-id="5594c-119">Sie können diesen Befehl jederzeit verwenden, bevor oder nachdem der Wechsel erfolgt ist. Daher ist es einfach, wieder zu der Sucherfahrung zurückwechseln, die Sie zuvor hatten.</span><span class="sxs-lookup"><span data-stu-id="5594c-119">You can use this command at any time, before or after the switch happens, so it is easy to go back to the search experience you had previously.</span></span>

<span data-ttu-id="5594c-120">Um die folgenden Befehle auszuführen, verwenden Sie PowerShell mit SharePoint PnP PowerShell-Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="5594c-120">To run the commands below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="5594c-121">Hier können Sie die ersten Schritte installieren und weitere Informationen [dazu erhalten.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="5594c-121">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="5594c-122">Mit dem folgenden Befehl melden Sie sich bei Ihrer Website oder Websitesammlung an:</span><span class="sxs-lookup"><span data-stu-id="5594c-122">You will sign in to your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

<span data-ttu-id="5594c-123">Führen Sie den folgenden Befehl aus, um mit der klassischen Sucherfahrung für eine Website zu bleiben:</span><span class="sxs-lookup"><span data-stu-id="5594c-123">To stay with classic search experience for a site, run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

<span data-ttu-id="5594c-124">Alternativ können Sie diesen Befehl verwenden, wenn Sie ihn für alle Websites in einer Websitesammlung festlegen möchten:</span><span class="sxs-lookup"><span data-stu-id="5594c-124">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a><span data-ttu-id="5594c-125">Opting to Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="5594c-125">Opting into Microsoft Search</span></span>

<span data-ttu-id="5594c-126">Für Websites, die die oben aufgeführten Kriterien nicht erfüllen, oder für bestimmte Websites in einer Websitesammlung, die sich für die klassische Verwendung entschieden haben, können Sie die Microsoft Search-Erfahrung manuell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5594c-126">For those sites that do not meet the criteria listed above, or for specific sites in a site collection that opted to stay in classic, you can manually enable the Microsoft Search experience.</span></span>

<span data-ttu-id="5594c-127">Um diese Einstellung für einen bestimmten Standort zu ändern, können Sie diesen Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="5594c-127">To change this setting for a specific site, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

<span data-ttu-id="5594c-128">Wenn Sie es für alle Websites in einer Websitesammlung festlegen möchten, können Sie diesen Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="5594c-128">If you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> <span data-ttu-id="5594c-129">Sie können Microsoft Search nur für eine Teamwebsite oder Veröffentlichungswebsite manuell aktivieren (Vorlagen-IDs, die "STS", "CMSPUBLISHING", "BLANKINTERNET" und "GROUP" enthalten).</span><span class="sxs-lookup"><span data-stu-id="5594c-129">You can manually enable Microsoft Search only for a Team Site or Publishing Site (template ids that contain "STS", "CMSPUBLISHING", "BLANKINTERNET" and "GROUP").</span></span>
