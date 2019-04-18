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
description: Erstellen Sie viele Lesezeichen gleichzeitig mit Importtools für das Microsoft Search-Verwaltungsportal.
ms.openlocfilehash: 7c134784f0ca0d4cc84d5bce3a98f7e75aa6f441
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901792"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="863e5-103">Massenerstellung von Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="863e5-103">Bulk create bookmarks</span></span>

<span data-ttu-id="863e5-104">Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie zum Massen erstellen, bearbeiten und Speichern von Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="863e5-104">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="863e5-105">Zum Massen Bearbeiten vorhandener Lesezeichen, exportieren Sie diese aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="863e5-105">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="863e5-106">Klicken Sie in der oberen rechten Ecke des Abschnitts Lesezeichen auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="863e5-106">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="863e5-107">Klicken Sie auf **Lesezeichen Vorlage herunterladen (. CSV)**</span><span class="sxs-lookup"><span data-stu-id="863e5-107">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="863e5-108">Speichern und Öffnen der CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="863e5-108">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="863e5-109">Hinzufügen des Inhalts und der Einstellungen für die Textmarke und Speichern der Datei</span><span class="sxs-lookup"><span data-stu-id="863e5-109">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="863e5-110">Die CSV-Datei sollte als CSV-UTF-8-Datei gespeichert werden, andere Dateitypen und Codierungen können zu Importfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="863e5-110">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="863e5-111">Klicken Sie in der oberen rechten Ecke des Abschnitts Lesezeichen auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="863e5-111">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="863e5-112">Klicken Sie im Bereich Lesezeichen importieren auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="863e5-112">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="863e5-113">Klicken Sie auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="863e5-113">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="863e5-114">Verhindern von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="863e5-114">Prevent import errors</span></span>      
<span data-ttu-id="863e5-115">Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="863e5-115">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="863e5-116">Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="863e5-116">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="863e5-117">Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren.</span><span class="sxs-lookup"><span data-stu-id="863e5-117">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="863e5-118">Sie können keine Lesezeichen erstellen oder bearbeiten, bis alle Fehler aufgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="863e5-118">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="863e5-119">Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="863e5-119">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="863e5-120">Enthält die Überschriftenzeile, die sich in der Importvorlage befand</span><span class="sxs-lookup"><span data-stu-id="863e5-120">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="863e5-121">Enthält alle Spalten, die in der Importvorlage enthalten waren.</span><span class="sxs-lookup"><span data-stu-id="863e5-121">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="863e5-122">Die Reihenfolge der Spalten ist identisch mit der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="863e5-122">The column order is the same as the import template</span></span>
- <span data-ttu-id="863e5-123">Diese Spalten können leer sein: ID, zuletzt geändert und zuletzt geändert von</span><span class="sxs-lookup"><span data-stu-id="863e5-123">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="863e5-124">Die Spalte Status kann nicht leer sein, diese Informationen sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="863e5-124">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="863e5-125">Basierend auf dem Feld Status werden Lesezeichen als Entwurf, vorgeschlagen oder geplant gespeichert, oder Sie werden automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="863e5-125">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="863e5-126">Wenn Sie die ID einer vorhandenen Textmarke hinzufügen, wird Sie auch durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="863e5-126">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="863e5-127">Für Organisationen mit mehreren Stand-Mandanten können Sie Ihre Lesezeichen aus einem Mandanten exportieren und in einen anderen importieren.</span><span class="sxs-lookup"><span data-stu-id="863e5-127">For organizations with mulitple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="863e5-128">Sie müssen jedoch vor dem Importieren alle Daten in der Spalte "ID" entfernen.</span><span class="sxs-lookup"><span data-stu-id="863e5-128">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="863e5-129">Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Create Bookmarks](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="863e5-129">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
