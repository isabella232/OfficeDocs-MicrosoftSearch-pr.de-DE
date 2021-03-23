---
title: Dateifreigabe Graph Connector für Microsoft Search
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
ROBOTS: NoIndex
description: Einrichten des Graph-Connectors für die Dateifreigabe für Microsoft Search
ms.openlocfilehash: 792e853e5d2b7a23835dc031ff4ba4c09d619f9c
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031611"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="5facb-103">Dateifreigabe Graph-Connector</span><span class="sxs-lookup"><span data-stu-id="5facb-103">File share Graph connector</span></span>

<span data-ttu-id="5facb-104">Mit dem Graph-Connector für Dateifreigaben können Benutzer in Ihrer Organisation lokale Windows-Dateifreigaben durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="5facb-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="5facb-105">Lesen Sie [**den Artikel Setup für Ihren Graph-Connector,**](configure-connector.md) um den allgemeinen Setupprozess für Graph Connectors zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="5facb-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="5facb-106">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="5facb-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="5facb-107">Installieren des Graph-Connector-Agents</span><span class="sxs-lookup"><span data-stu-id="5facb-107">Install the Graph connector agent</span></span>

<span data-ttu-id="5facb-108">Zum Indizieren Ihrer Windows-Dateifreigaben müssen Sie den Graph-Connector-Agent installieren und registrieren.</span><span class="sxs-lookup"><span data-stu-id="5facb-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="5facb-109">Weitere Informationen finden Sie unter [Installieren des Graph-Connector-Agents.](on-prem-agent.md)</span><span class="sxs-lookup"><span data-stu-id="5facb-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="5facb-110">Inhaltsanforderungen</span><span class="sxs-lookup"><span data-stu-id="5facb-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="5facb-111">Dateitypen</span><span class="sxs-lookup"><span data-stu-id="5facb-111">File types</span></span>

<span data-ttu-id="5facb-112">Inhalte der folgenden Formate können indiziert und durchsucht werden: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLSB, XLSX, XLT, XLXM, XML, XPS und ZIP.</span><span class="sxs-lookup"><span data-stu-id="5facb-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="5facb-113">Nur der Textinhalt dieser Formate wird indiziert.</span><span class="sxs-lookup"><span data-stu-id="5facb-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="5facb-114">Alle Multimediainhalte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="5facb-114">All multimedia content is ignored.</span></span> <span data-ttu-id="5facb-115">Für alle Dateien, die nicht zu diesem Format gehören, werden die Metadaten allein indiziert.</span><span class="sxs-lookup"><span data-stu-id="5facb-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="5facb-116">Dateigrößenbegrenzungen</span><span class="sxs-lookup"><span data-stu-id="5facb-116">File size limits</span></span>

<span data-ttu-id="5facb-117">Die maximale unterstützte Dateigröße beträgt 100 MB.</span><span class="sxs-lookup"><span data-stu-id="5facb-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="5facb-118">Dateien, die 100 MB überschreiten, werden nicht indiziert.</span><span class="sxs-lookup"><span data-stu-id="5facb-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="5facb-119">Die maximale Nachverarbeitungsgröße beträgt 4 MB.</span><span class="sxs-lookup"><span data-stu-id="5facb-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="5facb-120">Die Verarbeitung wird beendet, wenn die Dateigröße 4 MB erreicht.</span><span class="sxs-lookup"><span data-stu-id="5facb-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="5facb-121">Daher können einige in der Datei enthaltene Ausdrücke möglicherweise nicht für die Suche verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5facb-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="5facb-122">Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="5facb-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="5facb-123">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5facb-123">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="5facb-124">Schritt 2: Benennen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="5facb-124">Step 2: Name the connection</span></span>

<span data-ttu-id="5facb-125">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5facb-125">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="5facb-126">Schritt 3: Konfigurieren der Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="5facb-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="5facb-127">Wählen Sie **auf der Seite** Mit Datenquelle verbinden die Option **Dateifreigabe aus,** und geben Sie den Namen, die Verbindungs-ID und die Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="5facb-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="5facb-128">Geben Sie auf der nächsten Seite den Pfad zur Dateifreigabe an, und wählen Sie Den zuvor installierten Graph-Connector-Agent aus.</span><span class="sxs-lookup"><span data-stu-id="5facb-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="5facb-129">Geben Sie die Anmeldeinformationen für ein [Microsoft Windows-Benutzerkonto](https://microsoft.com/windows) mit Lesezugriff auf alle Dateien in der Dateifreigabe ein.</span><span class="sxs-lookup"><span data-stu-id="5facb-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="5facb-130">Beibehalten der letzten Zugriffszeit</span><span class="sxs-lookup"><span data-stu-id="5facb-130">Preserve last access time</span></span>

<span data-ttu-id="5facb-131">Wenn der Connector versucht, eine Datei zu durchforsten, wird das Feld "Letzte Zugriffszeit" in den Metadaten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="5facb-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="5facb-132">Wenn Sie für Archivierungs- und Sicherungslösungen auf dieses Feld angewiesen sind und es nicht aktualisieren möchten, wenn der Connector darauf zutritt, können Sie diese Option auf der Seite Erweiterte Einstellungen **konfigurieren.**</span><span class="sxs-lookup"><span data-stu-id="5facb-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="5facb-133">Schritt 4: Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="5facb-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="5facb-134">Sie können die Berechtigung zum Suchen nach einer beliebigen Datei basierend auf Zugriffssteuerungslisten für freigabebasierte Oder NTFS-Zugriffssteuerungslisten (New Technology File System) einschränken, indem Sie auf der Seite Suchberechtigungen verwalten die gewünschte Option **auswählen.**</span><span class="sxs-lookup"><span data-stu-id="5facb-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists, by selecting the desired option in **Manage search permissions** page.</span></span> <span data-ttu-id="5facb-135">Die in diesen Zugriffssteuerungslisten bereitgestellten Benutzerkonten und Gruppen müssen von Active Directory (AD) verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="5facb-135">The user accounts and groups provided in these Access Control Lists must be managed by Active Directory (AD).</span></span> <span data-ttu-id="5facb-136">Wenn Sie ein anderes System für die Benutzerkontenverwaltung verwenden, können Sie die Option "Jeder" auswählen, mit der Benutzer nach allen Dateien ohne Zugriffseinschränkungen suchen können.</span><span class="sxs-lookup"><span data-stu-id="5facb-136">If you are using any other system for user accounts management, you can select 'everyone' option, which lets users search for all the files without any access restrictions.</span></span> <span data-ttu-id="5facb-137">Wenn Benutzer jedoch versuchen, die Datei zu öffnen, gelten die an der Quelle festgelegten Zugriffssteuerelemente.</span><span class="sxs-lookup"><span data-stu-id="5facb-137">However, when users try to open the file, access controls set at the source apply.</span></span>

<span data-ttu-id="5facb-138">Beachten Sie, dass Windows standardmäßig die Berechtigung "Lesen" für "Jeder" in Freigabe-ACLs bietet, wenn ein Ordner im Netzwerk freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5facb-138">Note that windows by default provides 'Read' permission to 'Everyone' in Share ACLs when a folder is shared on network.</span></span> <span data-ttu-id="5facb-139">Wenn Sie in Verwalten von Suchberechtigungen Freigabe-ACLs **auswählen,** können Benutzer nach allen Dateien suchen.</span><span class="sxs-lookup"><span data-stu-id="5facb-139">By extension, if you are choosing Share ACLs in **Manage search permissions**, users will be able to search for all the files.</span></span> <span data-ttu-id="5facb-140">Wenn Sie den Zugriff einschränken möchten, entfernen Sie "Lesezugriff" für "Jeder" in Dateifreigaben, und stellen Sie nur den gewünschten Benutzern und Gruppen Zugriff zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5facb-140">If you want to restrict access, remove 'Read' access for 'Everyone' in file shares and provide access only to the desired users and groups.</span></span> <span data-ttu-id="5facb-141">Der Connector liest dann diese Zugriffseinschränkungen und wendet diese auf die Suche an.</span><span class="sxs-lookup"><span data-stu-id="5facb-141">The connector then reads these access restrictions and applies them to search.</span></span>

<span data-ttu-id="5facb-142">Sie können nur dann Freigabe-ACLs auswählen, wenn der von Ihnen bereitgestellte Freigabepfad dem UNC-Pfadformat folgt.</span><span class="sxs-lookup"><span data-stu-id="5facb-142">You can choose Share ACLs only if the share path you provided follows UNC path format.</span></span> <span data-ttu-id="5facb-143">Sie können einen Pfad im UNC-Format erstellen, indem Sie unter "Freigabe" zu "Erweiterte Freigabe" gehen.</span><span class="sxs-lookup"><span data-stu-id="5facb-143">You can create a path in UNC format by going to 'Advanced Sharing' under 'Sharing' option.</span></span>

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="5facb-145">Schritt 5: Zuweisen von Eigenschaftsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="5facb-145">Step 5: Assign property labels</span></span>

<span data-ttu-id="5facb-146">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5facb-146">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="5facb-147">Schritt 6: Verwalten des Schemas</span><span class="sxs-lookup"><span data-stu-id="5facb-147">Step 6: Manage schema</span></span>

<span data-ttu-id="5facb-148">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5facb-148">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="5facb-149">Schritt 7: Auswählen von Aktualisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="5facb-149">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="5facb-150">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5facb-150">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="5facb-151">Schritt 8: Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="5facb-151">Step 8: Review connection</span></span>

<span data-ttu-id="5facb-152">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5facb-152">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->