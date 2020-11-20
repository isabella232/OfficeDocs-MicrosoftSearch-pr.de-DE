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
ms.openlocfilehash: 7f6b34dcafc4b82ab3778ec1d7a4921383e44a44
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367640"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="d126d-103">MediaWiki-Connector</span><span class="sxs-lookup"><span data-stu-id="d126d-103">MediaWiki connector</span></span>

<span data-ttu-id="d126d-104">Mit dem MediaWiki-Konnektor kann Ihre Organisation Daten aus einem wiki ermitteln und indizieren, das mit MediaWiki-Software erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d126d-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="d126d-105">Dieser Connector indiziert angegebene Inhalte in Microsoft Search und unterstützt regelmäßige Crawls, um den Index auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="d126d-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="d126d-106">Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen MediaWiki-Connector konfigurieren, ausführen und überwachen.</span><span class="sxs-lookup"><span data-stu-id="d126d-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="d126d-107">Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d126d-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="d126d-108">Herstellen einer Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="d126d-108">Connect to a data source</span></span>

<span data-ttu-id="d126d-109">Geben Sie Ihre MediaWiki-URL und Anmeldeinformationen für die Authentifizierung der Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="d126d-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="d126d-110">Sie benötigen die folgenden Informationen: **Mandanten-ID**, **Ressourcen-** ID, **Client-ID** und den **geheimen Client Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="d126d-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="d126d-111">Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="d126d-111">Manage search permissions</span></span>

<span data-ttu-id="d126d-112">Der MediaWiki-Connector unterstützt nur Suchberechtigungen, die für **alle** sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="d126d-112">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="d126d-113">Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d126d-113">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="d126d-114">Zuweisen von Eigenschaften Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="d126d-114">Assign property labels</span></span>

<span data-ttu-id="d126d-115">Sie können jeder Beschriftung eine Source-Eigenschaft zuweisen, indem Sie in einem Menü mit Optionen auswählen.</span><span class="sxs-lookup"><span data-stu-id="d126d-115">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="d126d-116">Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaften Bezeichnungen verbessern die Suchrelevanz und stellen genauere Suchergebnisse für Endbenutzer sicher.</span><span class="sxs-lookup"><span data-stu-id="d126d-116">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="d126d-117">Schema verwalten</span><span class="sxs-lookup"><span data-stu-id="d126d-117">Manage schema</span></span>

<span data-ttu-id="d126d-118">Auf dem Bildschirm " **Schema verwalten** " haben Sie die Möglichkeit, die den Eigenschaften zugeordneten Schema **Attribute (** abfragbar, **durchsuchbar**, **abrufbar** und **verfeinernd**) zu ändern, optionale Aliase hinzuzufügen und die **Content** -Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d126d-118">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="d126d-119">Festlegen des Aktualisierungszeitplans</span><span class="sxs-lookup"><span data-stu-id="d126d-119">Set the refresh schedule</span></span>

<span data-ttu-id="d126d-120">In diesem Zeitplan werden die indizierten Daten aktualisiert, sodass Änderungen am wiki in der Microsoft-Suche wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d126d-120">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="d126d-121">Alle neuen Seiten, gelöschten Seiten, Seiteninhalte oder Metadaten-Änderungen werden nach dem angegebenen Aktualisierungsintervall in den Suchergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d126d-121">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="d126d-122">Die Durchforstungs Zeit hängt von der Größe des Wikis ab.</span><span class="sxs-lookup"><span data-stu-id="d126d-122">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="d126d-123">Der Connector crawlt derzeit um etwa 50 Seiten pro Minute.</span><span class="sxs-lookup"><span data-stu-id="d126d-123">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="d126d-124">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d126d-124">Limitations</span></span>

<span data-ttu-id="d126d-125">Der MediaWiki-Konnektor hat diese Einschränkungen in der Preview-Version:</span><span class="sxs-lookup"><span data-stu-id="d126d-125">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="d126d-126">Unterstützt nur Cloud-basierte Wikis.</span><span class="sxs-lookup"><span data-stu-id="d126d-126">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="d126d-127">Unterstützt nur Basic oder OAuth 2,0 mit Azure Active Directory oder Azure-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d126d-127">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="d126d-128">Unterstützt keine Namespace Auswahl für die Indizierung.</span><span class="sxs-lookup"><span data-stu-id="d126d-128">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="d126d-129">Indiziert nur **Haupt**-, **Kategorie**-und **Datei** Namespaces.</span><span class="sxs-lookup"><span data-stu-id="d126d-129">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="d126d-130">Unterstützt keine Zugriffssteuerungslisten (Access Control Lists, ACLs).</span><span class="sxs-lookup"><span data-stu-id="d126d-130">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="d126d-131">Daher sind indizierte Seiten für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d126d-131">Thus, indexed pages are visible to all users in the organization.</span></span>
