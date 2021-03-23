---
title: Verwalten des Suchfelds auf SharePoint-Websites
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
description: Anpassen der Suchfelderfahrung auf SharePoint-Websites
ms.openlocfilehash: c58e7cf0a47d22fa9c6fd3abd93cc97087625690
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031359"
---
# <a name="search-box-settings-on-sharepoint-sites"></a><span data-ttu-id="8e5ee-103">Suchfeldeinstellungen auf SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="8e5ee-103">Search box settings on SharePoint sites</span></span>

<span data-ttu-id="8e5ee-104">Eine der verschiedenen Möglichkeiten, mit der Microsoft Search auf SharePoint-Websites angepasst werden kann, besteht in der Anpassung der Funktionsweise des Suchfelds in der Suitennavigationsleiste auf SharePoint-Websites an Ihre Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-104">One of the several ways Microsoft Search can be customized on SharePoint sites is to tailor how the search box in the suite navigation bar works in SharePoint sites to best fit your needs.</span></span>

<span data-ttu-id="8e5ee-105">Weitere Anpassungsoptionen finden Sie unter Ändern der Microsoft Search-Ergebnisseite, um benutzerdefinierte [Vertikalen,](customize-search-page.md)Ergebnistypen und Layouts hinzuzufügen, und Erstellen einer benutzerdefinierten [Suchergebnissetseite](create-search-results-pages.md).</span><span class="sxs-lookup"><span data-stu-id="8e5ee-105">For other customization options, see [Changing the Microsoft Search results page to add custom verticals, result types and layouts](customize-search-page.md), and [Creating a custom search results page](create-search-results-pages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8e5ee-106">Das Suchfeld suitenavigationsleiste ist derzeit nicht für alle Kunden verfügbar, aber diese Optionen können jetzt noch festgelegt werden und werden wirksam, wenn es verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-106">The suite navigation bar search box is not available for all customers at this time, but these options can still be set now and they will take effect when it becomes available.</span></span>

<span data-ttu-id="8e5ee-107">Für die unten aufgeführten Aufgaben verwenden Sie PowerShell mit SharePoint PnP PowerShell-Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-107">For the tasks listed below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="8e5ee-108">Sie können hier installieren und mehr über die ersten Schritte [erfahren.](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="8e5ee-108">You can install and learn more about how to get started [here](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="8e5ee-109">Mit diesem Befehl melden Sie sich bei Ihrer Website oder Websitesammlung an:</span><span class="sxs-lookup"><span data-stu-id="8e5ee-109">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a><span data-ttu-id="8e5ee-110">Ändern des Suchbereichs</span><span class="sxs-lookup"><span data-stu-id="8e5ee-110">Changing the scope of search</span></span>

<span data-ttu-id="8e5ee-111">Wenn Sie heute eine neue Website in SharePoint Online erstellen und in das Suchfeld eingeben, werden Sie zur Microsoft Search-Ergebnisseite weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-111">When you create a new site in SharePoint Online today, and type into the search box, you are taken to the Microsoft Search results page.</span></span> <span data-ttu-id="8e5ee-112">Diese Seite zeigt standardmäßig Ergebnisse ihrer aktuellen Website und ermöglicht Es Ihnen, den Suchbereich auf den Hub zu erweitern, dem die aktuelle Website zugeordnet ist (sofern vorhanden), oder auf die gesamte Organisation.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-112">This page shows results from your current site by default and allows you to expand the scope of your search to the hub that the current site is associated with (if there is one), or to the whole organization.</span></span>

<span data-ttu-id="8e5ee-113">Der vom Suchfeld verwendete Bereich hängt standardmäßig vom Typ der Website ab.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-113">The scope the search box uses, by default, depends on type of site.</span></span>

* <span data-ttu-id="8e5ee-114">Reguläre Websites suchen über die aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-114">Regular sites search over the current site.</span></span>
* <span data-ttu-id="8e5ee-115">Hubwebsites suchen über alle Websites im Hub.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-115">Hub sites search over all sites in the hub.</span></span>
* <span data-ttu-id="8e5ee-116">Startseiten suchen über alle Inhalte.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-116">Home sites search over all content.</span></span>

<span data-ttu-id="8e5ee-117">In einigen Fällen können Sie diese Standardeinstellungen so ändern, dass sie immer über die gesamte Organisation oder über den Hub, dem eine Website zugeordnet ist, durchsucht werden, ohne dass sie einen zusätzlichen Klick benötigen.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-117">In some cases, you may want to change these defaults to always search over the whole organization, or across the hub a site is associated with, without needing an additional click.</span></span>

<span data-ttu-id="8e5ee-118">Als Websitebesitzer können Sie diese Standardwerte mithilfe des folgenden Befehls ändern:</span><span class="sxs-lookup"><span data-stu-id="8e5ee-118">As a site owner, you can change these defaults using the following command:</span></span>

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

<span data-ttu-id="8e5ee-119">Nachdem Sie diesen Befehl ausgeführt haben, werden auf der Website, auf der zuvor standardmäßig Ergebnisse der aktuellen Website angezeigt wurden, Ergebnisse aus der gesamten Organisation angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-119">After running this command, the site that was previously showing results from the current site by default will start to show results from the whole organization.</span></span>

<span data-ttu-id="8e5ee-120">Um zur Standardeinstellung zurück zu wechseln, führen Sie den Befehl erneut mit dem Wert "DefaultScope" aus.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-120">To go back to the default setting, run the command again with the value “DefaultScope".</span></span> <span data-ttu-id="8e5ee-121">Verwenden Sie zum Durchsuchen des Hubs "Hub" als SearchScope-Wert.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-121">To search across the Hub, use “Hub” as the SearchScope value.</span></span>

<span data-ttu-id="8e5ee-122">Diese Einstellung gilt für die einzelnen Websiteebenen.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-122">This setting applies at the individual site level.</span></span> <span data-ttu-id="8e5ee-123">Es gibt keine entsprechende Einstellung für Websitesammlungen.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-123">There is no equivalent setting for site collections.</span></span>

## <a name="show-or-hide-the-search-box"></a><span data-ttu-id="8e5ee-124">Ein- oder Ausblenden des Suchfelds</span><span class="sxs-lookup"><span data-stu-id="8e5ee-124">Show or hide the search box</span></span>

<span data-ttu-id="8e5ee-125">Sie können das Suchfeld der Suitenavigationsleiste ausblenden, wenn Sie verhindern möchten, dass Benutzer suchen oder eine benutzerdefinierte Suchfeldimplementierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-125">You can choose to hide the suite navigation bar search box if you want to prevent your users from searching or to use a custom search box implementation.</span></span>

<span data-ttu-id="8e5ee-126">Verwenden Sie diesen Befehl, um diese Einstellung für eine bestimmte Website zu ändern:</span><span class="sxs-lookup"><span data-stu-id="8e5ee-126">To change this setting for a given site use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="8e5ee-127">Wenn Sie es für alle Websites in einer Websitesammlung festlegen möchten, können Sie den folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="8e5ee-127">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="8e5ee-128">Nach dem Ausführen dieser Befehle wird das Suchfeld nicht mehr in der Navigationsleiste oben auf der Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-128">After running these commands, the search box will no longer show up in the navigation bar on top of your page.</span></span> <span data-ttu-id="8e5ee-129">Um zum Anzeigen des Suchfelds zurück zu wechseln, führen Sie die Befehle erneut mit dem Wert aus, der für den Parameter "SearchBoxInNavBar" in "Inherit" angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-129">To go back to showing the search box, run the commands again with the value provided to "SearchBoxInNavBar" parameter to “Inherit”.</span></span>

<span data-ttu-id="8e5ee-130">Es gibt mehrere Punkte, die Sie berücksichtigen sollten:</span><span class="sxs-lookup"><span data-stu-id="8e5ee-130">There are several points to consider:</span></span>

* <span data-ttu-id="8e5ee-131">Diese Einstellung gilt nur für das Suchfeld in der Suitenavigationsleiste.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-131">This setting only applies to the search box in the suite navigation bar.</span></span> <span data-ttu-id="8e5ee-132">Sie gilt nicht für Suchfelder, die sich auf der Seite befinden, oder für Suchfelder auf klassischen Seiten.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-132">It does not apply to search boxes that are in the page, or to search boxes on classic pages.</span></span>

* <span data-ttu-id="8e5ee-133">Nachdem Sie das Suchfeld in der Navigationsleiste deaktiviert haben, müssen Sie es selbst mithilfe eines benutzerdefinierten Web teils oder einer SharePoint-Framework-Erweiterung bereitstellen, wenn Sie Suchfunktionen in Ihrer Website benötigen.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-133">Once you’ve disabled the search box in the navigation bar, if you want search functionality in your site, you will have to provide it yourself using a custom web part or a SharePoint Framework extension.</span></span>

* <span data-ttu-id="8e5ee-134">Mit dieser Lösung wird das Suchfeld auch aus Listen und Bibliotheken für Ihre Website entfernt.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-134">This solution will remove the search box from lists and libraries for your site as well.</span></span> <span data-ttu-id="8e5ee-135">Ihre benutzerdefinierte Suchlösung muss neben der websiteweiten Suche auch kontextbezogene Suchen nach SharePoint-Listen und -Bibliotheken berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-135">Your custom search solution will need to consider contextual searches for SharePoint lists and libraries, in addition to site-wide search.</span></span>

* <span data-ttu-id="8e5ee-136">Wenn Sie die Einstellung auf die Stammwebsite Ihrer Domäne anwenden, wird auf der SharePoint-Startseite auch das Suchfeld nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-136">If you apply the setting to the root site of your domain, the SharePoint start page will also stop showing the search box.</span></span>

## <a name="changing-the-hint-displayed-in-the-search-box"></a><span data-ttu-id="8e5ee-137">Ändern des im Suchfeld angezeigten Hinweises</span><span class="sxs-lookup"><span data-stu-id="8e5ee-137">Changing the hint displayed in the search box</span></span>

<span data-ttu-id="8e5ee-138">Sie können den Hinweis ändern, der im Suchfeld für eine bestimmte Website oder Websitesammlung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-138">You can change the hint the search box shows for a given site or site collection.</span></span> <span data-ttu-id="8e5ee-139">Dies ist der Text, der im Suchfeld angezeigt wird, bevor sie mit der Eingabe beginnen.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-139">This is the text that appears in the search box before they start typing into it.</span></span> <span data-ttu-id="8e5ee-140">Dies kann Ihren Benutzern helfen, zu verstehen, was sie von der Suche erwarten können, wenn Sie eine benutzerdefinierte Ergebnisseite konfiguriert oder das Suchverhalten auf andere Weise geändert haben.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-140">This may help guide your users about what to expect from search if you’ve configured a custom results page or changed behavior of search in other ways.</span></span>

> [!NOTE]
> <span data-ttu-id="8e5ee-141">Um diese Änderung ausführen zu können, müssen Sie die Ausführung von benutzerdefinierten Skripts auf der in Frage 2013 in Frage gestellten Website als Mandantenadministrator zulassen, was standardmäßig nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-141">To be able to make this change, you need to allow running custom scripts on the site in question as a tenant administrator, which is disallowed by default.</span></span> <span data-ttu-id="8e5ee-142">Weitere Informationen https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-142">Please see https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script for details.</span></span> <span data-ttu-id="8e5ee-143">Sie können das Ausführen von benutzerdefinierten Skripts zulassen, die Änderung ausführen und dann bei Bedarf auf nicht zulässige Skripts für die Website zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-143">You can allow running custom scripts, make the change, and then revert to disallowing scripts for the site if necessary.</span></span>

<span data-ttu-id="8e5ee-144">Führen Sie den folgenden Befehl aus, um diese Einstellung für eine bestimmte Website zu ändern:</span><span class="sxs-lookup"><span data-stu-id="8e5ee-144">To change this setting for a given site run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="8e5ee-145">Wenn Sie es für alle Websites in einer Websitesammlung festlegen möchten, können Sie den folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="8e5ee-145">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="8e5ee-146">Um zum Standardplatzhaltertext zurück zu wechseln, legen Sie den Wert auf leer ("") festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8e5ee-146">To go back to the default placeholder text, set the value to be blank ("").</span></span>