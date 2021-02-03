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
ms.openlocfilehash: 9d9d7a1ef9aeaba079f8cccef1ec4a4836768e8d
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084983"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a><span data-ttu-id="59c37-103">MediaWiki Graph Connector</span><span class="sxs-lookup"><span data-stu-id="59c37-103">MediaWiki Graph connector</span></span>

<span data-ttu-id="59c37-104">Mit dem MediaWiki Graph-Connector kann Ihre Organisation Daten aus einem Wiki ermitteln und indizieren, das mit der Software MediaWiki erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="59c37-104">The MediaWiki Graph connector allows your organization to discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="59c37-105">Dieser Connector indiziert angegebene Inhalte in Microsoft Search und unterstützt regelmäßige Durchforstungen, um den Index auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="59c37-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

> [!NOTE]
> <span data-ttu-id="59c37-106">Lesen Sie [**den Artikel "Setup für Ihren Graph-Connector",**](configure-connector.md) um den allgemeinen Einrichtungsprozess für Graph Connectors zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="59c37-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="59c37-107">Dieser Artikel ist für jeden benutzer, der einen ServiceNow Graph Connector konfiguriert, ausgeführt und überwacht.</span><span class="sxs-lookup"><span data-stu-id="59c37-107">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="59c37-108">Sie ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den MediaWiki Graph-Connector gelten.</span><span class="sxs-lookup"><span data-stu-id="59c37-108">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span> <span data-ttu-id="59c37-109">Dieser Artikel enthält auch Informationen zu [Einschränkungen.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="59c37-109">This article also includes information about [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="59c37-110">Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="59c37-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="59c37-111">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="59c37-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="59c37-112">Schritt 2: Benennen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="59c37-112">Step 2: Name the connection</span></span>

<span data-ttu-id="59c37-113">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="59c37-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="59c37-114">Schritt 3: Konfigurieren der Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="59c37-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="59c37-115">Geben Sie Ihre **Wiki-URL** ein, und wählen Sie im Dropdownmenü der Optionen den Authentifizierungstyp aus. </span><span class="sxs-lookup"><span data-stu-id="59c37-115">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="59c37-116">Die Optionen sind **None**, **Basic** und **OAuth 2.0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="59c37-116">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="59c37-117">Wenn Sie **"Standard"** als Authentifizierungstyp  auswählen, müssen Sie den Benutzernamen und das **Kennwort für** das Wiki angeben.</span><span class="sxs-lookup"><span data-stu-id="59c37-117">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="59c37-118">Wenn Sie **OAuth 2.0 AAD** als Authentifizierungstyp auswählen, müssen Sie die **Ressourcen-ID** der Wiki-Installation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="59c37-118">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="59c37-119">Sie müssen auch die **Client-ID** und den **geheimen** Clientgeheimnis bereitstellen, die auf der Registrierungsseite der AAD-Anwendung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="59c37-119">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="59c37-120">Schritt 4: Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="59c37-120">Step 4: Manage search permissions</span></span>

<span data-ttu-id="59c37-121">Der Connector MediaWiki unterstützt nur Suchberechtigungen, die für jeden **sichtbar sind.**</span><span class="sxs-lookup"><span data-stu-id="59c37-121">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="59c37-122">Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="59c37-122">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="59c37-123">Schritt 5: Zuweisen von Eigenschaftsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="59c37-123">Step 5: Assign property labels</span></span>

<span data-ttu-id="59c37-124">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="59c37-124">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="59c37-125">Schritt 6: Verwalten des Schemas</span><span class="sxs-lookup"><span data-stu-id="59c37-125">Step 6: Manage schema</span></span>

<span data-ttu-id="59c37-126">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="59c37-126">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="59c37-127">Schritt 7: Auswählen von Aktualisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="59c37-127">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="59c37-128">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="59c37-128">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="59c37-129">Schritt 8: Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="59c37-129">Step 8: Review connection</span></span>

<span data-ttu-id="59c37-130">Folgen Sie den allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="59c37-130">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="59c37-131">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="59c37-131">Limitations</span></span>

<span data-ttu-id="59c37-132">Der MediaWiki Connector hat in der Vorschauversion die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="59c37-132">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="59c37-133">Unterstützt nur cloudbasierte Wikis.</span><span class="sxs-lookup"><span data-stu-id="59c37-133">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="59c37-134">Unterstützt nur Basic oder OAuth 2.0 mit Azure Active Directory- oder Azure-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="59c37-134">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="59c37-135">Unterstützt keine Namespaceauswahl für die Indizierung.</span><span class="sxs-lookup"><span data-stu-id="59c37-135">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="59c37-136">Indiziert nur Die Namespaces "Main", "Category" und "File".</span><span class="sxs-lookup"><span data-stu-id="59c37-136">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="59c37-137">Unterstützt keine Zugriffssteuerungslisten (Access Control Lists, ACLs).</span><span class="sxs-lookup"><span data-stu-id="59c37-137">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="59c37-138">Daher sind indizierte Seiten für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="59c37-138">Thus, indexed pages are visible to all users in the organization.</span></span>
