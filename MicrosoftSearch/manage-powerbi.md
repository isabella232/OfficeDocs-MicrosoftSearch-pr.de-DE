---
title: Verwalten von Power BI-Antworten
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Verwalten, wie Power BI-Berichte und -Daten in Suchergebnissen angezeigt werden
ms.openlocfilehash: 3d67f79cce2392f949541690879ffb9202d79060
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031440"
---
# <a name="manage-power-bi-answers"></a>Verwalten von Power BI-Antworten

Damit Ihre Benutzer die Daten und Analysen leichter finden können, die sie benötigen, um fundierte Entscheidungen zu treffen, hat Microsoft Search Unterstützung für Power BI-Dashboards und -Berichte hinzugefügt. Hier sind einige der Vorteile der Power BI-Suche:

* **Einfach zu verwenden:** Diese out-of-box-Sucherfahrung hilft Benutzern, Power BI-Dashboards und Berichte in Ihrer Organisation einfach und schnell zu finden.
* **Reichhaltigere Inhalte:** Um power BI-Suchergebnisse nützlicher zu machen, enthalten sie wichtige Informationen wie die Art des Inhalts (Dashboard oder Bericht) und das Team oder die Person, die der Benutzer ist.
* **Integrierter Datenschutz:** Power BI-Ergebnisse werden nur für Benutzer angezeigt, die Zugriff auf das Dashboard oder den Bericht haben.
* **Einheitliche Sucherfahrung:** Um ein einheitliches Erlebnis zu erhalten, sind die Power BI-Ergebnisse für alle Sucheingabepunkte konsistent. Unabhängig davon, wo Sie suchen, erhalten Sie dieselben Ergebnisse mit dem gleichen Aussehen und Gefühl.

## <a name="what-users-experience"></a>Benutzererfahrungen

Microsoft Search-Benutzer können Power BI-Ergebnisse finden, indem sie im Windows-Suchfeld, in SharePoint, Office 365 und Bing suchen. Benutzer können mit Abfragen wie den folgenden nach Berichten und Dashboards suchen:

* Power BI über `<topic>`
* Power BI für `<topic>`
* `<topic>` Power BI-Dashboard oder Power BI-Dashboard `<topic>`
* `<topic>` Power BI-Bericht oder Power BI-Bericht `<topic>`
* `<topic>` Power BI-Metriken oder Power BI-Metriken `<topic>`
* `<topic>` Power BI-Scorecard oder Power BI-Scorecard `<topic>`

Ersetzen Sie in den obigen Beispielen durch die gesuchten Informationen, z. B. `<topic>` Vertrieb, Nutzung, Kapazität, 2021, Q1 und mehr, um relevante Ergebnisse von Power BI zu sehen.

:::image type="content" source="media/powerbi-answers/powerbi-serp.png" alt-text="Screenshot einer SERP mit Power BI-Antworten und vertikal" border="true":::

## <a name="turn-power-bi-search-on-or-off"></a>Aktivieren oder Deaktivieren der Power BI-Suche

Power BI-Ergebnisse sind standardmäßig für Ihre Organisation aktiviert. Ihr Power BI-Administrator kann sie jederzeit deaktivieren. Wechseln Sie im Power BI Admin-Portal zu Mandanteneinstellungen, und deaktivieren Sie die Einstellung Globale **Suche für Power BI** verwenden. Weitere Informationen finden Sie [unter Administering Power BI im Admin Portal](/power-bi/admin/service-admin-portal#use-global-search-for-power-bi-preview).

:::image type="content" source="media/powerbi-answers/powerbi-admin.png" alt-text="Screenshot der Einstellung zum Aktivieren oder Deaktivieren von Power BI-Antworten" border="true":::

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F: Ist die Power BI-Suche standardmäßig aktiviert?**

**A:** Ja. Die Power BI-Suche ist für Microsoft Search standardmäßig aktiviert. Der Mandantenadministrator ist nicht zum ersten Mal für dieses Feature erforderlich.

**F: Kann die Power BI-Suche für bestimmte Gruppen oder Benutzer aktiviert oder deaktiviert werden?**

**A:** Derzeit kann sie nur für Ihre gesamte Organisation aktiviert oder deaktiviert werden.

**F: Wenn die Power BI-Suche deaktiviert ist, ist die Power BI-Suchergebnisseite ausgeblendet?**

**A:** Nein. Die Power BI-Suchergebnisseite wird mit einer Meldung angezeigt, in der Benutzer darüber informiert werden, dass sie derzeit nicht für ihre Organisation verfügbar ist.

**F: Wird die Power BI-Suchergebnisseite angezeigt, wenn ich keine Power BI-Lizenz habe?**

**A:** Nein. Wenn ein Suchbenutzer keine Power BI-Lizenz besitzt, wird die Power BI-Suchergebnisseite nicht in den Microsoft-Suchergebnissen angezeigt.

**F: Werden Power BI-Suchergebnisse angezeigt, auf die ich nicht zugreifen kann?**

**A:** Nein. Microsoft Search gibt nur Power BI-Ergebnisse zurück, auf die Sie Zugriff haben.

**F: Kann ich die Power BI-Suchergebnisse anpassen (z. B. den Berichtstyp oder den Berichtsbesitzer)?**

**A:** Derzeit wird das Anpassen der in den Power BI-Suchergebnissen enthaltenen Felder nicht unterstützt.