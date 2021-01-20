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
description: Einrichten des MediaWiki-Connectors für Microsoft Search
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905952"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="f6764-103">MediaWiki Connector</span><span class="sxs-lookup"><span data-stu-id="f6764-103">MediaWiki connector</span></span>

<span data-ttu-id="f6764-104">Mit dem MediaWiki Connector kann Ihre Organisation Daten aus einem Wiki ermitteln und indizieren, das mit der Software MediaWiki erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f6764-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="f6764-105">Dieser Connector indiziert angegebene Inhalte in Microsoft Search und unterstützt regelmäßige Durchforstungen, um den Index auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="f6764-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="f6764-106">Dieser Artikel ist für Microsoft 365-Administratoren oder alle Personen, die einen MediaWiki Graph-Connector konfigurieren, ausgeführt und überwachen.</span><span class="sxs-lookup"><span data-stu-id="f6764-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="f6764-107">Sie ergänzt die allgemeinen Anweisungen im Artikel ["Einrichten Ihres Graph-Connectors".](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="f6764-107">It supplements the general instructions provided in the [Set up your Graph connector](configure-connector.md) article.</span></span> <span data-ttu-id="f6764-108">Wenn Sie dies noch nicht getan haben, lesen Sie den gesamten Artikel zum Einrichten Ihres Graph-Connectors, um den allgemeinen Einrichtungsprozess zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="f6764-108">If you have not already done so, read the entire Set up your Graph connector article to understand the general setup process.</span></span>

<span data-ttu-id="f6764-109">Jeder Schritt im Setupprozess wird unten aufgeführt, zusammen mit einem Hinweis, der angibt, dass Sie die allgemeinen Setupanweisungen oder andere Anweisungen befolgen sollten, die nur für MediaWiki Graph-Connectors gelten.</span><span class="sxs-lookup"><span data-stu-id="f6764-109">Each step in the setup process is listed below along with either a note that indicates you should follow the general setup instructions OR other instructions that apply to only MediaWiki Graph connectors.</span></span> <span data-ttu-id="f6764-110">Dieser Artikel enthält auch Informationen zu [Einschränkungen für](#limitations) MediaWiki Graph-Connectors.</span><span class="sxs-lookup"><span data-stu-id="f6764-110">This article also includes information about [Limitations](#limitations) for MediaWiki Graph connectors.</span></span> 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f6764-111">Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="f6764-111">Step 1: Add a Graph connector in the Microsoft 365 admin center.</span></span>
<span data-ttu-id="f6764-112">Befolgen Sie die allgemeinen Setupanweisungen.</span><span class="sxs-lookup"><span data-stu-id="f6764-112">Follow the general setup instructions.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="f6764-113">Schritt 2: Benennen Sie die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="f6764-113">Step 2: Name the connection.</span></span>
<span data-ttu-id="f6764-114">Befolgen Sie die allgemeinen Setupanweisungen.</span><span class="sxs-lookup"><span data-stu-id="f6764-114">Follow the general setup instructions.</span></span>
 
## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="f6764-115">Schritt 3: Konfigurieren Sie die Verbindungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f6764-115">Step 3: Configure the connection settings.</span></span>
<span data-ttu-id="f6764-116">Geben Sie **Ihre Wiki-URL** ein, und wählen Sie im Dropdownmenü der Optionen den Authentifizierungstyp aus. </span><span class="sxs-lookup"><span data-stu-id="f6764-116">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="f6764-117">Die Optionen sind **None**, **Basic** und **OAuth 2.0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="f6764-117">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="f6764-118">Wenn Sie **"Standard"** als Authentifizierungstyp  auswählen, müssen Sie den Benutzernamen und das **Kennwort für** das Wiki angeben.</span><span class="sxs-lookup"><span data-stu-id="f6764-118">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="f6764-119">Wenn Sie **OAuth 2.0 AAD** als Authentifizierungstyp auswählen, müssen Sie die **Ressourcen-ID** der Wiki-Installation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f6764-119">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="f6764-120">Sie müssen auch die **Client-ID** und den geheimen **Clientgeheimnis** bereitstellen, die auf der Registrierungsseite der AAD-Anwendung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="f6764-120">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span> 

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="f6764-121">Schritt 4: Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="f6764-121">Step 4: Manage search permissions</span></span>
<span data-ttu-id="f6764-122">Der Connector MediaWiki unterstützt nur Suchberechtigungen, die für jeden **sichtbar sind.**</span><span class="sxs-lookup"><span data-stu-id="f6764-122">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="f6764-123">Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="f6764-123">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="f6764-124">Schritt 5: Zuweisen von Eigenschaftsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="f6764-124">Step 5: Assign property labels</span></span>
<span data-ttu-id="f6764-125">Befolgen Sie die allgemeinen Setupanweisungen.</span><span class="sxs-lookup"><span data-stu-id="f6764-125">Follow the general setup instructions.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="f6764-126">Schritt 6: Verwalten des Schemas</span><span class="sxs-lookup"><span data-stu-id="f6764-126">Step 6: Manage schema</span></span>
<span data-ttu-id="f6764-127">Befolgen Sie die allgemeinen Setupanweisungen.</span><span class="sxs-lookup"><span data-stu-id="f6764-127">Follow the general setup instructions.</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="f6764-128">Schritt 7: Auswählen von Aktualisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="f6764-128">Step 7: Choose refresh settings</span></span>
<span data-ttu-id="f6764-129">Befolgen Sie die allgemeinen Setupanweisungen.</span><span class="sxs-lookup"><span data-stu-id="f6764-129">Follow the general setup instructions.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="f6764-130">Schritt 8: Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="f6764-130">Step 8: Review connection</span></span>
<span data-ttu-id="f6764-131">Befolgen Sie die allgemeinen Setupanweisungen.</span><span class="sxs-lookup"><span data-stu-id="f6764-131">Follow the general setup instructions.</span></span>

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="f6764-132">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f6764-132">Limitations</span></span>
<span data-ttu-id="f6764-133">Der MediaWiki Connector hat in der Vorschauversion die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="f6764-133">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="f6764-134">Unterstützt nur cloudbasierte Wikis.</span><span class="sxs-lookup"><span data-stu-id="f6764-134">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="f6764-135">Unterstützt nur Basic oder OAuth 2.0 mit Azure Active Directory- oder Azure-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f6764-135">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="f6764-136">Unterstützt keine Namespaceauswahl für die Indizierung.</span><span class="sxs-lookup"><span data-stu-id="f6764-136">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="f6764-137">Indiziert nur Die Namespaces "Main", "Category" und "File".</span><span class="sxs-lookup"><span data-stu-id="f6764-137">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="f6764-138">Unterstützt keine Zugriffssteuerungslisten (Access Control Lists, ACLs).</span><span class="sxs-lookup"><span data-stu-id="f6764-138">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="f6764-139">Daher sind indizierte Seiten für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="f6764-139">Thus, indexed pages are visible to all users in the organization.</span></span>
