---
title: Massenerstellen von Lesezeichen
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
ms.openlocfilehash: 07694de1f546a1431f371fa24ffc5721ea66337c
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068402"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="1baf3-103">Massenerstellen von Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="1baf3-103">Bulk create bookmarks</span></span>

<span data-ttu-id="1baf3-p101">Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie zum Massen erstellen, bearbeiten und Speichern von Lesezeichen. Zum Massen Bearbeiten vorhandener Lesezeichen, exportieren Sie diese aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="1baf3-p101">Download and use the .csv template to bulk create, edit, and save bookmarks. To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="1baf3-106">Klicken Sie in der oberen rechten Ecke des Abschnitts Lesezeichen auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="1baf3-106">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="1baf3-107">Klicken Sie auf **Lesezeichen Vorlage herunterladen (. CSV)**</span><span class="sxs-lookup"><span data-stu-id="1baf3-107">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="1baf3-108">Speichern und Öffnen der CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="1baf3-108">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="1baf3-109">Hinzufügen des Inhalts und der Einstellungen für die Textmarke und Speichern der Datei</span><span class="sxs-lookup"><span data-stu-id="1baf3-109">Add the bookmark content and settings and save the file</span></span>
    
5. <span data-ttu-id="1baf3-110">Klicken Sie in der oberen rechten Ecke des Abschnitts Lesezeichen auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="1baf3-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="1baf3-111">Klicken Sie im Bereich Lesezeichen importieren auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1baf3-111">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="1baf3-112">Klicken Sie auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="1baf3-112">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="1baf3-113">Verhindern von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="1baf3-113">Prevent import errors</span></span>      
<span data-ttu-id="1baf3-p102">Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren.</span><span class="sxs-lookup"><span data-stu-id="1baf3-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="1baf3-117">Sie können keine Lesezeichen erstellen oder bearbeiten, bis alle Fehler aufgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="1baf3-117">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="1baf3-118">Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="1baf3-118">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="1baf3-119">Enthält die Überschriftenzeile, die sich in der Importvorlage befand</span><span class="sxs-lookup"><span data-stu-id="1baf3-119">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="1baf3-120">Enthält alle Spalten, die in der Importvorlage enthalten waren.</span><span class="sxs-lookup"><span data-stu-id="1baf3-120">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="1baf3-121">Die Reihenfolge der Spalten ist identisch mit der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="1baf3-121">The column order is the same as the import template</span></span>
- <span data-ttu-id="1baf3-122">Diese Spalten können leer sein: ID, zuletzt geändert und zuletzt geändert von</span><span class="sxs-lookup"><span data-stu-id="1baf3-122">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="1baf3-123">Die Spalte Status kann nicht leer sein, diese Informationen sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1baf3-123">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="1baf3-124">Basierend auf dem Feld Status werden Lesezeichen als Entwurf, vorgeschlagen oder geplant gespeichert, oder Sie werden automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="1baf3-124">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="1baf3-125">Wenn Sie die ID einer vorhandenen Textmarke hinzufügen, wird Sie auch durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1baf3-125">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="1baf3-p103">Für Organisationen mit mehreren Stand-Mandanten können Sie Ihre Lesezeichen aus einem Mandanten exportieren und in einen anderen importieren. Sie müssen jedoch vor dem Importieren alle Daten in der Spalte "ID" entfernen.</span><span class="sxs-lookup"><span data-stu-id="1baf3-p103">For organizations with mulitple tenants, you can export your bookmarks from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="1baf3-128">Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Create Bookmarks](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="1baf3-128">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
