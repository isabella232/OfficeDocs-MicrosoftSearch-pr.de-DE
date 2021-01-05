---
title: Dateifreigabe-Konnektor
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Einrichten des Dateifreigabe-Konnektors für Microsoft Search
ms.openlocfilehash: bf9fb730abd4ca6e42b681893525bbe3dd8a1419
ms.sourcegitcommit: 249f41723dd6fda1e93ee1a8f3f7571ef066454b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750897"
---
# <a name="file-share-connector"></a><span data-ttu-id="75eca-103">Dateifreigabe-Konnektor</span><span class="sxs-lookup"><span data-stu-id="75eca-103">File share connector</span></span>

<span data-ttu-id="75eca-104">Mit dem File Share Graph-Konnektor können Benutzer in Ihrer Organisation lokale Windows-Dateifreigaben durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="75eca-104">With the File share Graph connector, users in your organization can search on-premise Windows file shares.</span></span>

<span data-ttu-id="75eca-105">Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen Dateifreigabe-Konnektor konfigurieren, ausführen und überwachen.</span><span class="sxs-lookup"><span data-stu-id="75eca-105">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a file share connector.</span></span> <span data-ttu-id="75eca-106">Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="75eca-106">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-graph-connector-agent"></a><span data-ttu-id="75eca-107">Installieren des Graph Connector-Agents</span><span class="sxs-lookup"><span data-stu-id="75eca-107">Install Graph connector agent</span></span>

<span data-ttu-id="75eca-108">Um Ihre Windows-Dateifreigaben zu indizieren, müssen Sie die [Graph Connector Agent](on-prem-agent.md) -Software installieren und registrieren.</span><span class="sxs-lookup"><span data-stu-id="75eca-108">In order to index your Windows file shares, you must install and register [Graph connector agent](on-prem-agent.md) software.</span></span>

## <a name="content-requirements"></a><span data-ttu-id="75eca-109">Inhaltsanforderungen</span><span class="sxs-lookup"><span data-stu-id="75eca-109">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="75eca-110">Dateitypen</span><span class="sxs-lookup"><span data-stu-id="75eca-110">File types</span></span>

<span data-ttu-id="75eca-111">Der Inhalt der folgenden Formate kann indiziert und durchsucht werden: doc, DOCM, docx, dot, DOTX, eml, GIF, HTML, JPEG, MHT, MHTML, msg, nws, OBD, OBT, Odp, ODS, ODT, One, PDF, Pot, PPS, PPT, PPTM, PPTX, txt, XLB, XLC, xlsb, xls, xlsx, XLT, XLXM, XML, XPS und zip.</span><span class="sxs-lookup"><span data-stu-id="75eca-111">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="75eca-112">Nur der Textinhalt dieser Formate wird indiziert.</span><span class="sxs-lookup"><span data-stu-id="75eca-112">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="75eca-113">Alle Multimedia-Inhalte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="75eca-113">All multimedia content is ignored.</span></span> <span data-ttu-id="75eca-114">Für alle Dateien, die nicht zu diesem Format gehören, werden die Metadaten allein indiziert.</span><span class="sxs-lookup"><span data-stu-id="75eca-114">For any file that does not belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="75eca-115">Dateigrößenbegrenzungen</span><span class="sxs-lookup"><span data-stu-id="75eca-115">File size limits</span></span>

<span data-ttu-id="75eca-116">Die maximal unterstützte Dateigröße beträgt 100 MB.</span><span class="sxs-lookup"><span data-stu-id="75eca-116">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="75eca-117">Dateien, die 100 MB überschreiten, werden nicht indiziert.</span><span class="sxs-lookup"><span data-stu-id="75eca-117">Files that exceed 100 MB are not indexed.</span></span> <span data-ttu-id="75eca-118">Der maximale Grenzwert für die Post verarbeitete Größe beträgt 4 MB.</span><span class="sxs-lookup"><span data-stu-id="75eca-118">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="75eca-119">Die Verarbeitung wird angehalten, wenn die Größe einer Datei 4 MB erreicht.</span><span class="sxs-lookup"><span data-stu-id="75eca-119">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="75eca-120">Einige in der Datei vorhandene Ausdrücke funktionieren daher möglicherweise nicht für die Suche.</span><span class="sxs-lookup"><span data-stu-id="75eca-120">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="75eca-121">Herstellen einer Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="75eca-121">Connect to a data source</span></span>

<span data-ttu-id="75eca-122">Wählen Sie auf der Seite mit **Datenquelle verbinden** die Option **Dateifreigabe** aus, und geben Sie den Namen, die Verbindungs-ID und die Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="75eca-122">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="75eca-123">Geben Sie auf der nächsten Seite den Pfad zur Dateifreigabe an, und wählen Sie den zuvor installierten Graph Connector-Agent aus.</span><span class="sxs-lookup"><span data-stu-id="75eca-123">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="75eca-124">Geben Sie die Anmeldeinformationen für ein [Microsoft Windows](https://microsoft.com/windows) -Benutzerkonto mit Lesezugriff auf alle Dateien in der Dateifreigabe ein.</span><span class="sxs-lookup"><span data-stu-id="75eca-124">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

## <a name="preserve-last-access-time"></a><span data-ttu-id="75eca-125">Beibehalten der letzten Zugriffszeit</span><span class="sxs-lookup"><span data-stu-id="75eca-125">Preserve last access time</span></span>

<span data-ttu-id="75eca-126">Wenn der Connector versucht, eine Datei zu durchforsten, wird das Feld "Letzter Zugriffszeit" in den zugehörigen Metadaten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="75eca-126">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="75eca-127">Wenn Sie dieses Feld für Archivierungs-und Sicherungslösungen benötigen und es nicht aktualisieren möchten, wenn der Connector darauf zugreift, können Sie diese Option auf der Seite **Erweiterte Einstellungen** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="75eca-127">If you depend on that field for any archiving and backup solutions and do not want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="75eca-128">Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="75eca-128">Manage search permissions</span></span>

<span data-ttu-id="75eca-129">Sie können die Berechtigung für die Suche nach beliebigen Dateien einschränken, die auf Freigabe-Zugriffssteuerungslisten oder NTFS-Zugriffssteuerungslisten (Access Control Lists) für neue Technologie-Dateisysteme basieren.</span><span class="sxs-lookup"><span data-stu-id="75eca-129">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="75eca-130">Wenn Sie Zugriffssteuerungslisten freigeben verwenden möchten, wählen Sie die entsprechende Option auf der Seite **Erweiterte Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="75eca-130">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="75eca-131">Wenn Sie NTFS-Zugriffssteuerungslisten verwenden möchten, wählen Sie die entsprechende Option auf der Seite **Suchberechtigungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="75eca-131">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="75eca-132">Zuweisen von Eigenschaften Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="75eca-132">Assign property labels</span></span>

<span data-ttu-id="75eca-133">Sie können jeder Beschriftung eine Source-Eigenschaft zuweisen, indem Sie in einem Menü mit Optionen auswählen.</span><span class="sxs-lookup"><span data-stu-id="75eca-133">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="75eca-134">Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaften Bezeichnungen verbessern die Suchrelevanz und stellen genauere Suchergebnisse für Endbenutzer sicher.</span><span class="sxs-lookup"><span data-stu-id="75eca-134">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="75eca-135">Schema verwalten</span><span class="sxs-lookup"><span data-stu-id="75eca-135">Manage schema</span></span>

<span data-ttu-id="75eca-136">Auf dem Bildschirm " **Schema verwalten** " haben Sie die Möglichkeit, die den Eigenschaften zugeordneten Schema **Attribute (** abfragbar, **durchsuchbar**, **abrufbar** und **verfeinernd**) zu ändern, optionale Aliase hinzuzufügen und die **Content** -Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="75eca-136">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="75eca-137">Festlegen des Aktualisierungszeitplans</span><span class="sxs-lookup"><span data-stu-id="75eca-137">Set the refresh schedule</span></span>

<span data-ttu-id="75eca-138">Das empfohlene Standardintervall für die Aktualisierungsplanung beträgt 15 Minuten, Sie können es jedoch basierend auf Ihren Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="75eca-138">The recommended default refresh schedule interval is 15 minutes, but you can change it based on your preferences.</span></span>

## <a name="result-layout"></a><span data-ttu-id="75eca-139">Ergebnis Layout</span><span class="sxs-lookup"><span data-stu-id="75eca-139">Result layout</span></span>

<span data-ttu-id="75eca-140">Es wird empfohlen, das Standardergebnis Layout zum Anzeigen der Ergebnisse der FileShare-Konnektoren zu verwenden, da es über entsprechende Symbole und Steuerelemente verfügt, mit denen Sie zum Dateipfad navigieren können.</span><span class="sxs-lookup"><span data-stu-id="75eca-140">We recommend that you use the default result layout to display your Fileshare connector results because it has appropriate icons and controls that help you navigate to the file path.</span></span> <span data-ttu-id="75eca-141">Wenn Sie ein neues Ergebnis Layout erstellen, wird die Standardeinstellung außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="75eca-141">If you create a new result layout, it will override the default.</span></span>
