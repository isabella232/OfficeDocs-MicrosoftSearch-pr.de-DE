---
title: Massenerstellen von Standorten
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
description: Fügen Sie mit den Importtools für das Microsoft Search-Verwaltungsportal sehr viele Standorte gleichzeitig hinzu.
ms.openlocfilehash: 186f6973de1ff87b62b5f07a47eb41acdd842010
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591395"
---
# <a name="bulk-create-locations"></a>Massenerstellen von Standorten

> [!IMPORTANT]
> Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal. Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird es entfernt. Es wird empfohlen, dass Sie zu Beginn das Microsoft 365 Admin Center verwenden. [Übersicht über Microsoft Search](overview-microsoft-search.md).
    
Laden Sie die CSV-Vorlage herunter, und verwenden Sie sie zur Massenerstellung, -bearbeitung und -speicherung von Standorten. 
  
1. Klicken Sie in der oberen rechten Ecke des Abschnitts "Standorte" auf **Importieren**.
    
2. Klicken Sie auf **Standortvorlage (CSV) herunterladen**.
    
3. Speichern und öffnen Sie die CSV-Datei.
    
4. Hinzufügen des Standortinhalts und Speichern der Datei

    Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.
    
5. Klicken Sie in der oberen rechten Ecke des Abschnitts "Standorte" auf **Importieren**.
    
6. Klicken Sie im Bereich "Standorte importieren" auf **Durchsuchen**, und navigieren Sie zu der CSV-Datei, die Sie importieren möchten. 
    
7. Klicken Sie auf **Importieren**.

Die Felder in den Vorlagen zum Importieren und Exportieren von Standortvorlagen sind identisch. Sie können die Änderungen exportieren, in einem Massenvorgang bearbeiten und importieren, oder Sie können mit einer leeren Vorlage beginnen, um neue Standorte in einem Massenvorgang zu erstellen. Wenn Sie eine Massenbearbeitung von vorhandenen Standorten ausführen möchten, exportieren Sie sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie sie.

# <a name="prevent-import-errors"></a>Vermeiden von Importfehlern  
Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie alle erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut importieren.
  
> [!NOTE]
> Bis alle Fehler behoben wurden, können Sie keine Standorte erstellen oder bearbeiten. 

Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:
- Enthält die Überschriftenzeile aus der Importvorlage.
- Enthält alle Spalten aus der Importvorlage.
- Die Spaltenreihenfolge die gleiche ist wie in der Importvorlage.
- Diese Spalten können leer sein: "ID", "Zuletzt geändert", "Zuletzt geändert von" und "Längen-/Breitengrad".  
Wir werden versuchen, den Längen- und Breitengrad anhand der Adresse zu ermitteln, wenn dieses Feld leer ist.
- Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.  
Auf der Grundlage des Felds „Status“ werden Standorte als „Entwurf“, „vorgeschlagen“ oder „geplant“ gespeichert, oder sie werden automatisch veröffentlicht.

Und wenn Sie die ID eines vorhandenen Standorts angeben, wird sie durch die Informationen in der Importdatei ersetzt.

Bei Organisationen mit mehreren Mandanten können Sie Ihre Standorte von einem Mandanten exportieren und zu einem anderen importieren. Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.
  
Unter [Hinzufügen eines Standorts](add-a-location.md) erfahren Sie mehr zu erforderlichen und empfohlenen Feldern.

  

