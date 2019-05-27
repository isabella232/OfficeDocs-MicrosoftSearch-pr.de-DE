---
title: Lesezeichen verwalten
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/08/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Suchen von Lesezeichen, die aktualisiert werden müssen, und von Methoden zur Massenbearbeitung von Lesezeichenergebnissen für Microsoft Search.
ms.openlocfilehash: d5cebbfd5779bc8a6aa25cdbcdedb6e9b18f242e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968483"
---
# <a name="manage-bookmarks"></a>Lesezeichen verwalten

> [!IMPORTANT]
> Die Einstellungen für Microsoft Search in Bing sind jetzt im Microsoft 365 Admin Center verfügbar. Beginnen Sie, indem Sie in Ihrem Admin Center[Suchadministratoren zuweisen](https://docs.microsoft.com/de-DE/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor).
    
Im Laufe der Zeit müssen Sie den Status und Inhalt eines Lesezeichens möglicherweise aktualisieren, damit es relevant bleibt. 
  
## <a name="filter-bookmarks"></a>Filtern von Lesezeichen

Verwenden Sie die Filteroption in der oberen rechten Ecke der Seite "Lesezeichen", um Lesezeichen nach Datum und der Person, die sie geändert hat, zu suchen. Setzen Sie beispielsweise den Schieberegler für das Datum auf „30 Tage“ und wählen Sie einen Administrator oder Editor aus, um die Liste der Lesezeichen anzuzeigen, die diese während dieser Zeitspanne erstellt oder geändert haben.
  
## <a name="change-bookmark-content-or-settings"></a>Lesezeicheninhalte oder -einstellungen ändern

1. Wechseln zum Microsoft Search-Verwaltungsportal
    
2. Klicken Sie im Navigationsbereich auf **Lesezeichen**.
    
3. Um ein Lesezeichen zu finden, suchen, filtern oder klicken Sie auf einen Lesezeichenstatus, um Ihre Ergebnisse einzuschränken
    
4. Klicken Sie zum Ändern oder Aktualisieren eines Lesezeichens auf den Titel.
    
5. Nehmen Sie alle Änderungen oder Aktualisierungen an Inhalt oder Einstellungen vor, und zeigen Sie eine Vorschau davon an. 
    
6. Klicken Sie auf **Speichern**.
    
## <a name="bulk-export-and-edit-bookmarks"></a>Massenexport und -bearbeitung von Lesezeichen

Bearbeiten Sie nie Daten in folgenden Feldern:
  
- ID
    
- Zuletzt geändert
    
- Zuletzt geändert von
    
"ID" ist ein eindeutiger Bezeichner für jedes Lesezeichen und sollte nie bearbeitet werden. Die Felder "Zuletzt geändert" und "Zuletzt geändert von" sollten nur zum Sortieren und Suchen von Lesezeichen verwendet werden.
  
1. Wenn Sie eine Teilmenge Ihrer Lesezeichen exportieren möchten, filtern Sie sie.
    
2. Klicken Sie in der oberen rechten Ecke der Seite "Lesezeichen" auf **Exportieren**.
    
3. Speichern oder öffnen Sie die CSV-Datei.
    
4. Bearbeiten Sie Daten in jedem beliebigen der folgenden Felder:
   - Titel
    
   - URL
    
   - Schlüsselwörter
    
   - Zustand
    
   - Beschreibung
    
   - Reservierte Schlüsselwörter
    
   - Anfangstermin
    
   - Endtermin
    
   - Land/Region
    
   - Gruppen
    
   - Gerät und Betriebssystem
    
   - Gezielte Variationen
    
5. Die CSV-Datei speichern

    Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen
    
6. Klicken Sie in der oberen rechten Ecke der Seite „Lesezeichen“ auf **Importieren**
    
7. Klicken Sie im Bereich „Lesezeichen importieren“ auf **Durchsuchen** und wählen Sie die bearbeitete CSV-Datei aus 
    
8. Klicken Sie auf **Importieren**