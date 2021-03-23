---
title: Übersicht über Microsoft Graph Connectors
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Übersicht über Microsoft Graph-Connectors für Microsoft Search
ms.openlocfilehash: 2d49471c703b765f6e99324f39dbe730f6dea814
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031656"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a>Übersicht über Microsoft Graph-Connectors

[Microsoft Search](./overview-microsoft-search.md) indiziert alle [Ihre Microsoft 365-Daten,](https://www.microsoft.com/microsoft-365) damit sie für Benutzer durchsucht werden können. Mit Microsoft Graph-Connectors kann Ihre Organisation Drittanbieterdaten indizieren, sodass sie in den Microsoft-Suchergebnissen angezeigt werden. Dieses Feature erweitert die Typen von Inhaltsquellen, die in Ihren Microsoft 365-Produktivitäts-Apps durchsucht werden können, und das umfassendere Microsoft-Ökosystem. Die Drittanbieterdaten können lokal oder in öffentlichen oder privaten Clouds gehostet werden.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Dieser Artikel soll Microsoft 365-Administratoren dabei helfen, die Ressourcen zu finden, die zur Beantwortung der folgenden Fragen zur Verfügung stehen:

* [Welche Datenquellen können mit Microsoft Search verbunden werden?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Wie verwalte ich meine Verbindungen?](#how-do-i-manage-my-connections)
* [Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Graph-Connectors?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [Was sind die Vorschaufeatures?](#what-are-the-preview-features)
* [Wie kann ich Suchergebnisse anpassen und konfigurieren?](#how-do-i-customize-and-configure-search-results)
* [Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?](#how-do-i-search-my-connector-data-from-a-custom-application)
* [Wie kann ich Suchergebnisse anpassen?](#how-do-i-customize-search-results)
* [Was sind die Connectoreinschränkungen?](#what-are-the-connector-limitations)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> Microsoft Graph-Connectors und Microsoft Search-APIs sind jetzt allgemein verfügbar. Die ersten Rollouts sind für Kunden, die für die gezielte Veröffentlichung konfiguriert sind. Wenn Sie einen Graph-Connector in Ihrem Mandanten verwenden möchten, müssen Sich Benutzer und Administratoren für die gezielte [Version entscheiden.](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)

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

Microsoft stellt 9 Graph-Connectors zur Verfügung, und unsere Ökosystempartner haben mehr als 100 weitere Graph-Connectors erstellt. Sie können auch einen eigenen Graph-Connector erstellen.

### <a name="graph-connectors-by-microsoft"></a>Microsoft Graph-Connectors

Sie können eine Verbindung mit den folgenden Datenquellen herstellen, indem Sie von Microsoft erstellte Graph-Connectors verwenden:

<!---Add links below when new docs are created--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [Azure SQL und Microsoft SQL Server](MSSQL-connector.md)
* [Unternehmenswebsites](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Dateifreigabe](fileshare-connector.md)
* [Oracle SQL (Vorschau)](OracleSQL-connector.md)
* [Salesforce (Vorschau)](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

Der [Graph-Connectors-Katalog](connectors-gallery.md) enthält eine kurze Beschreibung der einzelnen Graph-Connectors. Wenn Sie bereit sind, eine dieser Datenquellen mit Ihrem Mandanten [](configure-connector.md) zu verbinden, lesen Sie unbedingt die Setupübersicht und alle anderen Artikel im Abschnitt Setup connectors by Microsoft, die für Ihre Datenquelle gelten.

### <a name="graph-connectors-by-our-partners"></a>Graph connectors by our partners

Der [Microsoft Graph-Connectorskatalog](connectors-gallery.md) enthält eine kurze Beschreibung der von unseren Partnern erstellten Graph-Connectors und einen Link zur Website jedes Partners. Um mehr zu erfahren, wenden Sie sich direkt an jeden Partner.

### <a name="build-your-own-graph-connector"></a>Erstellen Eines eigenen Graph-Connectors

Sie können einen eigenen Graph-Connector erstellen, wenn Sie dies bevorzugen. Weitere Informationen zum Erstellen von Graph-Connectors finden Sie unter Übersicht über die [Microsoft Search-API in Microsoft Graph](/graph/search-concept-overview).

## <a name="how-do-i-manage-my-connections"></a>Wie verwalte ich meine Verbindungen?

Sie können Ihre Verbindungen über die Registerkarte [Connectors im](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) [Microsoft 365 Admin Center verwalten.](https://admin.microsoft.com/) Weitere Informationen zum Verwalten von Verbindungen finden Sie unter: [Verwalten Ihrer Verbindungen](manage-connector.md).

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>Welche Lizenzanforderungen und Nutzungsbedingungen gelten für Graph-Connectors?

Sie benötigen eine gültige Microsoft 365- oder Office 365-Lizenz und ein ausreichendes Graph Connectors-Kontingent für Benutzer in Ihrer Organisation, um Daten von Connectors in ihren Suchergebnissen anzuzeigen.

Weitere Informationen finden Sie unter [Lizenzanforderungen und Preise](licensing.md) und [Nutzungsbedingungen](terms-of-use.md).

## <a name="what-are-the-preview-features"></a>Was sind die Vorschaufeatures?

Obwohl Microsoft Graph-Connectors und Microsoft Search-APIs jetzt allgemein verfügbar sind, stehen mehrere Features in der Vorschau zur Verfügung.

Zu den Connectors und Features in der Vorschau gehören:

* [Azure DevOps Connector](azure-devops-connector.md)
* [Salesforce Connector](salesforce-connector.md)
* [ServiceNow-Connector](servicenow-connector.md) mit Suchberechtigungen, die Quell-ACLs verwenden
* [Verwalten von Ergebnisclusters](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a>Wie kann ich Suchergebnisse anpassen und konfigurieren?

Es gibt viele Möglichkeiten zum Anpassen und Konfigurieren von Suchergebnissen. Weitere Informationen finden Sie in den folgenden Artikeln:

* [Branchen und Ergebnistypen verwalten](customize-search-page.md)
* [Verwalten von Layouts für Suchergebnisse](customize-results-layout.md)
* [Verwalten von Ergebnisclusters](result-cluster.md)
* [Verwalten benutzerdefinierter Filter](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Wie kann ich meine Connectordaten aus einer benutzerdefinierten Anwendung durchsuchen?

Nachdem benutzerdefinierte Daten indiziert wurden, können Entwickler [diese Daten abfragen.](/graph/search-concept-custom-types) Sie können Ihre Daten in einer beliebigen Anwendung anzeigen. Weitere Informationen finden Sie unter [Übersicht über die Microsoft Search-API in Microsoft Graph](/graph/search-concept-overview).

## <a name="how-do-i-customize-search-results"></a>Wie kann ich Suchergebnisse anpassen?

Der nächste Schritt besteht im Anpassen der Suchergebnisse wie in diesem Artikel empfohlen. Wie kann ich [Suchergebnisse anpassen und konfigurieren?](#how-do-i-customize-and-configure-search-results). Weitere Informationen zum Anpassen von Suchergebnissen finden Sie unter [Customize the search results page](./configure-connector.md#next-steps-customize-the-search-results-page).

## <a name="what-are-the-connector-limitations"></a>Was sind die Connectoreinschränkungen?

* Wenn Sie **einen** von Microsoft erstellten Connector veröffentlichen, kann es einige Minuten dauern, bis die Verbindung erstellt wurde. Während dieser Zeit wird der Status der Verbindung als ausstehend angezeigt.

* Das [Microsoft 365 Admin Center](https://admin.microsoft.com) unterstützt  die Bearbeitung des Suchschemas nach der Veröffentlichung einer Verbindung nicht. Um das Suchschema zu bearbeiten, löschen Sie Ihre Verbindung, und erstellen Sie dann eine neue.

* Der Erfassungsdurchsatz wird bei etwa vier Elementen pro Sekunde gedrosselt.

* Schemaupdates werden nicht unterstützt. Nachdem Sie eine Verbindungseinrichtung erstellt haben, gibt es keine Möglichkeit, das Schema zu aktualisieren. Sie können die Verbindung nur löschen und neu erstellen.

* Es gibt einen Verbindungsgrenzwert. Jeder Mandant kann bis zu 10 Verbindungen erstellen.

* Die Bearbeitungsunterstützung für die Verbindung ist nicht verfügbar. Nachdem die Verbindung erstellt wurde, können Sie sie nicht bearbeiten oder ändern. Wenn Sie Details ändern müssen, müssen Sie die Verbindung löschen und neu erstellen.