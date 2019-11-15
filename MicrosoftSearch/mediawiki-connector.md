---
title: MediaWiki Connector für Microsoft Search
ms.author: v-pamcn
author: monaray
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
ms.openlocfilehash: 2aa0ef494aa42b1a7364ec68f6532dec737b9c25
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626963"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="b4a6f-103">MediaWiki-Connector</span><span class="sxs-lookup"><span data-stu-id="b4a6f-103">MediaWiki connector</span></span>

<span data-ttu-id="b4a6f-104">Mit dem MediaWiki-Konnektor kann Ihre Organisation Daten aus einem wiki ermitteln und indizieren, das mit MediaWiki-Software erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="b4a6f-105">Dieser Connector indiziert angegebene Inhalte in Microsoft Search und unterstützt regelmäßige Crawls, um den Index auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="b4a6f-106">Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen MediaWiki-Connector konfigurieren, ausführen und überwachen.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="b4a6f-107">Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="b4a6f-108">Herstellen einer Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="b4a6f-108">Connect to a data source</span></span>
<span data-ttu-id="b4a6f-109">Geben Sie Ihre MediaWiki-URL und Anmeldeinformationen für die Authentifizierung der Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="b4a6f-110">Sie benötigen die folgenden Informationen: **Mandanten-ID**, **Ressourcen-** ID, **Client-ID**und den **geheimen Client Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-the-search-schema"></a><span data-ttu-id="b4a6f-111">Verwalten des Suchschemas</span><span class="sxs-lookup"><span data-stu-id="b4a6f-111">Manage the search schema</span></span>
<span data-ttu-id="b4a6f-112">Konfigurieren Sie nach erfolgreicher Verbindung die Suchschema Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-112">After successful connection, configure the search schema mapping.</span></span> <span data-ttu-id="b4a6f-113">Sie können auswählen, welche Eigenschaften **abgefragt**, **durchsuchbar**und **abrufbar**gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-113">You can choose which properties to make **queryable**, **searchable**, and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="b4a6f-114">Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="b4a6f-114">Manage search permissions</span></span>
<span data-ttu-id="b4a6f-115">Der MediaWiki-Connector unterstützt nur Suchberechtigungen, die für **alle**sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-115">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="b4a6f-116">Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-116">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="b4a6f-117">Festlegen des Aktualisierungszeitplans</span><span class="sxs-lookup"><span data-stu-id="b4a6f-117">Set the refresh schedule</span></span> 
<span data-ttu-id="b4a6f-118">In diesem Zeitplan werden die indizierten Daten aktualisiert, sodass Änderungen am wiki in der Microsoft-Suche wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-118">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="b4a6f-119">Alle neuen Seiten, gelöschten Seiten, Seiteninhalte oder Metadaten-Änderungen werden nach dem angegebenen Aktualisierungsintervall in den Suchergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-119">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="b4a6f-120">Die Durchforstungs Zeit hängt von der Größe des Wikis ab.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-120">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="b4a6f-121">Der Connector crawlt derzeit um etwa 50 Seiten pro Minute.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-121">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="b4a6f-122">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b4a6f-122">Limitations</span></span> 
<span data-ttu-id="b4a6f-123">Der MediaWiki-Konnektor hat diese Einschränkungen in der Preview-Version:</span><span class="sxs-lookup"><span data-stu-id="b4a6f-123">The MediaWiki connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="b4a6f-124">Unterstützt nur Cloud-basierte Wikis.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-124">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="b4a6f-125">Unterstützt nur Basic oder OAuth 2,0 mit Azure Active Directory oder Azure-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-125">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="b4a6f-126">Unterstützt keine Namespace Auswahl für die Indizierung.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-126">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="b4a6f-127">Indiziert nur **Haupt**-, **Kategorie**-und **Datei** Namespaces.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-127">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="b4a6f-128">Unterstützt keine Zugriffssteuerungslisten (Access Control Lists, ACLs).</span><span class="sxs-lookup"><span data-stu-id="b4a6f-128">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="b4a6f-129">Daher sind indizierte Seiten für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="b4a6f-129">Thus, indexed pages are visible to all users in the organization.</span></span>
