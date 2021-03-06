---
title: Azure Data Lake Graph Connector für Microsoft Search
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
description: Einrichten des Azure Data Lake Storage Gen2 Graph-Connectors für Microsoft Search
ms.openlocfilehash: 2bb9570bc3b0a5adef7ac72ea1620c4f22a8aefb
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508886"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a><span data-ttu-id="54755-103">Azure Data Lake Storage Gen2 Graph Connector</span><span class="sxs-lookup"><span data-stu-id="54755-103">Azure Data Lake Storage Gen2 Graph connector</span></span>

<span data-ttu-id="54755-104">Mit dem Azure Data Lake Storage Gen2 Graph-Connector können Benutzer in Ihrer Organisation nach Dateien suchen, die in [Azure Blob Storage-](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) und [Azure Data Lake Gen 2-Speicherkonten gespeichert](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) sind.</span><span class="sxs-lookup"><span data-stu-id="54755-104">The Azure Data Lake Storage Gen2 Graph connector allows users in your organization to search for files stored in [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="54755-105">Lesen Sie [**den Artikel Setup your Graph connector,**](configure-connector.md) um die allgemeinen Anweisungen zum Einrichten von Graph Connectors zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="54755-105">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="54755-106">Dieser Artikel ist für jeden Benutzer verfügbar, der einen Azure Data Lake Storage Gen2-Connector konfiguriert, ausgeführt und überwacht.</span><span class="sxs-lookup"><span data-stu-id="54755-106">This article is for anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="54755-107">Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Azure Data Lake Storage Gen2-Connector gelten.</span><span class="sxs-lookup"><span data-stu-id="54755-107">It supplements the general setup process, and shows instructions that apply only for the Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="54755-108">Dieser Artikel enthält auch Informationen zu [Einschränkungen](#limitations).</span><span class="sxs-lookup"><span data-stu-id="54755-108">This article also includes information about [Limitations](#limitations).</span></span>

<span data-ttu-id="54755-109">In diesem Artikel verwenden wir *Azure Storage* als generischen Begriff für Azure [Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) und Azure Data Lake [Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).</span><span class="sxs-lookup"><span data-stu-id="54755-109">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="54755-110">Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="54755-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="54755-111">Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).</span><span class="sxs-lookup"><span data-stu-id="54755-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="54755-112">Schritt 2: Benennen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="54755-112">Step 2: Name the connection</span></span>

<span data-ttu-id="54755-113">Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).</span><span class="sxs-lookup"><span data-stu-id="54755-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="54755-114">Schritt 3: Konfigurieren der Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="54755-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="54755-115">Geben Sie ihre primäre Speicherverbindung String ein.</span><span class="sxs-lookup"><span data-stu-id="54755-115">Enter your Primary storage connection String.</span></span> <span data-ttu-id="54755-116">Diese Zeichenfolge ist erforderlich, um den Zugriff auf Ihr Speicherkonto zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="54755-116">This string is required to allow access to your storage account.</span></span> <span data-ttu-id="54755-117">Um Ihre Verbindungszeichenfolge zu finden, wechseln Sie zum [Azure-Portal,](https://ms.portal.azure.com/#home) und navigieren Sie zum Abschnitt **Schlüssel** Ihres relevanten Azure Storage-Kontos.</span><span class="sxs-lookup"><span data-stu-id="54755-117">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span>

<span data-ttu-id="54755-118">Wenn Sie den **AccountKey** (einen Parameter in der primären Speicherverbindungszeichenfolge) nicht angeben möchten, gewähren Sie für die folgenden Rollen Zugriff auf unseren Graph Connectors-Dienst:</span><span class="sxs-lookup"><span data-stu-id="54755-118">If you prefer not to provide the **AccountKey** (a parameter in the primary storage connection string), grant access to our Graph Connectors Service for the following roles:</span></span>

* <span data-ttu-id="54755-119">Speicher-Blob-Datenleser</span><span class="sxs-lookup"><span data-stu-id="54755-119">Storage Blob Data Reader</span></span>
* <span data-ttu-id="54755-120">Datenwirkender in der Speicherwarteschlange</span><span class="sxs-lookup"><span data-stu-id="54755-120">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="54755-121">Speicher-Blob-Delegator</span><span class="sxs-lookup"><span data-stu-id="54755-121">Storage Blob Delegator</span></span>

<span data-ttu-id="54755-122">Navigieren Sie zur **Registerkarte Zugriffssteuerung** Ihres Azure Storage-Kontos, und befolgen Sie die Anweisungen dort, um Zugriff auf die folgende App zu gewähren:</span><span class="sxs-lookup"><span data-stu-id="54755-122">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="54755-123">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="54755-123">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="54755-124">**Name der First Party App:** Graph Connector Service</span><span class="sxs-lookup"><span data-stu-id="54755-124">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="54755-125">Speicherkonto- und Warteschlangenbenachrichtigungen (Optional)</span><span class="sxs-lookup"><span data-stu-id="54755-125">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="54755-126">Unterstützung zum Verarbeiten von Änderungen in Echtzeit im Graph Connectors-Dienst wird möglicherweise in Der Zukunft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="54755-126">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="54755-127">In diesem Fall überwachen wir Änderungsbenachrichtigungen für Azure Storage, die in einer Warteschlange gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="54755-127">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="54755-128">Sie müssen eine Warteschlange im gleichen Konto wie Ihr Azure Storage-Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="54755-128">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="54755-129">Nachdem Sie eine Warteschlange erstellt haben, wechseln Sie zur Registerkarte **Ereignisse** auf der Warteschlangenseite, um das **Ereignisabonnement zu konfigurieren.**</span><span class="sxs-lookup"><span data-stu-id="54755-129">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="54755-130">Wählen Sie alle Blob-Ereignisse aus, die die Warteschlange erhält, und verbinden Sie die Warteschlange mit dem Azure Storage-Konto.</span><span class="sxs-lookup"><span data-stu-id="54755-130">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="54755-131">Schritt 4: Zuweisen von Eigenschaftsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="54755-131">Step 4: Assign property labels</span></span>

<span data-ttu-id="54755-132">Sie können jeder Bezeichnung eine Quelleigenschaft zuweisen, indem Sie aus einem Menü mit Optionen auswählen.</span><span class="sxs-lookup"><span data-stu-id="54755-132">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="54755-133">Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaftsbezeichnungen verbessern die Suchrelevanz und sorgen für bessere Suchergebnisse für Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="54755-133">While this step isn't mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="54755-134">Schritt 5: Verwalten des Schemas</span><span class="sxs-lookup"><span data-stu-id="54755-134">Step 5: Manage schema</span></span>

<span data-ttu-id="54755-135">Auf dem **Bildschirm Schema verwalten** können Sie die den Eigenschaften zugeordneten Schemaattribute ändern, die Optionen sind **Query,** **Search,** **Retrieve** und **Refine.**</span><span class="sxs-lookup"><span data-stu-id="54755-135">On the **Manage Schema** screen, you can change the schema attributes associated with the properties, the options are **Query**, **Search**, **Retrieve**, and **Refine**.</span></span> <span data-ttu-id="54755-136">Sie können auch optionale Aliase hinzufügen und die **Content-Eigenschaft** auswählen.</span><span class="sxs-lookup"><span data-stu-id="54755-136">You also can add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="54755-137">Schritt 6: Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="54755-137">Step 6: Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="54755-138">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="54755-138">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="54755-139">Sie können die Zugriffssteuerungslisten (Access Control Lists, ACLs) von Ihrem [Azure Data Lake Gen 2-Speicherkonto](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) aus verwenden.</span><span class="sxs-lookup"><span data-stu-id="54755-139">You can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="54755-140">Wenn diese Suchberechtigungen festgelegt sind, wird der Suchinhalt basierend auf den Berechtigungen des in Azure Active Directory signierten [Benutzers gekürzt.](https://docs.microsoft.com/azure/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="54755-140">When these search permissions are set, search content is trimmed based on the permissions of the user signed in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/).</span></span> <span data-ttu-id="54755-141">Alternativ können Sie festlegen, dass alle Inhalte, die aus Ihrem Speicherkonto indiziert werden, für alle Benutzer in Ihrer Organisation sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="54755-141">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="54755-142">In diesem Fall hat jeder Benutzer in Ihrer Organisation Zugriff auf alle Daten in Ihrem Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="54755-142">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

<span data-ttu-id="54755-143">Der Azure Data Lake Storage Gen2 Graph-Connector unterstützt Suchberechtigungen, die für **Jeder** oder nur Personen mit Zugriff **auf diese Datenquelle sichtbar sind.**</span><span class="sxs-lookup"><span data-stu-id="54755-143">The Azure Data Lake Storage Gen2 Graph connector supports search permissions visible to **Everyone**, or **Only people with access to this data source**.</span></span> <span data-ttu-id="54755-144">Indizierte Daten, die in den Suchergebnissen angezeigt werden, können benutzern in der Organisation angezeigt werden, die Zugriff auf jedes Element haben.</span><span class="sxs-lookup"><span data-stu-id="54755-144">Indexed data that appears in the search results could be visible to users in the organization who have access to each item.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="54755-145">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="54755-145">Azure Blob Storage</span></span>

<span data-ttu-id="54755-146">Bei einer Verbindung mit [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)sind alle Inhalte, die aus der konfigurierten Quelle indiziert wurden, für alle Benutzer in Ihrer Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="54755-146">For a connection to [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="54755-147">Zugriffssteuerungslisten werden auf Blobebene in Azure Blob Storage nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="54755-147">Access control lists aren't supported at Blob level in Azure Blob Storage.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="54755-148">Schritt 7: Festlegen des Aktualisierungszeitplans</span><span class="sxs-lookup"><span data-stu-id="54755-148">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="54755-149">Auf dem **Bildschirm Einstellungen aktualisieren** können Sie das inkrementelle Durchforstungsintervall und das vollständige Durchforstungsintervall festlegen.</span><span class="sxs-lookup"><span data-stu-id="54755-149">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="54755-150">Die Standardintervalle für den Azure Data Lake Storage Gen2-Connector sind 15 Minuten für eine inkrementelle Durchforstung und eine Woche für eine vollständige Durchforstung.</span><span class="sxs-lookup"><span data-stu-id="54755-150">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="54755-151">Schritt 8: Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="54755-151">Step 8: Review connection</span></span>

<span data-ttu-id="54755-152">Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).</span><span class="sxs-lookup"><span data-stu-id="54755-152">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="54755-153">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="54755-153">Limitations</span></span>

<span data-ttu-id="54755-154">Eine veröffentlichte Verbindung für Azure Blob Storage kann nicht für die Azure Data Lake Storage Gen2-Quelle und umgekehrt neu konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="54755-154">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and the other way around.</span></span> <span data-ttu-id="54755-155">In solchen Szenarien wird empfohlen, eine neue Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="54755-155">In such scenarios, it's recommended to configure a new connection.</span></span>

<span data-ttu-id="54755-156">Außerdem muss die Größe der Dateien 4 MB oder weniger betragen, damit sie durchforstet werden können.</span><span class="sxs-lookup"><span data-stu-id="54755-156">Also, the size of the files needs to be 4 MB or less for it to be crawled.</span></span> <span data-ttu-id="54755-157">Derzeit werden die folgenden Dateitypen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="54755-157">File types currently supported are:</span></span>

* <span data-ttu-id="54755-158">Word (docx, .docm, .dotx, .dotm)</span><span class="sxs-lookup"><span data-stu-id="54755-158">Word (docx, .docm, .dotx, .dotm)</span></span>
* <span data-ttu-id="54755-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span><span class="sxs-lookup"><span data-stu-id="54755-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span></span>
* <span data-ttu-id="54755-160">Excel (.xlsx, .xlsm)</span><span class="sxs-lookup"><span data-stu-id="54755-160">Excel (.xlsx, .xlsm)</span></span>
* <span data-ttu-id="54755-161">Ältere Office-Formate (DOC, DOT usw.)</span><span class="sxs-lookup"><span data-stu-id="54755-161">Legacy Office formats (.doc, .dot, etc.)</span></span>
* <span data-ttu-id="54755-162">Text (.txt)</span><span class="sxs-lookup"><span data-stu-id="54755-162">Text (.txt)</span></span>
* <span data-ttu-id="54755-163">HTML</span><span class="sxs-lookup"><span data-stu-id="54755-163">HTML</span></span>
* <span data-ttu-id="54755-164">PDF</span><span class="sxs-lookup"><span data-stu-id="54755-164">PDF</span></span>

<span data-ttu-id="54755-165">Binärdateien wie Bilder (.jpg, .bmp usw.) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="54755-165">Binary files like images (.jpg, .bmp, etc.) are not supported.</span></span> <span data-ttu-id="54755-166">Wenn eine DOCX-Datei beispielsweise nur Bilder enthält, wird sie möglicherweise übersprungen, da sie keinen Inhalt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="54755-166">For example, if a .docx file contains only images, it might be skipped because it didn't return any content.</span></span>
