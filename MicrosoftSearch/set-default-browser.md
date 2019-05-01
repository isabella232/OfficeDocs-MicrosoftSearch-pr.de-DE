---
title: Festlegen des Standardbrowsers
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
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Erfahren Sie, wie einen Standardbrowser für Ihr Unternehmen mit Microsoft Search konfigurieren.
ms.openlocfilehash: 160dbbef9981127b74c51f54f86428667ecd4471
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508993"
---
# <a name="set-default-browser"></a><span data-ttu-id="7b8cd-103">Festlegen des Standardbrowsers</span><span class="sxs-lookup"><span data-stu-id="7b8cd-103">Set default browser</span></span>

<span data-ttu-id="7b8cd-104">Das Konfigurieren des Standardbrowsers, der Standardsuchmaschine und der standardmäßigen Startseite hilft Ihren Benutzern, die Microsoft Search-Funktionen zu entdecken, fördert deren Verwendung und ermöglicht eine gleichmäßigere Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="7b8cd-105">Führen Sie zum Festlegen des Standardbrowsers für Ihre Organisation die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-105">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="7b8cd-106">Windows 8 und höher</span><span class="sxs-lookup"><span data-stu-id="7b8cd-106">Windows 8 and above</span></span>

<span data-ttu-id="7b8cd-107">Wenn Sie Internet Explorer oder Microsoft Edge als Standardbrowser festlegen möchten, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="7b8cd-107">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="7b8cd-108">Erstellen der Standardzuordnungsdatei</span><span class="sxs-lookup"><span data-stu-id="7b8cd-108">Create default associations file</span></span>

1. <span data-ttu-id="7b8cd-109">Öffnen Sie eine PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-109">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="7b8cd-110">Diese Schritte testen und erstellen die Standardzuordnungsdatei im Ordner „SYSVOL“ des Domänencontrollers.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="7b8cd-111">Hinzufügen oder Bearbeiten der Standardzuordnungsdatei</span><span class="sxs-lookup"><span data-stu-id="7b8cd-111">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="7b8cd-112">Bearbeiten Sie die folgenden Einträge (.htm, .html, http, https), und entfernen Sie die anderen Einträge, wenn sie nicht benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-112">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="7b8cd-113">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="7b8cd-113">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="7b8cd-114">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="7b8cd-114">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="7b8cd-115">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-115">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="7b8cd-116">Navigieren Sie zu **Computerkonfiguration\Administrative Vorlagen\Windows-Komponenten\Datei-Explorer**</span><span class="sxs-lookup"><span data-stu-id="7b8cd-116">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="7b8cd-117">Doppelklicken Sie auf **Konfigurationsdatei für Standardzuordnungen festlegen**, legen Sie es auf **Aktiviert** fest, und geben Sie den Pfad zu AppAssoc.xml (z. B. %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) ein.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-117">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="7b8cd-118">Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-118">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="7b8cd-119">Benutzer können den Browser ändern, nachdem diese Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-119">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="7b8cd-120">Windows 7</span><span class="sxs-lookup"><span data-stu-id="7b8cd-120">Windows 7</span></span>

1. <span data-ttu-id="7b8cd-121">Konfigurieren Sie den lokalen Computer, der verwendet wird, um das Gruppenrichtlinienobjekt festlegen.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-121">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="7b8cd-122">Öffnen Sie **Systemsteuerung\Programme\Standardprogramme\Standardprogramme festlegen**, und legen Sie Internet Explorer als Standard fest.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-122">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="7b8cd-123">Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-123">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="7b8cd-124">Navigieren Sie zu \*\* \<Computer/Benutzer\> Konfiguration\Richtlinien\Einstellungen\Windows-Einstellungen\*\*.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-124">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="7b8cd-125">Klicken Sie mit der rechten Maustaste auf **Registrierung\Neu**, und wählen Sie **Registrierungs-Assistent** aus.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-125">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="7b8cd-126">Wählen Sie im Fenster „Registrierungsbrowser“ die Option **Lokaler Computer** aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-126">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="7b8cd-p101">Navigieren Sie zu **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https**, und wählen Sie den Wert „ProgId“ aus. Stellen Sie sicher, dass der Wert wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="7b8cd-p101">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Auswählen des ProgId-Werts in „Zeichenfolge bearbeiten“](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="7b8cd-p102">Navigieren Sie zu **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https**, und wählen Sie den Wert „ProgId“ aus. Stellen Sie sicher, dass der Wert wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="7b8cd-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Auswählen des ProgId-Werts für HTTPS in „Zeichenfolge bearbeiten“](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="7b8cd-133">Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="7b8cd-134">Benutzer können den Browser ändern, nachdem diese Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-134">Users will be able to change the browser after this policy is set.</span></span>