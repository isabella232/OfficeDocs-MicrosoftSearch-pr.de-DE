---
title: F & As verwalten
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Suchen und aktualisieren Sie Antworten einzeln oder verwenden Sie die verfügbaren Microsoft Search-Tools, um alle gleichzeitig zu bearbeiten
ms.openlocfilehash: ee239aa73d4e650289f39d33c63c3e2df4f100cc
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968467"
---
# <a name="manage-qas"></a>F & As verwalten

> [!IMPORTANT]
> Die Einstellungen für Microsoft Search in Bing sind jetzt im Microsoft 365 Admin Center verfügbar. Beginnen Sie, indem Sie in Ihrem Admin Center[Suchadministratoren zuweisen](https://docs.microsoft.com/de-DE/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor).
    
Im Laufe der Zeit müssen Sie den Status und Inhalt einer F & A möglicherweise aktualisieren, damit sie relevant bleibt.
  
## <a name="filter-qas"></a>Filtern von Fragen und Antworten

Verwenden Sie die Filteroption in der oberen rechten Ecke der Seite "Fragen und Antworten", um Fragen und Antworten nach Datum und der Person, die sie geändert hat, zu suchen. Setzen Sie beispielsweise den Schieberegler für das Datum auf „30 Tage“ und wählen Sie einen Administrator oder Editor aus, um die Liste der Fragen und Antworten anzuzeigen, die diese während dieser Zeitspanne erstellt oder geändert hat.
  
## <a name="change-qa-content-or-settings"></a>F & A- Inhalte oder -Einstellungen ändern

1. Wechseln zum Microsoft Search-Verwaltungsportal
    
2. Klicken Sie im Navigationsbereich auf **Fragen und Antworten**.
    
3. Um eine Frage und Antwort zu finden, suchen oder filtern Sie einen F & A-Status, oder klicken Sie darauf, um Ihre Ergebnisse einzuschränken.
    
4. Zum Ändern oder Aktualisieren einer Frage und Antwort klicken Sie auf den Titel.
    
5. Nehmen Sie alle Änderungen oder Aktualisierungen an Inhalt oder Einstellungen vor, und zeigen Sie eine Vorschau davon an.
    
6. Klicken Sie auf **Speichern**.
    
## <a name="bulk-export-and-edit-qas"></a>Massenexport und -bearbeitung von Fragen und Antworten

Bearbeiten Sie nie Daten in folgenden Feldern:
  
- ID
    
- Zuletzt geändert
    
- Zuletzt geändert von
    
„ID“ ist ein eindeutiger Bezeichner für jede Frage und Antwort und sollte nie bearbeitet werden. Die Felder „Zuletzt geändert“ und „Zuletzt geändert von“ sollten nur zum Sortieren und Suchen von Fragen und Antworten verwendet werden.
  
1. Wenn Sie eine Teilmenge Ihrer Fragen und Antworten exportieren möchten, filtern Sie sie.
    
2. Klicken Sie in der oberen rechten Ecke der Seite "Fragen und Antworten" auf **Exportieren**.
    
3. Speichern oder öffnen Sie die CSV-Datei.
    
4. Bearbeiten Sie Daten in jedem beliebigen der folgenden Felder:
    
   - Frage
    
   - URL
      
   - Schlüsselwörter
    
   - Zustand
    
   - Antwortbeschreibung
    
   - Reservierte Schlüsselwörter
    
   - Anfangstermin
    
   - Endtermin
    
   - Land/Region
    
   - Gruppen
    
   - Geräte und Betriebssystem
    
   - Gezielte Variationen
    
5. Die CSV-Datei speichern

    Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen
    
6. Klicken Sie in der oberen rechten Ecke der Seite „F & A“ auf **Importieren**
    
7. Klicken Sie im Bereich „F & As importieren" auf**Durchsuchen**und wählen Sie die bearbeitete CSV-Datei aus 
    
8. Klicken Sie auf **Importieren**.
    
Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie alle erforderlichen Änderungen vor und versuchen Sie erneut, die Datei zu importieren.
  
> [!NOTE]
> Sie können keine Fragen und Antworten erstellen oder bearbeiten, solange nicht alle Fehler behoben sind.  
  
Nicht alle Felder sind erforderlich und die erforderlichen Felder variieren je nach F & A-Status. Auf der Grundlage des Statusfelds werden Fragen und Antworten als „Entwurf“, „vorgeschlagen“ oder „geplant“ gespeichert oder werden automatisch veröffentlicht. Erfahren Sie mehr zu erforderlichen und empfohlenen Feldern in [F & As erstellen](create-qas.md).

  

