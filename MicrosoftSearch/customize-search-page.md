---
title: Anpassen der Seite "Microsoft-Suche"
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Hinzufügen von Such vertikalen und Anpassen von Suchergebnissen
ms.openlocfilehash: 198e5c85c1544b05cdc622f7b617e8bddbcd6a00
ms.sourcegitcommit: 78dc72e99e148898455e016b4ccb110d16b3d81c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40987676"
---
# <a name="customize-the-search-results-page"></a>Anpassen der Suchergebnisseite

Durch das Erstellen von Such vertikalen und Ergebnistypen können Sie die Suchergebnisse anpassen, die Benutzern angezeigt werden, wenn Sie in [Bing](https://Bing.com)nach [SharePoint](http://sharepoint.com/), [Microsoft Office](https://Office.com)und Microsoft Search suchen. Vertikals erleichtern Benutzern die Suche nach Informationen, für die Sie die Berechtigung erhalten haben. Sie können beispielsweise eine Such Sparte für Marketing Analyse Daten aus Drittanbietersoftware für Ihre Benutzer in der Marketingabteilung erstellen. Sie können auch Ergebnistypen definieren und das Layout für diese Daten anpassen.  

Sie können vertikale und Ergebnistypen auf diesen Ebenen erstellen: 

- **Organisationsebene** – Wenn Sie eine vertikale auf Organisationsebene hinzufügen, wird Sie auf der Suchergebnisseite angezeigt, wenn Benutzer auf Ihrer [SharePoint](http://sharepoint.com/) -Startseite, in [Office](https://Office.com)und in [Bing](https://Bing.com)suchen. 
- **Websiteebene** – Sie möchten beispielsweise Ihren Kundendienstmitarbeitern die Suche nach schwer **wiegenden 1** -Vorfällen direkt von der SharePoint-Website der Abteilung aus gestatten. 

## <a name="whats-a-search-vertical"></a>Was ist eine vertikale Suche?

Oben auf der Microsoft Suchergebnisseite befindet sich eine Zeile mit Registerkarten, die die Such vertikalen sind. Bei einer Such vertikalen werden nur Ergebnisse eines bestimmten Typs oder von bestimmten Inhalten angezeigt. Ein Beispiel sind nur Dateien oder Nachrichten. Standardmäßig zeigt Microsoft Search die vertikalen **alle**, **Personen**, **Dateien**, **Websites**und **Nachrichten**an.  

Sie können Such vertikale hinzufügen, die für Ihre Organisation relevant sind. Diese werden auf der Seite Microsoft-Suchergebnisse in [SharePoint](http://sharepoint.com/), [Office](https://Office.com)und [Bing](https://Bing.com)angezeigt. Sie können beispielsweise eine vertikale für marketingbezogene Inhalte und eine weitere für den Vertrieb erstellen, basierend auf der Art der Informationen, die jede Gruppe erhalten möchte. Sie können vertikale Werte hinzufügen, um Ergebnisse nur aus Inhalten anzuzeigen, die über Connectors indiziert sind.  

**Haftungsausschluss:** Vertikale und Ergebnistypen befinden sich derzeit als Teil der Vorschau der Microsoft Graph-Konnektoren in der Vorschau. Sie können keine vertikale für Inhalte erstellen, die sich in [SharePoint](http://sharepoint.com/) befinden, oder aus Inhalten, die durch den [Dateifreigabe-Konnektor](file-share-connector.md)indiziert sind. Weitere Informationen zur Vorschau finden Sie unter [Connectors Preview](connectors-preview.md). Um an der Vorschau teilzunehmen, müssen Sie zuerst das [Anmeldeformular für Microsoft Graph Connectors Preview](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)einreichen.

## <a name="things-to-consider"></a>Dinge, die Sie beachten sollten...

Bevor Sie beginnen, stellen Sie sicher, dass der Connector indiziert wurde. Je nach Dateigröße kann es bis zu 48 Stunden dauern.

Sie können keine vertikale für Inhalte erstellen, die sich in [SharePoint](http://sharepoint.com/) befinden, oder aus Inhalten, die durch den [Dateifreigabe-Konnektor](file-share-connector.md)indiziert sind. Informationen zum [Indizieren von Inhalten](configure-connector.md).

Auf einer hohen Ebene gibt es drei Hauptschritte zum Hinzufügen eines vertikalen: 

1. Erstellen Sie den vertikalen. In diesem Schritt definieren Sie den vertikalen Namen, die Inhaltsquelle und den Bereich der zu durchsuchenden Inhalte. 
2. Legen Sie fest, wie die Ergebnisse für diese vertikale aussehen sollen.  
3. Aktivieren Sie die vertikale (anzuzeigende Anzeige) auf der vertikalen Listenseite.   

## <a name="step-1-create-the-search-vertical"></a>Schritt 1: Erstellen der vertikalen Suche

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte zum Definieren des vertikalen namens, der Inhaltsquelle und des Bereichs des Inhalts geleitet, der durchsucht werden soll. Die vertikale wird im deaktivierten Zustand erstellt. Die vertikale wird später aktiviert.

Sie können eine begrenzte Menge von [KQL (Keyword Query Language)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) verwenden, um den Bereich einzuschränken, und auf der Seite werden die verfügbaren Eigenschaften aufgelistet. Wir empfehlen die Verwendung von freien Text-Schlüsselwörtern und Eigenschafteneinschränkungen mit booleschen Operatoren zum Erstellen der KQL. 

### <a name="create-a-vertical-at-the-organization-level"></a>Erstellen eines vertikalen auf Organisationsebene

Führen Sie die folgenden Schritte aus, um die vertikale auf der Microsoft-Suche in [SharePoint](http://sharepoint.com/) Home, [Office](https://Office.com)oder [Bing](https://Bing.com)zu erstellen:

1. Wechseln Sie im Microsoft [365 Admin Center](https://admin.microsoft.com)zu **Einstellungen** > **Microsoft Search** > **Verticals**.
1. Wählen Sie **Add** to Get Started aus.  

### <a name="create-a-vertical-at-the-site-level"></a>Erstellen eines vertikalen auf Websiteebene

1. Wechseln Sie auf der [SharePoint](http://sharepoint.com/) -Website, auf der Sie die vertikale erstellen möchten, zu **Einstellungen**.
1. Wählen Sie **Website Informationen** aus, und zeigen Sie dann **Alle Websiteeinstellungen**an.
1. Suchen Sie nach dem Abschnitt **Microsoft-Suche** , und wählen Sie dann **Microsoft-Suche für diese Websitesammlung konfigurieren**aus.
1. Wechseln Sie im Navigationsbereich zu **benutzerdefiniertes Erlebnis**, und wählen Sie dann die Registerkarte **vertikal** aus.
1. Um eine vertikale hinzuzufügen, wählen Sie **Hinzufügen**aus. <br>
ODER <br>Um eine vertikale zu bearbeiten, wählen Sie Sie in der Liste aus.

Beachten Sie, dass vertikale im deaktivierten Zustand erstellt werden. Sie müssen Sie dennoch aktivieren, damit Benutzer die vertikalen anzeigen können.

## <a name="step-2-create-the-result-types"></a>Schritt 2: Erstellen der Ergebnistypen

Sie können definieren, wie die Ergebnisse in der vertikalen angezeigt werden, indem Sie das Layout mithilfe von Ergebnistypen entwerfen. Das Ergebnis Layout ermöglicht es Ihnen, wichtige Informationen direkt in den Suchergebnissen anzuzeigen, damit Benutzer nicht jedes Ergebnis auswählen müssen, um zu sehen, ob Sie gefunden haben, wonach Sie suchen.

Ein Ergebnistyp einer Suche ist eine Regel, die bewirkt, dass unterschiedliche Arten von Suchergebnissen auf verschiedene Weisen angezeigt werden. Ein Ergebnistyp hat folgende Bestandteile:

- **Eine oder mehrere Bedingungen** zum Vergleichen der einzelnen Suchergebnisse, beispielsweise die Inhaltsquelle des Suchergebnisses.  
- Ein **Ergebnis Layout** , das für Suchergebnisse verwendet wird, die die Bedingungen erfüllen. Das Ergebnis Layout steuert die Art und Weise, in der alle Ergebnisse, die die Bedingungen erfüllen, auf einer Suchergebnisseite angezeigt werden und sich Verhalten.

**Sie müssen mindestens einen Ergebnistyp erstellen, damit die Ergebnisse in der vertikalen angezeigt werden.** Sie können mehrere Ergebnistypen für jede vertikale erstellen, mit der Sie unterschiedliche Layouts für verschiedene Ergebnistypen verwenden können. Beispielsweise können Sie die Vorfälle von **Severity 1** anpassen, um mehr prominente Farben und eine größere Schriftart im Vergleich zu **Schweregrad 3** Vorfälle zu haben. 

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte zum Definieren des Namens, der Inhaltsquelle und der Bedingungen für den Ergebnistyp geführt. Sie können die Priorität des Ergebnistyps in der Listenansicht definieren. 
  
### <a name="create-a-result-type-at-the-organization-level"></a>Erstellen eines Ergebnistyps auf Organisationsebene

1. Wechseln Sie im [Admin Center](https://admin.microsoft.com)zu **Einstellung** > **Microsoft Search**, und wählen Sie dann **Ergebnistyp**aus.
1. Zum Hinzufügen eines **Ergebnistyps**wählen Sie **Hinzufügen**aus. Zum Bearbeiten eines Ergebnistyps wählen Sie den Ergebnistyp in der entsprechenden Liste aus.
 
### <a name="create-a-results-type-at-the-site-level"></a>Erstellen eines Ergebnistyps auf Websiteebene

1. Wechseln Sie auf der [SharePoint](http://sharepoint.com/) -Website, auf der Sie den Ergebnistyp erstellen möchten, zu **Einstellungen**.
1. Wählen Sie **Website Informationen** aus, und zeigen Sie dann **Alle Websiteeinstellungen**an. 
1. Suchen Sie nach dem Abschnitt Microsoft-Suche, und wählen Sie dann **Microsoft-Suche für diese Websitesammlung konfigurieren**aus.
1. Wechseln Sie im Navigationsbereich zu **benutzerdefiniertes Verhalten**, und wählen Sie dann Registerkarte **Ergebnistyp** aus.
1. Zum Hinzufügen eines Ergebnistyps wählen Sie **Hinzufügen**aus. <br> ODER <br>Zum Bearbeiten eines Ergebnistyps wählen Sie den Ergebnistyp in der Liste aus.

### <a name="view-the-vertical-after-enabling"></a>Anzeigen der vertikalen nach Aktivierung

Nachdem Sie die vertikale aktiviert haben, kann es eine Weile dauern, bis Sie Sie anzeigen können.
Wenn Sie nicht warten möchten, nachdem Sie es aktiviert haben, können Sie **cacheClear = true** an die URL in [SharePoint](http://sharepoint.com/) und [Office](https://Office.com) anfügen, um die vertikale sofort anzuzeigen.

## <a name="troubleshooting"></a>Problembehandlung

Im folgenden finden Sie eine Liste mit häufig auftretenden Problemen und Aktionen zur Behebung dieser Probleme.


|Fehler  |Aktion  |
|---------|---------|
|Ich sehe, dass ein Fehler auf der vertikalen *etwas falsch gelaufen* ist. |   Zum Abschließen des Setups sind sowohl vertikale als auch Ergebnistypen erforderlich. Stellen Sie sicher, dass Sie beide für dieselbe Inhaltsquelle erstellt haben.      |
|Warum wird mein Ergebnis Layout nicht angezeigt, obwohl ich ein erstellt habe? | Es dauert ein paar Minuten, bis die Ergebnistypen verwendet werden, da diese Einstellungen im allgemeinen zwischengespeichert werden. Warten Sie einige Minuten, und versuchen Sie es erneut.        |
|Auf der Seite "vertikal" oder "Ergebnistyp" werden keine Inhaltsquellen angezeigt.     |      Stellen Sie sicher, dass Sie Connectors und indizierte Daten konfiguriert haben.   |



## <a name="next-steps"></a>Nächste Schritte
[Schritt 3: Anpassen des Ergebnis Layouts](customize-results-layout.md)
