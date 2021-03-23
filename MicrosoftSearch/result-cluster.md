---
title: Connectors-Ergebniscluster
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Details zur Connector-Ergebniscluster-Erfahrung
ms.openlocfilehash: ae5528f2e12c9e331b66e821f2a9c03947d788df
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031773"
---
# <a name="graph-connectors-result-cluster"></a>Ergebniscluster für Graphconnectors

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Übersicht über den Graph Connectors-Ergebniscluster (Vorschau)  

Mit Ergebnisclustern von Graph Connectors können Unternehmen in ihrer Standardansicht, auf der Registerkarte **Alle,** in SharePoint, Office.com und Microsoft Search in Bing nach Inhalten aus Datenquellen von Drittanbietern suchen.

Ergebniscluster helfen Benutzern, alle Inhalte von Drittanbietern an einem Ort zu ermitteln. Die in einem Ergebniscluster angezeigten Ergebnisse werden basierend auf der vertikalen Suchkonfiguration gruppiert.

## <a name="how-connector-results-are-selected-and-displayed"></a>Auswahl und Anzeige von Connectorergebnissen

Im Ergebniscluster bereitgestellte Connectorergebnisse werden von einzelnen Such vertikal mit Connectorinhalt abgeleitet. Jede Such vertikal bietet eine Reihe relevanter Ergebnisse, die zu einem Kandidatenergebniscluster werden. Relevante Ergebnisse werden basierend auf der "title"-Eigenschaft und der "content"-Eigenschaft jedes Elements ausgewählt. Die Content-Eigenschaft wird im *Schema als isContent=true* markiert.

Um sicherzustellen, dass Inhalte aus den Such vertikal gefunden werden, wird empfohlen, aussagekräftige Titel für Ihre Elemente zur Verfügung zu stellen. Dies wirkt sich positiv auf die Vermittlung von Ergebnisclusterkandidaten und die Wahrscheinlichkeit aus, dass Ihre Inhalte in einem Ergebniscluster angezeigt werden. Vermeiden Sie beispielsweise die Verwendung von IDs als Werte für die Eigenschaft "title", es sei denn, Ihre Benutzer verwenden IDs, um nach Inhalten zu suchen.

Wie oft ein Ergebniscluster angezeigt wird, hängt von Faktoren ab, z. B. von der Anzahl der konfigurierten Such vertikaler Suchtypen und dem Inhaltstyp. Durch die Interaktion oder das Ignorieren eines Ergebnisclusters geben Benutzer implizit Hinweise, die ihre Auslösung im Laufe der Zeit anpassen.

Die Suchergebniserfahrung für Connectorelemente, die in Ihrem Ergebniscluster angezeigt werden, verwendet [von](./customize-search-page.md#create-your-own-result-type) Ihnen definierte Ergebnistypen. Wenn kein Ergebnistyp konfiguriert ist, wird [ein vom System generiertes Layout](./customize-search-page.md#default-search-result-layout) verwendet. 

Es wird empfohlen, die "title"-Eigenschaft als Suchergebnistitel und die "content"-Eigenschaft als Suchbeschreibung zu verwenden. Dies bietet den Benutzern die beste Erfahrung durch genaues Auslösen des Ergebnisclusters und der relevantesten Ergebnisse im Cluster. 

## <a name="enable-result-clusters"></a>Aktivieren von Ergebnisclustern
  
Die Ergebnisclustererfahrung ist standardmäßig deaktiviert.  

Führen Sie die folgenden Schritte aus, um die Benutzererfahrung auf Organisationsebene zu aktivieren:

1. Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Wählen Sie die **Vertikale Alle** aus, und aktivieren Sie **dann Konnektorergebnisse anzeigen.** 


Führen Sie die folgenden Schritte aus, um die Benutzererfahrung auf SharePoint-Websiteebene zu aktivieren:

1. Wechseln Sie auf der SharePoint-Website, auf der Sie die Ergebnisclustererfahrung wünschen, zu **Einstellungen**.
2. Wechseln Sie zu **Websiteinformationen** > **Alle Websiteeinstellungen anzeigen**.
3. Wechseln Sie zum Abschnitt Microsoft Search, und wählen Sie **Dann Konfigurieren von Microsoft Search für diese Websitesammlung aus.**
4. Wechseln Sie im Navigationsbereich zu **Benutzerdefinierte Benutzerdefinierte Benutzererfahrung,** und wählen Sie **dann Vertikal aus.**
5. Wählen Sie die **Vertikale Alle** aus, und aktivieren Sie **dann Konnektorergebnisse anzeigen.**

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Anzeigen der Ergebnisclustererfahrung nach der Aktivierung

Nachdem Sie die Ergebnisclustererfahrung aktivieren, kann es bis zu 12 Stunden dauern, bis Sie sie anzeigen können. Wenn Sie die Erfahrung sofort wünschen, können Sie *cacheClear=true* an die URL in SharePoint und Office anhängen.