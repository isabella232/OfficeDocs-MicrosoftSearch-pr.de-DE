---
title: Übersicht über Connectors
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
description: Übersicht über Microsoft Graph Connectors für Microsoft Search
ms.openlocfilehash: 677c91f121185faa6dc96f80c517917f429a3ab0
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847519"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Übersicht über Microsoft Graph Connectors

[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indiziert alle [Ihre Microsoft 365-Daten,](https://www.microsoft.com/microsoft-365) um sie für Benutzer durchsuchbar zu machen. Mit Microsoft Graph Connectors kann Ihre Organisation Drittanbieterdaten indizieren, sodass sie in den Microsoft Search-Ergebnissen angezeigt werden. Dadurch werden die Typen von Inhaltsquellen erweitert, die in Ihren Microsoft 365-Produktivitäts-Apps und dem umfassenderen Microsoft-Ökosystem durchsuchbar sind. Die Drittanbieterdaten können lokal oder in öffentlichen oder privaten Clouds gehostet werden.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Der Rest dieses Artikels soll Microsoft 365-Administratoren dabei helfen, die verfügbaren Ressourcen für die Beantwortung der folgenden Fragen zu finden:

* [Welche Datenquellen können mit Microsoft Search verbunden werden?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Wie verwalte ich meine Verbindungen?](#how-do-i-manage-my-connections)
* [Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Graph-Connectors?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [Wie kann ich Suchergebnisse anpassen und konfigurieren?](#how-do-i-customize-and-configure-search-results)
* [Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> Microsoft Graph Connectors und Microsoft Search-APIs sind jetzt allgemein verfügbar. Die ersten Rollouts sind für Kunden, die für die gezielte Veröffentlichung konfiguriert sind. Wenn Sie einen Graph Connector in Ihrem Mandanten verwenden möchten, müssen Sich Benutzer und Administratoren für die [Zielversion entscheiden.](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Welche Datenquellen können mit Microsoft Search verbunden werden?

Microsoft bietet zehn Graph-Connectors, und unsere Ökosystempartner haben mehr als 100 zusätzliche Graph Connectors erstellt. Sie können auch einen eigenen Graph-Connector erstellen. 

### <a name="graph-connectors-by-microsoft"></a>Microsoft Graph-Connectors

Sie können mithilfe von von Microsoft erstellten Graph-Connectors eine Verbindung mit den folgenden Datenquellen herstellen:

<!---Need to add a few links below when docs exist--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* Azure SQL
* [Unternehmenswebsites](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server ](MSSQL-connector.md)
* [Dateifreigabe](fileshare-connector.md)
* Oracle (Vorschau)
* [Salesforce (Vorschau)](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

Der [Graph Connectors Gallery](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen Graph-Connectors. Wenn Sie bereit sind, eine dieser Datenquellen mit Ihrem [](configure-connector.md) Mandanten zu verbinden, lesen Sie unbedingt die Setupübersicht und alle anderen Artikel im Abschnitt "Setupconnectors von Microsoft", die für Ihre Datenquelle gelten.

### <a name="graph-connectors-by-our-partners"></a>Graph connectors von unseren Partnern

Der [Microsoft Graph Connectors Gallery](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen graph-Connectors, die von unseren Partnern erstellt wurden, sowie einen Link zur Website der einzelnen Partner. Wenden Sie sich direkt an jeden Partner, um weitere Informationen zu erhalten.

### <a name="build-your-own-graph-connector"></a>Erstellen Eines eigenen Graph-Connectors

Wenn Sie einen eigenen Graph-Connector erstellen möchten, finden Sie weitere Informationen in der Übersicht über die [Microsoft Search-API in Microsoft Graph.](https://docs.microsoft.com/graph/search-concept-overview)

## <a name="how-do-i-manage-my-connections"></a>Wie verwalte ich meine Verbindungen?

Sie können Ihre Verbindungen über die Registerkarte ["Connectors"](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) im [Microsoft 365 Admin Center verwalten.](https://admin.microsoft.com/) Weitere [Informationen finden Sie unter "Verwalten](manage-connector.md) Ihrer Verbindungen".

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Graph-Connectors?

Sie benötigen eine gültige Microsoft 365- oder Office 365-Lizenz und ein ausreichendes Graph Connectors-Kontingent, damit Benutzer in Ihrer Organisation Daten von Connectors in ihren Suchergebnissen anzeigen können.

Weitere Informationen finden Sie unter [Lizenzanforderungen, Preise](licensing.md) und [Nutzungsbedingungen.](terms-of-use.md)

## <a name="how-do-i-customize-and-configure-search-results"></a>Wie kann ich Suchergebnisse anpassen und konfigurieren?

Es gibt eine Reihe von Möglichkeiten zum Anpassen und Konfigurieren von Suchergebnissen. Weitere Informationen finden Sie in den folgenden Artikeln:

* [Branchen und Ergebnistypen verwalten](customize-search-page.md)
* [Verwalten von Layouts für Suchergebnisse](customize-results-layout.md)
* [Verwalten von Ergebnisclusters](result-cluster.md)
* [Verwalten benutzerdefinierter Filter](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?

Nachdem benutzerdefinierte Daten indiziert wurden, können Entwickler [diese Daten abfragen.](https://docs.microsoft.com/graph/search-concept-custom-types) Sie können Ihre Daten in jeder Anwendung anzeigen. Weitere Informationen finden Sie in der [Übersicht über die Microsoft Search-API in Microsoft Graph.](https://docs.microsoft.com/graph/search-concept-overview)

## <a name="limitations"></a>Einschränkungen

* Wenn Sie **einen** von Microsoft erstellten Connector veröffentlichen, kann es einige Minuten dauern, bis die Verbindung erstellt wurde. Während dieser Zeit zeigt die Verbindung ihren Status als ausstehend an.

* Das [Microsoft 365 Admin Center](https://admin.microsoft.com) unterstützt  die Bearbeitung des Suchschemas nach der Veröffentlichung einer Verbindung nicht. Um das Suchschema zu bearbeiten, löschen Sie Ihre Verbindung, und erstellen Sie dann eine neue.

* Der Erfassungsdurchsatz wird bei etwa vier Elementen pro Sekunde gedrosselt.

* Schemaupdates werden nicht unterstützt. Nachdem Sie eine Verbindungseinrichtung erstellt haben, gibt es keine Möglichkeit, das Schema zu aktualisieren. Sie können die Verbindung nur löschen und neu erstellen.

* Es gibt ein Verbindungslimit. Jeder Mandant kann bis zu 10 Verbindungen erstellen.

* Die Bearbeitungsunterstützung für die Verbindung ist nicht verfügbar. Nachdem die Verbindung erstellt wurde, können Sie sie nicht mehr bearbeiten oder ändern. Wenn Sie Details ändern müssen, müssen Sie die Verbindung löschen und neu erstellen.
