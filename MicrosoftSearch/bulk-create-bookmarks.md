---
title: Massenerstellung von Lesezeichen
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
ROBOTS: NoIndex
description: Erstellen Sie viele Lesezeichen gleichzeitig mit Importtools für das Microsoft Search-Verwaltungsportal.
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948924"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="6e0bd-103">Massenerstellung von Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="6e0bd-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e0bd-104">Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="6e0bd-105">Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird das Microsoft Search im Bing-Portal entfernt.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="6e0bd-106">Es wird empfohlen, dass Sie für die ersten Schritte das Microsoft 365 Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="6e0bd-107">[Übersicht über Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="6e0bd-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="6e0bd-108">Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie zum Massen erstellen, bearbeiten und Speichern von Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-108">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="6e0bd-109">Wenn Sie vorhandene Lesezeichen Massen bearbeiten möchten, exportieren Sie Sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie dann.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-109">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="6e0bd-110">Klicken Sie in der oberen rechten Ecke des Abschnitts Lesezeichen auf **importieren** .</span><span class="sxs-lookup"><span data-stu-id="6e0bd-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="6e0bd-111">Klicken Sie auf **Lesezeichen Vorlage herunterladen (. CSV)**</span><span class="sxs-lookup"><span data-stu-id="6e0bd-111">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="6e0bd-112">Speichern und öffnen Sie die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-112">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="6e0bd-113">Hinzufügen der Lesezeichen Inhalte und-Einstellungen und Speichern der Datei</span><span class="sxs-lookup"><span data-stu-id="6e0bd-113">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="6e0bd-114">Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-114">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="6e0bd-115">Klicken Sie in der oberen rechten Ecke des Abschnitts Lesezeichen auf **importieren** .</span><span class="sxs-lookup"><span data-stu-id="6e0bd-115">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="6e0bd-116">Klicken Sie im Bereich Lesezeichen importieren auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-116">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="6e0bd-117">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-117">Click **Import**</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="6e0bd-118">Vermeiden von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="6e0bd-118">Prevent import errors</span></span>      
<span data-ttu-id="6e0bd-119">Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="6e0bd-120">Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="6e0bd-121">Nehmen Sie alle erforderlichen Änderungen vor und versuchen Sie erneut, die Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-121">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="6e0bd-122">Bis alle Fehler behoben sind, können Sie keine Lesezeichen erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-122">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="6e0bd-123">Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="6e0bd-123">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="6e0bd-124">Enthält die Überschriftenzeile aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-124">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="6e0bd-125">Enthält alle Spalten aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-125">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="6e0bd-126">Die Spaltenreihenfolge die gleiche ist wie in der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="6e0bd-127">Diese Spalten können leer sein: "ID", "Zuletzt geändert" und "Zuletzt geändert von".</span><span class="sxs-lookup"><span data-stu-id="6e0bd-127">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="6e0bd-128">Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-128">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="6e0bd-129">Auf der Grundlage des Felds „Status“ werden Lesezeichen als „Entwurf“, „vorgeschlagen“ oder „geplant“ gespeichert, oder sie werden automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-129">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="6e0bd-130">Wenn Sie die ID einer vorhandenen Textmarke hinzufügen, wird Sie auch durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-130">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="6e0bd-131">Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Lesezeichen aus einer org exportieren und in eine andere importieren.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-131">For partners who manage multiple organizations, you can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="6e0bd-132">Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.</span><span class="sxs-lookup"><span data-stu-id="6e0bd-132">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="6e0bd-133">Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Create Bookmarks](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="6e0bd-133">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
