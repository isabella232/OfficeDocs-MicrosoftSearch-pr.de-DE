---
title: Connectors (Übersicht)
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
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367523"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Übersicht über Microsoft Graph-Connectors

[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indiziert alle Ihre [Microsoft 365](https://www.microsoft.com/microsoft-365) -Daten, damit Sie für Benutzer durchsucht werden können. Mit Microsoft Graph-Connectors kann Ihre Organisation Daten von Drittanbietern indizieren, damit diese in Microsoft-Suchergebnissen angezeigt werden. Dadurch werden die Arten von Inhaltsquellen erweitert, die in Ihren Microsoft 365-Produktivitäts-apps und dem breiteren Microsoft-Ökosystem durchsucht werden können. Die drittanbieterdaten können lokal oder in öffentlichen oder privaten Clouds gehostet werden.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Der Rest dieses Artikels soll Microsoft 365 Administratoren dabei helfen, die Ressourcen zu finden, die für die Beantwortung der folgenden Fragen zur Verfügung stehen:

* [Welche Datenquellen können mit Microsoft Search verbunden werden?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Wie verwalte ich meine Verbindungen?](#how-do-i-manage-my-connections)
* [Was sind die Lizenzanforderungen und Nutzungsbedingungen für Graph Connectors?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [Wie kann ich Suchergebnisse anpassen und konfigurieren?](#how-do-i-customize-and-configure-search-results)
* [Wie kann ich meine connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> Microsoft Graph-Connectors und Microsoft Search-APIs sind jetzt allgemein verfügbar. Die ersten Rollouts erfolgen für Kunden, die für eine gezielte Veröffentlichung konfiguriert sind. Wenn Sie einen Graph-Konnektor in Ihrem Mandanten verwenden möchten, müssen sich Benutzer und Administratoren für eine [gezielte Veröffentlichung](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)entscheiden.

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

Microsoft bietet zehn Graph-Konnektoren, und unsere Ökosystempartner haben mehr als 100 zusätzliche Graph-Konnektoren erstellt. Sie können auch einen eigenen Graph-Konnektor erstellen. 

### <a name="graph-connectors-by-microsoft"></a>Graph-Konnektoren von Microsoft

Sie können eine Verbindung mit den folgenden Datenquellen herstellen, indem Sie von Microsoft erstellte Graph-Konnektoren verwenden:

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

Der [Gallery Graph Connectors](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen Graph-Konnektoren. Wenn Sie bereit sind, eine dieser Datenquellen mit Ihrem Mandanten zu verbinden, lesen Sie unbedingt die [Setup-Übersicht](configure-connector.md) und alle anderen Artikel im Abschnitt Setup Connectors by Microsoft, die für Ihre Datenquelle gelten.

### <a name="graph-connectors-by-our-partners"></a>Graph-Konnektoren von unseren Partnern

Der [Microsoft Graph Connectors-Katalog](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen Graph-Konnektoren, die von unseren Partnern erstellt wurden, sowie einen Link zu den Websites der einzelnen Partner. Wenden Sie sich direkt an jeden Partner, um weitere Informationen zu erhalten.

### <a name="build-your-own-graph-connector"></a>Erstellen eines eigenen Graph-Konnektors

Wenn Sie einen eigenen Graph-Konnektor erstellen möchten, finden Sie weitere Informationen unter [Übersicht über die Microsoft-Such-API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) .

## <a name="how-do-i-manage-my-connections"></a>Wie verwalte ich meine Verbindungen?

Sie können Ihre Verbindungen über die [Registerkarte Connectors](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) im [Microsoft 365 Admin Center](https://admin.microsoft.com/)verwalten. Weitere Informationen finden Sie unter [Manage Your Connections](manage-connector.md) .

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>Was sind die Lizenzanforderungen und Nutzungsbedingungen für Graph Connectors?

Für Benutzer in Ihrer Organisation benötigen Sie eine gültige Microsoft 365-oder Office 365-Lizenz sowie ausreichende Graph-Konnektoren, um Daten aus Konnektoren in ihren Suchergebnissen anzuzeigen.

Weitere Informationen finden Sie unter [License Requirements and Pricing](licensing.md) and [Terms of use](terms-of-use.md).

## <a name="how-do-i-customize-and-configure-search-results"></a>Wie kann ich Suchergebnisse anpassen und konfigurieren?

Es gibt eine Reihe von Möglichkeiten zum Anpassen und Konfigurieren von Suchergebnissen. Weitere Informationen finden Sie in den folgenden Artikeln:

* [Branchen und Ergebnistypen verwalten](customize-search-page.md)
* [Verwalten von Layouts für Suchergebnisse](customize-results-layout.md)
* [Verwalten des Ergebnis Clusters](result-cluster.md)
* [Verwalten von benutzerdefinierten Filtern](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Wie kann ich meine connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?

Nachdem benutzerdefinierte Daten indiziert wurden, können Entwickler [diese Daten Abfragen](https://docs.microsoft.com/graph/search-concept-custom-types). Sie können Ihre Daten in einer beliebigen Anwendung anzeigen. Weitere Informationen finden Sie in der [Übersicht über die Microsoft-Such-API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).
