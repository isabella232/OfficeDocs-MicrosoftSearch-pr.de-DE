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
ROBOTS: NoIndex
description: Fügen Sie Antworten auf häufig gestellte Fragen mit den Importtools im Microsoft Search-Verwaltungsportal schnell hinzu.
ms.openlocfilehash: 7368014f3bc2f21a788625f0bf826af963366e1b
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591368"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="a53b7-103">Massenerstellung von Fragen und Antworten</span><span class="sxs-lookup"><span data-stu-id="a53b7-103">Bulk create Q&As</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a53b7-104">Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal.</span><span class="sxs-lookup"><span data-stu-id="a53b7-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="a53b7-105">Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird es entfernt.</span><span class="sxs-lookup"><span data-stu-id="a53b7-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="a53b7-106">Es wird empfohlen, dass Sie zu Beginn das Microsoft 365 Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="a53b7-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="a53b7-107">[Übersicht über Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="a53b7-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="a53b7-108">Laden Sie die CSV-Vorlage herunter, und verwenden Sie sie zur Massenerstellung oder -bearbeitung von Fragen und Antworten.</span><span class="sxs-lookup"><span data-stu-id="a53b7-108">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="a53b7-109">Dies ist auch eine einfache Möglichkeit zum Speichern von Fragen und Antworten des Typs "Entwurf", bei denen zusätzliche Bearbeitungen oder Aktualisierungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a53b7-109">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="a53b7-110">Wenn Sie eine Massenbearbeitung von vorhandenen Fragen und Antworten ausführen müssen, exportieren Sie sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="a53b7-110">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="a53b7-111">Klicken Sie in der oberen rechten Ecke des Abschnitts "Fragen und Antworten" auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="a53b7-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="a53b7-112">Klicken Sie auf **F & A-Vorlage (CSV) herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="a53b7-112">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="a53b7-113">Speichern und öffnen Sie die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="a53b7-113">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="a53b7-114">Fügen Sie den F & A-Inhalt und die Einstellungen hinzu, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="a53b7-114">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="a53b7-115">Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="a53b7-115">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="a53b7-116">Klicken Sie in der oberen rechten Ecke des Abschnitts "Fragen und Antworten" auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="a53b7-116">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="a53b7-117">Klicken Sie im Bereich "Fragen und Antworten importieren" auf **Durchsuchen**, und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a53b7-117">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="a53b7-118">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="a53b7-118">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="a53b7-119">Vermeiden von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="a53b7-119">Prevent import errors</span></span>      
<span data-ttu-id="a53b7-120">Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a53b7-120">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="a53b7-121">Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a53b7-121">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="a53b7-122">Nehmen Sie alle erforderlichen Änderungen vor und versuchen Sie erneut, die Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="a53b7-122">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="a53b7-123">Bis alle Fehler behoben wurden, können Sie keine Fragen und Antworten erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a53b7-123">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="a53b7-124">Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="a53b7-124">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="a53b7-125">Enthält die Überschriftenzeile aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="a53b7-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="a53b7-126">Enthält alle Spalten aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="a53b7-126">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="a53b7-127">Die Spaltenreihenfolge die gleiche ist wie in der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="a53b7-127">The column order is the same as the import template</span></span>
- <span data-ttu-id="a53b7-128">Diese Spalten können leer sein: "ID", "Zuletzt geändert" und "Zuletzt geändert von".</span><span class="sxs-lookup"><span data-stu-id="a53b7-128">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="a53b7-129">Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a53b7-129">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="a53b7-130">Auf der Grundlage des Statusfelds werden Fragen und Antworten als "Entwurf", "vorgeschlagen" oder "geplant" gespeichert, oder sie werden automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="a53b7-130">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="a53b7-131">Und wenn Sie die ID eines vorhandenen Frage&Antwort-Eintrags angeben, wird dieser durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a53b7-131">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="a53b7-132">Bei Organisationen mit mehreren Mandanten können Sie Ihre Frage&Antwort-Einträge von einem Mandanten exportieren und zu einem anderen importieren.</span><span class="sxs-lookup"><span data-stu-id="a53b7-132">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="a53b7-133">Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.</span><span class="sxs-lookup"><span data-stu-id="a53b7-133">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="a53b7-134">Unter [Erstellen von Fragen und Antworten](create-qas.md) erfahren Sie mehr zu erforderlichen und empfohlenen Feldern.</span><span class="sxs-lookup"><span data-stu-id="a53b7-134">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

