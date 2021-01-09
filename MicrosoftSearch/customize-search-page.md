---
title: Anpassen der Microsoft Search-Seite
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
ms.openlocfilehash: 4896fdb9923c93602acc48c2360039d512e4d72e
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790334"
---
# <a name="customize-the-search-results-page"></a>Anpassen der Suchergebnissetseite

Sie können Such vertikal und Ergebnistypen erstellen, um die Suchergebnisse anzupassen, die Benutzern angezeigt werden, wenn sie in Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com)und Microsoft Search in [Bing suchen.](https://bing.com) Vertikale Daten erleichtern Benutzern die Suche nach den Informationen, für die sie über die Berechtigung verfügen. Sie können beispielsweise eine Such vertikal für Marketinganalysedaten aus Drittanbietersoftware für Ihre Benutzer in der Marketingabteilung erstellen. Sie können auch Ergebnistypen definieren und das Layout für diese Daten anpassen.  

Sie können vertikale Und Ergebnistypen auf diesen Ebenen erstellen:

- **Organisationsebene** – Wenn Sie eine Vertikale auf Organisationsebene hinzufügen, wird sie auf der Suchergebnisseseite angezeigt, wenn Benutzer von ihrer [SharePoint-Startseite,](https://sharepoint.com/) auf [Office](https://office.com)oder in [Bing suchen.](https://bing.com)
- **Websiteebene** – Beispielsweise möchten Sie Ihren Kundendienstmitarbeitern ermöglichen, direkt auf der SharePoint-Website ihrer Abteilung nach Vorfällen des Schweregrads *1* zu suchen.

## <a name="search-verticals-explained"></a>Search verticals explained

Oben auf der Microsoft Search-Ergebnisse-Seite gibt es eine Reihe von Registerkarten. Dies sind die Such vertikal. Eine Such vertikal zeigt nur Ergebnisse eines bestimmten Typs oder aus bestimmten Inhalten an. Beispiele sind **Dateien** oder **Nachrichten.** Standardmäßig zeigt Microsoft Search die Vertikalen **"Alle",** **"Personen",** **"Dateien",** **"Websites"** und **"News" an.**  

Sie können Such vertikal hinzufügen, die für Ihre Organisation relevant sind. Diese werden auf der Microsoft Search-Ergebnisse-Seite in [SharePoint,](https://sharepoint.com/) [Office](https://Office.com)und [Bing angezeigt.](https://bing.com) Sie können beispielsweise eine Vertikale für marketingbezogene Inhalte und eine weitere für den Vertrieb basierend auf der Art der Informationen erstellen, die jede Gruppe benötigt. Sie können Vertikalen hinzufügen, um nur Ergebnisse aus Inhalten anzuzeigen, die über Connectors indiziert wurden.  

### <a name="multiple-connections-in-a-vertical"></a>Mehrere Verbindungen in einer vertikalen

Eine Such vertikal kann jetzt Ergebnisse aus mehreren Connectorquellen angezeigt werden. Dies bietet mehr Flexibilität beim Entwerfen der Suchergebnissetseite. Mit der vorhandenen Verwaltungserfahrung des vertikalen Setups können Sie im Schritt "Inhaltsquelle" mehrere Verbindungen auswählen.
Wenn Sie so viele semantische Bezeichnungen wie möglich genau benennen, wird diese Erfahrung verbessert. Sie können semantische Bezeichnungen zur Schemadefinition und Erfassung hinzufügen.

[Hier](configure-connector.md#step-5-assign-property-labels) finden Sie weitere Informationen zum Erstellen und Verwalten semantischer Bezeichnungen.

### <a name="things-you-should-know"></a>Dinge, die Sie wissen sollten

1. Eine Verbindung kann nur unter einer vertikalen Ebene als Inhaltsquelle hinzugefügt werden. Das Erneute Verwenden von Verbindungen unter mehreren Vertikalen ist nicht zulässig.
2. Wenn Sie eine Abfrage für eine Such vertikal einrichten müssen, in der mehrere Verbindungsquellen hinzugefügt wurden, sollten allgemeine Quelleigenschaften verwendet werden, um eine solche Abfrage zu erstellen.

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte

Bevor Sie beginnen, stellen Sie sicher, dass der Connector indiziert wurde. Dies kann je nach Dateigröße bis zu 48 Stunden dauern.

Sie können keine Vertikale für Inhalte erstellen, die sich in [SharePoint befinden.](https://sharepoint.com/)

Es gibt drei grundlegende Schritte zum Hinzufügen einer Vertikalen:

1. Erstellen Sie die Vertikale. In diesem Schritt definieren Sie den Namen, die Inhaltsquelle und den Umfang des zu durchsuchende Inhalts der Vertikalen.
2. Definieren Sie, wie die Ergebnisse für diese Vertikale aussehen.  
3. Aktivieren Sie die vertikale (zu zeigende) Vertikale auf der vertikalen Listenseite.

## <a name="step-1-create-the-search-vertical"></a>SCHRITT 1: Erstellen der Such vertikal

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte zum Definieren des Namens, der Inhaltsquelle und des Bereichs des zu durchsuchende Inhalts geführt. Die Vertikale wird in einem deaktivierten Zustand erstellt. Sie aktivieren sie später.

Sie können einen begrenzten Satz von [KQL (Keyword Query Language)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) verwenden, um den Bereich zu einengt. Auf dieser Seite werden die verfügbaren Eigenschaften aufgeführt. Es wird empfohlen, Freitextschlüsselwörter und Eigenschaftseinschränkungen mit booleschen Operatoren zum Erstellen der KQL zu verwenden.

### <a name="create-a-vertical-at-the-organization-level"></a>Erstellen einer Vertikalen auf Organisationsebene

Führen Sie die folgenden Schritte aus, um die Vertikale in Microsoft Search in [SharePoint](https://sharepoint.com/) Home, [Office](https://office.com)oder [Bing](https://bing.com)zu erstellen:

1. Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**"Vertikal".**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Wählen Sie **"Hinzufügen"** aus, um zu beginnen.  

### <a name="create-a-vertical-at-the-site-level"></a>Erstellen einer Vertikalen auf Standortebene

1. Wechseln Sie [auf der SharePoint-Website,](https://sharepoint.com/) auf der sie vertikal angezeigt werden soll, zu **"Einstellungen".**
2. Wählen Sie **"Websiteinformationen"** aus, und **zeigen Sie dann alle Websiteeinstellungen an.**
3. Suchen Sie nach dem **Microsoft Search-Abschnitt,** und wählen Sie dann **"Microsoft Search für diese Websitesammlung konfigurieren" aus.**
4. Wechseln Sie im Navigationsbereich zu **"Benutzerdefiniert",** und wählen Sie dann die Registerkarte **"Vertikal"** aus.
5. Wenn Sie eine vertikale Hinzufügen möchten, wählen Sie **"Hinzufügen" aus.**
  Wenn Sie eine Vertikale bearbeiten möchten, wählen Sie sie in der Liste aus.

Beachten Sie, dass Vertikalen in einem deaktivierten Zustand erstellt werden. Sie müssen aktiviert werden, bevor Benutzer sie sehen können.

## <a name="step-2-create-the-result-types"></a>SCHRITT 2: Erstellen der Ergebnistypen

Sie können definieren, wie Ergebnisse in der Vertikalen angezeigt werden, indem Sie das Layout mithilfe von Ergebnistypen entwerfen. Mit dem Ergebnislayout können Sie wichtige Informationen direkt in den Suchergebnissen anzeigen, sodass Benutzer nicht jedes Ergebnis auswählen müssen, um zu sehen, ob sie das Gesuchte gefunden haben.

### <a name="default-search-result-layout"></a>Standardlayout für Suchergebnisse

Für Connectorinhalte wird ein Standardmäßiges  Suchergebnislayout angezeigt, wenn Bezeichnungen und Inhaltseigenschaften zum Zeitpunkt der Konfiguration des Connectors den Quelleigenschaften ordnungsgemäß zugeordnet wurden.  Der **Bezeichnungstitel** ist die wichtigste Bezeichnung. Es wird **dringend empfohlen,** dieser Bezeichnung eine Eigenschaft zur Verwendung des standardmäßigen Suchergebnislayouts zugewiesen zu haben.

### <a name="create-your-own-result-type"></a>Erstellen Eines eigenen Ergebnistyps

Sie können ein eigenes Suchergebnislayout erstellen und das Standardmäßige Suchergebnislayout überschreiben, indem Sie einen **Ergebnistyp erstellen.** Ein Ergebnistyp einer Suche ist eine Regel, die bewirkt, dass unterschiedliche Arten von Suchergebnissen auf verschiedene Weisen angezeigt werden. Ein Ergebnistyp hat folgende Bestandteile:

- **Eine oder mehrere Bedingungen zum** Vergleichen der einzelnen Suchergebnisse, z. B. die Inhaltsquelle des Suchergebnisses.  
- Ein **Ergebnislayout,** das für Suchergebnisse verwendet werden soll, die die Bedingungen erfüllen. Das Ergebnislayout steuert, wie alle Ergebnisse, die die Bedingungen erfüllen, auf einer Suchergebnissetseite angezeigt werden und sich verhalten.

**Wenn keine entsprechende Zuordnung erfolgt, um das Standardmäßige Suchergebnislayout zu zeigen, müssen Sie mindestens einen Ergebnistyp erstellen, damit die Ergebnisse in der vertikalen Ansicht angezeigt werden.** Sie können für jede Vertikale mehrere Ergebnistypen erstellen, wodurch Sie unterschiedliche Layouts für verschiedene Ergebnistypen verwenden können. Sie können z. B. Schweregrad *1-Vorfälle* so anpassen, dass sie im Vergleich zu Schweregrad *3* auffälligere Farben und eine größere Schriftart haben.

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte zum Definieren des Namens, der Inhaltsquelle und der Bedingungen für den Ergebnistyp geführt. Sie können die Priorität des Ergebnistyps in der Listenansicht definieren.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Erstellen eines Ergebnistyps auf Organisationsebene

1. Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Ergebnistypen.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)
2. Um einen **Ergebnistyp hinzuzufügen,** wählen Sie **"Hinzufügen" aus.** Um einen Ergebnistyp zu bearbeiten, wählen Sie den Ergebnistyp in der relevanten Liste aus.

### <a name="create-a-results-type-at-the-site-level"></a>Erstellen eines Ergebnistyps auf Websiteebene

1. Wechseln Sie [auf der SharePoint-Website,](https://sharepoint.com/) auf der Sie den Ergebnistyp erstellen möchten, zu **"Einstellungen".**
2. Wählen Sie **"Websiteinformationen"** aus, und **zeigen Sie dann alle Websiteeinstellungen an.**
3. Suchen Sie nach dem Microsoft Search-Abschnitt, und wählen Sie dann **"Microsoft Search für diese Websitesammlung konfigurieren" aus.**
4. Wechseln Sie im Navigationsbereich zu **"Benutzerdefinierte** Benutzererfahrung", und wählen Sie die Registerkarte **"Ergebnistyp"** aus.
5. Um einen Ergebnistyp hinzuzufügen, wählen Sie **"Hinzufügen" aus.**  Oder wählen Sie zum Bearbeiten eines Ergebnistyps den Ergebnistyp in der Liste aus.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>SCHRITT 3: Anzeigen der Vertikalen nach der Aktivierung

Nachdem Sie die Vertikale aktiviert haben, kann es eine Weile dauern, bis Sie sie anzeigen können. Wenn Sie nach der Aktivierung nicht warten möchten, können Sie **cacheClear=true** an die URL in [SharePoint](https://sharepoint.com/) und [Office](https://office.com) anfügen, um die Vertikale sofort anzeigen zu können. Fügen [Sie für Bing](https://bing.com)&**features=uncachedVerticals** an die Vertikale URL Arbeit an, um die Vertikalen sofort anzuzeigen.

## <a name="troubleshooting"></a>Problembehandlung

Hier finden Sie eine Liste der häufigen Probleme, die auftreten können, sowie Aktionen zur Behebung dieser Probleme.

|Fehler  |Maßnahme  |
|---------|---------|
| Auf der vertikalen Ebene wird die Fehlermeldung "Etwas ist nicht gefehlert" angezeigt. | Sowohl die vertikalen typen als auch die Ergebnistypen sind erforderlich, um die Einrichtung abzuschließen. Stellen Sie sicher, dass Sie beide für dieselbe Inhaltsquelle erstellt haben. |
| Ich kann mein Ergebnislayout nicht sehen, obwohl ich ein Layout erstellt habe. | Es dauert ein paar Minuten, da diese Einstellungen im Allgemeinen zwischengespeichert werden. Warten Sie einige Minuten, und versuchen Sie es erneut.        |
| Auf der Vertikalen oder Ergebnistypseite werden keine Inhaltsquellen angezeigt. | Stellen Sie sicher, dass Sie Connectors und indizierte Daten konfiguriert haben.   |

## <a name="next-steps"></a>Nächste Schritte

[Anpassen des Ergebnislayouts](customize-results-layout.md)
