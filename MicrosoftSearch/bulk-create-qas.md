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
ROBOTS: NoIndex
description: Fügen Sie Antworten auf häufig gestellte Fragen mit den Importtools im Microsoft Search-Verwaltungsportal schnell hinzu.
ms.openlocfilehash: 660f5663ff6238f4ab59dab36d51f1311d5c7260
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949032"
---
# <a name="bulk-create-qas"></a>Massenerstellung von Fragen und Antworten

> [!IMPORTANT]
> Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal. Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird Microsoft Search im Bing-Portal entfernt. Wir empfehlen, für die ersten Schritte das Microsoft 365 Admin Center zu verwenden. [Übersicht über Microsoft Search](overview-microsoft-search.md).
    
Laden Sie die CSV-Vorlage herunter, und verwenden Sie sie zur Massenerstellung oder -bearbeitung von Fragen und Antworten. Dies ist auch eine einfache Möglichkeit zum Speichern von Fragen und Antworten des Typs "Entwurf", bei denen zusätzliche Bearbeitungen oder Aktualisierungen erforderlich sind. Wenn Sie eine Massenbearbeitung von vorhandenen Fragen und Antworten ausführen müssen, exportieren Sie sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie sie.
  
1. Klicken Sie in der oberen rechten Ecke des Abschnitts "Fragen und Antworten" auf **Importieren**.
    
2. Klicken Sie auf **F & A-Vorlage (CSV) herunterladen**.
    
3. Speichern und öffnen Sie die CSV-Datei.
    
4. Fügen Sie den F & A-Inhalt und die Einstellungen hinzu, und speichern Sie die Datei.

    Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.
    
5. Klicken Sie in der oberen rechten Ecke des Abschnitts "Fragen und Antworten" auf **Importieren**.
    
6. Klicken Sie im Bereich "Fragen und Antworten importieren" auf **Durchsuchen**, und navigieren Sie zu der CSV-Datei, die Sie importieren möchten. 
    
7. Klicken Sie auf **Importieren**.

## <a name="prevent-import-errors"></a>Vermeiden von Importfehlern      
Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie alle erforderlichen Änderungen vor und versuchen Sie erneut, die Datei zu importieren.

> [!NOTE]
> Bis alle Fehler behoben wurden, können Sie keine Fragen und Antworten erstellen oder bearbeiten. 

Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:
- Enthält die Überschriftenzeile aus der Importvorlage.
- Enthält alle Spalten aus der Importvorlage.
- Die Spaltenreihenfolge die gleiche ist wie in der Importvorlage.
- Diese Spalten können leer sein: "ID", "Zuletzt geändert" und "Zuletzt geändert von".
- Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.  
Auf der Grundlage des Statusfelds werden Fragen und Antworten als "Entwurf", "vorgeschlagen" oder "geplant" gespeichert, oder sie werden automatisch veröffentlicht.

Und wenn Sie die ID eines vorhandenen Frage&Antwort-Eintrags angeben, wird dieser durch die Informationen in der Importdatei ersetzt.

Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Q-&aus einer org exportieren und in eine andere importieren. Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.

Unter [Erstellen von Fragen und Antworten](create-qas.md) erfahren Sie mehr zu erforderlichen und empfohlenen Feldern.

  

