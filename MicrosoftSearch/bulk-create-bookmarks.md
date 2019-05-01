---
title: Massenerstellung von Lesezeichen
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
description: Erstellen Sie viele Lesezeichen gleichzeitig mit Importtools für das Microsoft Search-Verwaltungsportal.
ms.openlocfilehash: 7c134784f0ca0d4cc84d5bce3a98f7e75aa6f441
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508618"
---
# <a name="bulk-create-bookmarks"></a>Massenerstellung von Lesezeichen

Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie zum Massen erstellen, bearbeiten und Speichern von Lesezeichen. Zum Massen Bearbeiten vorhandener Lesezeichen, exportieren Sie diese aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie.
  
1. Klicken Sie in der oberen rechten Ecke des Abschnitts Lesezeichen auf **importieren**
    
2. Klicken Sie auf **Lesezeichen Vorlage herunterladen (. CSV)**
    
3. Speichern und Öffnen der CSV-Datei
    
4. Hinzufügen des Inhalts und der Einstellungen für die Textmarke und Speichern der Datei

    Die CSV-Datei sollte als CSV-UTF-8-Datei gespeichert werden, andere Dateitypen und Codierungen können zu Importfehlern führen.
    
5. Klicken Sie in der oberen rechten Ecke des Abschnitts Lesezeichen auf **importieren**
    
6. Klicken Sie im Bereich Lesezeichen importieren auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten. 
    
7. Klicken Sie auf **importieren**

# <a name="prevent-import-errors"></a>Verhindern von Importfehlern      
Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren.

> [!NOTE]
> Sie können keine Lesezeichen erstellen oder bearbeiten, bis alle Fehler aufgelöst wurden. 

Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:
- Enthält die Überschriftenzeile, die sich in der Importvorlage befand
- Enthält alle Spalten, die in der Importvorlage enthalten waren.
- Die Reihenfolge der Spalten ist identisch mit der Importvorlage.
- Diese Spalten können leer sein: ID, zuletzt geändert und zuletzt geändert von
- Die Spalte Status kann nicht leer sein, diese Informationen sind erforderlich.  
Basierend auf dem Feld Status werden Lesezeichen als Entwurf, vorgeschlagen oder geplant gespeichert, oder Sie werden automatisch veröffentlicht.

Wenn Sie die ID einer vorhandenen Textmarke hinzufügen, wird Sie auch durch die Informationen in der Importdatei ersetzt.

Für Organisationen mit mehreren Stand-Mandanten können Sie Ihre Lesezeichen aus einem Mandanten exportieren und in einen anderen importieren. Sie müssen jedoch vor dem Importieren alle Daten in der Spalte "ID" entfernen.

Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Create Bookmarks](create-bookmarks.md).
