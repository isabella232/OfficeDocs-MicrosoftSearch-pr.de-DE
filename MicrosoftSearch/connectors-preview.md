---
title: Vorschau der Connectors
ms.author: v-pamcn
author: monaray
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
ms.openlocfilehash: 025b4f0d7ad4ecae2909f02687c66938d931a2fc
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949812"
---
# <a name="microsoft-graph-connectors-preview"></a>Vorschau der Microsoft Graph-Konnektoren

Microsoft Graph-Connectors, Indizierungs-APIs und Such-APIs befinden sich derzeit in der Vorschau. Um auf Connectors-Funktionen zugreifen zu können, müssen Sie den Beitritt zum Vorschauprogramm anfordern, indem Sie das <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">Anmeldeformular für die Microsoft Graph-Konnektoren</a>in der Vorschau einreichen. Dies ist eine frühe Vorschau, und es gibt keine Garantie auf Service Level. Wir ermutigen Kunden, konnektorfunktionen zu testen und Feedback zu geben. Es wird nicht empfohlen, Connectors für Produktionszwecke während des Vorschauzeitraums zu verwenden.

## <a name="set-up-targeted-release"></a>Einrichten der gezielten Version
Wenn Sie Connectors testen möchten, müssen Sie die Option **Targeted Release** für alle Benutzer in Ihrer Organisation festgelegt haben. Die gezielte Freigabeanforderung gilt unabhängig davon, welche der folgenden Vorschau Umgebungen Sie auswählen.
Weitere Informationen zur Option "Targeted Release" und dazu, wie Sie Sie festlegen, finden Sie unter <a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">Einrichten der Standard-oder Targeted Release-Optionen in Office 365</a>.

## <a name="choose-a-preview-environment"></a>Auswählen einer vorschauumgebung 
Um Konnektoren, Indizierungs-APIs und Such-APIs zu testen, empfehlen wir diese beiden Methoden:
1. **Test Mandant**.  Wir empfehlen Ihnen, einen Testmandanten zu verwenden, um die Vorschau der Microsoft Graph-Konnektoren auszuprobieren.
2. **Testen der Websitesammlung**. Wenn Sie keinen Testmandanten haben, können Sie eine TestWebsite Sammlung zum Ausprobieren von connectorfunktionen erstellen. Wenn Sie Ergebnisse aus Konnektoren anzeigen möchten, ohne dass sich dies auf die Suchseiten in Ihrer Organisation auswirkt, passen Sie die Suchumgebung nur für diese Websitesammlung an.

## <a name="preview-limitations"></a>Vorschau Einschränkungen
Die Vorschauversion weist die folgenden Einschränkungen auf:
* Der Durchsatz für die Einnahme wird mit etwa vier Elementen pro Sekunde gedrosselt.
* Es gibt keine Unterstützung für Schemaaktualisierungen. Nachdem Sie eine Verbindungseinrichtung erstellt haben, können Sie das Schema nicht aktualisieren. Sie können die Verbindung nur löschen und neu erstellen.
* Indizierte Inhalte werden nur auf der Suchergebnisseite unter einer benutzerdefinierten vertikalen angezeigt. Diese Einschränkung gilt für Inhalte mit benutzerdefinierten Typen.
* Vor der allgemeinen Verfügbarkeit müssen alle Verbindungen, die Sie während des Vorschauzeitraums eingerichtet haben, möglicherweise gelöscht und neu erstellt werden. Diese Verbindungen funktionieren nicht mehr, wenn Sie mit Änderungen, die zur Verbesserung des Produkts vorgenommen wurden, nicht kompatibel sind.
* Grenzwert für Verbindungen. Jeder Mandant kann bis zu 10 Verbindungen erstellen.
