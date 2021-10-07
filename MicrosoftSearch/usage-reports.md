---
title: Suchverwendungsberichte
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.topic: article
ms.service: mssearch
audience: Admin
ms.audience: Admin
ms.date: 09/24/2021
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Überprüfen Microsoft Search Nutzungsberichte
ms.openlocfilehash: 1f2afa6e2c7691aa3284ae017913827761981529
ms.sourcegitcommit: ca6f0488b842e7fc0d98c7b84b2b8bc5817d3e7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2021
ms.locfileid: "60224867"
---
# <a name="microsoft-search-usage-reports"></a>Microsoft Search Verwendungsberichte

Mithilfe von Suchverwendungsberichten können Sie besser verstehen, wie die Suche in Ihrer Organisation funktioniert. Die aus diesen Berichten generierten Erkenntnisse helfen Ihnen, Aktionen zu ergreifen, die die Suche für Ihre Benutzer nützlicher und ansprechender gestalten.

> [!IMPORTANT]
> Microsoft Search Nutzungsberichte befinden sich derzeit in der Vorschau

Die [Microsoft Search Verwendungsberichte](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) enthalten Diagramme und Tabellen, die aus Suchvorgängen generiert werden, die von SharePoint Home (der Website mit der URL mit der Endung "/SharePoint.aspx"), Office.com und Microsoft Search in Bing Suchfeldern ausgeführt werden. Sie können Daten aus den letzten 31 Tagen, pro Tag oder monatlich für das vorherige Jahr anzeigen. Diese Berichte werden gerade eingeführt, sodass es zeitaufwendige Zeit dauert, bis die verlaufshistorischen Daten fällig sind.

> [!div class="mx-imgBorder"]
> ![Dashboard für Suchverwendungsberichte.](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>Übersicht über Suchberichte

| Bericht | Beschreibung |
|:-----|:-----|
|Abfragevolume|Dieser Bericht zeigt die Anzahl der ausgeführten Suchabfragen an. Verwenden Sie diesen Bericht, um Trends im Suchabfragevolumen zu identifizieren und Zeiträume mit hoher und niedriger Suchaktivität zu ermitteln.|
|Häufigste Suchvorgänge|Dieser Bericht enthält die beliebtesten Suchabfragen. Eine Abfrage wird diesem Bericht hinzugefügt, wenn sie mindestens dreimal mit einem Klick auf ein Ergebnis durchsucht wird. Verwenden Sie diesen Bericht, um zu verstehen, nach welchen Arten von Informationen Ihre Benutzer suchen.|
|Abgebrochene Abfragen|Dieser Bericht zeigt häufig verwendete Suchabfragen, die nur wenig Klick-und-Los erhalten. Mithilfe dieses Berichts können Sie Suchvorgänge identifizieren, die unzufriedene Benutzer erzeugen, und das Auffinden von Inhalten verbessern. Sie können dann ermitteln, ob das Erstellen einer Antwort, z. B. ein Lesezeichen, oder das Erfassen neuer Inhalte über einen Graph Connector die richtige Aktion ist.|
|Keine Ergebnisabfragen|Dieser Bericht zeigt beliebte Suchabfragen, die keine Ergebnisse zurückgegeben haben. Mithilfe dieses Berichts können Sie Suchvorgänge identifizieren, die unzufriedene Benutzer erzeugen, und das Auffinden von Inhalten verbessern. Sie können dann ermitteln, ob das Erstellen einer Antwort, z. B. ein Lesezeichen, oder das Erfassen neuer Inhalte über einen Graph Connector die richtige Aktion ist.|

>[!NOTE]
>Es gibt derzeit ein bekanntes Problem, bei dem Abfragen, die mit einer Antwort wie einem Lesezeichen zufrieden sind, als abgebrochene Abfrage gezählt werden.

## <a name="viewing-reports"></a>Anzeigen von Berichten

Wenn Sie zur Seite "Verwendungsberichte" navigieren, können alle Berichte angezeigt werden. Mit dem Datumsfilter können Sie einen bestimmten Tag oder Monat auswählen, der angezeigt werden soll.

Wenn Sie einen Bericht herunterladen, können Sie Berichte aus einem größeren Zeitraum anzeigen. Klicken Sie auf den Downloadpfeil, und wählen Sie **nach 31 Tagen** oder **nach 12 Monaten** aus. Der Bericht wird als Excel Kalkulationstabelle heruntergeladen. Wenn Sie nach 31 Tagen ausgewählt haben, verfügt die Tabelle über eine einzelne Registerkarte für jeden Tag. In den letzten 12 Monaten wird für jeden Monat eine Registerkarte angezeigt.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wenn ich die letzten 31 Tage oder letzten 12 Monate auswähle, warum muss ich dann einen bestimmten Tag oder einen bestimmten Monat auswählen.**

Die Kalenderansicht ist heute in Microsoft Search-Verwendungsberichten ein Prozess in zwei Schritten. Wählen Sie zunächst den Datumsbereich aus der Dropdownliste aus (in den letzten 31 Tagen oder in den letzten 12 Monaten), und wählen Sie dann den Starttag oder -monat aus.

In den Abfragetabellen "Oben", "Abgebrochen" und "Fehlgeschlagen" werden Ergebnisse aus dem ausgewählten Tag oder Monat angezeigt.

**Wann werden aggregierte Daten für die letzten 7 Tage, die letzten 30 Tage usw. angezeigt?**

Wir erwägen diese Art der Aggregation und vereinfachen die Datenbereichsfilterung für zukünftige Versionen dieser Berichte.

**Warum kann ich keine Aufschlüsselung der Nutzungsberichte nach verschiedenen Apps (Quellen) sehen?**

Derzeit ist die Filterung nach Quelle nicht verfügbar. Die Berichte kombinieren Suchvorgänge aus SharePoint Home und Office.com. Unsere nächste Version enthält die Quellfilterung, damit Sie für jede Anwendung spezifische Metriken sehen können.

**Welche weitere Filterung für Nutzungsberichte ist verfügbar?**

Wir arbeiten an weiteren Filtern, die dazu beitragen, die Suchnutzung auf einer präziseren Ebene Ihrer Organisation sinnvoller zu gestalten. Beispielsweise können Sie das Abfragevolumen für eine bestimmte Geografie oder Abteilung anzeigen.
