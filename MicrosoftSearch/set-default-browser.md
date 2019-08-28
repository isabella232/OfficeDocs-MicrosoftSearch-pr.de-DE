---
title: Festlegen des Standardbrowsers
ms.author: anfowler
author: adefowler
manager: shohara
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
ROBOTS: NOINDEX
description: Legen Sie Microsoft Edge oder Internet Explorer als Standardbrowser für Microsoft Search-Benutzer fest.
ms.openlocfilehash: ed145a1811aba0b58158ed04dd3bf8dc089a0682
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639739"
---
# <a name="make-microsoft-edge-the-default-browser"></a><span data-ttu-id="f53e4-103">Festlegen von Microsoft Edge als Standardbrowser</span><span class="sxs-lookup"><span data-stu-id="f53e4-103">Make Microsoft Edge the default browser</span></span>
  
<span data-ttu-id="f53e4-104">Um Ihren Benutzern die optimale Erfahrung mit Microsoft Search zu bieten, können Sie Microsoft Edge als Standardbrowser festlegen.</span><span class="sxs-lookup"><span data-stu-id="f53e4-104">To give your users the best experience with Microsoft Search, you can make Microsoft Edge the default browser.</span></span> <span data-ttu-id="f53e4-105">Damit wird Microsoft Edge nur als Standardbrowser für Benutzer in Ihrer Organisation festgelegt. Einzelne Benutzer können weiterhin einen anderen Browser auswählen.</span><span class="sxs-lookup"><span data-stu-id="f53e4-105">This will only set Microsoft Edge as the default browser for users in your org, individual users can still select a different browser.</span></span>
  
  
## <a name="windows-8-and-later"></a><span data-ttu-id="f53e4-106">Windows 8 und höher</span><span class="sxs-lookup"><span data-stu-id="f53e4-106">Windows 8 and above</span></span>

<span data-ttu-id="f53e4-107">In diesen Anweisungen wird gezeigt, wie Sie Microsoft Edge oder Internet Explorer als Standardbrowser für Computer unter Windows 8 oder höher festlegen.</span><span class="sxs-lookup"><span data-stu-id="f53e4-107">These instructions show you how to make Microsoft Edge or Internet Explorer as the default browser for computers running Windows 8 or later.</span></span> <span data-ttu-id="f53e4-108">Benutzer können den Browser ändern, nachdem diese Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f53e4-108">Users will be able to change the browser after this policy is set.</span></span>
  
### <a name="step-1-create-the-default-associations-file"></a><span data-ttu-id="f53e4-109">SCHRITT 1: Erstellen der Standardzuordnungsdatei</span><span class="sxs-lookup"><span data-stu-id="f53e4-109">STEP 1: Create the default associations file</span></span>
<span data-ttu-id="f53e4-110">Erstellen Sie die Standardzuordnungsdatei im Ordner "SYSVOL" des Domänencontrollers.</span><span class="sxs-lookup"><span data-stu-id="f53e4-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>

1. <span data-ttu-id="f53e4-111">Öffnen Sie eine PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="f53e4-111">Open an administrative PowerShell console.</span></span>
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a><span data-ttu-id="f53e4-112">SCHRITT 2:</span><span class="sxs-lookup"><span data-stu-id="f53e4-112">Step 2</span></span> <span data-ttu-id="f53e4-113">Hinzufügen oder Bearbeiten der Standardzuordnungsdatei</span><span class="sxs-lookup"><span data-stu-id="f53e4-113">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. <span data-ttu-id="f53e4-114">Bearbeiten Sie die folgenden Einträge (.htm, .html, http, https), und entfernen Sie die anderen Einträge, wenn sie nicht benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="f53e4-114">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
  - <span data-ttu-id="f53e4-115">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="f53e4-115">**Microsoft Edge**</span></span>
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="f53e4-116">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="f53e4-116">**Internet Explorer**</span></span>
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a><span data-ttu-id="f53e4-117">SCHRITT 3:</span><span class="sxs-lookup"><span data-stu-id="f53e4-117">Step 3.</span></span> <span data-ttu-id="f53e4-118">Bearbeiten der Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f53e4-118">Edit the Group Policy</span></span>

1. <span data-ttu-id="f53e4-119">Öffnen Sie die **Gruppenrichtlinien-Verwaltungskonsole** (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.</span><span class="sxs-lookup"><span data-stu-id="f53e4-119">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
1. <span data-ttu-id="f53e4-120">Navigieren Sie zu **Computerkonfiguration\Administrative Vorlagen\Windows-Komponenten\Datei-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f53e4-120">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
1. <span data-ttu-id="f53e4-121">Doppelklicken Sie auf **Konfigurationsdatei für Standardzuordnungen festlegen**, legen Sie es auf **Aktiviert** fest, und geben Sie den Pfad zu AppAssoc.xml (z. B. %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) ein.Erzwingen Sie das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="f53e4-121">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

  
## <a name="windows-7"></a><span data-ttu-id="f53e4-122">Windows 7</span><span class="sxs-lookup"><span data-stu-id="f53e4-122">Windows 7</span></span>

1. <span data-ttu-id="f53e4-123">Konfigurieren Sie den lokalen Computer, der verwendet wird, um das Gruppenrichtlinienobjekt festlegen.</span><span class="sxs-lookup"><span data-stu-id="f53e4-123">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="f53e4-124">Öffnen Sie **Systemsteuerung\Programme\Standardprogramme\Standardprogramme festlegen**, und legen Sie Internet Explorer als Standard fest.</span><span class="sxs-lookup"><span data-stu-id="f53e4-124">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="f53e4-125">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.</span><span class="sxs-lookup"><span data-stu-id="f53e4-125">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="f53e4-126">Navigieren Sie zu \*\* \<Computer/Benutzer\> Konfiguration\Richtlinien\Einstellungen\Windows-Einstellungen\*\*.</span><span class="sxs-lookup"><span data-stu-id="f53e4-126">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="f53e4-127">Klicken Sie mit der rechten Maustaste auf **Registrierung\Neu**, und wählen Sie **Registrierungs-Assistent** aus.</span><span class="sxs-lookup"><span data-stu-id="f53e4-127">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="f53e4-128">Wählen Sie im Fenster „Registrierungsbrowser“ die Option **Lokaler Computer** aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f53e4-128">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="f53e4-p105">Navigieren Sie zu **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https**, und wählen Sie den Wert „ProgId“ aus. Stellen Sie sicher, dass der Wert wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="f53e4-p105">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Auswählen des ProgId-Werts in „Zeichenfolge bearbeiten“](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="f53e4-p106">Navigieren Sie zu **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https**, und wählen Sie den Wert „ProgId“ aus. Stellen Sie sicher, dass der Wert wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="f53e4-p106">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Auswählen des ProgId-Werts für HTTPS in „Zeichenfolge bearbeiten“](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="f53e4-135">Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="f53e4-135">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
