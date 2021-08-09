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
ms.openlocfilehash: 7ad9ff2a0fde5ad5d84a7a51785767fd2e5d21df6654a76b09e9796917a92a0f
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2021
ms.locfileid: "54534194"
---
# <a name="make-bing-the-default-search-engine"></a>Festlegen von Bing als Standardsuchmaschine
  
In diesem Artikel wird erläutert, wie Sie Bing als Standardsuchmaschine für Microsoft Edge, Google Chrome und Internet Explorer festlegen. 
  
## <a name="microsoft-edge-on-windows-10-version-1703-or-later"></a>Microsoft Edge unter Windows 10, Version 1703 oder höher

Auch wenn Sie Bing als Standardsuchmaschine festgelegt haben, können Benutzer unter Microsoft Edge ihre Einstellungen so ändern, dass eine andere Suchmaschine verwendet wird.
  
Die neuesten ADMX-Dateien für verschiedene Windows-Versionen finden Sie unter [Erstellen und Verwalten des zentralen Speichers für administrative Vorlagen für Gruppenrichtlinien unter Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).
  
Wenn die in diesem Abschnitt beschriebene Einstellung in der Gruppenrichtlinien-Verwaltungskonsole nicht zu finden ist, laden Sie die entsprechende ADMX herunter, und kopieren Sie sie in den zentralen Speicher. Weitere Informationen finden Sie unter [Bearbeiten Domain-Based GPOs mithilfe von ADMX-Dateien.](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29) Der zentrale Speicher auf dem Controller ist ein Ordner mit der folgenden **Benennungskonvention: %systemroot%\sysvol \\<domäne \> \policies\PolicyDefinitions**
  
Jede Domäne, die Ihr Controller verarbeitet, sollte einen separaten Ordner erhalten. Mit dem folgenden Befehl kann die ADMX-Datei aus der Befehlszeile kopiert werden:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.
2. Navigieren Sie zu **&lt;Computer/Benutzerkonfiguration&gt;\Administrationsvorlagen\Windows-Komponenten\Microsoft Edge**.
3. Doppelklicken Sie auf **Festlegen der Standardsuchmaschine**, wählen Sie **Aktiviert** aus, und geben Sie `https://www.bing.com/sa/osd/bfb.xml` ein.
4. Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.


## <a name="google-chrome-on-windows-10-version-1507-or-later"></a>Google Chrome auf Windows 10, Version 1507 oder höher

Benutzer können die Standardsuchmaschine nicht mehr ändern, nachdem diese Richtlinie festgelegt wurde.
  
Chrome verfügt über einen eigenen Satz von Gruppenrichtlinieneinstellungen, die in Form einer ADMX-Datei von [Google Chrome Enterprise Hilfe](https://support.google.com/chrome/a/answer/187202)heruntergeladen werden können.
  
Kopieren Sie die Vorlagendatei in einen zentralen Speicher für ADMX-Dateien auf dem Domänencontroller. Weitere Informationen finden Sie unter [Bearbeiten Domain-Based GPOs mithilfe von ADMX-Dateien.](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29) Der zentrale Speicher auf dem Controller ist ein Ordner mit der folgenden **Benennungskonvention: %systemroot%\sysvol \\<domäne \> \policies\PolicyDefinitions**
  
Jede Domäne, die Ihr Controller verarbeitet, sollte einen separaten Ordner erhalten. Mit dem folgenden Befehl kann die ADMX-Datei aus der Befehlszeile kopiert werden:
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.
2. Stellen Sie sicher, dass die folgenden Ordner im Abschnitt Administrationsvorlagen der Benutzer- und Computerkonfiguration angezeigt werden: Google Chrome und Google Chrome - Standardeinstellungen.

    - Die Einstellungen des ersten Abschnitts wurden festgelegt, und lokale Administratoren können sie nicht im Browser ändern.
    - Die Einstellungen im nachfolgenden Abschnitt der Richtlinien können von Benutzern in den Browsereinstellungen geändert werden.

3. Navigieren Sie zu **\<Computer/User\> "Konfiguration\Administrative Vorlagen\Google Chrome\Standardsuchanbieter"**
4. Doppelklicken Sie auf **Aktivieren des Standardsuchanbieters**, und wählen Sie **Aktiviert** aus.
5. Doppelklicken Sie auf das **Standardsuchanbieter-Symbol**, wählen Sie **Aktiviert** aus, und geben Sie `https://www.bing.com/sa/simg/bb.ico` ein.
6. Doppelklicken Sie auf die **Standardsuchanbieter-Instant-URL**, und geben Sie `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR` ein.
7. Doppelklicken Sie auf den **Standardsuchanbieter-Namen**, wählen Sie Aktiviert aus, und geben Sie „Microsoft Search in Bing“ ein.
8. Doppelklicken Sie auf die **Standardsuchanbieter-Such-URL**, wählen Sie **Aktiviert** aus, und geben Sie `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR` ein.
9. Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.

## <a name="internet-explorer-11-or-later"></a>Internet Explorer 11 oder höher

Benutzer können den Suchanbieter ändern, nachdem diese Richtlinie festgelegt wurde.
  
### <a name="step-1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>SCHRITT 1: Konfigurieren Sie den lokalen Computer, der verwendet wird, um das Gruppenrichtlinienobjekt festzulegen.

Fügen Sie den folgenden Text in eine REG-Datei (\*.reg) ein.
  
Windows-Registrierungs-Editor, Version 5.00
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
Doppelklicken Sie auf die erstellte Datei, und befolgen Sie die Schritte zum Importieren der Datei. Nach einem erfolgreichen Import wird der folgende Dialog angezeigt:
  
![Nachricht: Registrierungs-Editor erfolgreich importiert](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
### <a name="step-2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>SCHRITT 2: Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (gpmc.msc), und wechseln Sie zum Bearbeiten einer vorhandenen Richtlinie oder zum Erstellen einer neuen.

1. Navigieren Sie zu **Benutzerkonfiguration\Richtlinien\Einstellungen\Windows-Einstellungen**.
2. Klicken Sie mit der rechten Maustaste auf **Registrierung\Neu** und **Registrierungsassistent**. Wählen Sie im Fenster "Registrierungsbrowser" **Lokaler Computer**, und klicken Sie auf **Weiter**.
3. Navigieren Sie zu **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.
4. Wählen Sie aus diesem Schlüssel DefaultScope aus.

    ![Im Registrierungsbrowser wurde DefaultScope ausgewählt](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
5. Überprüfen Sie alle untergeordneten Schlüssel, die die GUID für Microsoft Search in Bing enthalten, und jeden Wert unter dem Schlüssel mit Ausnahme von Pfaden zu Benutzerprofilen. Scrollen Sie nach unten, um weitere Elemente auszuwählen.
6. Klicken Sie auf Fertig stellen, um die Konfiguration abzuschließen.

### <a name="step-3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>SCHRITT 3: Richten Sie Benutzereinstellungen ein, um eine Warnung zu vermeiden, die der Benutzer möglicherweise erhält, wenn die DefaultScope-Suche erzwungen wird.

Diese Warnung warnt Benutzer eines Programmes davor, ihre Einstellungen zu ändern.
  
1. Klicken Sie im gleichen Gruppenrichtlinienobjekt mit der rechten Maustaste auf **Registrierung\Neu**, und wählen Sie **Registrierungsassistent** aus.
2. Navigieren Sie zu **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.
3. Wählen Sie den Schlüssel **Benutzereinstellung**.
4. Klicken Sie auf **Fertig stellen**.
5. Klicken Sie auf das neu erstellte Objekt. Doppelklicken Sie im Bereich rechts auf das Benutzereinstellungen-Objekt, und ändern Sie die **Aktion** in **Löschen und Speichern**.
6. Erzwingen das resultierende GPO, indem Sie es mit der entsprechenden Domäne verknüpfen.