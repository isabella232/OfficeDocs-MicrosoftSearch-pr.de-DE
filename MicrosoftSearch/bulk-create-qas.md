---
title: Massenerstellung von Fragen und Antworten
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
description: Fügen Sie Antworten auf häufig gestellte Fragen mit den Importtools im Microsoft Search-Verwaltungsportal schnell hinzu.
ms.openlocfilehash: f535cb7ae843def536976cb1f05c8601de592cbb
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968302"
---
# <a name="bulk-create-qas"></a>Massenerstellung von Fragen und Antworten

> [!IMPORTANT]
> Die Einstellungen für Microsoft Search in Bing sind nun im Microsoft 365 Admin Center verfügbar. Beginnen Sie, indem Sie [Suchadministratoren](https://docs.microsoft.com/de-DE/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in Ihrem Admin Center zuweisen.
    
Laden Sie die CSV-Vorlage herunter, und verwenden Sie sie zur Massenerstellung oder -bearbeitung von Fragen und Antworten. Dies ist auch eine einfache Möglichkeit zum Speichern von Fragen und Antworten des Typs "Entwurf", bei denen zusätzliche Bearbeitungen oder Aktualisierungen erforderlich sind. Wenn Sie eine Massenbearbeitung von vorhandenen Fragen und Antworten ausführen müssen, exportieren Sie sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie sie.
  
1. Klicken Sie in der oberen rechten Ecke des Abschnitts "Fragen und Antworten" auf **Importieren**.
    
2. Klicken Sie auf **F & A-Vorlage (CSV) herunterladen**.
    
3. Speichern und öffnen Sie die CSV-Datei.
    
4. Fügen Sie den F & A-Inhalt und die Einstellungen hinzu, und speichern Sie die Datei.

    Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.
    
5. Klicken Sie in der oberen rechten Ecke des Abschnitts "Fragen und Antworten" auf **Importieren**.
    
6. Klicken Sie im Bereich "Fragen und Antworten importieren" auf **Durchsuchen**, und navigieren Sie zu der CSV-Datei, die Sie importieren möchten. 
    
7. Klicken Sie auf **Importieren**.

# <a name="prevent-import-errors"></a>Vermeiden von Importfehlern      
Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie alle erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut importieren.

> [!NOTE]
> Bis alle Fehler behoben wurden, können Sie keine Fragen und Antworten erstellen oder bearbeiten. 

Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:
- Enthält die Überschriftenzeile aus der Importvorlage.
- Enthält alle Spalten aus der Importvorlage.
- Die Spaltenreihenfolge ist die gleiche wie in der Importvorlage.
- Diese Spalten können leer sein: "ID", "Zuletzt geändert" und "Zuletzt geändert von".
- Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.  
Auf der Grundlage des Statusfelds werden Fragen und Antworten als "Entwurf", "vorgeschlagen" oder "geplant" gespeichert, oder sie werden automatisch veröffentlicht.

Und wenn Sie die ID eines vorhandenen Frage&Antwort-Eintrags angeben, wird dieser durch die Informationen in der Importdatei ersetzt.

Bei Organisationen mit mehreren Mandanten können Sie Ihre Frage&Antwort-Einträge von einem Mandanten exportieren und zu einem anderen importieren. Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.

Unter [Erstellen von Fragen und Antworten](create-qas.md) erfahren Sie mehr zu erforderlichen und empfohlenen Feldern.

  

