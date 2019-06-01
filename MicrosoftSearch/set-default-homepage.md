---
title: Festlegen der standardmäßigen Startseite
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
ROBOTS: NOINDEX
description: Erfahren Sie, wie Bing als standardmäßige Startseite für Ihr Unternehmen mit Microsoft Search festlegen.
ms.openlocfilehash: 0fc16bc7389b8cfffc2ad528b3b10c7ae1d498c3
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591179"
---
# <a name="set-default-homepage"></a><span data-ttu-id="0d682-103">Festlegen der standardmäßigen Startseite</span><span class="sxs-lookup"><span data-stu-id="0d682-103">Set default homepage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d682-104">Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal.</span><span class="sxs-lookup"><span data-stu-id="0d682-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="0d682-105">Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird es entfernt.</span><span class="sxs-lookup"><span data-stu-id="0d682-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="0d682-106">Es wird empfohlen, dass Sie zu Beginn das Microsoft 365 Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d682-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="0d682-107">[Übersicht über Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="0d682-107">Overview of Microsoft Search</span></span>

<span data-ttu-id="0d682-108">Das Konfigurieren des Standardbrowsers, der Standardsuchmaschine und der standardmäßigen Startseite hilft Ihren Benutzern, die Microsoft Search-Funktionen zu entdecken, fördert deren Verwendung und ermöglicht eine gleichmäßigere Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="0d682-108">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="0d682-109">Führen Sie zum Festlegen der standardmäßigen Startseite für Ihre Organisation die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="0d682-109">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="0d682-110">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="0d682-110">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="0d682-111">Internet Explorer 5.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="0d682-111">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="0d682-112">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.</span><span class="sxs-lookup"><span data-stu-id="0d682-112">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="0d682-113">Navigieren Sie zu **Benutzerkonfiguration\Einstellungen\Systemsteuerungseinstellungen\Internet-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="0d682-113">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="0d682-114">Klicken Sie mit der rechten Maustaste auf **Internet-Einstellungen**, und wählen Sie **Internet Explorer 10** aus.</span><span class="sxs-lookup"><span data-stu-id="0d682-114">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0d682-115">Sie müssen die Option „Internet Explorer 10“ auswählen, um die Einstellungen für Internet Explorer 11 anzuwenden, da dieselben Einstellungen für Internet Explorer 11 gelten.</span><span class="sxs-lookup"><span data-stu-id="0d682-115">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="0d682-p102">Einstellungen, die rot unterstrichen sind, werden auf dem Zielrechner nicht konfiguriert, während grün unterstrichene Einstellungen auf dem Zielrechner konfiguriert werden. Um die Unterstreichung zu ändern, verwenden Sie die folgenden Funktionstasten:</span><span class="sxs-lookup"><span data-stu-id="0d682-p102">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="0d682-118">F5 – alle Einstellungen auf der aktuellen Registerkarte aktivieren</span><span class="sxs-lookup"><span data-stu-id="0d682-118">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="0d682-119">F6 – die aktuell ausgewählte Einstellung aktivieren</span><span class="sxs-lookup"><span data-stu-id="0d682-119">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="0d682-120">F7 – die aktuell ausgewählte Einstellung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="0d682-120">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="0d682-121">F8 – alle Einstellungen auf der aktuellen Registerkarte deaktivieren</span><span class="sxs-lookup"><span data-stu-id="0d682-121">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="0d682-p103">Drücken Sie **F8**, um alle Einstellungen zu deaktivieren, bevor Sie irgendetwas konfigurieren. Der Bildschirm sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="0d682-p103">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Eigenschaftendialogfeld von Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="0d682-125">Drücken Sie für die Einstellung der Startseite **F6**, und geben Sie `https://www.bing.com/business?form=BFBSPR` ein.</span><span class="sxs-lookup"><span data-stu-id="0d682-125">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="0d682-126">Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="0d682-126">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0d682-127">Benutzer können die Startseite weiterhin ändern, nachdem diese Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0d682-127">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="0d682-128">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0d682-128">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="0d682-129">Windows 10, Version 1511 oder höher</span><span class="sxs-lookup"><span data-stu-id="0d682-129">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="0d682-130">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.</span><span class="sxs-lookup"><span data-stu-id="0d682-130">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="0d682-131">Navigieren Sie zu **Administrative Vorlagen\Windows-Komponenten\Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="0d682-131">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="0d682-132">Doppelklicken Sie auf **Startseiten konfigurieren**, legen Sie es auf **Aktiviert** fest, und geben Sie `https://www.bing.com/business` ein.</span><span class="sxs-lookup"><span data-stu-id="0d682-132">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="0d682-133">Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="0d682-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="0d682-134">Benutzer können den Suchanbieter nicht mehr ändern, nachdem diese Richtlinie festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="0d682-134">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="0d682-135">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="0d682-135">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="0d682-136">Windows XP SP2 oder höher</span><span class="sxs-lookup"><span data-stu-id="0d682-136">Windows XP SP2 or later</span></span>

<span data-ttu-id="0d682-137">Den Windows Support-Artikel zum Verwalten von ADMX-Dateien und die neuesten ADMX-Dateien für verschiedene Windows-Versionen finden Sie [auf der Microsoft-Supportwebsite](https://support.microsoft.com/de-DE/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="0d682-137">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="0d682-138">Sie benötigen auch die neueste Google-Richtliniendatei. Sie finden sie unter [Hilfe zu Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="0d682-138">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="0d682-p104">Wenn Sie die in diesem Abschnitt beschriebenen Einstellungen in der Gruppenrichtlinien-Verwaltungskonsole nicht finden, laden Sie die entsprechenden ADMX herunter, und kopieren Sie sie in den [zentralen Speicher](https://docs.microsoft.com/de-DE/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Der zentrale Speicher auf dem Controller ist ein Ordner mit der folgenden Benennungskonvention:</span><span class="sxs-lookup"><span data-stu-id="0d682-p104">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="0d682-141">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="0d682-141">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="0d682-p105">Jede Domäne, die Ihr Controller verarbeitet, sollte einen separaten Ordner erhalten. Mit dem folgenden Befehl kann die ADMX-Datei aus der Befehlszeile kopiert werden:</span><span class="sxs-lookup"><span data-stu-id="0d682-p105">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="0d682-144">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.</span><span class="sxs-lookup"><span data-stu-id="0d682-144">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="0d682-145">Stellen Sie sicher, dass die folgenden Ordner im Abschnitt **Administrative Vorlagen** der *Benutzer- und der Computerkonfiguration* angezeigt werden: Google Chrome und Google Chrome – Standardeinstellungen (Benutzer können diese überschreiben).</span><span class="sxs-lookup"><span data-stu-id="0d682-145">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="0d682-146">Die Einstellungen des ersten Abschnitts sind festgelegt, und der lokale Administrator kann sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="0d682-146">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="0d682-p106">Die Einstellungen im nachfolgenden Richtlinienabschnitt können von Benutzern in ihren Browsereinstellungen geändert werden. Entscheiden Sie, ob Benutzer Ihre Standardeinstellung außer Kraft setzen können. Ändern Sie in den folgenden Schritten die Einstellung in den Ordner, welcher der Richtlinie und den Anforderungen in Ihrer Organisation entspricht. Die folgenden Schritte verwenden „Google Chrome – Standardeinstellungen“ als Standard.</span><span class="sxs-lookup"><span data-stu-id="0d682-p106">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="0d682-151">Navigieren Sie zu **&lt;Computer/Benutzerkonfiguration&gt;\Administrative Vorlagen\Google Chrome – Standardeinstellungen\Startseite**.</span><span class="sxs-lookup"><span data-stu-id="0d682-151">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="0d682-152">Doppelklicken Sie auf **Neue Registerkartenseite als Startseite verwenden**, und legen Sie es auf **Aktiviert** fest.</span><span class="sxs-lookup"><span data-stu-id="0d682-152">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="0d682-153">Navigieren Sie zu **&lt;Computer/Benutzerkonfiguration&gt;\Administrative Vorlagen\Google Chrome – Standardeinstellungen\Neue Registerkartenseite**.</span><span class="sxs-lookup"><span data-stu-id="0d682-153">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="0d682-154">Doppelklicken Sie auf **URL der neuen Registerkartenseite konfigurieren**, legen Sie es auf **Aktiviert** fest, und geben Sie `https://www.bing.com/business?form=BFBSPR` ein.</span><span class="sxs-lookup"><span data-stu-id="0d682-154">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="0d682-155">Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="0d682-155">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="0d682-156">Benutzer können die Startseite ändern, nachdem diese Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0d682-156">Users will be able to change the home page after this policy is set.</span></span>