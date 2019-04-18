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
description: Schnelles Hinzufügen von Antworten auf häufig gestellte Fragen mit Importtools im Microsoft Search Admin Portal
ms.openlocfilehash: 28fcf57c44f809e7f9b0c1b27042f4549067a0f8
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901816"
---
# <a name="bulk-create-qas"></a>Massenerstellung von Fragen und Antworten

Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie, um Q&As massenweise zu erstellen oder zu bearbeiten. Es ist auch eine einfache Möglichkeit zum Massenspeichern von Entwurfs-Q&As, die zusätzliche Änderungen oder Aktualisierungen erfordern. Wenn Sie vorhandene Q&As massenweise bearbeiten müssen, exportieren Sie Sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie.
  
1. Klicken Sie in der oberen rechten Ecke des Abschnitts Q&As auf **importieren**
    
2. Klicken Sie auf **Q&A-Vorlage herunterladen (. CSV)**
    
3. Speichern und Öffnen der CSV-Datei
    
4. Hinzufügen des Q&A-Inhalts und der Einstellungen und Speichern der Datei

    Die CSV-Datei sollte als CSV-UTF-8-Datei gespeichert werden, andere Dateitypen und Codierungen können zu Importfehlern führen.
    
5. Klicken Sie in der oberen rechten Ecke des Abschnitts Q&As auf **importieren**
    
6. Klicken Sie im Bereich Q&As importieren auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten. 
    
7. Klicken Sie auf **importieren**

# <a name="prevent-import-errors"></a>Verhindern von Importfehlern      
Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren.

> [!NOTE]
> Sie können keine Q&As erstellen oder bearbeiten, bis alle Fehler aufgelöst wurden. 

Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:
- Enthält die Überschriftenzeile, die sich in der Importvorlage befand
- Enthält alle Spalten, die in der Importvorlage enthalten waren.
- Die Reihenfolge der Spalten ist identisch mit der Importvorlage.
- Diese Spalten können leer sein: ID, zuletzt geändert und zuletzt geändert von
- Die Spalte Status kann nicht leer sein, diese Informationen sind erforderlich.  
Basierend auf dem Feld Status wird Q&As als Entwurf, vorgeschlagen, geplant gespeichert oder automatisch veröffentlicht.

Wenn Sie auch die ID eines vorhandenen Q&A-Objekt hinzufügen, wird es durch die Informationen in der Importdatei ersetzt.

Für Organisationen mit mehreren Stand-Mandanten können Sie Ihre Q&As aus einem Mandanten exportieren und in einen anderen importieren. Sie müssen jedoch vor dem Importieren alle Daten in der Spalte "ID" entfernen.

Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Create Q&As](create-qas.md).

  

