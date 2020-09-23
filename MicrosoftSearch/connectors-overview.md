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
ms.openlocfilehash: 2e3ca14b408ca6471c3163871c80fb24d62cff26
ms.sourcegitcommit: be0c64845477127d73ee24dc727e4583ced3d0e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48206986"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Übersicht über Microsoft Graph-Connectors

Microsoft Search indiziert alle Ihre [Microsoft 365](https://www.microsoft.com/microsoft-365) -Daten, damit Sie für Benutzer durchsucht werden können. Mit Microsoft Graph Connectors kann Ihre Organisation Daten von Drittanbietern indizieren, die in den Ergebnissen von Microsoft Search angezeigt werden sollen. Die drittanbieterdaten können lokal oder in öffentlichen oder privaten Clouds gehostet werden. Connectors erweitern Sie die Typen von Inhaltsquellen, die in Ihren Microsoft 365-Produktivitäts-apps und dem breiteren Microsoft-Ökosystem durchsucht werden können.

> [!IMPORTANT]
> **Haftungsausschluss**: Microsoft Graph-Connectors und Microsoft Search-APIs (Abfrage und Index) sind derzeit im Vorschaustatus für Mandanten in der gezielten Version verfügbar. Um Connectors mit Microsoft Search zu verwenden oder um Connectors zu erstellen, wählen Sie [Targeted Release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)aus. Weitere Informationen zur Vorschau finden Sie unter [Connectors Preview Program](connectors-preview.md).

## <a name="architecture"></a>Architektur

Das folgende Architekturdiagramm der Microsoft Graph-Plattform zeigt, wie der Connector-Inhalt durch die Inhaltsindizierung zu Benutzer Ergebnissen in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) -Clients fließt. In diesem Artikel werden die wichtigsten Bausteine im Datenfluss Prozess von Microsoft Graph Connectors erläutert.

![Diagramm: lokale und Cloud-basierte Daten werden von Konnektoren abgerufen und von der Microsoft-Such-API indiziert, und der Microsoft Search-Dienst sendet die Ergebnisse an die Benutzer.](media/highlevel-connectors_FINAL.png)

Die API instanziiert eine Verbindung pro Datenquelle. Anschließend werden die Daten von der API indiziert und gespeichert. Hergestellte Verbindungen interagieren mit der Microsoft-Suche, sodass Benutzer Suchergebnisse abrufen können.

Sie können alle von Microsoft erstellten Connectors im Microsoft 365 [Admin Center](https://admin.microsoft.com)konfigurieren. Das Admin Center vereinfacht die Konfiguration Ihres Connectors mit einer einfachen Benutzeroberfläche.

Um eine **Verbindung** mit einer Datenquelle herzustellen, benötigen Administratoren authentifizierten Zugriff auf die Daten und das gesamte Inhalts-Repository. Die Daten werden für die Indizierung an den Graph Connector-Dienst zugeführt.

## <a name="available-connectors"></a>Verfügbare Connectors

Es gibt derzeit 6 von Microsoft erstellte Connectors, und über 100-Connectors stehen in unseren Ecosystem-Partnern zur Verfügung.

Um eine Vorschau der Connectors von einem unserer Ecosystem-Partner anzuzeigen, wenden Sie sich direkt an Sie. Weitere Informationen finden Sie im [Microsoft Graph Connectors-Katalog](connectors-gallery.md).

Sie können auch [einen eigenen Connector erstellen](https://docs.microsoft.com/graph/search-concept-overview).

### <a name="connectors-by-microsoft"></a>Connectors von Microsoft

Die Microsoft Graph Connectors Preview-Version enthält 6 von Microsoft erstellte Connectors. Sie können Sie im [Admin Center](https://admin.microsoft.com) einrichten und erfahren, wie Sie [ihren von Microsoft erstellten Connector](configure-connector.md)einrichten.

Die folgenden Abschnitte enthalten kurze Beschreibungen für diese von Microsoft erstellten Connectors. Sie können weitere Informationen in den verknüpften Artikeln für jeden Connector erhalten.

- **[Azure Data Lake-Speicher Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)**. Mit diesem Microsoft Graph-Connector können Benutzer in Ihrer Organisation nach Dateien und Inhalten suchen, die in Azure-BLOB-Containern gespeichert sind. Der Azure Data Lake Storage Gen2-Connector indiziert auch Hierarchie fähige Ordner in Azure Data Lake-Speicher Gen2-Konten, die Sie angeben.
Erfahren Sie mehr über den [Azure Data Lake-Speicher Gen2-Connector](azure-data-lake-connector.md).

- **[Azure DevOps](https://azure.microsoft.com/services/devops)**. Mit diesem Microsoft Graph-Connector können Benutzer in Ihrer Organisation in ihrer Azure DevOps-Instanz nach Arbeitsaufgaben suchen.
Erfahren Sie mehr über den [Azure DevOps-Connector](azure-devops-connector.md).

- **[Azure SQL](https://azure.microsoft.com/services/sql-database)**. Mit diesem Microsoft Graph-Connector können Benutzer in Ihrer Organisation nach Daten aus ihrer Azure SQL-Datenbank suchen.
Erfahren Sie mehr über den [Azure SQL Connector](MSSQL-connector.md).

- **Enterprise-Websites**. Mit diesem Microsoft Graph-Connector können Benutzer in Ihrer Organisation Seiten in einer nicht-SharePoint-Unternehmenswebsite durchsuchen.
Erfahren Sie mehr über den [Enterprise-Websites-Connector](enterprise-web-connector.md).

- **[MediaWiki](https://www.mediawiki.org/wiki/MediaWiki)**. Mit diesem Microsoft Graph-Connector können Benutzer nach Knowledge-Base-Artikeln auf Wiki-Websites suchen, die Ihre Organisation mit MediaWiki erstellt.
Erfahren Sie mehr über den [MediaWiki-Connector](mediawiki-connector.md).

- **[Microsoft SQL Server](https://www.microsoft.com/sql-server/sql-server-2017)**. Mit diesem Microsoft Graph-Connector können Benutzer in Ihrer Organisation nach Daten in lokalen SQL Server-Datenbanken suchen.
Erfahren Sie mehr über den [Microsoft SQL Server-Connector](MSSQL-connector.md).

- **[ServiceNow](https://www.servicenow.com)**. Mit diesem Microsoft Graph-Connector können Benutzer in Ihrer Organisation nach Knowledge Base-Artikeln aus ihrer ServiceNow-Instanz suchen.
Erfahren Sie mehr über den [ServiceNow-Connector](servicenow-connector.md).

### <a name="connectors-from-our-partners"></a>Connectors von unseren Partnern

Es stehen über 100 Connectors für die Vorschau von unseren Ecosystem-Partnern zur Verfügung. Um eine Vorschau der Connectors von einem unserer Ecosystem-Partner anzuzeigen, wenden Sie sich direkt an Sie.
Erfahren Sie mehr über Connectors von unseren Partnern im [Microsoft Graph Connectors-Katalog](connectors-gallery.md).

### <a name="build-your-own-connector"></a>Erstellen eines eigenen Connectors

Um benutzerdefinierte Datentypen oder Dateien zu indizieren, können Entwickler Connectors in [Microsoft Graph](https://developer.microsoft.com/graph/)erstellen. Bei einem Connector handelt es sich um eine Anwendung, mit der [eine Verbindung erstellt](https://docs.microsoft.com/graph/search-index-manage-connections) und Elemente in den Microsoft Search-Index verschoben werden. Weitere Informationen finden Sie in der [Übersicht zum Erweitern der Microsoft-Suchumgebung für apps in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).

### <a name="search-results-with-your-custom-built-connector"></a>Suchergebnisse mit Ihrem benutzerdefinierten Connector

Nachdem benutzerdefinierte Daten indiziert wurden, können Entwickler [diese Daten Abfragen](https://docs.microsoft.com/graph/search-concept-custom-types). Sie können Ihre Daten in einer beliebigen Anwendung anzeigen. Weitere Informationen finden Sie in der [Übersicht zum Erweitern der Microsoft-Suchumgebung für apps in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).

## <a name="license-requirements"></a>Lizenzanforderungen

Um Daten aus Konnektoren in ihren Suchergebnissen anzuzeigen, müssen Benutzer über eines der folgenden Microsoft 365-oder Office 365-Abonnements verfügen:

- [Microsoft 365 oder Office 365 Enterprise E3 oder E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

- [Microsoft 365 oder Office 365 Education a3 oder A5](https://www.microsoft.com/microsoft-365/academic/compare-office-365-education-plans?activetab=tab:primaryr1)
