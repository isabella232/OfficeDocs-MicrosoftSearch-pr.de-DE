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
ms.openlocfilehash: e5c4ab8d507e0e6096a5b9d52dc0e818faebefb6
ms.sourcegitcommit: a07c957dfa1d31542f0362379251bc9679dfae41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2021
ms.locfileid: "51639853"
---
# <a name="customize-the-search-results-page"></a>Anpassen der Suchergebnissetseite

Sie können Such vertikal und Ergebnistypen erstellen, um die Suchergebnisse anzupassen, die Benutzern angezeigt werden, wenn sie in Microsoft [SharePoint,](https://sharepoint.com/) [Microsoft Office](https://office.com)und Microsoft Search in [Bing suchen.](https://bing.com) Vertikalen erleichtern Benutzern das Suchen der Informationen, die sie sehen dürfen. Sie könnten beispielsweise eine Such vertikal für Marketinganalysedaten aus Drittanbietersoftware für Ihre Benutzer in der Marketingabteilung erstellen. Sie können auch Ergebnistypen definieren und das Layout für diese Daten anpassen.  

Sie können Vertikalen und Ergebnistypen auf folgenden Ebenen erstellen:

- **Organisationsebene** – Wenn Sie eine Vertikale auf Organisationsebene hinzufügen, wird sie auf der Suchergebnissetseite angezeigt, wenn Benutzer auf ihrer [SharePoint-Startseite,](https://sharepoint.com/) in [Office](https://office.com)oder [bing suchen.](https://bing.com)
- **Websiteebene** – Beispielsweise möchten Sie es Ihren Kundendienstmitarbeitern ermöglichen, direkt auf der SharePoint-Website ihrer Abteilung nach Vorfällen des Schweregrads *1* zu suchen.

## <a name="search-verticals-explained"></a>Erläuterte Such vertikal

Oben auf der Microsoft Search-Ergebnisseite gibt es eine Zeile mit Registerkarten. Dies sind die Such vertikal. Eine Such vertikal zeigt nur Ergebnisse eines bestimmten Typs oder aus bestimmten Inhalten an. Beispiele sind **Dateien** oder **News**. Standardmäßig zeigt Microsoft Search die Vertikalen **All**, **People**, **Files**, **Sites** und **News an.**  

Sie können Such vertikal hinzufügen, die für Ihre Organisation relevant sind. Diese werden auf der Microsoft Search-Ergebnisseite in [SharePoint,](https://sharepoint.com/) [Office](https://Office.com)und [Bing angezeigt.](https://bing.com) Sie könnten beispielsweise eine Vertikale für Marketinginhalte und eine weitere für den Vertrieb erstellen, basierend auf der Art der Informationen, die für jede Gruppe benötigt werden. Sie können Vertikalen hinzufügen, um nur Ergebnisse aus Inhalten anzuzeigen, die über Connectors indiziert wurden.  

### <a name="multiple-connections-in-a-vertical"></a>Mehrere Verbindungen in einer Vertikalen

Eine Such vertikal kann jetzt Ergebnisse aus mehreren Connectorquellen angezeigt werden. Dies bietet mehr Flexibilität beim Entwerfen Ihrer Suchergebnisseite. Mit der vorhandenen verwaltungstechnischen Erfahrung der vertikalen Einrichtung können Sie im Schritt "Inhaltsquelle" mehrere Verbindungen auswählen.
Wenn Sie so viele semantische Bezeichnungen wie möglich genau ernennen, wird diese Erfahrung verbessert. Sie können semantische Bezeichnungen zur Schemadefinition und -aufnahme hinzufügen.

[Hier](configure-connector.md#step-5-assign-property-labels) finden Sie weitere Informationen zum Erstellen und Verwalten semantischer Bezeichnungen.

> [!NOTE]
> Mehrere Verbindungen in einer Vertikalen werden derzeit in der Vorschau angezeigt. Weitere Informationen zur Vorschau finden Sie unter [Connectors preview features](connectors-overview.md#what-are-the-preview-features).

### <a name="things-you-should-know"></a>Dinge, die Sie wissen sollten

1. Eine Verbindung kann nur unter einer Vertikalen als Inhaltsquelle hinzugefügt werden. Das erneute Verwenden von Verbindungen unter mehreren Vertikalen ist nicht zulässig.
2. Wenn Sie eine Abfrage für eine Such vertikal einrichten müssen, in der mehrere Verbindungsquellen hinzugefügt wurden, sollten allgemeine Quelleigenschaften verwendet werden, um eine solche Abfrage zu erstellen.

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte

Stellen Sie vor dem Start sicher, dass der Connector indiziert wurde. Dies kann je nach Dateigröße bis zu 48 Stunden dauern.

Sie können keine Vertikale für Inhalte erstellen, die sich in [SharePoint befinden.](https://sharepoint.com/)

Es gibt drei grundlegende Schritte zum Hinzufügen einer Vertikalen:

1. Erstellen Sie die Vertikale. In diesem Schritt definieren Sie den Namen, die Inhaltsquelle und den Bereich des zu durchsuchende Inhalts.
2. Definieren Sie, wie die Ergebnisse für diese Vertikale aussehen.  
3. Aktivieren Sie die Vertikale (die angezeigt werden soll) auf der vertikalen Listenseite.

## <a name="step-1-create-the-search-vertical"></a>SCHRITT 1: Erstellen der Such vertikal

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte geführt, um den Namen, die Inhaltsquelle und den Umfang des zu durchsuchende Inhalts zu definieren. Die Vertikale wird in einem deaktivierten Zustand erstellt. Sie aktivieren sie zu einem späteren Zeitpunkt.

Sie können einen begrenzten Satz von [Keyword Query Language (KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) verwenden, um den Bereich zu einenten. Auf dieser Seite werden die verfügbaren Eigenschaften aufgeführt. Es wird empfohlen, Freitextschlüsselwörter und Eigenschaftseinschränkungen mit booleschen Operatoren zum Erstellen der KQL zu verwenden.

### <a name="create-a-vertical-at-the-organization-level"></a>Erstellen einer Vertikalen auf Organisationsebene

Führen Sie die folgenden Schritte aus, um die Vertikale in Microsoft Search in [SharePoint](https://sharepoint.com/) home, [Office](https://office.com)oder [Bing](https://bing.com)zu erstellen:

1. Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Wählen **Sie Hinzufügen** aus, um die ersten Schritte zu starten.  

### <a name="create-a-vertical-at-the-site-level"></a>Erstellen einer Vertikalen auf Standortebene

1. Wechseln Sie auf der [SharePoint-Website,](https://sharepoint.com/) auf der Die Vertikale angezeigt werden soll, zu **Einstellungen**.
2. Wählen **Sie Websiteinformationen** aus, und zeigen **Sie dann alle Websiteeinstellungen an.**
3. Suchen Sie nach **dem Abschnitt Microsoft Search,** und wählen Sie **dann Konfigurieren von Microsoft Search für diese Websitesammlung aus.**
4. Wechseln Sie im Navigationsbereich zu **Benutzerdefinierte Benutzerdefinierte Benutzererfahrung,** und wählen Sie dann die Registerkarte **Vertikal** aus.
5. Wählen Sie Hinzufügen aus, um eine Vertikale **hinzuzufügen.**
  Oder wählen Sie sie in der Liste aus, um eine Vertikale zu bearbeiten.

Denken Sie daran, dass Vertikalen in einem deaktivierten Zustand erstellt werden. Sie müssen aktiviert sein, bevor Benutzer sie sehen können.

## <a name="step-2-create-the-result-types"></a>SCHRITT 2: Erstellen der Ergebnistypen

Sie können definieren, wie Ergebnisse in der Vertikalen angezeigt werden, indem Sie das Layout mithilfe von Ergebnistypen entwerfen. Mit dem Ergebnislayout können Sie wichtige Informationen direkt in den Suchergebnissen anzeigen, sodass Benutzer nicht jedes Ergebnis auswählen müssen, um zu sehen, ob sie das gesuchte Ergebnis gefunden haben.

### <a name="default-search-result-layout"></a>Standardmäßiges Suchergebnislayout

Ein Standardmäßiges Suchergebnislayout wird für  Connectorinhalte angezeigt, wenn Bezeichnungen und Inhaltseigenschaften zum Zeitpunkt der Konfiguration des Connectors den Quelleigenschaften ordnungsgemäß zugeordnet wurden.  Der **Bezeichnungstitel** ist die wichtigste Bezeichnung. Es wird **dringend empfohlen,** dieser Bezeichnung eine Eigenschaft zur Verwendung des Standardmäßigen Suchergebnislayouts zugewiesen zu haben.

### <a name="create-your-own-result-type"></a>Erstellen Eines eigenen Ergebnistyps

Sie können ihr eigenes Suchergebnislayout erstellen und das Standardmäßige Suchergebnislayout überschreiben, indem Sie einen **Ergebnistyp erstellen.** Ein Ergebnistyp einer Suche ist eine Regel, die bewirkt, dass unterschiedliche Arten von Suchergebnissen auf verschiedene Weisen angezeigt werden. Ein Ergebnistyp hat folgende Bestandteile:

- **Eine oder mehrere Bedingungen zum** Vergleichen jedes Suchergebniss, z. B. die Inhaltsquelle des Suchergebniss.  
- Ein **Ergebnislayout,** das für Suchergebnisse verwendet werden soll, die die Bedingungen erfüllen. Das Ergebnislayout steuert, wie alle Ergebnisse, die die Bedingungen erfüllen, auf einer Suchergebnissetseite angezeigt und verhalten werden.

**Wenn keine entsprechende Zuordnung zum Anzeigen des Standardmäßigen Suchergebnislayouts erfolgt, müssen Sie mindestens einen Ergebnistyp erstellen, damit die Ergebnisse in der Vertikalen angezeigt werden können.** Sie können mehrere Ergebnistypen für jede Vertikale erstellen, wodurch Sie unterschiedliche Layouts für unterschiedliche Ergebnistypen verwenden können. Beispielsweise können Sie Schweregrad *1-Vorfälle* so anpassen, dass sie im Vergleich zu Schweregrad *3* auffälligere Farben und eine größere Schriftart haben.

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte zum Definieren des Namens, der Inhaltsquelle und der Bedingungen für den Ergebnistyp geführt. Sie können die Priorität des Ergebnistyps in der Listenansicht definieren.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Erstellen eines Ergebnistyps auf Organisationsebene

1. Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Ergebnistypen**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).
2. Wählen Sie Hinzufügen aus, um einen **Ergebnistyp** **hinzuzufügen.** Wählen Sie zum Bearbeiten eines Ergebnistyps den Ergebnistyp in der entsprechenden Liste aus.

### <a name="create-a-results-type-at-the-site-level"></a>Erstellen eines Ergebnistyps auf Websiteebene

1. Wechseln Sie auf der [SharePoint-Website,](https://sharepoint.com/) auf der Sie den Ergebnistyp erstellen möchten, zu **Einstellungen**.
2. Wählen **Sie Websiteinformationen** aus, und zeigen **Sie dann alle Websiteeinstellungen an.**
3. Suchen Sie nach dem Abschnitt Microsoft Search, und wählen Sie **dann Konfigurieren von Microsoft Search für diese Websitesammlung aus.**
4. Wechseln Sie im Navigationsbereich zu **Benutzerdefinierte Benutzerdefinierte Benutzererfahrung,** und wählen Sie die Registerkarte **Ergebnistyp** aus.
5. Wählen Sie Hinzufügen aus, um einen Ergebnistyp **hinzuzufügen.**  Oder wählen Sie zum Bearbeiten eines Ergebnistyps den Ergebnistyp in der Liste aus.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>SCHRITT 3: Anzeigen der Vertikalen nach der Aktivierung

Nachdem Sie die Vertikale aktiviert haben, dauert es einige Stunden, bis Sie sie anzeigen können. Wenn Sie nach der Aktivierung nicht warten möchten, können Sie **cacheClear=true** an die URL in [SharePoint](https://sharepoint.com/) und [Office](https://office.com) anfügen, um die Vertikale sofort anzeigen zu können. Fügen [Sie für Bing](https://bing.com)&**features=uncachedVerticals** an die vertikale ARBEITS-URL an, um die Vertikalen sofort anzuzeigen. 

> [!NOTE]
> Hinzugefügte Vertikalen werden in [SharePoint](https://sharepoint.com/) und [Office](https://office.com) nicht angezeigt, wenn sie von mobilen Webbrowsern angezeigt werden.

## <a name="troubleshooting"></a>Problembehandlung

Hier finden Sie eine Liste der häufigen Probleme, auf die Sie möglicherweise stoßen, und Aktionen, um sie zu beheben.

|Fehler  |Maßnahme  |
|---------|---------|
| In der Vertikalen wird die Fehlermeldung "Etwas ist falsch gelaufen" angezeigt. | Sowohl die vertikalen als auch die Ergebnistypen sind erforderlich, um das Setup abzuschließen. Stellen Sie sicher, dass Sie beide für dieselbe Inhaltsquelle erstellt haben. |
| Mein Ergebnislayout wird nicht angezeigt, obwohl ich ein Ergebnislayout erstellt habe. | Es dauert einige Minuten, da diese Einstellungen im Allgemeinen zwischengespeichert werden. Warten Sie einige Minuten, und versuchen Sie es erneut.        |
| Auf der Vertikalen- oder Ergebnistypseite werden keine Inhaltsquellen angezeigt. | Stellen Sie sicher, dass Sie Connectors und indizierte Daten konfiguriert haben.   |

## <a name="next-steps"></a>Nächste Schritte

[Anpassen des Ergebnislayouts](customize-results-layout.md)
