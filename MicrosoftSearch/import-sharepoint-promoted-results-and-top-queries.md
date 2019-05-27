---
title: Importieren von höhergestuften SharePoint-Ergebnissen und wichtigsten Abfragen
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/8/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
description: Verwenden Sie Suchabfragen aus SharePoint zum Erstellen von Arbeitsergebnissen für Microsoft Search.
ms.openlocfilehash: 6e55e2000792bdb576a18a0efeb353dc3ea13605
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968451"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importieren von höhergestuften SharePoint-Ergebnissen und wichtigsten Abfragen

> [!IMPORTANT]
> Die Einstellungen für Microsoft Search in Bing sind jetzt im Microsoft 365 Admin Center verfügbar. Beginnen Sie, indem Sie in Ihrem Admin Center[Suchadministratoren zuweisen](https://docs.microsoft.com/de-DE/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor).
    
Um Benutzerabfragen und von Ihnen in SharePoint erstellte beste Suchergebnisse zu nutzen, schließt Microsoft Search zwei Tools zum Importieren dieser Informationen als vorgeschlagene Lesezeichen mit ein:  
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importieren von Abfrageregeln zu höhergestuften SharePoint-Ergebnissen

Importieren Sie diese Regeln, die früher als „Beste Suchergebnisse“ bezeichnet wurden, als vorgeschlagene Lesezeichen. Wenn Sie sie Ihren Benutzern zur Verfügung stellen möchten, veröffentlichen Sie sie. Die Veröffentlichungszeit variiert je nach der Anzahl der von Ihnen ausgewählten Lesezeichen.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importieren der wichtigsten SharePoint-Abfragen mithilfe von PowerShell

- Laden Sie die wichtigsten Abfragen aus Ihrem SharePoint herunter. Das PowerShell-Skript fordert Sie zur Eingabe Ihrer SharePoint-Administrator-Anmeldeinformationen auf.
    
- Führen Sie eine SharePoint-Suche nach jeder der wichtigsten Abfragen aus, um das wichtigste Suchergebnis zu erhalten.
    
- Fügen Sie dem Verwaltungsportal vorgeschlagene Lesezeichen hinzu.
    
- Ihre wichtigsten SharePoint-Abfragen sind für Lesezeichen hervorragend geeignet. Mithilfe des PowerShell-Skripts können Sie sie als vorgeschlagene Lesezeichen importieren. Dieses Skript ermöglicht Folgendes:
    
Wenn Sie Informationen zu den Anforderungen, Beispielen und verfügbaren Parametern benötigen, laden Sie das Skript herunter, und lesen Sie die Infodatei. Nach der Ausführung des PowerShell-Skripts sollte ein Administrator oder Editor die vorgeschlagenen Lesezeichen überprüfen und alle erforderlichen Änderungen vornehmen, bevor sie veröffentlicht werden.

  

