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
ms.openlocfilehash: f2355213a0b1821968c801153841c274e539d72e
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773027"
---
# <a name="graph-connectors-result-cluster"></a>Ergebnis Cluster "Graph Connectors"

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Übersicht über den Ergebnis Cluster "Graph Connectors" (Vorschau)  

Mit Graph Connectors result Clusters können Unternehmen in Ihrer Standardansicht, der Registerkarte **alle** , in SharePoint, Office.com und Microsoft Search in Bing nach Inhalten von Drittanbieter-Datenquellen suchen.

Ergebnis Cluster helfen Benutzern, alle Inhalte von Drittanbietern an einer einzigen Stelle zu entdecken. Die in einem Ergebnis Cluster angezeigten Ergebnisse werden basierend auf der Such vertikalen Konfiguration zusammengefasst.

## <a name="how-connector-results-are-selected-and-displayed"></a>Auswählen und Anzeigen von Verbindungs Ergebnissen

Die im Ergebnis Cluster bereitgestellten Connector-Ergebnisse werden von einzelnen Such vertikalen mit Connector-Inhalten abgeleitet. Jede vertikale Suche enthält eine Reihe relevanter Ergebnisse, die zu einem Kandidaten Ergebnis Cluster werden. Relevante Ergebnisse werden basierend auf der Eigenschaft "Title" und der Eigenschaft "Content" jedes Elements ausgewählt. Die Content-Eigenschaft wird im Schema als *iscontent = true* gekennzeichnet.

Um sicherzustellen, dass Inhalte aus den Such vertikalen gefunden werden, wird empfohlen, aussagekräftige Titel für ihre Elemente bereitzustellen. Dies wirkt sich positiv auf das Schiedsverfahren von Ergebnis Cluster Kandidaten und die Wahrscheinlichkeit aus, dass Ihre Inhalte in einem Ergebnis Cluster angezeigt werden. Vermeiden Sie beispielsweise die Verwendung von IDs als Werte für die Eigenschaft "Title", es sei denn, Ihre Benutzer verwenden IDs, um nach Inhalten zu suchen.

Wie oft ein Ergebnis Cluster angezeigt wird, hängt von Faktoren wie der Anzahl der von Ihnen konfigurierten Such vertikalen Elementen und dem Typ des Inhalts ab. Durch Interaktion oder Ignorierung eines Ergebnis Clusters geben Benutzer implizit Hinweise an, mit denen die Auslösung im Laufe der Zeit angepasst wird.

Die Suchergebnis Erfahrung für Konnektoren, die im Ergebnis Cluster angezeigt werden, verwendet [Ergebnistypen](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) , die von Ihnen definiert wurden. Wenn kein Ergebnistyp konfiguriert ist, wird ein vom [System generiertes Layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) verwendet. 

Es wird empfohlen, die Eigenschaft "Title" als Suchergebnis Titel und die Eigenschaft "Inhalt" als Such Beschreibung zu verwenden. Dadurch erhalten Ihre Benutzer die beste Erfahrung durch eine genaue Auslösung des Ergebnis Clusters und der relevantesten Ergebnisse im Cluster. 

## <a name="enable-result-clusters"></a>Ergebnis Cluster aktivieren
  
Die Ergebnis Cluster Erfahrung ist standardmäßig deaktiviert.  

Führen Sie die folgenden Schritte aus, um die Benutzeroberfläche auf Organisationsebene zu aktivieren:

1. Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**vertikal**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Wählen Sie die Option **alle** vertikal aus, und aktivieren Sie dann **Show Connector results**. 


Führen Sie die folgenden Schritte aus, um die Benutzerfreundlichkeit auf der SharePoint-Websiteebene zu aktivieren:

1. Wechseln Sie auf der SharePoint-Website, auf der Sie das Ergebnis-Cluster-Erlebnis wünschen, zu **Einstellungen**.
2. Wechseln Sie zu **Website Informationen** > **Alle Websiteeinstellungen anzeigen**.
3. Wechseln Sie zum Abschnitt Microsoft-Suche, und wählen Sie dann **Microsoft-Suche für diese Websitesammlung konfigurieren** aus.
4. Wechseln Sie im Navigationsbereich zu **benutzerdefiniertes Erlebnis**, und wählen Sie dann **vertikal** aus.
5. Wählen Sie die Option **alle** vertikal aus, und aktivieren Sie dann **Show Connector results**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Anzeigen der Ergebnis Cluster Erfahrung nach der Aktivierung

Nachdem Sie die Ergebnis Cluster Erfahrung aktiviert haben, kann es einige Minuten dauern, bis Sie Sie anzeigen können. Wenn Sie die Benutzeroberfläche sofort nutzen möchten, können Sie *cacheClear = true* an die URL in SharePoint und Office anfügen.
