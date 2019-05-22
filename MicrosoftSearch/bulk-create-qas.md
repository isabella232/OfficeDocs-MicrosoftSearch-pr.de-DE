---
title: Massenerstellung von Fragen und Antworten
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
description: Fügen Sie Antworten auf häufig gestellte Fragen mit den Importtools im Microsoft Search-Verwaltungsportal schnell hinzu.
ms.openlocfilehash: f535cb7ae843def536976cb1f05c8601de592cbb
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968302"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="fb594-103">Massenerstellung von Fragen und Antworten</span><span class="sxs-lookup"><span data-stu-id="fb594-103">Bulk create Q&As</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb594-104">Die Einstellungen für Microsoft Search in Bing sind nun im Microsoft 365 Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb594-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="fb594-105">Beginnen Sie, indem Sie [Suchadministratoren](https://docs.microsoft.com/de-DE/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in Ihrem Admin Center zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fb594-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="fb594-106">Laden Sie die CSV-Vorlage herunter, und verwenden Sie sie zur Massenerstellung oder -bearbeitung von Fragen und Antworten.</span><span class="sxs-lookup"><span data-stu-id="fb594-106">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="fb594-107">Dies ist auch eine einfache Möglichkeit zum Speichern von Fragen und Antworten des Typs "Entwurf", bei denen zusätzliche Bearbeitungen oder Aktualisierungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fb594-107">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="fb594-108">Wenn Sie eine Massenbearbeitung von vorhandenen Fragen und Antworten ausführen müssen, exportieren Sie sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="fb594-108">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="fb594-109">Klicken Sie in der oberen rechten Ecke des Abschnitts "Fragen und Antworten" auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="fb594-109">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="fb594-110">Klicken Sie auf **F & A-Vorlage (CSV) herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="fb594-110">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="fb594-111">Speichern und öffnen Sie die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="fb594-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="fb594-112">Fügen Sie den F & A-Inhalt und die Einstellungen hinzu, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="fb594-112">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="fb594-113">Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="fb594-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="fb594-114">Klicken Sie in der oberen rechten Ecke des Abschnitts "Fragen und Antworten" auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="fb594-114">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="fb594-115">Klicken Sie im Bereich "Fragen und Antworten importieren" auf **Durchsuchen**, und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="fb594-115">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="fb594-116">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="fb594-116">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="fb594-117">Vermeiden von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="fb594-117">Prevent import errors</span></span>      
<span data-ttu-id="fb594-118">Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb594-118">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="fb594-119">Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fb594-119">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="fb594-120">Nehmen Sie alle erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut importieren.</span><span class="sxs-lookup"><span data-stu-id="fb594-120">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="fb594-121">Bis alle Fehler behoben wurden, können Sie keine Fragen und Antworten erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="fb594-121">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="fb594-122">Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="fb594-122">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="fb594-123">Enthält die Überschriftenzeile aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="fb594-123">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="fb594-124">Enthält alle Spalten aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="fb594-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="fb594-125">Die Spaltenreihenfolge ist die gleiche wie in der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="fb594-125">The column order is the same as the import template</span></span>
- <span data-ttu-id="fb594-126">Diese Spalten können leer sein: "ID", "Zuletzt geändert" und "Zuletzt geändert von".</span><span class="sxs-lookup"><span data-stu-id="fb594-126">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="fb594-127">Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fb594-127">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="fb594-128">Auf der Grundlage des Statusfelds werden Fragen und Antworten als "Entwurf", "vorgeschlagen" oder "geplant" gespeichert, oder sie werden automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="fb594-128">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="fb594-129">Und wenn Sie die ID eines vorhandenen Frage&Antwort-Eintrags angeben, wird dieser durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="fb594-129">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="fb594-130">Bei Organisationen mit mehreren Mandanten können Sie Ihre Frage&Antwort-Einträge von einem Mandanten exportieren und zu einem anderen importieren.</span><span class="sxs-lookup"><span data-stu-id="fb594-130">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="fb594-131">Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.</span><span class="sxs-lookup"><span data-stu-id="fb594-131">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="fb594-132">Unter [Erstellen von Fragen und Antworten](create-qas.md) erfahren Sie mehr zu erforderlichen und empfohlenen Feldern.</span><span class="sxs-lookup"><span data-stu-id="fb594-132">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

