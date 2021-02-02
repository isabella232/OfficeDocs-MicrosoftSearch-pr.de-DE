---
title: Verwendungsberichte für Die Suche
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
ms.openlocfilehash: ad349e60794f219fa757861081b12a33c6806091
ms.sourcegitcommit: 25b82bce1eaec5803111161b04ee9fd9e82a0bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50072239"
---
# <a name="microsoft-search-usage-reports"></a>Verwendungsberichte für Microsoft Search

Mit Suchverwendungsberichten können Sie besser verstehen, wie die Suche in Ihrer Organisation funktioniert. Die aus diesen Berichten generierten Erkenntnisse helfen Ihnen, Inhalte leicht zu finden und Aktionen zu ergreifen, die die Suche für Ihre Benutzer nützlicher und angenehmer machen. [](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find)

Die [Microsoft Search-Verwendungsberichte](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) enthalten Diagramme und Tabellen, die aus Suchfeldern generiert werden, die von der SharePoint Home- und Office.com ausgeführt werden. Sie können Daten aus den letzten 31 Tagen, pro Tag oder monatlich für das vorherige Jahr sehen. Diese Berichte werden gerade erst ausgerollt, sodass es einige Zeit dauert, bis die verlaufshistorischen Daten anfallen.

Eine frühere Version dieser Seite enthielt Daten aus Suchen, die für Microsoft Search in Bing am Bing.com. Diese Daten werden in Kürze in diese Berichte integriert, aber vorerst können Sie diese Berichte weiterhin anzeigen, indem Sie auf den Link unten auf der Seite klicken, um die obersten Abfragen von **Bing** und die Verteilung von Impressionen anzeigen.

> [!div class="mx-imgBorder"]
> ![Dashboard für Verwendungsberichte durchsuchen](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>Übersicht über Suchberichte

| Bericht | Beschreibung |
|:-----|:-----|
|Abfragevolume|Dieser Bericht zeigt die Anzahl der ausgeführten Suchabfragen. Verwenden Sie diesen Bericht, um Trends beim Suchabfragevolumen zu identifizieren und Zeiträume mit hoher und niedriger Suchaktivität zu ermitteln.|
|Häufigste Suchvorgänge|Dieser Bericht enthält die beliebtesten Suchabfragen. Verwenden Sie diesen Bericht, um zu verstehen, nach welchen Arten von Informationen Ihre Benutzer suchen.|
|Abgebrochene Abfragen|In diesem Bericht werden beliebte Suchabfragen angezeigt, die nur ein geringes Klickergebnis erhalten. Mithilfe dieses Berichts können Sie Suchvorgänge identifizieren, die unzufriedene Benutzer erzeugen, und das Auffinden von Inhalten verbessern. Sie können dann bestimmen, ob das Erstellen einer Antwort, z. B. ein Lesezeichen oder das Einfügen neuer Inhalte über einen Graph-Connector, die richtige Aktion ist.|
|Keine Ergebnisabfragen|Dieser Bericht enthält beliebte Suchabfragen, die keine Ergebnisse zurückgegeben haben. Mithilfe dieses Berichts können Sie Suchvorgänge identifizieren, die unzufriedene Benutzer erzeugen, und das Auffinden von Inhalten verbessern. Sie können dann bestimmen, ob das Erstellen einer Antwort, z. B. ein Lesezeichen oder das Einfügen neuer Inhalte über einen Graph-Connector, die richtige Aktion ist.|

## <a name="viewing-reports"></a>Anzeigen von Berichten

Wenn Sie zur Seite "Verwendungsberichte" navigieren, stehen alle Berichte zum Anzeigen zur Verfügung. Mit dem Datumsfilter können Sie einen bestimmten Tag oder Monat auswählen, der angezeigt werden soll.

Wenn Sie einen Bericht herunterladen, können Sie Berichte aus einem größeren Zeitraum anzeigen. Klicken Sie auf den Downloadpfeil, und wählen Sie die letzten **31 Tage** oder **letzten 12 Monate aus.** Der Bericht wird als Excel-Kalkulationstabelle heruntergeladen. Wenn Sie die letzten 31 Tage ausgewählt haben, enthält die Tabelle für jeden Tag eine individuelle Registerkarte. Der Download der letzten 12 Monate enthält eine Registerkarte für jeden Monat.

Klicken Sie auf den Link auf der Seite, um die am besten verwendeten Abfragen und Berichte zur Impressionverteilung von Bing zu sehen.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wenn ich die letzten 31 Tage oder letzten 12 Monate auswähle, warum muss ich einen bestimmten Tag oder einen bestimmten Monat auswählen?**

Die Kalenderansicht in Microsoft Search ist heute ein Zwei-Schritte-Prozess. Wählen Sie zuerst den Datumsbereich aus der Dropdownliste aus (die letzten 31 Tage oder letzten 12 Monate), und wählen Sie dann den Starttag oder -monat aus.

In den obersten, abgebrochenen und fehlgeschlagenen Abfragetabellen werden Ergebnisse aus dem tag oder dem Monat angezeigt, den Sie auswählen.

**Wann werden aggregierte Daten für die letzten 7 Tage, die letzten 30 Tage usw. Wie die Berichte für die am besten verwendeten Abfragen von Bing?**

Wir erwägen diese Art der Aggregation und vereinfachen die Datenbereichsfilterung für zukünftige Versionen dieser Berichte.

**Warum kann ich keine Aufschlüsselung der Nutzungsberichte nach verschiedenen Apps (Quellen) anzeigen?**

Derzeit ist die Filterung nach Quelle nicht verfügbar. Die Berichte kombinieren Suchbegriffe aus der SharePoint-Startseite und Office.com. Unsere nächste Version umfasst die Quellfilterung, damit Sie Metriken sehen können, die für jede Anwendung spezifisch sind.

**Welche weitere Filterung für Verwendungsberichte wird noch kommen?**

We are working on additional filters that will make sense of search usage at a more granular level of your organization. Beispielsweise können Sie das Abfragevolumen für eine bestimmte Region oder Abteilung anzeigen.

**Warum befindet sich Microsoft Search in Bing auf einer separaten Seite?**

Die Modernisierung der Suche in Office 365-Anwendungen in Microsoft Search erforderte, dass wir zuvor unterschiedlichen Systemen beitreten mussten, einschließlich der Berichterstellung. Dies dauert etwas, und wir waren der Meinung, dass es wichtiger war, diese Berichte jetzt zu erstellen und nicht zu warten, bis wir die Integration der Daten von Bing abschließen konnten. Sobald die Integration abgeschlossen ist, werden die Daten von allen Suchendpunkten in die gleichen Berichte eingeschlossen.
