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
ROBOTS: NoIndex
description: Erstellen Sie viele Lesezeichen gleichzeitig mit Importtools für das Microsoft Search-Verwaltungsportal.
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311641"
---
# <a name="bulk-create-bookmarks"></a>Massenerstellung von Lesezeichen

> [!IMPORTANT]
> Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal. Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird das Microsoft Search im Bing-Portal entfernt. Es wird empfohlen, dass Sie für die ersten Schritte das Microsoft 365 Admin Center verwenden. [Übersicht über Microsoft Search](overview-microsoft-search.md).
    
Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie zum Massen erstellen, bearbeiten und Speichern von Lesezeichen. Wenn Sie vorhandene Lesezeichen Massen bearbeiten möchten, exportieren Sie Sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie dann.
  
1. Klicken Sie in der oberen rechten Ecke des Abschnitts Lesezeichen auf **importieren** .
    
2. Klicken Sie auf **Lesezeichen Vorlage herunterladen (. CSV)**
    
3. Speichern und öffnen Sie die CSV-Datei.
    
4. Hinzufügen der Lesezeichen Inhalte und-Einstellungen und Speichern der Datei

    Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.
    
5. Klicken Sie in der oberen rechten Ecke des Abschnitts Lesezeichen auf **importieren** .
    
6. Klicken Sie im Bereich Lesezeichen importieren auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten. 
    
7. Klicken Sie auf **Importieren**.

## <a name="prevent-import-errors"></a>Vermeiden von Importfehlern      
Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie alle erforderlichen Änderungen vor und versuchen Sie erneut, die Datei zu importieren.

> [!NOTE]
> Bis alle Fehler behoben sind, können Sie keine Lesezeichen erstellen oder bearbeiten. 

Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:
- Enthält die Überschriftenzeile aus der Importvorlage.
- Enthält alle Spalten aus der Importvorlage.
- Die Spaltenreihenfolge die gleiche ist wie in der Importvorlage.
- Diese Spalten können leer sein: "ID", "Zuletzt geändert" und "Zuletzt geändert von".
- Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.  
Auf der Grundlage des Felds „Status“ werden Lesezeichen als „Entwurf“, „vorgeschlagen“ oder „geplant“ gespeichert, oder sie werden automatisch veröffentlicht.

Wenn Sie die ID einer vorhandenen Textmarke hinzufügen, wird Sie auch durch die Informationen in der Importdatei ersetzt.

Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Lesezeichen aus einer org exportieren und in eine andere importieren. Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.

Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Create Bookmarks](create-bookmarks.md).
