---
title: MediaWiki Graph Connector für Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des MediaWiki -Graph-Connectors für Microsoft Search
ms.openlocfilehash: e2b2b7c506d92623dd0f68801312c1820b5b9d4e
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097394"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a><span data-ttu-id="ff2bf-103">MediaWiki Graph Connector</span><span class="sxs-lookup"><span data-stu-id="ff2bf-103">MediaWiki Graph connector</span></span>

<span data-ttu-id="ff2bf-104">Mit dem MediaWiki Graph-Connector kann Ihre Organisation Daten aus einem Wiki ermitteln und indizieren, das mit der Software MediaWiki erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-104">The MediaWiki Graph connector allows your organization to discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="ff2bf-105">Dieser Connector indiziert angegebene Inhalte in Microsoft Search und unterstützt regelmäßige Durchforstungen, um den Index auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

> [!NOTE]
> <span data-ttu-id="ff2bf-106">Lesen Sie [**den Artikel "Setup für Ihren Graph-Connector",**](configure-connector.md) um den allgemeinen Einrichtungsprozess für Graph Connectors zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="ff2bf-107">Dieser Artikel ist für alle Benutzer, die einen MediaWiki -Graph-Connector konfigurieren, ausgeführt und überwachen.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-107">This article is for anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="ff2bf-108">Sie ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den MediaWiki Graph-Connector gelten.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-108">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span> <span data-ttu-id="ff2bf-109">Dieser Artikel enthält auch Informationen zu [Einschränkungen.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="ff2bf-109">This article also includes information about [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ff2bf-110">Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="ff2bf-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="ff2bf-111">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff2bf-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="ff2bf-112">Schritt 2: Benennen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="ff2bf-112">Step 2: Name the connection</span></span>

<span data-ttu-id="ff2bf-113">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff2bf-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="ff2bf-114">Schritt 3: Konfigurieren der Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ff2bf-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="ff2bf-115">Geben Sie **Ihre Wiki-URL** ein, und wählen Sie im Dropdownmenü der Optionen den Authentifizierungstyp aus. </span><span class="sxs-lookup"><span data-stu-id="ff2bf-115">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="ff2bf-116">Die Optionen sind **None**, **Basic** und **OAuth 2.0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-116">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="ff2bf-117">Wenn Sie **"Standard"** als Authentifizierungstyp  auswählen, müssen Sie den Benutzernamen und das **Kennwort für** das Wiki angeben.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-117">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="ff2bf-118">Wenn Sie **OAuth 2.0 AAD** als Authentifizierungstyp auswählen, müssen Sie die **Ressourcen-ID** der Wiki-Installation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-118">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="ff2bf-119">Sie müssen auch die **Client-ID** und den **geheimen** Clientgeheimnis bereitstellen, die auf der Registrierungsseite der AAD-Anwendung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-119">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="ff2bf-120">Schritt 4: Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="ff2bf-120">Step 4: Manage search permissions</span></span>

<span data-ttu-id="ff2bf-121">Der Connector MediaWiki unterstützt nur Suchberechtigungen, die für jeden **sichtbar sind.**</span><span class="sxs-lookup"><span data-stu-id="ff2bf-121">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="ff2bf-122">Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-122">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="ff2bf-123">Schritt 5: Zuweisen von Eigenschaftsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ff2bf-123">Step 5: Assign property labels</span></span>

<span data-ttu-id="ff2bf-124">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff2bf-124">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="ff2bf-125">Schritt 6: Verwalten des Schemas</span><span class="sxs-lookup"><span data-stu-id="ff2bf-125">Step 6: Manage schema</span></span>

<span data-ttu-id="ff2bf-126">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff2bf-126">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="ff2bf-127">Schritt 7: Auswählen von Aktualisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ff2bf-127">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="ff2bf-128">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff2bf-128">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="ff2bf-129">Schritt 8: Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="ff2bf-129">Step 8: Review connection</span></span>

<span data-ttu-id="ff2bf-130">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff2bf-130">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="ff2bf-131">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ff2bf-131">Limitations</span></span>

<span data-ttu-id="ff2bf-132">Der MediaWiki Connector hat in der Vorschauversion die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="ff2bf-132">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="ff2bf-133">Unterstützt nur cloudbasierte Wikis.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-133">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="ff2bf-134">Unterstützt nur Basic oder OAuth 2.0 mit Azure Active Directory- oder Azure-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-134">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="ff2bf-135">Unterstützt keine Namespaceauswahl für die Indizierung.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-135">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="ff2bf-136">Indiziert nur Die Namespaces "Main", "Category" und "File".</span><span class="sxs-lookup"><span data-stu-id="ff2bf-136">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="ff2bf-137">Unterstützt keine Zugriffssteuerungslisten (Access Control Lists, ACLs).</span><span class="sxs-lookup"><span data-stu-id="ff2bf-137">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="ff2bf-138">Daher sind indizierte Seiten für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ff2bf-138">Thus, indexed pages are visible to all users in the organization.</span></span>
