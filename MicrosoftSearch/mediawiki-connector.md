---
title: MediaWiki Connector für Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten von MediaWiki Connector für Microsoft Search
ms.openlocfilehash: d8aa4a99c353a80f7d3dcf768d8287200b17fdc6
ms.sourcegitcommit: be0c64845477127d73ee24dc727e4583ced3d0e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48206950"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="96f3b-103">MediaWiki-Connector</span><span class="sxs-lookup"><span data-stu-id="96f3b-103">MediaWiki connector</span></span>

<span data-ttu-id="96f3b-104">Mit dem MediaWiki-Konnektor kann Ihre Organisation Daten aus einem wiki ermitteln und indizieren, das mit MediaWiki-Software erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="96f3b-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="96f3b-105">Dieser Connector indiziert angegebene Inhalte in Microsoft Search und unterstützt regelmäßige Crawls, um den Index auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="96f3b-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="96f3b-106">Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen MediaWiki-Connector konfigurieren, ausführen und überwachen.</span><span class="sxs-lookup"><span data-stu-id="96f3b-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="96f3b-107">Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="96f3b-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="96f3b-108">Herstellen einer Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="96f3b-108">Connect to a data source</span></span>

<span data-ttu-id="96f3b-109">Geben Sie Ihre MediaWiki-URL und Anmeldeinformationen für die Authentifizierung der Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="96f3b-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="96f3b-110">Sie benötigen die folgenden Informationen: **Mandanten-ID**, **Ressourcen-** ID, **Client-ID**und den **geheimen Client Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="96f3b-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-the-search-schema"></a><span data-ttu-id="96f3b-111">Verwalten des Suchschemas</span><span class="sxs-lookup"><span data-stu-id="96f3b-111">Manage the search schema</span></span>

<span data-ttu-id="96f3b-112">Konfigurieren Sie nach erfolgreicher Verbindung die Suchschema Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="96f3b-112">After successful connection, configure the search schema mapping.</span></span> <span data-ttu-id="96f3b-113">Sie können auswählen, welche Eigenschaften **abgefragt**, **durchsuchbar**und **abrufbar**gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="96f3b-113">You can choose which properties to make **queryable**, **searchable**, and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="96f3b-114">Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="96f3b-114">Manage search permissions</span></span>

<span data-ttu-id="96f3b-115">Der MediaWiki-Connector unterstützt nur Suchberechtigungen, die für **alle**sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="96f3b-115">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="96f3b-116">Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="96f3b-116">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="96f3b-117">Festlegen des Aktualisierungszeitplans</span><span class="sxs-lookup"><span data-stu-id="96f3b-117">Set the refresh schedule</span></span>

<span data-ttu-id="96f3b-118">In diesem Zeitplan werden die indizierten Daten aktualisiert, sodass Änderungen am wiki in der Microsoft-Suche wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="96f3b-118">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="96f3b-119">Alle neuen Seiten, gelöschten Seiten, Seiteninhalte oder Metadaten-Änderungen werden nach dem angegebenen Aktualisierungsintervall in den Suchergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96f3b-119">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="96f3b-120">Die Durchforstungs Zeit hängt von der Größe des Wikis ab.</span><span class="sxs-lookup"><span data-stu-id="96f3b-120">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="96f3b-121">Der Connector crawlt derzeit um etwa 50 Seiten pro Minute.</span><span class="sxs-lookup"><span data-stu-id="96f3b-121">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="96f3b-122">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="96f3b-122">Limitations</span></span>

<span data-ttu-id="96f3b-123">Der MediaWiki-Konnektor hat diese Einschränkungen in der Preview-Version:</span><span class="sxs-lookup"><span data-stu-id="96f3b-123">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="96f3b-124">Unterstützt nur Cloud-basierte Wikis.</span><span class="sxs-lookup"><span data-stu-id="96f3b-124">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="96f3b-125">Unterstützt nur Basic oder OAuth 2,0 mit Azure Active Directory oder Azure-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="96f3b-125">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="96f3b-126">Unterstützt keine Namespace Auswahl für die Indizierung.</span><span class="sxs-lookup"><span data-stu-id="96f3b-126">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="96f3b-127">Indiziert nur **Haupt**-, **Kategorie**-und **Datei** Namespaces.</span><span class="sxs-lookup"><span data-stu-id="96f3b-127">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="96f3b-128">Unterstützt keine Zugriffssteuerungslisten (Access Control Lists, ACLs).</span><span class="sxs-lookup"><span data-stu-id="96f3b-128">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="96f3b-129">Daher sind indizierte Seiten für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="96f3b-129">Thus, indexed pages are visible to all users in the organization.</span></span>
