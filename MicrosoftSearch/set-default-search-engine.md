---
title: Festlegen der Standardsuchmaschine
ms.author: jeffkizn
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Erfahren Sie, wie Sie Bing als Standardsuchmaschine Ihres Unternehmens für Microsoft Search festlegen.
ms.openlocfilehash: 1ac2f23a8263c01901e252e7dd830e7373380669
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508670"
---
# <a name="make-bing-the-default-search-engine"></a><span data-ttu-id="05a20-103">Festlegen von Bing als Standardsuchmaschine</span><span class="sxs-lookup"><span data-stu-id="05a20-103">Make Bing the default search engine</span></span>
  
<span data-ttu-id="05a20-104">In diesem Artikel wird erläutert, wie Sie Bing als Standardsuchmaschine für Microsoft Edge, Google Chrome und Internet Explorer festlegen.</span><span class="sxs-lookup"><span data-stu-id="05a20-104">This article explains how you can make Bing the default search engine for Microsoft Edge, Google Chrome, and Internet Explorer.</span></span> 
  
## <a name="microsoft-edge-on-windows-10-version-1703-or-later"></a><span data-ttu-id="05a20-105">Microsoft Edge unter Windows 10, Version 1703 oder höher</span><span class="sxs-lookup"><span data-stu-id="05a20-105">Microsoft Edge on Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="05a20-106">Auch wenn Sie Bing als Standardsuchmaschine festgelegt haben, können Benutzer unter Microsoft Edge ihre Einstellungen so ändern, dass eine andere Suchmaschine verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="05a20-106">Although you'll set Bing as the default search engine, Microsoft Edge allows users to change their settings to use a different search engine.</span></span>
  
<span data-ttu-id="05a20-107">Die neuesten ADMX-Dateien für verschiedene Windows-Versionen finden Sie unter [Erstellen und Verwalten des zentralen Speichers für administrative Vorlagen für Gruppenrichtlinien unter Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="05a20-107">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="05a20-108">Wenn die in diesem Abschnitt beschriebene Einstellung nicht in der GPMC gefunden werden kann, laden Sie die entsprechende ADMX herunter, und kopieren Sie sie in den zentralen Speicher.</span><span class="sxs-lookup"><span data-stu-id="05a20-108">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store.</span></span> <span data-ttu-id="05a20-109">Weitere Informationen finden Sie unter [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span><span class="sxs-lookup"><span data-stu-id="05a20-109">For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span></span> <span data-ttu-id="05a20-110">Der zentrale Speicher auf dem Controller ist ein Ordner mit der folgenden **Benennungskonvention: %systemroot%\sysvol \\<Domäne \> \policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="05a20-110">Central store on the controller is a folder with the following naming convention: **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="05a20-p102">Jede Domäne, die Ihr Controller verarbeitet, sollte einen separaten Ordner erhalten. Mit dem folgenden Befehl kann die ADMX-Datei aus der Befehlszeile kopiert werden:</span><span class="sxs-lookup"><span data-stu-id="05a20-p102">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="05a20-113">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.</span><span class="sxs-lookup"><span data-stu-id="05a20-113">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
2. <span data-ttu-id="05a20-114">Navigieren Sie zu **&lt;Computer/Benutzerkonfiguration&gt;\Administrationsvorlagen\Windows-Komponenten\Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="05a20-114">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
3. <span data-ttu-id="05a20-115">Doppelklicken Sie auf **Festlegen der Standardsuchmaschine**, wählen Sie **Aktiviert** aus, und geben Sie `https://www.bing.com/sa/osd/bfb.xml` ein.</span><span class="sxs-lookup"><span data-stu-id="05a20-115">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
4. <span data-ttu-id="05a20-116">Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="05a20-116">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>


## <a name="google-chrome-on-windows-10-version-1507-or-later"></a><span data-ttu-id="05a20-117">Google Chrome unter Windows 10, Version 1507 oder höher</span><span class="sxs-lookup"><span data-stu-id="05a20-117">Google Chrome on Windows 10, Version 1507 or later</span></span>

<span data-ttu-id="05a20-118">Benutzer können die Standardsuchmaschine nicht mehr ändern, nachdem diese Richtlinie festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="05a20-118">Users won't be able to change the default search engine after this policy is set.</span></span>
  
<span data-ttu-id="05a20-119">Chrome verfügt über einen eigenen Satz von Gruppenrichtlinieneinstellungen, die in Form einer ADMX-Datei aus der [Google Chrome Enterprise-Hilfe heruntergeladen werden können.](https://support.google.com/chrome/a/answer/187202)</span><span class="sxs-lookup"><span data-stu-id="05a20-119">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="05a20-120">Kopieren Sie die Vorlagendatei in einen zentralen Speicher für ADMX-Dateien auf dem Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="05a20-120">Copy the template file to a central store for ADMX files on the domain controller.</span></span> <span data-ttu-id="05a20-121">Weitere Informationen finden Sie unter [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span><span class="sxs-lookup"><span data-stu-id="05a20-121">For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span></span> <span data-ttu-id="05a20-122">Der zentrale Speicher auf dem Controller ist ein Ordner mit der folgenden **Benennungskonvention: %systemroot%\sysvol \\<Domäne \> \policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="05a20-122">Central store on the controller is a folder with the following naming convention: **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="05a20-p104">Jede Domäne, die Ihr Controller verarbeitet, sollte einen separaten Ordner erhalten. Mit dem folgenden Befehl kann die ADMX-Datei aus der Befehlszeile kopiert werden:</span><span class="sxs-lookup"><span data-stu-id="05a20-p104">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="05a20-125">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.</span><span class="sxs-lookup"><span data-stu-id="05a20-125">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
2. <span data-ttu-id="05a20-126">Stellen Sie sicher, dass die folgenden Ordner im Abschnitt Administrationsvorlagen der Benutzer- und Computerkonfiguration angezeigt werden: Google Chrome und Google Chrome - Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="05a20-126">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>

    - <span data-ttu-id="05a20-127">Die Einstellungen des ersten Abschnitts wurden festgelegt, und lokale Administratoren können sie nicht im Browser ändern.</span><span class="sxs-lookup"><span data-stu-id="05a20-127">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    - <span data-ttu-id="05a20-128">Die Einstellungen im nachfolgenden Abschnitt der Richtlinien können von Benutzern in den Browsereinstellungen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="05a20-128">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>

3. <span data-ttu-id="05a20-129">Navigieren Sie **\<Computer/User\> zu Configuration\Administrative Templates\Google Chrome\Default search provider**</span><span class="sxs-lookup"><span data-stu-id="05a20-129">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
4. <span data-ttu-id="05a20-130">Doppelklicken Sie auf **Aktivieren des Standardsuchanbieters**, und wählen Sie **Aktiviert** aus.</span><span class="sxs-lookup"><span data-stu-id="05a20-130">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
5. <span data-ttu-id="05a20-131">Doppelklicken Sie auf das **Standardsuchanbieter-Symbol**, wählen Sie **Aktiviert** aus, und geben Sie `https://www.bing.com/sa/simg/bb.ico` ein.</span><span class="sxs-lookup"><span data-stu-id="05a20-131">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
6. <span data-ttu-id="05a20-132">Doppelklicken Sie auf die **Standardsuchanbieter-Instant-URL**, und geben Sie `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR` ein.</span><span class="sxs-lookup"><span data-stu-id="05a20-132">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
7. <span data-ttu-id="05a20-133">Doppelklicken Sie auf den **Standardsuchanbieter-Namen**, wählen Sie Aktiviert aus, und geben Sie „Microsoft Search in Bing“ ein.</span><span class="sxs-lookup"><span data-stu-id="05a20-133">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
8. <span data-ttu-id="05a20-134">Doppelklicken Sie auf die **Standardsuchanbieter-Such-URL**, wählen Sie **Aktiviert** aus, und geben Sie `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR` ein.</span><span class="sxs-lookup"><span data-stu-id="05a20-134">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
9. <span data-ttu-id="05a20-135">Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="05a20-135">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

## <a name="internet-explorer-11-or-later"></a><span data-ttu-id="05a20-136">Internet Explorer 11 oder höher</span><span class="sxs-lookup"><span data-stu-id="05a20-136">Internet Explorer 11 or later</span></span>

<span data-ttu-id="05a20-137">Benutzer können den Suchanbieter ändern, nachdem diese Richtlinie festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="05a20-137">Users will be able to change the search provider after this policy is set.</span></span>
  
### <a name="step-1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="05a20-138">SCHRITT 1:</span><span class="sxs-lookup"><span data-stu-id="05a20-138">STEP 1.</span></span> <span data-ttu-id="05a20-139">Konfigurieren Sie den lokalen Computer, der verwendet wird, um das Gruppenrichtlinienobjekt festzulegen.</span><span class="sxs-lookup"><span data-stu-id="05a20-139">Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="05a20-140">Fügen Sie den folgenden Text in eine REG-Datei (\*.reg) ein.</span><span class="sxs-lookup"><span data-stu-id="05a20-140">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="05a20-141">Windows-Registrierungs-Editor, Version 5.00</span><span class="sxs-lookup"><span data-stu-id="05a20-141">Windows Registry Editor Version 5.00</span></span>
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
<span data-ttu-id="05a20-p106">Doppelklicken Sie auf die erstellte Datei, und befolgen Sie die Schritte zum Importieren der Datei. Nach einem erfolgreichen Import wird der folgende Dialog angezeigt:</span><span class="sxs-lookup"><span data-stu-id="05a20-p106">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![Nachricht: Registrierungs-Editor erfolgreich importiert](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
### <a name="step-2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="05a20-145">SCHRITT 2:</span><span class="sxs-lookup"><span data-stu-id="05a20-145">STEP 2.</span></span> <span data-ttu-id="05a20-146">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.</span><span class="sxs-lookup"><span data-stu-id="05a20-146">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="05a20-147">Navigieren Sie zu **Benutzerkonfiguration\Richtlinien\Einstellungen\Windows-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="05a20-147">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
2. <span data-ttu-id="05a20-p108">Klicken Sie mit der rechten Maustaste auf **Registrierung\Neu** und **Registrierungsassistent**. Wählen Sie im Fenster "Registrierungsbrowser" **Lokaler Computer**, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="05a20-p108">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
3. <span data-ttu-id="05a20-150">Navigieren Sie zu **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span><span class="sxs-lookup"><span data-stu-id="05a20-150">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
4. <span data-ttu-id="05a20-151">Wählen Sie aus diesem Schlüssel DefaultScope aus.</span><span class="sxs-lookup"><span data-stu-id="05a20-151">From this key, make sure to select DefaultScope.</span></span>

    ![Im Registrierungsbrowser wurde DefaultScope ausgewählt](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
5. <span data-ttu-id="05a20-p109">Überprüfen Sie alle untergeordneten Schlüssel, die die GUID für Microsoft Search in Bing enthalten, und jeden Wert unter dem Schlüssel mit Ausnahme von Pfaden zu Benutzerprofilen. Scrollen Sie nach unten, um weitere Elemente auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="05a20-p109">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
6. <span data-ttu-id="05a20-155">Klicken Sie auf Fertig stellen, um die Konfiguration abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="05a20-155">Click Finish to complete this configuration.</span></span>

### <a name="step-3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="05a20-156">SCHRITT 3:</span><span class="sxs-lookup"><span data-stu-id="05a20-156">STEP 3.</span></span> <span data-ttu-id="05a20-157">Richten Sie Benutzereinstellungen ein, um eine Warnung zu vermeiden, die der Benutzer möglicherweise erhält, wenn die DefaultScope-Suche erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="05a20-157">Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="05a20-158">Diese Warnung warnt Benutzer eines Programmes davor, ihre Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="05a20-158">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="05a20-159">Klicken Sie im gleichen Gruppenrichtlinienobjekt mit der rechten Maustaste auf **Registrierung\Neu**, und wählen Sie **Registrierungsassistent** aus.</span><span class="sxs-lookup"><span data-stu-id="05a20-159">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
2. <span data-ttu-id="05a20-160">Navigieren Sie zu **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span><span class="sxs-lookup"><span data-stu-id="05a20-160">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
3. <span data-ttu-id="05a20-161">Wählen Sie den Schlüssel **Benutzereinstellung**.</span><span class="sxs-lookup"><span data-stu-id="05a20-161">Select the **User Preference** key.</span></span>
4. <span data-ttu-id="05a20-162">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="05a20-162">Click **Finish**.</span></span>
5. <span data-ttu-id="05a20-p111">Klicken Sie auf das neu erstellte Objekt. Doppelklicken Sie im Bereich rechts auf das Benutzereinstellungen-Objekt, und ändern Sie die **Aktion** in **Löschen und Speichern**.</span><span class="sxs-lookup"><span data-stu-id="05a20-p111">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
6. <span data-ttu-id="05a20-165">Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="05a20-165">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
