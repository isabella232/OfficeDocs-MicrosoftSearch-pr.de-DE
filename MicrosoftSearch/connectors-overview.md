---
title: Übersicht über Microsoft Graph Connectors
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Übersicht über Microsoft Graph Connectors für Microsoft Search
ms.openlocfilehash: 006ab3f56eb4976b44904e5191ae8fd256c8d5de
ms.sourcegitcommit: 3e069fd920b5fcdfe97a0261930447e9e87d9013
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973525"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a>Übersicht über Microsoft Graph-Connectors

[Microsoft Search](./overview-microsoft-search.md) indiziert alle [Microsoft 365](https://www.microsoft.com/microsoft-365) Daten, damit sie für Benutzer durchsucht werden können. Mit Microsoft Graph Connectors kann Ihre Organisation Drittanbieterdaten so indizieren, dass sie in Microsoft Search Ergebnissen angezeigt werden. Dieses Feature erweitert die Arten von Inhaltsquellen, die in Ihren Microsoft 365-Produktivitäts-Apps und im breiteren Microsoft-Ökosystem durchsuchbar sind. Die Drittanbieterdaten können lokal oder in den öffentlichen oder privaten Clouds gehostet werden.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Dieser Artikel soll Microsoft 365 Administratoren helfen, die Ressourcen zu finden, die für die Beantwortung der folgenden Fragen verfügbar sind:

* [Welche Datenquellen können mit Microsoft Search verbunden werden?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Wie verwalte ich meine Verbindungen?](#how-do-i-manage-my-connections)
* [Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Microsoft Graph Connectors?](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [Was sind die Vorschaufeatures?](#what-are-the-preview-features)
* [Wie kann ich Suchergebnisse anpassen und konfigurieren?](#how-do-i-customize-and-configure-search-results)
* [Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?](#how-do-i-search-my-connector-data-from-a-custom-application)
* [Wie kann ich Suchergebnisse anpassen?](#how-do-i-customize-search-results)
* [Was sind die Connectoreinschränkungen?](#what-are-the-connector-limitations)

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](./overview-microsoft-search.md) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Welche Datenquellen können mit Microsoft Search verbunden werden?

Microsoft bietet 9 Connectors, und unsere Ökosystempartner haben über 100 weitere Connectors erstellt. Sie können auch einen eigenen Connector erstellen.

### <a name="microsoft-graph-connectors-by-microsoft"></a>Microsoft Graph Connectors von Microsoft

Sie können über von Microsoft erstellte Connectors eine Verbindung mit den folgenden Datenquellen herstellen:

<!---Add links below when new docs are created--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [Azure SQL und Microsoft SQL Server](MSSQL-connector.md)
* [Confluence Cloud (Vorschau)](confluence-cloud-connector.md)
* [Unternehmenswebsites](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Dateifreigabe](fileshare-connector.md)
* [Oracle SQL](OracleSQL-connector.md)
* [Salesforce](salesforce-connector.md)
* [ServiceNow-Wissen](servicenow-knowledge-connector.md)
* [ServiceNow-Katalog (Vorschau)](servicenow-catalog-connector.md)


Der [Microsoft Graph Connectors-Katalog](https://www.microsoft.com/microsoft-search/connectors) enthält eine kurze Beschreibung dieser Connectors. Wenn Sie bereit sind, eine dieser Datenquellen mit Ihrem Mandanten zu verbinden, lesen Sie unbedingt die [Setupübersicht](configure-connector.md) und alle anderen Artikel im Abschnitt "Setup connectors by Microsoft", die für Ihre Datenquelle gelten.

### <a name="microsoft-graph-connectors-by-our-partners"></a>Microsoft Graph Connectors von unseren Partnern

Der [Connectorkatalog](https://www.microsoft.com/microsoft-search/connectors) von Microsoft Graph enthält eine kurze Beschreibung der einzelnen Connectors, die von unseren Partnern erstellt wurden, sowie einen Link zur Website jedes Partners. Um mehr zu erfahren, wenden Sie sich direkt an jeden Partner.

### <a name="build-your-own-microsoft-graph-connector"></a>Erstellen Eines eigenen Microsoft Graph-Connectors

Sie können ihren eigenen Connector erstellen, wenn Sie möchten. Weitere Informationen zum Erstellen von Connectors finden Sie unter [Erstellen Ihres ersten benutzerdefinierten Microsoft Graph Connectors.](/graph/connecting-external-content-build-quickstart)

## <a name="how-do-i-manage-my-connections"></a>Wie verwalte ich meine Verbindungen?

Sie können Ihre Verbindungen über die [Registerkarte Connectors](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) im [Microsoft 365 Admin Center](https://admin.microsoft.com/)verwalten. Weitere Informationen zum Verwalten von Verbindungen finden Sie unter: [Verwalten Ihrer Verbindungen.](manage-connector.md)

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a>Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Connectors?

Sie benötigen eine gültige Microsoft 365- oder Office 365-Lizenz und ein ausreichendes Connectors-Kontingent für Benutzer in Ihrer Organisation, um Daten aus Connectors in ihren Suchergebnissen anzuzeigen.

Weitere Informationen finden Sie unter [Lizenzanforderungen, Preise](licensing.md) und [Nutzungsbedingungen.](terms-of-use.md)

## <a name="what-are-the-preview-features"></a>Was sind die Vorschaufeatures?

Obwohl Microsoft Graph Connectors und Microsoft Search-APIs jetzt allgemein verfügbar sind, gibt es mehrere Features, die sich in der Vorschau befinden.

Zu den Konnektoren und Features in der Vorschau gehören:

* [Azure DevOps Connector](azure-devops-connector.md)
* [Confluence Cloud Connector](confluence-cloud-connector.md)
* [ServiceNow-Katalogconnector](servicenow-catalog-connector.md)
* [Verwalten benutzerdefinierter Filter](custom-filters.md)
* [Mehrere Verbindungen in einer vertikalen](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a>Wie kann ich Suchergebnisse anpassen und konfigurieren?

Es gibt viele Möglichkeiten zum Anpassen und Konfigurieren von Suchergebnissen. Weitere Informationen finden Sie in den folgenden Artikeln:

* [Branchen und Ergebnistypen verwalten](customize-search-page.md)
* [Verwalten von Layouts für Suchergebnisse](customize-results-layout.md)
* [Verwalten von Ergebnisclusters](result-cluster.md)
* [Verwalten benutzerdefinierter Filter](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?

Nachdem benutzerdefinierte Daten indiziert wurden, können Entwickler [diese Daten abfragen.](/graph/search-concept-custom-types) Sie können Ihre Daten in einer beliebigen Anwendung anzeigen. Weitere Informationen finden Sie [in der Übersicht über die Microsoft Search-API in Microsoft Graph.](/graph/search-concept-overview)

## <a name="how-do-i-customize-search-results"></a>Wie kann ich Suchergebnisse anpassen?

Der nächste Schritt besteht darin, die Suchergebnisse wie in diesem Artikel empfohlen [anzupassen. Wie kann ich Suchergebnisse anpassen und konfigurieren?](#how-do-i-customize-and-configure-search-results). Weitere Informationen zum Anpassen von Suchergebnissen finden Sie unter [Anpassen der Suchergebnisseite.](customize-search-page.md)

## <a name="what-are-the-connector-limitations"></a>Was sind die Connectoreinschränkungen?

* Wenn Sie einen von Microsoft erstellten Connector **veröffentlichen,** kann es einige Minuten dauern, bis die Verbindung erstellt wurde. Während dieser Zeit zeigt die Verbindung ihren Status als ausstehend an.

* Der Aufnahmedurchsatz wird bei ungefähr vier Elementen pro Sekunde gedrosselt.

* Schemaupdates werden nicht unterstützt. Nachdem Sie eine Verbindungseinrichtung erstellt haben, gibt es keine Möglichkeit, das Schema zu aktualisieren. Sie können die Verbindung nur löschen und erneut erstellen.

* Es gibt einen Verbindungsgrenzwert. Jeder Mandant kann bis zu 10 Verbindungen erstellen.

* Sie können eine Verbindung nicht bearbeiten oder ändern, nachdem sie erstellt wurde. Wenn Sie Details ändern müssen, müssen Sie die Verbindung löschen und neu erstellen.
