---
title: Festlegen der Standardsuchmaschine
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Erfahren Sie, wie Bing als Ihres Unternehmens Standard-Suchmaschine mithilfe von Microsoft Search festgelegt.
ms.openlocfilehash: a0798da94f4433bb754c71b9e0d00e09ba5a543b
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612529"
---
# <a name="set-default-search-engine"></a><span data-ttu-id="5db97-103">Festlegen der Standardsuchmaschine</span><span class="sxs-lookup"><span data-stu-id="5db97-103">Set default search engine</span></span>

<span data-ttu-id="5db97-104">Konfigurieren der Standard-Browser, Standard-Suchmaschine und Standard-Homepage helfen Ihre Benutzer entdecken Sie Microsoft Search-Funktionen, weitere Verwendung fördern und bieten einen reibungsloseren.</span><span class="sxs-lookup"><span data-stu-id="5db97-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="5db97-105">Wenn die Standard-Suchmaschine für Ihre Organisation festlegen möchten, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="5db97-105">To set the default search engine for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="5db97-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="5db97-106">Internet Explorer</span></span>

### <a name="internet-explorer-11"></a><span data-ttu-id="5db97-107">Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="5db97-107">Internet Explorer 11</span></span>

<span data-ttu-id="5db97-108">Benutzer können Suchanbieter ändern, nachdem diese Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5db97-108">Users will be able to change the search provider after this policy is set.</span></span>
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="5db97-109">1 Konfigurieren Sie 1 den lokalen Computer, der zum Festlegen des Gruppenrichtlinienobjekts verwendet werden</span><span class="sxs-lookup"><span data-stu-id="5db97-109">1. Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="5db97-110">Fügen Sie den folgenden Text in einer Reg (\*reg) Datei.</span><span class="sxs-lookup"><span data-stu-id="5db97-110">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="5db97-111">Windows-Registrierungs-Editor, Version 5.00</span><span class="sxs-lookup"><span data-stu-id="5db97-111">Windows Registry Editor Version 5.00</span></span>
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"SuggestionsURL_JSON"="https://business.ing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA"
"ShowSearchSuggestions"=dword:00000001
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
<span data-ttu-id="5db97-p101">Doppelklicken Sie auf die Datei erstellt, und führen Sie die Schritte zum Importieren der Datei. Das folgende Dialogfeld sollte ein erfolgreicher Import führen:</span><span class="sxs-lookup"><span data-stu-id="5db97-p101">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![Registrierungs-Editor erfolgreichen Import Nachricht](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="5db97-115">2. Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Erstellen einer neuen oder Bearbeiten einer vorhandenen Richtlinie</span><span class="sxs-lookup"><span data-stu-id="5db97-115">2. Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="5db97-116">Navigieren Sie zu **Configuration\Policies\Preferences\Windows Benutzereinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="5db97-116">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="5db97-p102">Mit der rechten Maustaste auf **Registry\New** , und wählen Sie **Registry Wizard**. Wählen Sie aus der Registrierung Browserfenster **Lokaler Computer** , und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5db97-p102">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
3. <span data-ttu-id="5db97-119">Navigieren Sie zu **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span><span class="sxs-lookup"><span data-stu-id="5db97-119">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
    
4. <span data-ttu-id="5db97-120">Dieser Schlüssel ist Vergewissern Sie sich, um DefaultScope auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="5db97-120">From this key, make sure to select DefaultScope.</span></span>
    
    ![Registrierung Browser mit DefaultScope ausgewählt](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. <span data-ttu-id="5db97-p103">Überprüfen Sie alle Sub-Schlüssel, die mit der GUID für Microsoft Search in Bing und jeder Wert unter dem Schlüssel mit Ausnahme der Pfad zum von Benutzerprofilen. Führen Sie einen Bildlauf nach unten, andere Elemente auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="5db97-p103">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
    
    ![Registrierung Browser mit zusätzlichen Werte ausgewählt](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. <span data-ttu-id="5db97-125">Klicken Sie auf Fertig stellen, um diese Konfiguration abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5db97-125">Click Finish to complete this configuration.</span></span>
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="5db97-126">3. Einrichten von Voreinstellungen des Benutzers zu eine Warnung zu löschen, die der Benutzer angezeigt wird, wenn DefaultScope Suche erzwungen wird</span><span class="sxs-lookup"><span data-stu-id="5db97-126">3. Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="5db97-127">Diese Warnung ist entwurfsbedingt und Sie warnt Benutzer, der ein Programm versucht, können Sie ihre Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="5db97-127">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="5db97-128">Innerhalb der gleichen Gruppenrichtlinienobjekt klicken Sie mit der rechten Maustaste auf **Registry\New** , und wählen Sie **Registry Wizard**.</span><span class="sxs-lookup"><span data-stu-id="5db97-128">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
    
2. <span data-ttu-id="5db97-129">Navigieren Sie zu **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Voreinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="5db97-129">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
    
3. <span data-ttu-id="5db97-130">Wählen Sie den Schlüssel **Benutzervoreinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="5db97-130">Select the **User Preference** key.</span></span>
    
4. <span data-ttu-id="5db97-131">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="5db97-131">Click **Finish**.</span></span>
    
5. <span data-ttu-id="5db97-p104">Klicken Sie auf das neu erstellte Objekt. Klicken Sie im rechten Bereich einen Doppelklick auf das Objekt Benutzervoreinstellungen, ändern Sie die **Aktion** **Löschen**und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5db97-p104">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
    
<span data-ttu-id="5db97-134">Erzwingen Sie das resultierende GPO durch Verknüpfung mit der entsprechenden Domäne.</span><span class="sxs-lookup"><span data-stu-id="5db97-134">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
  
## <a name="microsoft-edge"></a><span data-ttu-id="5db97-135">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5db97-135">Microsoft Edge</span></span>

### <a name="windows-10-version-1703-or-later"></a><span data-ttu-id="5db97-136">Windows-10, Version 1703 oder höher</span><span class="sxs-lookup"><span data-stu-id="5db97-136">Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="5db97-137">Benutzer können Suchanbieter ändern, nachdem diese Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5db97-137">Users will be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="5db97-138">Die neuesten ADMX-Dateien für die verschiedenen Versionen von Windows finden Sie unter [Erstellen und verwalten den zentralen Speicher für Administrative Vorlagendateien für Gruppenrichtlinien in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="5db97-138">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="5db97-p105">Wenn die Einstellung in diesem Abschnitt beschriebenen innerhalb der Gruppenrichtlinien-Verwaltungskonsole nicht gefunden werden kann, laden Sie das entsprechende ADMX, und kopieren Sie sie in der zentralen Speicher. Weitere Informationen finden Sie unter [Bearbeiten domänenbasierter Gruppenrichtlinienobjekte mithilfe von ADMX-Dateien](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Zentralen Speicher auf dem Domänencontroller ist ein Ordner mit der folgenden Benennungskonvention:</span><span class="sxs-lookup"><span data-stu-id="5db97-p105">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="5db97-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="5db97-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="5db97-p106">Jede Domäne, die Ihren Controller behandelt sollte einen gesonderten Ordner abrufen. Der folgende Befehl kann verwendet werden, zum Kopieren von ADMX-Datei von der Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="5db97-p106">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="5db97-145">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Erstellen einer neuen oder Bearbeiten einer vorhandenen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="5db97-145">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="5db97-146">Navigieren Sie zu \*\* &lt;Computer/Benutzerkonfiguration&gt;\Administrative Templates\Windows Komponenten\Microsoft Edge\*\*.</span><span class="sxs-lookup"><span data-stu-id="5db97-146">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
    
1. <span data-ttu-id="5db97-147">Doppelklicken Sie auf **Standard-Suchmaschine festlegen**, legen Sie auf **aktiviert**, und geben Sie`https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="5db97-147">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
    
3. <span data-ttu-id="5db97-148">Erzwingen Sie das resultierende GPO durch Verknüpfung mit der entsprechenden Domäne.</span><span class="sxs-lookup"><span data-stu-id="5db97-148">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
## <a name="google-chrome"></a><span data-ttu-id="5db97-149">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="5db97-149">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="5db97-150">Windows XP SP2 oder höher</span><span class="sxs-lookup"><span data-stu-id="5db97-150">Windows XP SP2 or later</span></span>

<span data-ttu-id="5db97-151">Benutzer möglich nicht Suchanbieter ändern, nachdem diese Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5db97-151">Users won't be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="5db97-p107">Chrome verfügt über einen eigenen Satz von gruppenrichtlinieneinstellungen, die in Form einer ADMX-Datei aus der [Hilfe zu Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202)heruntergeladen werden kann. Wenn das Betriebssystem Windows Vista/Server 2008 oder höher dienen zum Verwalten des GPO für die Domäne, die in diesem Paket bereitgestellte ADMX-Datei kümmert Chrome-Einstellungen unter Windows XP SP2 oder höher.</span><span class="sxs-lookup"><span data-stu-id="5db97-p107">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). If operating systems Windows Vista/Server 2008 or later are used to manage GPO's for the domain, the ADMX file provided in this package takes care of Chrome settings on Windows XP SP2 or later.</span></span>
  
<span data-ttu-id="5db97-p108">Kopieren Sie die Vorlagendatei in einem zentralen Speicher für ADMX-Dateien auf dem Domänencontroller. Weitere Informationen finden Sie unter [Bearbeiten domänenbasierter Gruppenrichtlinienobjekte mithilfe von ADMX-Dateien](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Zentralen Speicher auf dem Domänencontroller ist ein Ordner mit der folgenden Benennungskonvention:</span><span class="sxs-lookup"><span data-stu-id="5db97-p108">Copy the template file to a central store for ADMX files on the domain controller. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="5db97-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="5db97-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="5db97-p109">Jede Domäne, die Ihren Controller behandelt sollte einen gesonderten Ordner abrufen. Der folgende Befehl kann verwendet werden, zum Kopieren von ADMX-Datei von der Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="5db97-p109">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="5db97-160">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Erstellen einer neuen oder bearbeiten die vorhandene Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="5db97-160">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="5db97-161">Stellen Sie sicher, dass die folgenden Ordner werden in den beide Benutzer/Computerkonfiguration im Bereich Administrative Vorlagen: Google Chrome und Google Chrome - Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="5db97-161">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>
    
  - <span data-ttu-id="5db97-162">Die Einstellungen des ersten Abschnitts behoben werden, und lokale Administratoren nicht möglich, um sie im Browser zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5db97-162">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    
  - <span data-ttu-id="5db97-163">Die Einstellungen des zweiten Abschnitts der Richtlinien können von Benutzern in den Browsereinstellungen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5db97-163">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>
    
3. <span data-ttu-id="5db97-164">Navigieren Sie zu \*\* \<Computerbenutzers/\> Benutzerkonfiguration\Administrative Templates\Google Chrome\Default Suchanbieter\*\*</span><span class="sxs-lookup"><span data-stu-id="5db97-164">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
    
4. <span data-ttu-id="5db97-165">Doppelklicken Sie auf **den Standardanbieter für die Suche zu aktivieren**, und legen sie auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="5db97-165">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="5db97-166">Doppelklicken Sie auf **Standard-Anbieter Suchsymbol**, legen Sie es auf **aktiviert**, und geben`https://www.bing.com/sa/simg/bb.ico`</span><span class="sxs-lookup"><span data-stu-id="5db97-166">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
    
6. <span data-ttu-id="5db97-167">Doppelklicken Sie auf **Standard instant Suche Provider-URL**, und geben Sie`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="5db97-167">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
7. <span data-ttu-id="5db97-168">Doppelklicken Sie auf **Standard-Anbieter Suchbegriff**, legen Sie es auf aktiviert, und geben Sie 'Microsoft Search in Bing'</span><span class="sxs-lookup"><span data-stu-id="5db97-168">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
    
8. <span data-ttu-id="5db97-169">Doppelklicken Sie auf **Standard-URL für die Suche Anbieter suchen**, legen Sie es auf **aktiviert**, und geben`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="5db97-169">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
9. <span data-ttu-id="5db97-170">Doppelklicken Sie auf **Standard-Suchanbieter vorschlagen URL**, legen Sie es auf **aktiviert**, und geben`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span><span class="sxs-lookup"><span data-stu-id="5db97-170">Double-click **Default search provider suggest URL**, set it to **Enabled**, and enter `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span></span>
    
10. <span data-ttu-id="5db97-171">Erzwingen Sie das resultierende GPO durch Verknüpfung mit der entsprechenden Domäne.</span><span class="sxs-lookup"><span data-stu-id="5db97-171">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="5db97-p110">Standard-Suchmaschine festlegen, wird die Suchfunktion Vorschläge Microsoft Search in der Adressleiste des Browsers hinzufügen. Dies unterstützt derzeit nur Lesezeichen. Die oberen zwei Textmarke Vorschläge oberhalb der öffentlichen Website Vorschläge wird angezeigt, während sie in der Adressleiste eingeben.</span><span class="sxs-lookup"><span data-stu-id="5db97-p110">Setting the default search engine will add the Microsoft Search search suggestions feature in the browser address bar. Currently, this supports bookmarks only. Users will see the top two bookmark suggestions above public web suggestions as they type in the address bar.</span></span>