---
title: Vorschau der Connectors
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Erfahren Sie mehr über die Microsoft Graph Connectors Preview für Microsoft Search.
ms.openlocfilehash: 81d169074a316b6ab07f47156e0f057e50c12e3e
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422892"
---
# <a name="microsoft-graph-connectors-preview"></a>Vorschau der Microsoft Graph-Konnektoren

Microsoft Graph-Connectors und Microsoft Search-APIs (Abfrage und Index) befinden sich zurzeit im Vorschaustatus. Um Zugriff auf Connectors-Funktionen zu erhalten, müssen Sie die Option "Targeted Release" in Ihrem Mandanten aktivieren. Dies ist eine frühe Vorschau, und es gibt keine Garantie auf Service Level. Wir ermutigen Kunden, konnektorfunktionen zu testen und Feedback zu geben. Es wird nicht empfohlen, Connectors für Produktionszwecke während des Vorschauzeitraums zu verwenden.

## <a name="set-up-targeted-release"></a>Einrichten der gezielten Version

Wenn Sie Connectors testen möchten, müssen Sie die Option **Targeted Release** für alle Benutzer in Ihrer Organisation festgelegt haben. Weitere Informationen zur Option "Targeted Release" und dazu, wie Sie Sie festlegen, finden Sie unter [Einrichten der Standard-oder Targeted Release-Optionen in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).

## <a name="choose-a-preview-environment"></a>Auswählen einer vorschauumgebung

Um Konnektoren, Indizierungs-APIs und Such-APIs zu testen, empfehlen wir diese beiden Methoden:

1. **Test Mandant**.  Wir empfehlen Ihnen, einen Testmandanten zu verwenden, um die Vorschau der Microsoft Graph-Konnektoren auszuprobieren.

2. **Testen der Websitesammlung**. Wenn Sie keinen Testmandanten haben, können Sie eine TestWebsite Sammlung zum Ausprobieren von connectorfunktionen erstellen. Wenn Sie Ergebnisse aus Konnektoren anzeigen möchten, ohne dass sich dies auf die Suchseiten in Ihrer Organisation auswirkt, passen Sie die Suchumgebung nur für diese Websitesammlung an.

## <a name="preview-limitations"></a>Vorschau Einschränkungen

Die Vorschauversion weist die folgenden Einschränkungen auf:

* Der Durchsatz für die Einnahme wird mit etwa vier Elementen pro Sekunde gedrosselt.

* Es gibt keine Unterstützung für Schemaaktualisierungen. Nachdem Sie eine Verbindungseinrichtung erstellt haben, können Sie das Schema nicht aktualisieren. Sie können die Verbindung nur löschen und neu erstellen.

* Indizierte Inhalte werden nur auf der Suchergebnisseite unter einer benutzerdefinierten vertikalen angezeigt. Diese Einschränkung gilt für Inhalte mit benutzerdefinierten Typen.

* Jede Verbindung, die Sie während des Vorschauzeitraums eingerichtet haben, muss möglicherweise gelöscht und neu erstellt werden. Diese Verbindungen funktionieren nicht mehr, wenn Sie mit Änderungen, die zur Verbesserung des Produkts vorgenommen wurden, nicht kompatibel sind.

* Es gibt einen Grenzwert für Verbindungen. Jeder Mandant kann bis zu 10 Verbindungen erstellen.

* Größe des Quell-Repositorys. Es wird empfohlen, Connectors mit einem Quell-Repository mit etwa 200.000 Elementen in der Vorschau anzuzeigen, da dies unsere getestete Skalierungsgrenze für die Suche darstellt. Wir arbeiten daran, die Leistung der Suche zu verbessern, und wir erwarten, dass in naher Zukunft größere Repository-Größen unterstützt werden.

* Die Bearbeitungsunterstützung für die Verbindung ist nicht verfügbar. Nachdem die Verbindung erstellt wurde, können Sie Sie nicht bearbeiten oder ändern. Wenn Sie Details ändern müssen, müssen Sie die Verbindung löschen und neu erstellen.

* Connector-Inhalte können nur nach benutzerdefinierten vertikalen durchsucht werden.

* Connector-Inhalt aus nur einer Verbindung kann in jeder benutzerdefinierten vertikalen angezeigt werden und erfordert die Erstellung von Ergebnistypen.
