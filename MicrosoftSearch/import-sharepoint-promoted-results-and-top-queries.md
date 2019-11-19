---
title: Importieren von höhergestuften SharePoint-Ergebnissen und den wichtigsten Abfragen
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
ROBOTS: NOINDEX
description: Verwenden von Suchabfragen aus SharePoint zum Erstellen von Arbeitsergebnissen für die Microsoft-Suche
ms.openlocfilehash: ae3535e322c4d06505595018669d8bd87171b9a9
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699871"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importieren von höhergestuften SharePoint-Ergebnissen und den wichtigsten Abfragen

> [!IMPORTANT]
> Dieser Artikel bezieht sich auf die Microsoft-Suche im Bing-Verwaltungsportal. Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird Microsoft Search im Bing-Portal entfernt. Wir empfehlen, für die ersten Schritte das Microsoft 365 Admin Center zu verwenden. [Übersicht über Microsoft Search](overview-microsoft-search.md).
    
Um die Abfragen und besten Suchergebnisse von Benutzern zu nutzen, die Sie in SharePoint erstellt haben, enthält Microsoft Search zwei Tools zum Importieren dieser Informationen als vorgeschlagene Lesezeichen: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importieren von in SharePoint höher gestuften Ergebnisabfrage Regeln

Importieren Sie diese Regeln, die zuvor als "beste Suchergebnisse" bezeichnet wurden, als vorgeschlagene Lesezeichen. Um Sie für Ihre Benutzer verfügbar zu machen, veröffentlichen Sie Sie. Die Veröffentlichungszeit variiert je nach der Anzahl der ausgewählten Lesezeichen.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importieren der wichtigsten SharePoint-Abfragen mithilfe von PowerShell

- Laden Sie die wichtigsten Abfragen aus Ihrer SharePoint-Datei herunter. Mit dem PowerShell-Skript werden Sie aufgefordert, Ihre SharePoint-Administratoranmeldeinformationen einzugeben.
    
- Führen Sie eine SharePoint-Suche für jede der häufigsten Abfragen aus, um das oberste Suchergebnis abzurufen.
    
- Fügen Sie dem Administratorportal vorgeschlagene Lesezeichen hinzu.
    
- Ihre wichtigsten SharePoint-Abfragen sind ausgezeichnete Kandidaten für Lesezeichen. Verwenden Sie das PowerShell-Skript, um Sie als vorgeschlagene Lesezeichen zu importieren. Dieses Skript führt die folgenden Schritte aus:
    - Fügt vorgeschlagene Lesezeichen basierend auf SharePoint Top-Abfragen hinzu, um die Microsoft Search Bookmark Coverage zu verbessern. Dieses Skript lädt die häufigsten Abfragen herunter, auf die vom SharePoint-Verwaltungsportal aus zugegriffen werden kann, und lädt diese dann als vorgeschlagene Lesezeichen für einen zu überprüfenden Administrator im Microsoft Search-Verwaltungsportal hoch.
    - Standardmäßig fügt das Skript dem angegebenen Mandanten vorgeschlagene Lesezeichen für alle verfügbaren Monate hinzu. Es ruft Top-Abfragen von einer bestimmten SharePoint-Verwaltungswebsite ab und fügt Sie Microsoft Search als vorgeschlagene Lesezeichen hinzu. Vorgeschlagene Lesezeichen benötigen einen Administrator/Editor, um Sie vor der Veröffentlichung im Administratorportal zu genehmigen. Wenn Sie dieses Skript ausführen, werden Sie zur Eingabe von Anmeldeinformationen aufgefordert, um auf das Microsoft Search-Verwaltungsportal zuzugreifen.
    - Mit dem Skript können zusätzliche Parameter angegeben werden. Sie können beispielsweise dem angegebenen Mandanten vorgeschlagene Lesezeichen für Top N-Abfragen in jedem der verfügbaren Monate hinzufügen.
    - Optional können Sie vorgeschlagene Lesezeichen für einen bestimmten Mandanten für Monate im angegebenen Jahr hinzufügen. Dieser Befehl Ruft Top-Abfragen für den angegebenen Zeitraum von der SharePoint-Verwaltungswebsite ab und fügt Sie Microsoft Search als vorgeschlagene Lesezeichen hinzu.
    - Außerdem gibt es zahlreiche weitere Optionen und Befehlsmodi: Herunterladen von Top-Abfragen aus SharePoint in einen bestimmten Ordner, Ausführen des Skripts im abgesicherten Modus, Ausführen des Skripts im ausführlichen Modus und Debuggen.
    - Laden Sie das Skript [hier](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip)herunter. 

Informationen zu den Anforderungen, Beispielen und verfügbaren Parametern erhalten Sie, indem Sie das Skript herunterladen und die Readme-Datei überprüfen. Nachdem das PowerShell-Skript ausgeführt wurde, sollte ein Administrator oder Editor die vorgeschlagenen Lesezeichen überprüfen und alle erforderlichen Änderungen vornehmen, bevor Sie veröffentlicht werden.