---
title: Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
description: Erhalten Sie relevante Suchvorschläge und Arbeitsergebnisser schneller, indem Sie ein Microsoft Search-Suchfeld zu einer Intranetwebsite oder -seite hinzufügen.
ms.openlocfilehash: 699cfd9c411c9b86f3a2f8742c425aaedef1ebc5
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612417"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite

Für schnellen Zugriff auf relevante Suchvorschläge und Arbeitsergebnisse, fügen Sie ein Microsoft Search-Suchfeld zu einer beliebigen Intranetwebsite oder -seite hinzu.
  
## <a name="add-a-search-box-to-an-intranet-page"></a>Hinzufügen eines Suchfelds zu einer Intranetseite

Sie müssen der Seite zwei Elemente hinzfügen: ein Container für das Suchfeld und das zugrunde liegende Skript.
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

Fügen Sie auf einer klassischen SharePoint-Website ein Skript-Editor-Webpart hinzu, und platzieren Sie das Skript darin.
  
## <a name="enable-the-search-box-for-mobile"></a>Aktivieren des Suchfelds für mobile Geräte

Fügen Sie für Intranetwebsites oder -seiten, die für mobile Benutzer verfügbar sind, „isMobile: true“ zum Einstellungsobjekt hinzu:
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox", 
        isMobile: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="put-focus-on-the-search-box-by-default"></a>Setzen des Fokus auf das Suchfeld als Standardeinstellung

Damit Benutzer schneller suchen können, platzieren Sie, wenn die Seite oder Website geladen wird, den Cursor im Suchfeld, indem Sie dem Einstellungsobjekt „focus: true“ hinzufügen:
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        focus: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a>Verwenden eines iFrame zum Einbetten eines Suchfelds

Wenn das Einbetten eines Skripts keine Option für die Website ist, verwenden Sie einen iFrame, der dem Suchfeld hinzugefügt wird:
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
