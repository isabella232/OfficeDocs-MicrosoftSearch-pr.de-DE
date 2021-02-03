---
title: Ergebniscluster für Connectors
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
description: Details zur Connectorergebnisclustererfahrung
ms.openlocfilehash: fb29fb9c14811698fb7c5d043853b57231c76a0b
ms.sourcegitcommit: d1bc6c41ecf47584373ce57543502bed55753d0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080837"
---
# <a name="graph-connectors-result-cluster"></a>Ergebniscluster für Graph connectors

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Übersicht über den Ergebniscluster "Graph Connectors" (Vorschau)  

Mit Ergebnisclustern für Graph Connectors können Unternehmen in ihrer Standardansicht, auf der Registerkarte "Alle", in SharePoint, Office.com und Microsoft Search in Bing nach Inhalten aus Drittanbieterdatenquellen suchen. 

Ergebniscluster helfen Benutzern, alle Inhalte von Drittanbietern an einem Ort zu finden. Die in einem Ergebniscluster angezeigten Ergebnisse werden basierend auf der Suchkonfiguration gruppiert.

## <a name="how-connector-results-are-selected-and-displayed"></a>Auswahl und Anzeige von Connectorergebnissen

Die im Ergebniscluster bereitgestellten Konnektorergebnisse werden von einzelnen Such vertikal mit Connectorinhalt abgeleitet. Jede Such vertikal stellt eine Reihe relevanter Ergebnisse zur Wahl eines Ergebnisclusters zur Wahl. Relevante Ergebnisse werden basierend auf der "title"-Eigenschaft und der "content"-Eigenschaft jedes Elements ausgewählt. Die Inhaltseigenschaft ist im Schema *als "isContent=true"* gekennzeichnet.

Um die Suche nach Inhalten aus den Such vertikal sicherzustellen, wird empfohlen, aussagekräftige Titel für Ihre Elemente zur Verfügung zu stellen. Dies wirkt sich positiv auf die Vermittlung von Ergebnisclusterkandidaten und die Wahrscheinlichkeit aus, dass Ihre Inhalte in einem Ergebniscluster angezeigt werden. Vermeiden Sie beispielsweise die Verwendung von IDs als Werte für die Eigenschaft "title", es sei denn, Ihre Benutzer verwenden IDs, um nach Inhalten zu suchen.

Wie oft ein Ergebniscluster angezeigt wird, hängt von Faktoren ab, z. B. von der Anzahl der konfigurierten Such vertikaler Suchressourcen und vom Inhaltstyp. Durch die Interaktion oder das Ignorieren eines Ergebnisclusters stellen Benutzer implizit Hinweise zur Verfügung, mit denen die Auslösung im Laufe der Zeit angepasst wird.

Die Suchergebniserfahrung für Connectorelemente, die in Ihrem Ergebniscluster angezeigt werden, verwendet [von](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) Ihnen definierte Ergebnistypen. Wenn kein Ergebnistyp konfiguriert ist, wird ein vom System [generiertes](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) Layout verwendet. 

Es wird empfohlen, die Eigenschaft "title" als Suchergebnistitel und die Eigenschaft "content" als Suchbeschreibung zu verwenden. Dies bietet den Benutzern die beste Benutzererfahrung durch genaues Auslösen des Ergebnisclusters und relevanteste Ergebnisse im Cluster. 

## <a name="enable-result-clusters"></a>Aktivieren von Ergebnisclustern
  
Die Ergebnisclustererfahrung ist standardmäßig deaktiviert.  

Führen Sie die folgenden Schritte aus, um die Benutzererfahrung auf Organisationsebene zu aktivieren:

1. Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**"Vertikal".**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Wählen Sie die **Vertikale "Alle"** aus, und aktivieren **Sie dann "Connectorergebnisse anzeigen".** 


Führen Sie die folgenden Schritte aus, um die Benutzererfahrung auf der Ebene der SharePoint-Website zu aktivieren:

1. Wechseln Sie auf der SharePoint-Website, auf der Sie die Ergebnisclustererfahrung wünschen, zu **"Einstellungen".**
2. Wechseln Sie zu **Websiteinformationen** > **Anzeigen aller Websiteeinstellungen.**
3. Wechseln Sie zum Microsoft Search-Abschnitt, und wählen Sie dann **"Microsoft Search für diese Websitesammlung konfigurieren" aus.**
4. Wechseln Sie im Navigationsbereich zu **"Benutzerdefiniert",** und wählen Sie dann **"Vertikal" aus.**
5. Wählen Sie die **Vertikale "Alle"** aus, und aktivieren **Sie dann "Connectorergebnisse anzeigen".**

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Anzeigen der Ergebnisclustererfahrung nach der Aktivierung

Nachdem Sie die Ergebnisclustererfahrung aktivieren, kann es bis zu 12 Stunden dauern, bis Sie sie anzeigen können. Wenn sie sofort angezeigt werden soll, können Sie *cacheClear=true* an die URL in SharePoint und Office anfügen.
