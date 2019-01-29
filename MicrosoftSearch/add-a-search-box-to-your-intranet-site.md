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
description: Möchten Sie relevante Suchvorschläge erhalten, und suchen Sie Arbeit Ergebnisse schneller, indem Sie ein Suchfeld Microsoft Search zu einer Intranet-Website oder Seite hinzufügen.
ms.openlocfilehash: 699cfd9c411c9b86f3a2f8742c425aaedef1ebc5
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612417"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite

Fügen Sie ein Suchfeld Microsoft Search für schnellen Zugriff auf relevante Suchvorschläge und Arbeit Ergebnisse an einem beliebigen Intranet-Website oder Seite.
  
## <a name="add-a-search-box-to-an-intranet-page"></a>Fügen Sie ein Suchfeld hinzu, um eine Seite im intranet

Sie müssen auf der Seite zwei Elemente hinzugefügt: ein Container für das Suchfeld und das Skript, das sie aktiviert.
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

Auf einer SharePoint-Website klassische ein Skript-Editor-Webpart hinzufügen, und das Skript einlassen.
  
## <a name="enable-the-search-box-for-mobile"></a>Aktivieren Sie das Suchfeld für mobile

Fügen Sie für Intranetwebsites oder Seiten mobilen Benutzern zur Verfügung stehen, IsMobile: true, wenn das Objekt Settings:
  
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

## <a name="put-focus-on-the-search-box-by-default"></a>Verschieben Sie den Fokus auf das Suchfeld in der Standardeinstellung

Damit Benutzer schneller, suchen Sie beim Laden der Seite oder einer Website durch Hinzufügen der Fokus den Cursor im Suchfeld platzieren: true, wenn das Objekt Settings:
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a>Verwenden eines IFRAMEs ein Suchfeld einbetten

Wenn eine Option für die Website nicht Einbetten eines Skripts ist, verwenden Sie einen iFrame Suchfeld hinzufügen:
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
