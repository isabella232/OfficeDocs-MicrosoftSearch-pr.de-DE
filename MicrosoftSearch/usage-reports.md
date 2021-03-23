---
title: Suchverwendungsberichte
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Überprüfen von Microsoft Search-Verwendungsberichten
ms.openlocfilehash: 2237fc978ad7b0d7b94b342a9f2646c9da6b73a4
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031746"
---
# <a name="microsoft-search-usage-reports"></a>Verwendungsberichte für Microsoft Search

Mit Suchverwendungsberichten können Sie besser verstehen, wie die Suche in Ihrer Organisation funktioniert. Die aus diesen Berichten gewonnenen Erkenntnisse helfen Ihnen dabei, Inhalte leichter zu finden und Aktionen zu ergreifen, die die Suche für Ihre Benutzer nützlicher und angenehmer machen. [](./make-content-easy-to-find.md)

Die [Microsoft Search-Verwendungsberichte](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) enthalten Diagramme und Tabellen, die aus Suchdurchsuchungen generiert werden, die von SharePoint Home und aus Office.com ausgeführt werden. Sie können Daten aus den letzten 31 Tagen, pro Tag oder monatlich für das vorherige Jahr sehen. Diese Berichte werden gerade erst ins Rollen gebracht, sodass es einige Zeit dauern wird, bis die Verlaufsdaten anfallen.

Eine frühere Version dieser Seite enthielt Daten aus suchten, die für Microsoft Search in Bing am Bing.com. Diese Daten werden in Kürze in diese Berichte integriert, aber vorerst können Sie diese Berichte weiterhin anzeigen, indem Sie auf den Link am unteren Rand der Seite klicken, um die obersten Abfragen von Bing und die Verteilung des **Eindrucks anzeigen.**

> [!div class="mx-imgBorder"]
> ![Dashboard für Suchverwendungsberichte](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>Übersicht über Suchberichte

| Bericht | Beschreibung |
|:-----|:-----|
|Abfragevolume|Dieser Bericht zeigt die Anzahl der ausgeführten Suchabfragen. Verwenden Sie diesen Bericht, um Trends beim Suchabfragevolumen zu identifizieren und Zeiträume mit hoher und niedriger Suchaktivität zu ermitteln.|
|Häufigste Suchvorgänge|Dieser Bericht enthält die beliebtesten Suchabfragen. Verwenden Sie diesen Bericht, um zu verstehen, nach welchen Arten von Informationen Ihre Benutzer suchen.|
|Abgebrochene Abfragen|Dieser Bericht zeigt beliebte Suchabfragen, die nur ein geringes Klickergebnis erhalten. Mithilfe dieses Berichts können Sie Suchvorgänge identifizieren, die unzufriedene Benutzer erzeugen, und das Auffinden von Inhalten verbessern. Anschließend können Sie ermitteln, ob das Erstellen einer Antwort, z. B. ein Lesezeichen, oder das Einsenden neuer Inhalte über einen Graph-Connector die richtige Aktion ist.|
|Keine Ergebnisabfragen|Dieser Bericht zeigt beliebte Suchabfragen, die keine Ergebnisse zurückgegeben haben. Mithilfe dieses Berichts können Sie Suchvorgänge identifizieren, die unzufriedene Benutzer erzeugen, und das Auffinden von Inhalten verbessern. Anschließend können Sie ermitteln, ob das Erstellen einer Antwort, z. B. ein Lesezeichen, oder das Einsenden neuer Inhalte über einen Graph-Connector die richtige Aktion ist.|

## <a name="viewing-reports"></a>Anzeigen von Berichten

Wenn Sie zur Seite Verwendungsberichte navigieren, stehen alle Berichte zur Verfügung. Mit dem Datumsfilter können Sie einen bestimmten Tag oder Monat auswählen, der angezeigt werden soll.

Wenn Sie einen Bericht herunterladen, können Sie Berichte aus einem größeren Zeitraum anzeigen. Klicken Sie auf den Downloadpfeil, und wählen Sie **die letzten 31 Tage** oder letzten **12 Monate aus.** Der Bericht wird als Excel-Kalkulationstabelle heruntergeladen. Wenn Sie die letzten 31 Tage ausgewählt haben, hat die Kalkulationstabelle für jeden Tag eine einzelne Registerkarte. Der Download der letzten 12 Monate enthält eine Registerkarte für jeden Monat.

Klicken Sie auf den Link auf der Seite, um die obersten Abfragen und Eindrucksverteilungsberichte von Bing zu sehen.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wenn ich die letzten 31 Tage oder letzten 12 Monate auswähle, warum muss ich dann einen bestimmten Tag oder bestimmten Monat auswählen.**

Die Kalenderansicht ist heute in Microsoft Search Usage Reports ein Zwei-Schritt-Prozess. Wählen Sie zuerst den Datumsbereich aus der Dropdownliste aus (die letzten 31 Tage oder letzten 12 Monate), und wählen Sie dann den Starttag oder Monat aus.

In den oberen, abgebrochenen und fehlgeschlagenen Abfragetabellen werden Ergebnisse aus dem tag oder dem Monat angezeigt, den Sie auswählen.

**Wann werden aggregierte Daten für die letzten 7 Tage, die letzten 30 Tage usw. wie die Berichte für die obersten Abfragen von Bing?**

Wir erwägen diese Art der Aggregation und vereinfachen die Datenbereichsfilterung für zukünftige Versionen dieser Berichte.

**Warum kann ich keine Aufschlüsselung der Verwendungsberichte nach verschiedenen Apps (Quellen) sehen?**

Derzeit ist die Filterung nach Quelle nicht verfügbar. Die Berichte kombinieren Suchen aus SharePoint Home und Office.com. Unsere nächste Version umfasst die Quellfilterung, damit Sie Metriken sehen können, die für jede Anwendung spezifisch sind.

**Welche weitere Filterung für Verwendungsberichte kommt?**

Wir arbeiten an zusätzlichen Filtern, die die Suchverwendung auf einer differenzierteren Ebene Ihrer Organisation sinnvoller machen. Beispielsweise können Sie das Abfragevolume für eine bestimmte Geografie oder Abteilung anzeigen.

**Warum wird microsoft search in Bing auf einer separaten Seite angezeigt?**

Die Modernisierung der Suche in Office 365-Anwendungen in Microsoft Search erforderte, dass wir zuvor unterschiedlichen Systemen beitreten mussten, einschließlich der Generierung von Berichten. Dies dauert, und wir waren der Meinung, dass es wichtiger war, diese Berichte jetzt heraus zu bekommen, statt zu warten, bis wir die Integration der Bing-Daten abschließen konnten. Sobald wir die Integration abgeschlossen haben, werden die Daten aller Suchendpunkte in die gleichen Berichte einbezogen.