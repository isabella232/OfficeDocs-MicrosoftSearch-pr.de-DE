---
title: Verwalten von Fragen und Antworten
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
description: Suchen und Aktualisieren von Antworten einzeln oder verwenden der verfügbaren Microsoft-Such Tools, um Sie alle gleichzeitig zu bearbeiten
ms.openlocfilehash: 47882deeb95133cfc19f4eec6417fc20fb7203de
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508817"
---
# <a name="manage-qas"></a>Verwalten von Fragen und Antworten

Im Lauf der Zeit müssen Sie möglicherweise einen Q&A's-Status und-Inhalt aktualisieren, um ihn relevant zu halten.
  
## <a name="filter-qas"></a>Filter Q&As

Verwenden Sie die Filter-Option in der oberen rechten Ecke der Q&As-Seite, um nach Q&As nach Datum zu suchen und diese zu ändern. Legen Sie beispielsweise den Schieberegler Datum auf 30 Tage fest, und wählen Sie einen Administrator oder Editor aus, um die Liste der Q&As anzuzeigen, die Sie in dieser Zeit erstellt oder geändert haben.
  
## <a name="change-qa-content-or-settings"></a>Ändern von Q&A-Inhalten oder-Einstellungen

1. Wechseln Sie zum Microsoft Search-Verwaltungsportal.
    
2. Klicken Sie im Navigationsbereich auf **Fragen und Antworten**.
    
3. So finden Sie ein Q&A, suchen, Filtern oder klicken auf einen Q&A-Status, um die Ergebnisse einzuschränken
    
4. Um eine Q&A zu ändern oder zu aktualisieren, klicken Sie auf den Titel
    
5. Nehmen Sie alle Änderungen oder Aktualisierungen an den Inhalten oder Einstellungen vor, und zeigen Sie eine Vorschau der Anzeige an.
    
6. Klicken Sie auf **Speichern**.
    
## <a name="bulk-export-and-edit-qas"></a>Massenexport und-Bearbeitung Q&As

Bearbeiten Sie nie Daten in diesen Feldern:
  
- Id
    
- Zuletzt geändert
    
- Zuletzt geändert von
    
ID ist ein eindeutiger Bezeichner für jede Q&A und sollte nie bearbeitet werden. Die Felder zuletzt geändert und zuletzt geändert von werden nur zum Sortieren und suchen von Q&As verwendet.
  
1. Wenn Sie eine Teilmenge ihrer Q&As exportieren möchten, Filtern Sie Sie.
    
2. Klicken Sie in der oberen rechten Ecke der Seite Q&As auf **exportieren** .
    
3. Speichern oder Öffnen der CSV-Datei
    
4. Bearbeiten von Daten in einem dieser Felder:
    
   - Frage
    
   - URL
      
   - Schlüsselwörter
    
   - Status
    
   - Antwort Beschreibung
    
   - ReServierte Schlüsselwörter
    
   - Anfangstermin
    
   - Enddatum
    
   - Land/Region
    
   - Gruppen
    
   - Geräte&amp;Betriebssystem
    
   - Gezielte Variationen
    
5. Speichern Sie die CSV-Datei

    Die CSV-Datei sollte als CSV-UTF-8-Datei gespeichert werden, andere Dateitypen und Codierungen können zu Importfehlern führen.
    
6. Klicken Sie in der oberen rechten Ecke der Seite Q&As auf **importieren**
    
7. Klicken Sie im Bereich Q&As importieren auf **Durchsuchen** , und wählen Sie die Datei edited. CSV aus. 
    
8. Klicken Sie auf **importieren**
    
Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren.
  
> [!NOTE]
> Sie können keine Q&As erstellen oder bearbeiten, bis alle Fehler aufgelöst wurden. 
  
Nicht alle Felder sind erforderlich, und die erforderlichen Felder hängen vom Q&A-Status ab. Basierend auf dem Feld Status wird Q&As als Entwurf, vorgeschlagen, geplant gespeichert oder automatisch veröffentlicht. Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Create Q&As](create-qas.md).

  

