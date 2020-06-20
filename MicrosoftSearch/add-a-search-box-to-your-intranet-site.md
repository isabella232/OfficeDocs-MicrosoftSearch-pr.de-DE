---
title: Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: Erhalten Sie relevante Suchvorschläge und Arbeitsergebnisser schneller, indem Sie ein Microsoft Search-Suchfeld zu einer Intranetwebsite oder -seite hinzufügen.
ms.openlocfilehash: af12ce4d17c2695e196f8e4d79ccd515f002f238
ms.sourcegitcommit: 92206ea179ec00b22496f6fd2866b5406449cf40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44798225"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite

Um Ihren Benutzern einfachen Zugriff auf Ergebnisse aus Ihrer Organisation zu ermöglichen, fügen Sie eine Microsoft Search in Bing Suchfeld zu jeder Intranetsite oder Website hinzu. Dies sind einige der Vorteile:

- Ein Suchfeld auf Ihrem SharePoint-oder Intranet-Portal stellt einen vertrauten, vertrauenswürdigen Einstiegspunkt zum Starten der Suche bereit.
- Unterstützt alle wichtigen Webbrowser, einschließlich Google Chrome und Microsoft Edge
- Nur Suchvorschläge aus Ihrer Organisation werden angezeigt, Webvorschläge werden nie berücksichtigt.
- Führt Benutzer zu einer Microsoft-Suche auf der Seite Bing work results, die anzeigen und Webergebnisse ausschließt.
- Sie steuern die Darstellung und das Verhalten des Such Felds.
  
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

## <a name="customize-the-appearance-of-the-search-box"></a>Anpassen des Erscheinungsbilds des Suchfelds 

Sie können eine Vielzahl von Konfigurationsoptionen verwenden, um das Suchfeld an den Stil Ihres Intranets anzupassen. Kombinieren Sie je nach Bedarf verschiedene Optionen.

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: true
        iconColor: "#067FA6",                   // default: #067FA6
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a>Verwenden eines iFrame zum Einbetten eines Suchfelds

Wenn das Einbetten eines Skripts keine Option für die Website ist, verwenden Sie einen iFrame, der dem Suchfeld hinzugefügt wird. Sie können das Erscheinungsbilds des Suchfelds nicht anpassen.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
