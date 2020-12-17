---
title: Klassische Seiten in SharePoint Online und Microsoft-Suche
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
description: Verwenden der Microsoft-Suche auf klassischen SharePoint-Seiten
ms.openlocfilehash: 605e63a30ad166c63320c7e89e1b2745e628e15d
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700973"
---
# <a name="classic-pages-and-microsoft-search"></a><span data-ttu-id="d6658-103">Klassische Seiten und Microsoft-Suche</span><span class="sxs-lookup"><span data-stu-id="d6658-103">Classic pages and Microsoft Search</span></span>

<span data-ttu-id="d6658-104">SharePoint-Websites, die vor modernen Websites erstellt wurden, verwenden ein klassisches Suchfeld und eine klassische Suchergebnis Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="d6658-104">SharePoint sites created prior to modern sites use a classic search box and classic search results experience.</span></span> <span data-ttu-id="d6658-105">Wir werden ein Feature bereitstellen, das standardmäßig die klassischen Seiten verwendet, um die moderne Suchumgebung zu verwenden, die die Microsoft-Suche verwendet, wodurch personalisierte Ergebnisse mit höherer Relevanz bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d6658-105">We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.</span></span>

<span data-ttu-id="d6658-106">Die Verwendung von Microsoft Search wird für alle Websites, einschließlich Classic, empfohlen, aber wenn Ihre klassischen Websites benutzerdefinierte Gestaltungsvorlagen verwenden und/oder Sie Ihre klassischen Suchergebnisse angepasst haben, werden wir diese Anpassungen automatisch erkennen und nicht zur Microsoft-Suche wechseln.</span><span class="sxs-lookup"><span data-stu-id="d6658-106">Using Microsoft Search is recommended for all sites, including classic, but if your classic sites use custom master pages and/or you have customized your classic search results experience, we will auto-detect these customizations and not switch to Microsoft Search.</span></span>

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a><span data-ttu-id="d6658-107">Klassische Websites, die automatisch zur Microsoft-Suche gewechselt werden</span><span class="sxs-lookup"><span data-stu-id="d6658-107">Classic sites that will automatically switch to Microsoft Search</span></span>

<span data-ttu-id="d6658-108">Bei klassischen Websites wird Microsoft Search verwendet, wenn alle der folgenden Kriterien zutreffen.</span><span class="sxs-lookup"><span data-stu-id="d6658-108">Classic sites will start using Microsoft Search if all of the following are true.</span></span>

* <span data-ttu-id="d6658-109">Die Website basiert auf der Vorlage für die Teamwebsite (wie STS # 0 und STS # 1).</span><span class="sxs-lookup"><span data-stu-id="d6658-109">The site is based on the team site template (like STS#0 and STS#1).</span></span>
* <span data-ttu-id="d6658-110">Auf der Website ist das Veröffentlichungsfeature nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d6658-110">The site does not have the publishing feature turned on.</span></span>
* <span data-ttu-id="d6658-111">Die Website verwendet keine benutzerdefinierte Gestaltungsvorlage (eine andere Gestaltungsvorlage als Oslo. Master oder Seattle. Master).</span><span class="sxs-lookup"><span data-stu-id="d6658-111">The site does not use a custom master page (a different master page than oslo.master or seattle.master).</span></span>
* <span data-ttu-id="d6658-112">Es gibt keine aktiven Abfrageregeln außer denen, die höher gestufte Ergebnisse für die Website, Websitesammlung oder den Mandanten in der Standardergebnis Quelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6658-112">There are no active query rules other than those adding promoted results for the site, site collection or tenant on the default result source.</span></span>
* <span data-ttu-id="d6658-113">Es gibt keine benutzerdefinierten Ergebnistypen für die Website oder die Websitesammlung in der Standardergebnis Quelle.</span><span class="sxs-lookup"><span data-stu-id="d6658-113">There are no custom result types for the site or the site collection on the default result source.</span></span>
* <span data-ttu-id="d6658-114">Die Website oder die Websitesammlung, in der Sie enthalten ist, hat sich nicht aus dem Switch mit der unten beschriebenen SearchBoxInNavBar-Einstellung entschieden.</span><span class="sxs-lookup"><span data-stu-id="d6658-114">The site or the site collection it is part of has not opted out of the switch using the SearchBoxInNavBar setting described below.</span></span>

<span data-ttu-id="d6658-115">Nach dem Wechsel zur Microsoft-Suche wird durch die klassischen Seiten der Website das Suchfeld in der Suite-Navigationsleiste angezeigt und das klassische Suchfeld von der Seite entfernt.</span><span class="sxs-lookup"><span data-stu-id="d6658-115">After the switch to Microsoft Search, classic pages in the site will start to show the search box in the suite navigation bar and remove the classic search box from the page.</span></span> <span data-ttu-id="d6658-116">Wenn ein Benutzer nach einem Begriff sucht, werden die Ergebnisse dann mithilfe der modernen Suchumgebung von Microsoft Search angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6658-116">Then, when a user searches for a term, the results will be displayed using the modern search experience of Microsoft Search.</span></span>

## <a name="staying-with-the-classic-search-experience"></a><span data-ttu-id="d6658-117">Wohnen mit der klassischen Suchumgebung</span><span class="sxs-lookup"><span data-stu-id="d6658-117">Staying with the classic search experience</span></span>

<span data-ttu-id="d6658-118">Wenn Ihre Website die oben aufgeführten Kriterien erfüllt, Sie jedoch nicht zu der Microsoft-Suchumgebung wechseln möchten, können Sie die folgenden Befehle als Website-oder Websitesammlungsbesitzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d6658-118">If your site meets the criteria listed above, but you do not want it to switch to the Microsoft Search experience, you can opt out using the following commands, as the site or site collection owner.</span></span>

<span data-ttu-id="d6658-119">Sie können diesen Befehl jederzeit verwenden, bevor oder nachdem der Wechsel erfolgt ist, sodass es einfach ist, wieder zu der zuvor verwendeten Suchumgebung zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="d6658-119">You can use this command at any time, before or after the switch happens, so it is easy to go back to the search experience you had previously.</span></span>

<span data-ttu-id="d6658-120">Um die folgenden Befehle auszuführen, verwenden Sie PowerShell mit SharePoint PNP PowerShell Extensions.</span><span class="sxs-lookup"><span data-stu-id="d6658-120">To run the commands below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="d6658-121">Sie können die ersten Schritte [hier](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)installieren und weitere Informationen dazu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d6658-121">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="d6658-122">Sie melden sich bei Ihrer Website oder Websitesammlung mit folgendem Befehl an:</span><span class="sxs-lookup"><span data-stu-id="d6658-122">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials
```

<span data-ttu-id="d6658-123">Führen Sie den folgenden Befehl aus, um mit der klassischen Suchumgebung für eine Website zu bleiben:</span><span class="sxs-lookup"><span data-stu-id="d6658-123">To stay with classic search experience for a site, run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

<span data-ttu-id="d6658-124">Alternativ können Sie diesen Befehl verwenden, wenn Sie ihn für alle Websites in einer Websitesammlung festlegen möchten:</span><span class="sxs-lookup"><span data-stu-id="d6658-124">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a><span data-ttu-id="d6658-125">Opting in Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="d6658-125">Opting into Microsoft Search</span></span>

<span data-ttu-id="d6658-126">Für Websites, die die oben aufgeführten Kriterien nicht erfüllen, oder für bestimmte Websites in einer Websitesammlung, die sich für den klassischen Aufenthalt entschieden haben, können Sie die Microsoft-Suchumgebung manuell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d6658-126">For those sites that do not meet the criteria listed above, or for specific sites in a site collection that opted to stay in classic, you can manually enable the Microsoft Search experience.</span></span>

<span data-ttu-id="d6658-127">Um diese Einstellung für eine bestimmte Website zu ändern, können Sie diesen Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="d6658-127">To change this setting for a specific site, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

<span data-ttu-id="d6658-128">Wenn Sie es für alle Websites in einer Websitesammlung festlegen möchten, können Sie diesen Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="d6658-128">If you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> <span data-ttu-id="d6658-129">Sie können Microsoft Search nur für eine Team Website oder eine Veröffentlichungswebsite manuell aktivieren (Vorlagen-IDs, die "STS", "CMSPUBLISHING", "BLANKINTERNET" und "Group" enthalten).</span><span class="sxs-lookup"><span data-stu-id="d6658-129">You can manually enable Microsoft Search only for a Team Site or Publishing Site (template ids that contain "STS", "CMSPUBLISHING", "BLANKINTERNET" and "GROUP").</span></span>
