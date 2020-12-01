---
title: Ergebnis Cluster "Connectors"
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
description: Details der Connectors result Cluster Experience
ms.openlocfilehash: fa6ac2dc720ed43e40454b952526734accd45ea4
ms.sourcegitcommit: a328b9764abf5cd0c1c0a8c7def0c6e334da9a1d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477113"
---
# <a name="graph-connectors-result-cluster"></a>Ergebnis Cluster "Graph Connectors"

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Übersicht über den Ergebnis Cluster "Graph Connectors" (Vorschau)  

Mit Graph Connectors result Clusters können Unternehmen in Ihrer Standardansicht (Registerkarte alle) in SharePoint und Office.com nach Inhalten aus Drittanbieter-Datenquellen suchen.

Ergebnis Cluster helfen Benutzern bei der Ermittlung aller Inhalte von Drittanbietern (previoulsy, die an einen einzelnen Connector und eine vertikale Verbindung gebunden sind) an einer Stelle. Die in einem Ergebnis Cluster angezeigten Ergebnisse werden basierend auf der Konfiguration des Mandanten Administrators in einer Such Sparte zusammengefasst.  

## <a name="how-connector-results-are-selected-and-displayed"></a>Auswählen und Anzeigen von Verbindungs Ergebnissen

Die im Ergebnis Cluster bereitgestellten Connector-Ergebnisse werden von einzelnen Such vertikalen mit Connector-Inhalten abgeleitet. Jede vertikale Suche enthält eine Reihe relevanter Ergebnisse, die zu einem Kandidaten Ergebnis Cluster werden. Relevante Ergebnisse werden basierend auf der Eigenschaft "Title", dem Ergebnisausschnitt und der Inhaltskomponente jedes Elements ausgewählt.

Um sicherzustellen, dass Inhalte aus den Such vertikalen gefunden werden, wird empfohlen, aussagekräftige Titel für ihre Elemente bereitzustellen. Dies wirkt sich positiv auf das Schiedsverfahren von Ergebnis Cluster Kandidaten und die Wahrscheinlichkeit aus, dass Ihre Inhalte in einem Ergebnis Cluster angezeigt werden. Vermeiden Sie beispielsweise die Verwendung von IDs als Werte für die Eigenschaft "Title", es sei denn, Ihre Benutzer verwenden IDs, um nach Inhalten zu suchen.

Wie oft ein Ergebnis Cluster angezeigt wird, hängt von Faktoren wie der Anzahl der von Ihnen konfigurierten Such vertikalen Elementen und dem Typ des Inhalts ab. Wenn Sie Ergebnis Cluster Ergebnisse entweder auswählen oder ignorieren, werden Sie implizit Hinweise bereitstellen, mit denen das Auslösen von Ergebnis Clustern im Laufe der Zeit angepasst wird.

Die Suchergebnis Erfahrung für Connector-Elemente, die in ihrem Ergebnis Cluster angezeigt werden, wird vom System generiert und verwendet keine benutzerdefinierten Ergebnis Layouts. Sie müssen die Eigenschaft "Title" und den Elementinhalt während der Verbindungs Registrierung deklarieren, wenn die Ergebnisse im Ergebnis Cluster angezeigt werden sollen.

## <a name="enable-result-clusters"></a>Ergebnis Cluster aktivieren
  
Die Ergebnis Cluster Erfahrung ist standardmäßig deaktiviert.  

Führen Sie die folgenden Schritte aus, um die Benutzeroberfläche auf Organisationsebene zu aktivieren:

1. Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/)zu **Einstellungen** für die  >  **Suche & Intelligence**  >  **Customization**  >  **Verticals**.  
2. Wählen Sie die Option **alle** vertikal aus, und aktivieren Sie dann **Show Connector results**. 


Führen Sie die folgenden Schritte aus, um die Benutzeroberfläche auf Websiteebene zu aktivieren:

1. Wechseln Sie auf der SharePoint-Website, auf der Sie das Ergebnis-Cluster-Erlebnis wünschen, zu **Einstellungen**.
2. Wechseln Sie zu **Website Informationen** > **Alle Websiteeinstellungen anzeigen**.
3. Wechseln Sie zum Abschnitt Microsoft-Suche, und wählen Sie dann **Microsoft-Suche für diese Websitesammlung konfigurieren** aus.
4. Wechseln Sie im Navigationsbereich zu **benutzerdefiniertes Erlebnis**, und wählen Sie dann **vertikal** aus.
5. Wählen Sie die Option **alle** vertikal aus, und aktivieren Sie dann **Show Connector results**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Anzeigen der Ergebnis Cluster Erfahrung nach der Aktivierung

Nachdem Sie die Ergebnis Cluster Erfahrung aktiviert haben, kann es einige Minuten dauern, bis Sie Sie anzeigen können. Wenn Sie die Benutzeroberfläche sofort nutzen möchten, können Sie *cacheClear = true* an die URL in SharePoint und Office anfügen.
