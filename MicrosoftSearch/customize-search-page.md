---
title: Anpassen der Seite "Microsoft-Suche"
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Hinzufügen von Such vertikalen und Anpassen von Suchergebnissen
ms.openlocfilehash: 8522a6daf05b718ee6a066272da181be6e95905e
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367487"
---
# <a name="customize-the-search-results-page"></a>Anpassen der Suchergebnisseite

Sie können Such vertikalen und Ergebnistypen erstellen, um die Suchergebnisse anzupassen, die Benutzern bei der Suche in Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com)und Microsoft Search in [Bing](https://bing.com)angezeigt werden. Vertikals erleichtern Benutzern die Suche nach Informationen, für die Sie die Berechtigung zum Anzeigen haben. Sie können beispielsweise eine Such Sparte für Marketing Analyse Daten aus Drittanbietersoftware für Ihre Benutzer in der Marketingabteilung erstellen. Sie können auch Ergebnistypen definieren und das Layout für diese Daten anpassen.  

Sie können vertikale und Ergebnistypen auf diesen Ebenen erstellen:

- **Organisationsebene** – Wenn Sie eine vertikale auf Organisationsebene hinzufügen, wird Sie auf der Suchergebnisseite angezeigt, wenn Benutzer auf Ihrer [SharePoint](https://sharepoint.com/) -Startseite, in [Office](https://office.com)oder in [Bing](https://bing.com)suchen.
- **Websiteebene** – Sie möchten beispielsweise Ihren Kundendienstmitarbeitern die Suche nach *Dringlichkeits* Vorfällen direkt von der SharePoint-Website Ihrer Abteilung ermöglichen.

## <a name="search-verticals-explained"></a>Erläuterte Such vertikalen

Oben auf der Microsoft-Suchergebnisseite gibt es eine Reihe von Registerkarten. Dies sind die Such vertikalen. Bei einer Such vertikalen werden nur Ergebnisse eines bestimmten Typs oder von bestimmten Inhalten angezeigt. Beispiele sind **Dateien** oder **Nachrichten**. Standardmäßig zeigt Microsoft Search die vertikalen **alle**, **Personen**, **Dateien**, **Websites** und **Nachrichten** an.  

Sie können Such vertikale hinzufügen, die für Ihre Organisation relevant sind. Diese werden auf der Seite Microsoft-Suchergebnisse in [SharePoint](https://sharepoint.com/), [Office](https://Office.com)und [Bing](https://bing.com)angezeigt. Sie können beispielsweise eine vertikale für marketingbezogene Inhalte und eine weitere für den Vertrieb erstellen, basierend auf dem Typ der Informationen, die jede Gruppe benötigt. Sie können vertikale Werte hinzufügen, um Ergebnisse nur aus Inhalten anzuzeigen, die über Connectors indiziert sind.  

### <a name="multiple-connections-in-a-vertical"></a>Mehrere Verbindungen in einer vertikalen

Eine Such Sparte kann nun zu Ergebnissen aus mehreren Connector-Quellen führen. Dies ermöglicht eine größere Flexibilität beim Entwerfen Ihrer Suchergebnisseite. Mit der vorhandenen administrativen Erfahrung des vertikalen Setups können Sie mehrere Verbindungen im Schritt "Inhaltsquelle" auswählen.
Wenn Sie genau so viele semantische Bezeichnungen wie möglich benennen, wird diese Erfahrung verbessert. Sie können semantische Bezeichnungen nach Schema Definition und Einnahme hinzufügen.

[Hier](#configure-connector-step-5-assign-property-labels) finden Sie weitere Informationen zum Erstellen und Verwalten von semantischen Bezeichnungen.

### <a name="things-you-should-know"></a>Dinge, die Sie kennen sollten

1. Eine Verbindung kann nur unter einer vertikalen als Inhaltsquelle hinzugefügt werden. Die Wiederverwendung von Verbindungen unter mehreren vertikalen ist nicht zulässig.
2. Wenn Sie eine Abfrage für eine Such Sparte einrichten müssen, bei der mehrere Verbindungs Quellen hinzugefügt wurden, sollten allgemeine Quelleigenschaften verwendet werden, um eine solche Abfrage zu erstellen.

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte

Bevor Sie beginnen, stellen Sie sicher, dass der Connector indiziert wurde. Je nach Dateigröße kann dies bis zu 48 Stunden dauern.

Sie können keinen vertikalen Inhalt für Inhalte erstellen, die sich in [SharePoint](https://sharepoint.com/)befinden.

Es gibt drei grundlegende Schritte zum Hinzufügen eines vertikalen:

1. Erstellen Sie den vertikalen. In diesem Schritt definieren Sie den vertikalen Namen, die Inhaltsquelle und den Bereich der zu durchsuchenden Inhalte.
2. Legen Sie fest, wie die Ergebnisse für diese vertikale aussehen sollen.  
3. Aktivieren Sie die vertikale (anzuzeigende Anzeige) auf der vertikalen Listenseite.

## <a name="step-1-create-the-search-vertical"></a>Schritt 1: Erstellen der vertikalen Suche

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte zum Definieren des vertikalen namens, der Inhaltsquelle und des Umfangs der zu durchsuchenden Inhalte geführt. Die vertikale wird im deaktivierten Zustand erstellt. Sie werden Sie später aktivieren.

Sie können eine begrenzte Menge von [KQL (Keyword Query Language)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) verwenden, um den Bereich einzuschränken. Auf dieser Seite werden die verfügbaren Eigenschaften aufgelistet. Es wird empfohlen, FREETEXT-Schlüsselwörter und Eigenschafteneinschränkungen mit booleschen Operatoren zum Erstellen des KQL zu verwenden.

### <a name="create-a-vertical-at-the-organization-level"></a>Erstellen eines vertikalen auf Organisationsebene

Führen Sie die folgenden Schritte aus, um die vertikale auf der Microsoft-Suche in [SharePoint](https://sharepoint.com/) Home, [Office](https://office.com)oder [Bing](https://bing.com)zu erstellen:

1. Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**vertikal**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Wählen Sie **Add** to Get Started aus.  

### <a name="create-a-vertical-at-the-site-level"></a>Erstellen eines vertikalen auf Websiteebene

1. Wechseln Sie auf der [SharePoint](https://sharepoint.com/) -Website, auf der Sie die vertikale möchten, zu **Einstellungen**.
2. Wählen Sie **Website Informationen** aus, und zeigen Sie dann **Alle Websiteeinstellungen** an.
3. Suchen Sie nach dem Abschnitt **Microsoft-Suche** , und wählen Sie dann **Microsoft-Suche für diese Websitesammlung konfigurieren** aus.
4. Wechseln Sie im Navigationsbereich zu **benutzerdefiniertes Erlebnis**, und wählen Sie dann die Registerkarte **vertikal** aus.
5. Um eine vertikale hinzuzufügen, wählen Sie **Hinzufügen** aus.
  Um eine vertikale zu bearbeiten, wählen Sie Sie aus der Liste aus.

Beachten Sie, dass vertikale im deaktivierten Zustand erstellt werden. Sie müssen aktiviert sein, damit Sie von Benutzern angezeigt werden können.

## <a name="step-2-create-the-result-types"></a>Schritt 2: Erstellen der Ergebnistypen

Sie können definieren, wie die Ergebnisse in der vertikalen angezeigt werden, indem Sie das Layout mithilfe von Ergebnistypen entwerfen. Das Ergebnis Layout ermöglicht es Ihnen, wichtige Informationen direkt in den Suchergebnissen anzuzeigen, sodass Benutzer nicht jedes Ergebnis auswählen müssen, um zu sehen, ob Sie die gewünschten Ergebnisse gefunden haben.

### <a name="default-search-result-layout"></a>Standardmäßiges Suchergebnislayout

Für Connector-Inhalte wird ein Standardmäßiges Suchergebnislayout angezeigt, wenn **Beschriftungen** und **Inhalts** Eigenschaften den Quelleigenschaften zum Zeitpunkt der Konfiguration des Connectors ordnungsgemäß zugeordnet wurden. Der Beschriftungs **Titel** ist die wichtigste Bezeichnung. Es wird **dringend empfohlen** , dass Sie über eine Eigenschaft verfügen, die dieser Bezeichnung zugewiesen ist, um das standardmäßige Suchergebnislayout zu verwenden.

### <a name="create-your-own-result-type"></a>Erstellen eines eigenen Ergebnistyps

Sie können beschließen, Ihr eigenes Suchergebnislayout zu erstellen und das standardmäßige Suchergebnislayout durch Erstellen eines **Ergebnistyps** außer Kraft zu setzen. Ein Ergebnistyp einer Suche ist eine Regel, die bewirkt, dass unterschiedliche Arten von Suchergebnissen auf verschiedene Weisen angezeigt werden. Ein Ergebnistyp hat folgende Bestandteile:

- **Eine oder mehrere Bedingungen** zum Vergleichen der einzelnen Suchergebnisse, beispielsweise die Inhaltsquelle des Suchergebnisses.  
- Ein **Ergebnis Layout** , das für Suchergebnisse verwendet wird, die die Bedingungen erfüllen. Das Ergebnis Layout steuert, wie alle Ergebnisse, die die Bedingungen erfüllen, auf einer Suchergebnisseite angezeigt werden und sich Verhalten.

**Wenn das standardmäßige Suchergebnislayout nicht ordnungsgemäß zugeordnet wird, muss yyou mindestens einen Ergebnistyp erstellen, damit die Ergebnisse im vertikalen Format angezeigt werden.** Sie können mehrere Ergebnistypen für jede vertikale erstellen, mit der Sie unterschiedliche Layouts für verschiedene Ergebnistypen verwenden können. Beispielsweise können Sie die Vorfälle von *Severity 1* anpassen, um mehr prominente Farben und eine größere Schriftart im Vergleich zu *Schweregrad 3* Vorfälle zu haben.

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte zum Definieren des Namens, der Inhaltsquelle und der Bedingungen für den Ergebnistyp geführt. Sie können die Priorität des Ergebnistyps in der Listenansicht definieren.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Erstellen eines Ergebnistyps auf Organisationsebene

1. Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Ergebnistypen**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).
2. Zum Hinzufügen eines **Ergebnistyps** wählen Sie **Hinzufügen** aus. Zum Bearbeiten eines Ergebnistyps wählen Sie den Ergebnistyp in der entsprechenden Liste aus.

### <a name="create-a-results-type-at-the-site-level"></a>Erstellen eines Ergebnistyps auf Websiteebene

1. Wechseln Sie auf der [SharePoint](https://sharepoint.com/) -Website, auf der Sie den Ergebnistyp erstellen möchten, zu **Einstellungen**.
2. Wählen Sie **Website Informationen** aus, und zeigen Sie dann **Alle Websiteeinstellungen** an.
3. Suchen Sie nach dem Abschnitt Microsoft-Suche, und wählen Sie dann **Microsoft-Suche für diese Websitesammlung konfigurieren** aus.
4. Wechseln Sie im Navigationsbereich zu **benutzerdefiniertes Verhalten**, und wählen Sie die Registerkarte **Ergebnistyp** aus.
5. Zum Hinzufügen eines Ergebnistyps wählen Sie **Hinzufügen** aus.  Oder wählen Sie zum Bearbeiten eines Ergebnistyps den Ergebnistyp in der Liste aus.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>Schritt 3: Anzeigen der vertikalen nach der Aktivierung

Nachdem Sie die vertikale aktiviert haben, kann es eine Weile dauern, bis Sie Sie anzeigen können. Wenn Sie nicht nach dem Aktivieren warten möchten, können Sie **cacheClear = true** an die URL in [SharePoint](https://sharepoint.com/) und [Office](https://office.com) anfügen, um die vertikale sofort anzuzeigen.

## <a name="troubleshooting"></a>Problembehandlung

Hier finden Sie eine Liste mit häufig auftretenden Problemen und Aktionen, die Sie beheben können.

|Error  |Aktion  |
|---------|---------|
| Ich sehe eine Fehlermeldung "something went wrong" auf der vertikalen. | Sowohl die vertikalen als auch die Ergebnistypen sind erforderlich, um das Setup abzuschließen. Stellen Sie sicher, dass Sie beide für dieselbe Inhaltsquelle erstellt haben. |
| Das Ergebnis Layout wird nicht angezeigt, obwohl ich ein erstellt habe. | Es dauert ein paar Minuten, da diese Einstellungen im allgemeinen zwischengespeichert werden. Warten Sie einige Minuten, und versuchen Sie es erneut.        |
| Auf der Seite "vertikal" oder "Ergebnistyp" werden keine Inhaltsquellen angezeigt. | Stellen Sie sicher, dass Sie Connectors und indizierte Daten konfiguriert haben.   |

## <a name="next-steps"></a>Nächste Schritte

[Schritt 3: Anpassen des Ergebnis Layouts](customize-results-layout.md)
