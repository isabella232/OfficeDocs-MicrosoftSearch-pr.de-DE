---
title: Verwalten des Such Felds in SharePoint-Websites
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
description: Vorgehensweise Anpassen des Such Feld Erlebnisses auf SharePoint-Websites
ms.openlocfilehash: 6ebd084aadb38acb5475b7e43d7c4092ffc09eb8
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700964"
---
# <a name="search-box-settings-on-sharepoint-sites"></a><span data-ttu-id="1b86c-103">Such Feld Einstellungen auf SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="1b86c-103">Search box settings on SharePoint sites</span></span>

<span data-ttu-id="1b86c-104">Eine der verschiedenen Möglichkeiten, auf denen die Microsoft-Suche auf SharePoint-Websites angepasst werden kann, besteht darin, die Funktionsweise des Suchfelds in der Suite-Navigationsleiste auf SharePoint-Websites zu optimieren und Ihren Anforderungen optimal anzupassen.</span><span class="sxs-lookup"><span data-stu-id="1b86c-104">One of the several ways Microsoft Search can be customized on SharePoint sites is to tailor how the search box in the suite navigation bar works in SharePoint sites to best fit your needs.</span></span>

<span data-ttu-id="1b86c-105">Weitere Anpassungsoptionen finden Sie unter [Ändern der Microsoft-Suchergebnisseite, um benutzerdefinierte vertikalen, Ergebnistypen und Layouts hinzuzufügen](customize-search-page.md)und [eine benutzerdefinierte Suchergebnisseite zu erstellen](create-search-results-pages.md).</span><span class="sxs-lookup"><span data-stu-id="1b86c-105">For other customization options, see [Changing the Microsoft Search results page to add custom verticals, result types and layouts](customize-search-page.md), and [Creating a custom search results page](create-search-results-pages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1b86c-106">Das Suchfeld für die Suite-Navigationsleiste steht derzeit nicht für alle Kunden zur Verfügung, aber diese Optionen können jetzt noch festgelegt werden, und Sie werden wirksam, sobald Sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1b86c-106">The suite navigation bar search box is not available for all customers at this time, but these options can still be set now and they will take effect when it becomes available.</span></span>

<span data-ttu-id="1b86c-107">Für die unten aufgeführten Aufgaben verwenden Sie PowerShell mit SharePoint PNP PowerShell-Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="1b86c-107">For the tasks listed below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="1b86c-108">Sie können die ersten Schritte [hier](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)installieren und weitere Informationen dazu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1b86c-108">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="1b86c-109">Sie melden sich bei Ihrer Website oder Websitesammlung mit folgendem Befehl an:</span><span class="sxs-lookup"><span data-stu-id="1b86c-109">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a><span data-ttu-id="1b86c-110">Ändern des Suchbereichs</span><span class="sxs-lookup"><span data-stu-id="1b86c-110">Changing the scope of search</span></span>

<span data-ttu-id="1b86c-111">Wenn Sie eine neue Website in SharePoint Online heute erstellen und in das Suchfeld eingeben, gelangen Sie zur Microsoft-Suchergebnisseite.</span><span class="sxs-lookup"><span data-stu-id="1b86c-111">When you create a new site in SharePoint Online today, and type into the search box, you are taken to the Microsoft Search results page.</span></span> <span data-ttu-id="1b86c-112">Auf dieser Seite werden die Ergebnisse Ihrer aktuellen Website standardmäßig angezeigt, und Sie können den Suchbereich auf den Hub erweitern, dem die aktuelle Website zugeordnet ist (sofern vorhanden), oder für die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="1b86c-112">This page shows results from your current site by default and allows you to expand the scope of your search to the hub that the current site is associated with (if there is one), or to the whole organization.</span></span>

<span data-ttu-id="1b86c-113">Der Bereich, den das Suchfeld verwendet, hängt standardmäßig vom Typ der Website ab.</span><span class="sxs-lookup"><span data-stu-id="1b86c-113">The scope the search box uses, by default, depends on type of site.</span></span>

* <span data-ttu-id="1b86c-114">Durchsuchen regulärer Websites über die aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="1b86c-114">Regular sites search over the current site.</span></span>
* <span data-ttu-id="1b86c-115">Hub-Standorte suchen über alle Standorte im Hub.</span><span class="sxs-lookup"><span data-stu-id="1b86c-115">Hub sites search over all sites in the hub.</span></span>
* <span data-ttu-id="1b86c-116">Home Websites-Suche über alle Inhalte.</span><span class="sxs-lookup"><span data-stu-id="1b86c-116">Home sites search over all content.</span></span>

<span data-ttu-id="1b86c-117">In einigen Fällen möchten Sie möglicherweise diese Standardwerte so ändern, dass Sie immer über die gesamte Organisation oder über den Hub hinweg suchen, dem eine Website zugeordnet ist, ohne dass ein zusätzlicher Mausklick erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1b86c-117">In some cases, you may want to change these defaults to always search over the whole organization, or across the hub a site is associated with, without needing an additional click.</span></span>

<span data-ttu-id="1b86c-118">Als Websitebesitzer können Sie diese Standardeinstellungen mit dem folgenden Befehl ändern:</span><span class="sxs-lookup"><span data-stu-id="1b86c-118">As a site owner, you can change these defaults using the following command:</span></span>

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

<span data-ttu-id="1b86c-119">Nachdem Sie diesen Befehl ausführen, zeigt die Website, auf der zuvor Ergebnisse der aktuellen Website standardmäßig angezeigt werden, die Ergebnisse der gesamten Organisation an.</span><span class="sxs-lookup"><span data-stu-id="1b86c-119">After running this command, the site that was previously showing results from the current site by default will start to show results from the whole organization.</span></span>

<span data-ttu-id="1b86c-120">Wenn Sie zur Standardeinstellung zurückkehren möchten, führen Sie den Befehl erneut mit dem Wert "DefaultScope" aus.</span><span class="sxs-lookup"><span data-stu-id="1b86c-120">To go back to the default setting, run the command again with the value “DefaultScope".</span></span> <span data-ttu-id="1b86c-121">Verwenden Sie "Hub" als SearchScope-Wert, um die Suche im Hub durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="1b86c-121">To search across the Hub, use “Hub” as the SearchScope value.</span></span>

<span data-ttu-id="1b86c-122">Diese Einstellung gilt für die jeweilige Websiteebene.</span><span class="sxs-lookup"><span data-stu-id="1b86c-122">This setting applies at the individual site level.</span></span> <span data-ttu-id="1b86c-123">Für Websitesammlungen gibt es keine entsprechende Einstellung.</span><span class="sxs-lookup"><span data-stu-id="1b86c-123">There is no equivalent setting for site collections.</span></span>

## <a name="show-or-hide-the-search-box"></a><span data-ttu-id="1b86c-124">Anzeigen oder Ausblenden des Suchfelds</span><span class="sxs-lookup"><span data-stu-id="1b86c-124">Show or hide the search box</span></span>

<span data-ttu-id="1b86c-125">Sie können das Suchfeld der Suite-Navigationsleiste ausblenden, wenn Sie verhindern möchten, dass Ihre Benutzer suchen oder eine benutzerdefinierte Such Feld Implementierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b86c-125">You can choose to hide the suite navigation bar search box if you want to prevent your users from searching or to use a custom search box implementation.</span></span>

<span data-ttu-id="1b86c-126">Verwenden Sie diesen Befehl, um diese Einstellung für eine bestimmte Website zu ändern:</span><span class="sxs-lookup"><span data-stu-id="1b86c-126">To change this setting for a given site use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="1b86c-127">Alternativ können Sie diesen Befehl verwenden, wenn Sie ihn für alle Websites in einer Websitesammlung festlegen möchten:</span><span class="sxs-lookup"><span data-stu-id="1b86c-127">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="1b86c-128">Nach dem Ausführen dieser Befehle wird das Suchfeld nicht mehr in der Navigationsleiste oben auf der Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b86c-128">After running these commands, the search box will no longer show up in the navigation bar on top of your page.</span></span> <span data-ttu-id="1b86c-129">Wenn Sie zum Anzeigen des Suchfeld zurückkehren möchten, führen Sie die Befehle erneut aus, wobei der Wert für den Parameter "SearchBoxInNavBar" auf "Inherit" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1b86c-129">To go back to showing the search box, run the commands again with the value provided to "SearchBoxInNavBar" parameter to “Inherit”.</span></span>

<span data-ttu-id="1b86c-130">Es gibt mehrere Punkte, die beachtet werden sollten:</span><span class="sxs-lookup"><span data-stu-id="1b86c-130">There are several points to consider:</span></span>

* <span data-ttu-id="1b86c-131">Diese Einstellung gilt nur für das Suchfeld in der Suite-Navigationsleiste.</span><span class="sxs-lookup"><span data-stu-id="1b86c-131">This setting only applies to the search box in the suite navigation bar.</span></span> <span data-ttu-id="1b86c-132">Sie gilt nicht für Suchfelder auf der Seite oder für Suchfelder auf klassischen Seiten.</span><span class="sxs-lookup"><span data-stu-id="1b86c-132">It does not apply to search boxes that are in the page, or to search boxes on classic pages.</span></span>

* <span data-ttu-id="1b86c-133">Wenn Sie das Suchfeld in der Navigationsleiste deaktiviert haben, müssen Sie es selbst mithilfe eines benutzerdefinierten Webparts oder einer SharePoint-Framework-Erweiterung bereitstellen, wenn Sie Suchfunktionen auf Ihrer Website benötigen.</span><span class="sxs-lookup"><span data-stu-id="1b86c-133">Once you’ve disabled the search box in the navigation bar, if you want search functionality in your site, you will have to provide it yourself using a custom web part or a SharePoint Framework extension.</span></span>

* <span data-ttu-id="1b86c-134">Mit dieser Lösung wird das Suchfeld auch aus Listen und Bibliotheken für Ihre Website entfernt.</span><span class="sxs-lookup"><span data-stu-id="1b86c-134">This solution will remove the search box from lists and libraries for your site as well.</span></span> <span data-ttu-id="1b86c-135">Ihre benutzerdefinierte Suchlösung muss neben der websiteweiten Suche auch kontextbezogene Suchvorgänge für SharePoint-Listen und-Bibliotheken in Frage stellen.</span><span class="sxs-lookup"><span data-stu-id="1b86c-135">Your custom search solution will need to consider contextual searches for SharePoint lists and libraries, in addition to site-wide search.</span></span>

* <span data-ttu-id="1b86c-136">Wenn Sie die Einstellung auf die Stammwebsite Ihrer Domäne anwenden, wird auch auf der SharePoint-Startseite das Suchfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b86c-136">If you apply the setting to the root site of your domain, the SharePoint start page will also stop showing the search box.</span></span>

## <a name="changing-the-hint-displayed-in-the-search-box"></a><span data-ttu-id="1b86c-137">Ändern des in das Suchfeld angezeigten antipps</span><span class="sxs-lookup"><span data-stu-id="1b86c-137">Changing the hint displayed in the search box</span></span>

<span data-ttu-id="1b86c-138">Sie können den Hinweis ändern, der im Suchfeld für eine bestimmte Website oder Websitesammlung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1b86c-138">You can change the hint the search box shows for a given site or site collection.</span></span> <span data-ttu-id="1b86c-139">Dies ist der Text, der im Suchfeld angezeigt wird, bevor Sie mit der Eingabe beginnen.</span><span class="sxs-lookup"><span data-stu-id="1b86c-139">This is the text that appears in the search box before they start typing into it.</span></span> <span data-ttu-id="1b86c-140">Dies kann dazu führen, dass Ihre Benutzer über die von der Suche erwarteten Ergebnisse erfahren, wenn Sie eine benutzerdefinierte Ergebnisseite oder ein geändertes Suchverhalten auf andere Weise konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="1b86c-140">This may help guide your users about what to expect from search if you’ve configured a custom results page or changed behavior of search in other ways.</span></span>

> [!NOTE]
> <span data-ttu-id="1b86c-141">Um diese Änderung vornehmen zu können, müssen Sie das Ausführen benutzerdefinierter Skripts auf der fraglichen Website als mandantenadministrator zulassen, was standardmäßig nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="1b86c-141">To be able to make this change, you need to allow running custom scripts on the site in question as a tenant administrator, which is disallowed by default.</span></span> <span data-ttu-id="1b86c-142">Weitere Informationen finden Sie unter https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script .</span><span class="sxs-lookup"><span data-stu-id="1b86c-142">Please see https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script for details.</span></span> <span data-ttu-id="1b86c-143">Sie können das Ausführen benutzerdefinierter Skripts zulassen, die Änderung vornehmen und dann bei Bedarf zu nicht zulässigen Skripts für die Website zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="1b86c-143">You can allow running custom scripts, make the change, and then revert to disallowing scripts for the site if necessary.</span></span>

<span data-ttu-id="1b86c-144">Führen Sie den folgenden Befehl aus, um diese Einstellung für eine bestimmte Website zu ändern:</span><span class="sxs-lookup"><span data-stu-id="1b86c-144">To change this setting for a given site run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="1b86c-145">Alternativ können Sie diesen Befehl verwenden, wenn Sie ihn für alle Websites in einer Websitesammlung festlegen möchten:</span><span class="sxs-lookup"><span data-stu-id="1b86c-145">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="1b86c-146">Wenn Sie zum Standardplatz Halter Text zurückkehren möchten, legen Sie den Wert auf leer ("") fest.</span><span class="sxs-lookup"><span data-stu-id="1b86c-146">To go back to the default placeholder text, set the value to be blank ("").</span></span>
