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
description: Details zur Connectors-Ergebnisclusteroberfläche
ms.openlocfilehash: 912e27942e9ae3bfef874ae66227880af676b7a1a28449cc82ae8fc02f4446c0
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533977"
---
# <a name="graph-connectors-result-cluster"></a>ergebniscluster für Graph Connectors

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Übersicht über den Ergebniscluster Graph Connectors (Vorschau)  

Mit Graph Connectors-Ergebnisclustern können Unternehmen in ihrer Standardansicht, der Registerkarte **"Alle",** in SharePoint, Office.com und Microsoft Search in Bing nach Inhalten aus Datenquellen von Drittanbietern suchen.

Ergebniscluster helfen Benutzern, alle Inhalte von Drittanbietern an einem Ort zu finden. Die in einem Ergebniscluster angezeigten Ergebnisse werden basierend auf der vertikalen Suchkonfiguration gruppiert.

## <a name="how-connector-results-are-selected-and-displayed"></a>Auswählen und Anzeigen der Connectorergebnisse

Die im Ergebniscluster bereitgestellten Connectorergebnisse werden von einzelnen Such-Vertikalen mit Connectorinhalt abgeleitet. Jede Such vertical provides a set of relevant results which becomes a candidate result cluster. Relevante Ergebnisse werden basierend auf der Eigenschaft "title" und "content" jedes Elements ausgewählt. Die Inhaltseigenschaft ist im Schema als *"isContent=true"* gekennzeichnet.

Um die Erkennung von Inhalten aus den Such-Vertikalen sicherzustellen, empfehlen wir die Bereitstellung aussagekräftiger Titel für Ihre Elemente. Dies wirkt sich positiv auf die Vermittlung von Ergebnisclusterkandidaten und die Wahrscheinlichkeit aus, dass Ihre Inhalte in einem Ergebniscluster angezeigt werden. Vermeiden Sie beispielsweise die Verwendung von IDs als Werte für den Eigenschaftstitel, es sei denn, Ihre Benutzer verwenden IDs, um nach Inhalten zu suchen.

Wie oft ein Ergebniscluster angezeigt wird, hängt von Faktoren wie der Anzahl der von Ihnen konfigurierten Such-Vertikalen und dem Inhaltstyp ab. Durch die Interaktion oder Das Ignorieren eines Ergebnisclusters geben Benutzer implizit Hinweise an, die die Auslösung im Laufe der Zeit anpassen.

Die Suchergebnisoberfläche für die in Ihrem Ergebniscluster angezeigten Connectorelemente verwendet von Ihnen definierte [Ergebnistypen.](./customize-search-page.md#create-your-own-result-type) Wenn kein Ergebnistyp konfiguriert ist, wird ein [vom System generiertes Layout](./customize-search-page.md#default-search-result-layout) verwendet. 

Es wird empfohlen, die Eigenschaft "title" als Suchergebnistitel und die Eigenschaft "content" als Suchbeschreibung zu verwenden. Dies bietet Ihren Benutzern die beste Erfahrung durch genaues Auslösen des Ergebnisclusters und der relevantesten Ergebnisse im Cluster. 

## <a name="enable-result-clusters"></a>Aktivieren von Ergebnisclustern
  
Die Ergebnisclusteroberfläche ist standardmäßig deaktiviert.  

Führen Sie die folgenden Schritte aus, um die Erfahrung auf Organisationsebene zu aktivieren:

1. Wechseln [Sie](https://admin.microsoft.com)im Microsoft 365 Admin Center zu [**"Verticals".**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Wählen Sie die vertikale **Option "Alle"** aus, und aktivieren Sie dann die Ergebnisse des **Verbinders anzeigen.** 


Führen Sie die folgenden Schritte aus, um die Benutzeroberfläche auf SharePoint Websiteebene zu aktivieren:

1. Wechseln Sie auf dem SharePoint Standort, an dem Sie die Ergebnisclusterumgebung verwenden möchten, zu **Einstellungen.**
2. Wechseln Sie zu **"Websiteinformationen** > **Anzeigen aller Websiteeinstellungen".**
3. Wechseln Sie zum Abschnitt Microsoft Search, und wählen Sie dann **Microsoft Search für diese Websitesammlung** konfigurieren aus.
4. Wechseln Sie im Navigationsbereich zu **"Benutzerdefinierte Oberfläche",** und wählen Sie dann **"Vertikal" aus.**
5. Wählen Sie die vertikale **Option "Alle"** aus, und aktivieren Sie dann die Ergebnisse des **Verbinders anzeigen.**

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Anzeigen der Ergebnisclustererfahrung nach der Aktivierung

Nachdem Sie die Ergebnisclusterumgebung aktiviert haben, kann es bis zu 12 Stunden dauern, bis Sie sie anzeigen können. Wenn Sie die Erfahrung sofort wünschen, können Sie *cacheClear=true* an die URL in SharePoint und Office anfügen.