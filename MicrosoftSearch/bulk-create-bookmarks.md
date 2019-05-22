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
description: Erstellen Sie mit den Importtools für das Microsoft Search-Verwaltungsportal sehr viele Lesezeichen gleichzeitig.
ms.openlocfilehash: 560cda6f94060d428f2d18cc61bd2430cb31b474
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968348"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="778f4-103">Massenerstellung von Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="778f4-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="778f4-104">Die Einstellungen für Microsoft Search in Bing sind nun im Microsoft 365 Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="778f4-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="778f4-105">Beginnen Sie, indem Sie [Suchadministratoren](https://docs.microsoft.com/de-DE/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in Ihrem Admin Center zuweisen.</span><span class="sxs-lookup"><span data-stu-id="778f4-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="778f4-106">Laden Sie die CSV-Vorlage herunter, und verwenden Sie sie zur Massenerstellung-, -bearbeitung und -speicherung von Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="778f4-106">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="778f4-107">Wenn Sie eine Massenbearbeitung von vorhandenen Lesezeichen ausführen möchten, exportieren Sie sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="778f4-107">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="778f4-108">Klicken Sie in der oberen rechten Ecke des Abschnitts "Lesezeichen" auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="778f4-108">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="778f4-109">Klicken Sie auf **Lesezeichenvorlage (CSV) herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="778f4-109">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="778f4-110">Speichern und öffnen Sie die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="778f4-110">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="778f4-111">Fügen Sie den Lesezeicheninhalt und die Einstellungen hinzu, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="778f4-111">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="778f4-112">Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="778f4-112">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="778f4-113">Klicken Sie in der oberen rechten Ecke des Abschnitts "Lesezeichen" auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="778f4-113">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="778f4-114">Klicken Sie im Bereich "Lesezeichen importieren" auf **Durchsuchen**, und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="778f4-114">In the Import bookmarks pane, select **Browse** and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="778f4-115">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="778f4-115">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="778f4-116">Vermeiden von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="778f4-116">Prevent import errors</span></span>      
<span data-ttu-id="778f4-117">Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="778f4-117">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="778f4-118">Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="778f4-118">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="778f4-119">Nehmen Sie alle erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut importieren.</span><span class="sxs-lookup"><span data-stu-id="778f4-119">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="778f4-120">Bis alle Fehler behoben wurden, können Sie keine Lesezeichen erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="778f4-120">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="778f4-121">Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="778f4-121">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="778f4-122">Enthält die Überschriftenzeile aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="778f4-122">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="778f4-123">Enthält alle Spalten aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="778f4-123">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="778f4-124">Die Spaltenreihenfolge die gleiche ist wie in der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="778f4-124">The column order is the same as the import template</span></span>
- <span data-ttu-id="778f4-125">Diese Spalten können leer sein: "ID", "Zuletzt geändert" und "Zuletzt geändert von".</span><span class="sxs-lookup"><span data-stu-id="778f4-125">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="778f4-126">Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="778f4-126">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="778f4-127">Auf der Grundlage des Felds „Status“ werden Lesezeichen als „Entwurf“, „vorgeschlagen“ oder „geplant“ gespeichert, oder sie werden automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="778f4-127">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="778f4-128">Und wenn Sie die ID eines vorhandenen Lesezeichens angeben, wird sie durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="778f4-128">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="778f4-129">Bei Organisationen mit mehreren Mandanten können Sie Ihre Lesezeichen von einem Mandanten exportieren und zu einem anderen importieren.</span><span class="sxs-lookup"><span data-stu-id="778f4-129">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="778f4-130">Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.</span><span class="sxs-lookup"><span data-stu-id="778f4-130">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="778f4-131">Unter [Erstellen von Lesezeichen](create-bookmarks.md) erfahren Sie mehr zu erforderlichen und empfohlenen Feldern.</span><span class="sxs-lookup"><span data-stu-id="778f4-131">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
