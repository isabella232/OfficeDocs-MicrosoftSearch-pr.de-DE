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
ROBOTS: NoIndex
description: Fügen Sie viele Orte gleichzeitig mit Importtools für das Microsoft Search-Verwaltungsportal hinzu.
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948971"
---
# <a name="bulk-create-locations"></a>Massenerstellen von Speicherorten

> [!IMPORTANT]
> Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal. Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird das Microsoft Search im Bing-Portal entfernt. Es wird empfohlen, dass Sie für die ersten Schritte das Microsoft 365 Admin Center verwenden. [Übersicht über Microsoft Search](overview-microsoft-search.md).
    
Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie zum Massen erstellen, bearbeiten und Speichern von Speicherorten. 
  
1. Klicken Sie in der oberen rechten Ecke des Abschnitts Speicherorte auf **importieren** .
    
2. Klicken Sie auf **Download Speicherorte Vorlage (. CSV)**
    
3. Speichern und öffnen Sie die CSV-Datei.
    
4. Hinzufügen des Standort Inhalts und Speichern der Datei

    Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.
    
5. Klicken Sie in der oberen rechten Ecke des Abschnitts Speicherorte auf **importieren** .
    
6. Klicken Sie im Bereich Import Speicherorte auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten. 
    
7. Klicken Sie auf **Importieren**.

Die Felder in den Vorlagen für das Importieren und Exportieren von Speicherorten sind identisch. Sie können die Bearbeitungsvorgänge exportieren, Massen bearbeiten und importieren oder mit einer leeren Vorlage beginnen, um massenhaft neue Speicherorte zu erstellen. Wenn Sie vorhandene Speicherorte massenweise bearbeiten möchten, exportieren Sie Sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie dann.

## <a name="prevent-import-errors"></a>Vermeiden von Importfehlern  
Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie alle erforderlichen Änderungen vor und versuchen Sie erneut, die Datei zu importieren.
  
> [!NOTE]
> Bis alle Fehler behoben sind, können Sie keine Speicherorte erstellen oder bearbeiten. 

Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:
- Enthält die Überschriftenzeile aus der Importvorlage.
- Enthält alle Spalten aus der Importvorlage.
- Die Spaltenreihenfolge die gleiche ist wie in der Importvorlage.
- Diese Spalten können leer sein: ID, zuletzt geändert, zuletzt geändert von und lat/long  
Wir versuchen, lat/long basierend auf der Adresse zu bestimmen, wenn das Feld leer ist.
- Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.  
Basierend auf dem Feld State werden die Standorte als Entwurf, vorgeschlagen, geplant oder automatisch veröffentlicht.

Wenn Sie die ID eines vorhandenen Speicherorts einschließen, wird dieser auch durch die Informationen in der Importdatei ersetzt.

Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Standorte aus einer Organisation exportieren und in eine andere importieren. Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.
  
Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Hinzufügen eines Standorts](add-a-location.md).

  

