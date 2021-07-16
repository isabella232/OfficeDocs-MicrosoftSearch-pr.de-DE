---
title: Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite
ms.author: dawholl
author: dawholl
manager: kellis
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
description: Rufen Sie relevante Suchvorschläge ab, und suchen Sie schneller nach Arbeitsergebnissen, indem Sie Ihrer Intranetwebsite oder -seite ein Microsoft Search Suchfeld hinzufügen.
ms.openlocfilehash: 7d9ca4be8d3be27a7549ffb940d6dc55b3763baf
ms.sourcegitcommit: 38a0f09596c2bca0e12bf4cada7b4c64fd4c48e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53449061"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Hinzufügen eines Suchfelds zu Ihrer Intranetwebsite

Um Ihren Benutzern einfachen Zugriff auf Ergebnisse aus Ihrer Organisation zu ermöglichen, fügen Sie einer Intranetwebsite oder -seite in Bing Suchfeld eine Microsoft Search hinzu. Dies sind einige der Vorteile:

- Ein Suchfeld in Ihrem SharePoint oder Intranetportal bietet einen vertrauten, vertrauenswürdigen Einstiegspunkt, um mit der Suche zu beginnen.
- Unterstützt alle gängigen Webbrowser, einschließlich Google Chrome und Microsoft Edge
- Es werden nur Suchvorschläge aus Ihrer Organisation angezeigt, Webvorschläge werden nie eingeschlossen.
- Führt Benutzer zu einem Microsoft Search auf Bing Seite mit Arbeitsergebnissen, die Anzeigen und Webergebnisse ausschließt
- Sie steuern die Darstellung und das Verhalten des Suchfelds, einschließlich der Möglichkeit, Benutzer auf einer Standard-Vertikal oder einer benutzerdefinierten Vertikalen zu landen, die Sie erstellt haben.
  
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
        dropShadow: true,                       // default: false
        iconColor: "#067FA6",                   // default: #067FA6
        title: "Search box",                    // default: "Search box"
        vertical: "Person-people",              // default: not specified, search box directs to the All vertical on the WORK results page
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="direct-users-to-a-default-or-custom-vertical"></a>Weiterleiten von Benutzern zu einer Standard- oder benutzerdefinierten vertikalen Komponente

Um eine einfache Integration zwischen Ihren Branchen-Apps oder Intranetwebsites und Ihren Arbeitsergebnissen zu ermöglichen, können Sie auch das Suchfeld anpassen, indem Sie eine Standard- oder benutzerdefinierte Vertikale angeben, auf der Benutzer landen sollten, wenn sie auf einen Suchvorschlag klicken.

Verwenden Sie die vertikale Option in bfbSearchBoxConfig, um die gewünschte Vertikale zu definieren. Wenn Benutzer beispielsweise immer auf der vertikalen Website(einer der Standard-Vertikalen) landen sollen, verwenden Sie den Wert "Websitewebsites".

:::image type="content" alt-text="Screenshot der Seite &quot;Arbeitsergebnisse&quot; auf Microsoft Search in Bing mit den vertikalen Ergebnissen und der URL der Websites." source="media/sites-vertical-esb.png" lightbox="media/sites-vertical-esb.png":::

Verwenden Sie für benutzerdefinierte Vertikale den Hash am Ende der URL. Sie finden diese Werte, indem Sie auf der Arbeitsseite auf Bing suchen, auf eine vertikale Beschriftung klicken und den Wert nach dem Nummernzeichen (#) kopieren.

:::image type="content" alt-text="Screenshot der Seite &quot;Arbeitsergebnisse&quot; auf Microsoft Search in Bing, auf der die vertikalen Ergebnisse und die URL einer benutzerdefinierten Präsentation angezeigt werden." source="media/custom-vertical-esb.png" lightbox="media/custom-vertical-esb.png":::

## <a name="use-an-iframe-to-embed-a-search-box"></a>Verwenden eines iFrame zum Einbetten eines Suchfelds

Wenn das Einbetten eines Skripts keine Option für die Website ist, verwenden Sie einen iFrame, der dem Suchfeld hinzugefügt wird. Sie können das Suchfeld nicht anpassen.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```

## <a name="inprivate-mode-and-conditional-access"></a>InPrivate-Modus und bedingter Zugriff

Ein eingebettetes Suchfeld wird deaktiviert, wenn die Seite oder Website in einem InPrivate-Fenster geöffnet wird. Darüber hinaus unterstützt Bing.com die AAD-Anmeldung bei Verwendung des InPrivate-Modus nicht, wenn azure AD conditional Access in Microsoft Edge unterstützt wird. Weitere Informationen zum bedingten Zugriff in Edge finden Sie unter [Microsoft Edge und bedingter Zugriff.](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge) 
