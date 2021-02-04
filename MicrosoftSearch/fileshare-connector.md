---
title: Dateifreigabe -Graph-Connector für Microsoft Search
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
ROBOTS: NoIndex
description: Einrichten des Dateifreigabe-Graph-Connectors für Microsoft Search
ms.openlocfilehash: e8a68a1c6b9c2c8a8592fb915fe9bf846a758e77
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097421"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="57cf0-103">Dateifreigabe -Graph-Connector</span><span class="sxs-lookup"><span data-stu-id="57cf0-103">File share Graph connector</span></span>

<span data-ttu-id="57cf0-104">Der Dateifreigabe-Graph-Connector ermöglicht Benutzern in Ihrer Organisation das Durchsuchen von lokalen Windows-Dateifreigaben.</span><span class="sxs-lookup"><span data-stu-id="57cf0-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="57cf0-105">Lesen Sie [**den Artikel "Setup für Ihren Graph-Connector",**](configure-connector.md) um den allgemeinen Einrichtungsprozess für Graph Connectors zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="57cf0-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="57cf0-106">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="57cf0-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="57cf0-107">Installieren des Graph-Connector-Agents</span><span class="sxs-lookup"><span data-stu-id="57cf0-107">Install the Graph connector agent</span></span>

<span data-ttu-id="57cf0-108">Um Ihre Windows-Dateifreigaben zu indizieren, müssen Sie den Graph-Connector-Agent installieren und registrieren.</span><span class="sxs-lookup"><span data-stu-id="57cf0-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="57cf0-109">Weitere [Informationen finden Sie unter "Installieren des Graph-Connector-Agents".](on-prem-agent.md)</span><span class="sxs-lookup"><span data-stu-id="57cf0-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="57cf0-110">Inhaltsanforderungen</span><span class="sxs-lookup"><span data-stu-id="57cf0-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="57cf0-111">Dateitypen</span><span class="sxs-lookup"><span data-stu-id="57cf0-111">File types</span></span>

<span data-ttu-id="57cf0-112">Inhalte der folgenden Formate können indiziert und durchsucht werden: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLSX, XLSX, XLT, XLXM, XML, XPS und ZIP.</span><span class="sxs-lookup"><span data-stu-id="57cf0-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="57cf0-113">Nur der Textinhalt dieser Formate wird indiziert.</span><span class="sxs-lookup"><span data-stu-id="57cf0-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="57cf0-114">Alle Multimediainhalte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="57cf0-114">All multimedia content is ignored.</span></span> <span data-ttu-id="57cf0-115">Für jede Datei, die nicht zu diesem Format gehört, werden die Metadaten allein indiziert.</span><span class="sxs-lookup"><span data-stu-id="57cf0-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="57cf0-116">Dateigrößenbegrenzungen</span><span class="sxs-lookup"><span data-stu-id="57cf0-116">File size limits</span></span>

<span data-ttu-id="57cf0-117">Die maximal unterstützte Dateigröße beträgt 100 MB.</span><span class="sxs-lookup"><span data-stu-id="57cf0-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="57cf0-118">Dateien, die 100 MB überschreiten, werden nicht indiziert.</span><span class="sxs-lookup"><span data-stu-id="57cf0-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="57cf0-119">Die maximale Nachverarbeitungsgröße beträgt 4 MB.</span><span class="sxs-lookup"><span data-stu-id="57cf0-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="57cf0-120">Die Verarbeitung wird beendet, wenn die Größe einer Datei 4 MB erreicht.</span><span class="sxs-lookup"><span data-stu-id="57cf0-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="57cf0-121">Daher können einige in der Datei enthaltene Ausdrücke möglicherweise nicht für die Suche verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="57cf0-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="57cf0-122">Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="57cf0-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="57cf0-123">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="57cf0-123">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="57cf0-124">Schritt 2: Benennen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="57cf0-124">Step 2: Name the connection</span></span>

<span data-ttu-id="57cf0-125">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="57cf0-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="57cf0-126">Schritt 3: Konfigurieren der Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="57cf0-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="57cf0-127">Wählen Sie **auf der Seite "Mit** Datenquelle verbinden" die **Dateifreigabe aus,** und geben Sie den Namen, die Verbindungs-ID und die Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="57cf0-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="57cf0-128">Geben Sie auf der nächsten Seite den Pfad zur Dateifreigabe an, und wählen Sie Ihren zuvor installierten Graph-Connector-Agent aus.</span><span class="sxs-lookup"><span data-stu-id="57cf0-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="57cf0-129">Geben Sie die Anmeldeinformationen für ein [Microsoft Windows-Benutzerkonto](https://microsoft.com/windows) mit Lesezugriff auf alle Dateien in der Dateifreigabe ein.</span><span class="sxs-lookup"><span data-stu-id="57cf0-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="57cf0-130">Beibehalten der letzten Zugriffszeit</span><span class="sxs-lookup"><span data-stu-id="57cf0-130">Preserve last access time</span></span>

<span data-ttu-id="57cf0-131">Wenn der Connector versucht, eine Datei zu durchforsten, wird das Feld "Letzte Zugriffszeit" in den Metadaten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="57cf0-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="57cf0-132">Wenn Sie dieses Feld für Archivierungs- und Sicherungslösungen verwenden und es nicht aktualisieren möchten, wenn der Connector darauf zutritt, können Sie diese Option auf der Seite "Erweiterte Einstellungen" **konfigurieren.**</span><span class="sxs-lookup"><span data-stu-id="57cf0-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="57cf0-133">Schritt 4: Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="57cf0-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="57cf0-134">Sie können die Berechtigung zum Suchen nach einer beliebigen Datei basierend auf Share Access Control Lists oder NTFS (New Technology File System)-Zugriffssteuerungslisten einschränken.</span><span class="sxs-lookup"><span data-stu-id="57cf0-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="57cf0-135">Wenn Sie Zugriffssteuerungslisten freigeben möchten, wählen Sie die entsprechende Option auf der Seite **"Erweiterte Einstellungen"** aus.</span><span class="sxs-lookup"><span data-stu-id="57cf0-135">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="57cf0-136">Wenn Sie NTFS-Zugriffssteuerungslisten verwenden möchten, wählen Sie auf der Seite Suchberechtigungen verwalten die **entsprechende Option** aus.</span><span class="sxs-lookup"><span data-stu-id="57cf0-136">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="57cf0-137">Schritt 5: Zuweisen von Eigenschaftsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="57cf0-137">Step 5: Assign property labels</span></span>

<span data-ttu-id="57cf0-138">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="57cf0-138">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="57cf0-139">Schritt 6: Verwalten des Schemas</span><span class="sxs-lookup"><span data-stu-id="57cf0-139">Step 6: Manage schema</span></span>

<span data-ttu-id="57cf0-140">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="57cf0-140">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="57cf0-141">Schritt 7: Auswählen von Aktualisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="57cf0-141">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="57cf0-142">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="57cf0-142">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="57cf0-143">Schritt 8: Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="57cf0-143">Step 8: Review connection</span></span>

<span data-ttu-id="57cf0-144">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="57cf0-144">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
