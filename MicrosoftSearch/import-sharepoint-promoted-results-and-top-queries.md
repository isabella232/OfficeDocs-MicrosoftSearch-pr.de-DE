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
description: Verwenden von Suchabfragen aus SharePoint zum Erstellen von Arbeitsergebnissen für Microsoft Search
ms.openlocfilehash: cfd5fafd0529f537a55e436ef078800a4b9714177e04c63e65e968f16fcf322e
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533824"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importieren von höhergestuften SharePoint-Ergebnissen und den wichtigsten Abfragen

> [!IMPORTANT]
> Dieser Artikel bezieht sich auf die Microsoft Search im Bing-Verwaltungsportal. Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird Microsoft Search im Bing-Portal entfernt. Wir empfehlen, für die ersten Schritte das Microsoft 365 Admin Center zu verwenden. [Übersicht über Microsoft Search](overview-microsoft-search.md).
    
Um die Abfragen von Benutzern und die besten Suchergebnisse zu nutzen, die Sie in SharePoint erstellt haben, enthält Microsoft Search zwei Tools zum Importieren dieser Informationen als vorgeschlagene Lesezeichen: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importieren SharePoint höhergestufter Ergebnisabfrageregeln

Importieren Sie diese Regeln, die zuvor als "beste Suchergebnisse" bezeichnet wurden, als vorgeschlagene Lesezeichen. Um sie Ihren Benutzern zur Verfügung zu stellen, veröffentlichen Sie sie. Die Veröffentlichungszeit variiert je nach Anzahl der von Ihnen ausgewählten Lesezeichen.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importieren der SharePoint Abfragen mithilfe von PowerShell

- Laden Sie die wichtigsten Abfragen aus Ihrem SharePoint herunter. Das PowerShell-Skript fordert Sie zur Eingabe Ihrer SharePoint Administratoranmeldeinformationen auf.
    
- Führen Sie eine SharePoint Suche nach jeder der obersten Abfragen aus, um das oberste Suchergebnis abzurufen.
    
- Fügen Sie dem Verwaltungsportal vorgeschlagene Lesezeichen hinzu.
    
- Ihre wichtigsten SharePoint Abfragen sind hervorragende Kandidaten für Lesezeichen. Verwenden Sie das PowerShell-Skript, um sie als vorgeschlagene Lesezeichen zu importieren. Dieses Skript führt die folgenden Aufgaben aus:
    - Fügt vorgeschlagene Lesezeichen basierend auf SharePoint wichtigsten Abfragen hinzu, um Microsoft Search Lesezeichenabdeckung zu verbessern. Dieses Skript lädt die wichtigsten Abfragen herunter, auf die von SharePoint Verwaltungsportal zugegriffen werden kann, und lädt sie dann als vorgeschlagene Lesezeichen hoch, die ein Administrator im Microsoft Search Admin-Portal überprüfen kann.
    - Standardmäßig fügt das Skript einem Mandanten für alle verfügbaren Monate Lesezeichen hinzu. Es ruft die wichtigsten Abfragen von einer bestimmten SharePoint Administratorwebsite ab und fügt sie Microsoft Search als vorgeschlagene Lesezeichen hinzu. Vorgeschlagene Lesezeichen benötigen einen Administrator/Editor, um sie im Verwaltungsportal zu genehmigen, bevor sie veröffentlicht werden. Wenn Sie dieses Skript ausführen, werden Sie zur Eingabe von Anmeldeinformationen aufgefordert, um auf das Microsoft Search Verwaltungsportal zuzugreifen.
    - Mit dem Skript können zusätzliche Parameter angegeben werden. Sie können z. B. vorgeschlagenen Lesezeichen zu einem bestimmten Mandanten für die wichtigsten N-Abfragen in jedem der verfügbaren Monate hinzufügen.
    - Optional können Sie einem Mandanten für Monate im angegebenen Jahr Lesezeichen vorschlagen. Dieser Befehl ruft die wichtigsten Abfragen für den angegebenen Zeitraum von SharePoint Administratorwebsite ab und fügt sie Microsoft Search als vorgeschlagene Lesezeichen hinzu.
    - Außerdem gibt es zahlreiche weitere Optionen und Befehlsmodi: Laden Sie die wichtigsten Abfragen von SharePoint in einen angegebenen Ordner herunter, führen Sie das Skript im Tresor Modus aus, führen Sie das Skript im ausführlichen Modus und einen Debugmodus aus.
    - Laden Sie das Skript [hier](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip)herunter. 

Um Informationen zu Anforderungen, Beispielen und verfügbaren Parametern zu erhalten, laden Sie das Skript herunter, und überprüfen Sie die README-Datei. Nachdem das PowerShell-Skript ausgeführt wurde, sollte ein Administrator oder Editor die vorgeschlagenen Lesezeichen überprüfen und alle erforderlichen Änderungen vornehmen, bevor sie veröffentlicht werden.