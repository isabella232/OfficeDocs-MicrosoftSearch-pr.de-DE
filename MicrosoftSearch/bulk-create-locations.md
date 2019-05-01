---
title: Massenerstellen von Speicherorten
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
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
description: Hinzufügen von vielen Standorten gleichzeitig mit Importtools für das Microsoft Search-Verwaltungsportal
ms.openlocfilehash: 3c7e43b03b97b46769d5e73f20ddae47b3459b59
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508561"
---
# <a name="bulk-create-locations"></a>Massenerstellen von Speicherorten

Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie zum Massen erstellen, bearbeiten und Speichern von Speicherorten. 
  
1. Klicken Sie in der oberen rechten Ecke des Abschnitts Standorte auf **importieren** .
    
2. Klicken Sie auf **Download Speicherorte Vorlage (. CSV)**
    
3. Speichern und Öffnen der CSV-Datei
    
4. Hinzufügen des Standort Inhalts und Speichern der Datei

    Die CSV-Datei sollte als CSV-UTF-8-Datei gespeichert werden, andere Dateitypen und Codierungen können zu Importfehlern führen.
    
5. Klicken Sie in der oberen rechten Ecke des Abschnitts Standorte auf **importieren** .
    
6. Klicken Sie im Bereich Speicherorte importieren auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten. 
    
7. Klicken Sie auf **importieren**

Die Felder in den Import-und Exportspeicherort Vorlagen sind identisch. Sie können die Bearbeitungen exportieren, Massen bearbeiten und importieren oder mit einer leeren Vorlage beginnen, um massenweise neue Speicherorte zu erstellen. Zum Massen Bearbeiten vorhandener Speicherorte, exportieren Sie diese aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie.

# <a name="prevent-import-errors"></a>Verhindern von Importfehlern  
Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren.
  
> [!NOTE]
> Sie können keine Speicherorte erstellen oder bearbeiten, bis alle Fehler aufgelöst wurden. 

Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:
- Enthält die Überschriftenzeile, die sich in der Importvorlage befand
- Enthält alle Spalten, die in der Importvorlage enthalten waren.
- Die Reihenfolge der Spalten ist identisch mit der Importvorlage.
- Diese Spalten können leer sein: ID, zuletzt geändert, zuletzt geändert von und lat/long  
Wir versuchen, lat/long basierend auf der Adresse zu ermitteln, wenn das Feld leer ist.
- Die Spalte Status kann nicht leer sein, diese Informationen sind erforderlich.  
Basierend auf dem Feld Status werden Speicherorte als Entwurf, vorgeschlagen oder geplant gespeichert, oder Sie werden automatisch veröffentlicht.

Wenn Sie die ID eines vorhandenen Speicherorts angeben, wird Sie auch durch die Informationen in der Importdatei ersetzt.

Für Organisationen mit mehreren Stand-Mandanten können Sie Ihre Standorte aus einem Mandanten exportieren und in einen anderen importieren. Sie müssen jedoch vor dem Importieren alle Daten in der Spalte "ID" entfernen.
  
Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Hinzufügen eines Standorts](add-a-location.md).

  

