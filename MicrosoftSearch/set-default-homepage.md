---
title: Set-Standard-homepage
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
description: Erfahren Sie, wie Bing als Standard-Homepage für Ihr Unternehmen mit Microsoft Search festgelegt.
ms.openlocfilehash: 9190e607f5e17a0b898ab131886de12cb300a74c
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378751"
---
# <a name="set-default-homepage"></a><span data-ttu-id="b55ef-103">Set-Standard-homepage</span><span class="sxs-lookup"><span data-stu-id="b55ef-103">Set default homepage</span></span>

<span data-ttu-id="b55ef-104">Konfigurieren der Standard-Browser, Standard-Suchmaschine und Standard-Homepage helfen Ihre Benutzer entdecken Sie Microsoft Search-Funktionen, weitere Verwendung fördern und bieten einen reibungsloseren.</span><span class="sxs-lookup"><span data-stu-id="b55ef-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="b55ef-105">Wenn die Standard-Homepage für Ihre Organisation festlegen möchten, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="b55ef-105">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="b55ef-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="b55ef-106">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="b55ef-107">InternetExplorer 5.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="b55ef-107">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="b55ef-108">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Erstellen einer neuen oder bearbeiten die vorhandene Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="b55ef-108">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="b55ef-109">Navigieren Sie zu **Einstellungen für den Benutzer Configuration\Preferences\Control Dokumentinformationsbereich Einstellungen\Internet**.</span><span class="sxs-lookup"><span data-stu-id="b55ef-109">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="b55ef-110">Mit der rechten Maustaste auf **Internet-Einstellungen** , und wählen Sie **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="b55ef-110">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b55ef-111">Sie müssen die Option von Internet Explorer 10 Anwendung die Einstellungen für Internet Explorer 11, wie die gleichen Einstellungen für Internet Explorer 11 gelten.</span><span class="sxs-lookup"><span data-stu-id="b55ef-111">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="b55ef-p101">Einstellungen der rot unterstrichen werden sind nicht auf dem Zielcomputer konfiguriert, während auf dem Zielcomputer Grün unterstrichene Einstellungen konfiguriert werden. Um die Unterstreichung zu ändern, verwenden Sie die folgenden Funktionstasten:</span><span class="sxs-lookup"><span data-stu-id="b55ef-p101">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="b55ef-114">F5 - alle Einstellungen auf der aktuellen Registerkarte aktivieren</span><span class="sxs-lookup"><span data-stu-id="b55ef-114">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="b55ef-115">F6 - Aktivieren der aktuell ausgewählten Einstellung</span><span class="sxs-lookup"><span data-stu-id="b55ef-115">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="b55ef-116">F7 - der aktuell ausgewählten Einstellung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="b55ef-116">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="b55ef-117">F8 - alle Einstellungen auf der aktuellen Registerkarte deaktivieren</span><span class="sxs-lookup"><span data-stu-id="b55ef-117">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="b55ef-p102">Drücken Sie **F8** , um alle Einstellungen, die vor dem Konfigurieren von Suchzeichenfolge deaktivieren. Der Bildschirm sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b55ef-p102">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Dialogfeld Eigenschaften von Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="b55ef-121">Drücken Sie **F6,** auf der Homepage und geben Sie`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="b55ef-121">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="b55ef-122">Erzwingen Sie das resultierende GPO durch Verknüpfung mit der entsprechenden Domäne.</span><span class="sxs-lookup"><span data-stu-id="b55ef-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b55ef-123">Benutzer können weiterhin die Homepage ändern, nachdem diese Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b55ef-123">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="b55ef-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b55ef-124">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="b55ef-125">Windows-10, Version 1511 oder höher</span><span class="sxs-lookup"><span data-stu-id="b55ef-125">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="b55ef-126">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Erstellen einer neuen oder bearbeiten die vorhandene Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="b55ef-126">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="b55ef-127">Navigieren Sie zu **Administrative Vorlagen\Windows-Komponenten\Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="b55ef-127">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="b55ef-128">Doppelklicken Sie auf **Seiten starten konfigurieren**, legen Sie es auf **aktiviert**, und geben`https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="b55ef-128">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="b55ef-129">Erzwingen Sie das resultierende GPO durch Verknüpfung mit der entsprechenden Domäne.</span><span class="sxs-lookup"><span data-stu-id="b55ef-129">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="b55ef-130">Benutzer möglich nicht Suchanbieter ändern, nachdem diese Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b55ef-130">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="b55ef-131">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="b55ef-131">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="b55ef-132">Windows XP SP2 oder höher</span><span class="sxs-lookup"><span data-stu-id="b55ef-132">Windows XP SP2 or later</span></span>

<span data-ttu-id="b55ef-133">Im Windows-Artikel zur Verwaltung von ADMX-Dateien und die neuesten ADMX-Dateien für die verschiedenen Versionen von Windows finden Sie [auf der Microsoft-Supportmitarbeiter](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="b55ef-133">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="b55ef-134">Sie benötigen auch die neuesten Google Richtliniendatei, die finden Sie auf [Hilfe zu Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202)können.</span><span class="sxs-lookup"><span data-stu-id="b55ef-134">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="b55ef-p103">Wenn die Einstellungen in diesem Abschnitt beschriebenen innerhalb der Gruppenrichtlinien-Verwaltungskonsole nicht gefunden werden können, laden Sie das entsprechende ADMX, und kopieren Sie sie an den [zentralen Speicher](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Zentralen Speicher auf dem Domänencontroller ist ein Ordner mit der folgenden Benennungskonvention:</span><span class="sxs-lookup"><span data-stu-id="b55ef-p103">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="b55ef-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="b55ef-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="b55ef-p104">Jede Domäne sollte die Controller Handles einen gesonderten Ordner abrufen. Der folgende Befehl kann verwendet werden, zum Kopieren von ADMX-Datei von der Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="b55ef-p104">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="b55ef-140">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Erstellen einer neuen oder bearbeiten die vorhandene Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="b55ef-140">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="b55ef-141">Stellen Sie sicher, dass die folgenden Ordner angezeigt werden, im Abschnitt **Administrative Vorlagen** des beide *Benutzer/Computerkonfiguration*: Google Chrome und Google Chrome - Default Settings (vom Benutzer überschreibbar).</span><span class="sxs-lookup"><span data-stu-id="b55ef-141">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="b55ef-142">Die Einstellungen des ersten Abschnitts behoben werden, und der lokale Administrator wird nicht in der Lage, sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b55ef-142">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="b55ef-p105">Die Einstellungen des zweiten Abschnitts der Richtlinien können von Benutzern in ihrer Browsereinstellungen geändert werden. Sie sollten entscheiden, ob Benutzer die Standardeinstellung außer Kraft setzen können. Ändern Sie in den folgenden Schritten in den Ordner, der entspricht der Einstellung für Ihre Organisationsrichtlinie und Anforderungen. In den nachfolgenden Schritten verwenden die Google Chrome - Standardeinstellungen als Standard.</span><span class="sxs-lookup"><span data-stu-id="b55ef-p105">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="b55ef-147">Navigieren Sie zu \*\* &lt;Computer/Benutzerkonfiguration&gt;\Administrative Templates\Google Chrome - Standardseite Settings\Home\*\*.</span><span class="sxs-lookup"><span data-stu-id="b55ef-147">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="b55ef-148">Doppelklicken Sie auf **Neue Registerkartenseite als Homepage verwenden**, und legen sie auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="b55ef-148">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="b55ef-149">Navigieren Sie zu \*\* &lt;Computer/Benutzerkonfiguration&gt;\Administrative Templates\Google Chrome - Standardseite Settings\New-Registerkarte\*\*.</span><span class="sxs-lookup"><span data-stu-id="b55ef-149">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="b55ef-150">Doppelklicken Sie auf **die URL für die neue Registerkarte Konfigurieren**, legen Sie es auf **aktiviert**, und geben`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="b55ef-150">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="b55ef-151">Erzwingen Sie das resultierende GPO durch Verknüpfung mit der entsprechenden Domäne.</span><span class="sxs-lookup"><span data-stu-id="b55ef-151">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="b55ef-152">Benutzer können auf der Homepage des ändern, nachdem diese Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b55ef-152">Users will be able to change the home page after this policy is set.</span></span>