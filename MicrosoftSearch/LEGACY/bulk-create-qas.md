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
ms.openlocfilehash: 660f5663ff6238f4ab59dab36d51f1311d5c7260
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311611"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="38823-103">Massenerstellung von Fragen und Antworten</span><span class="sxs-lookup"><span data-stu-id="38823-103">Bulk create Q&As</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38823-104">Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal.</span><span class="sxs-lookup"><span data-stu-id="38823-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="38823-105">Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird Microsoft Search im Bing-Portal entfernt.</span><span class="sxs-lookup"><span data-stu-id="38823-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="38823-106">Wir empfehlen, für die ersten Schritte das Microsoft 365 Admin Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="38823-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="38823-107">[Übersicht über Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="38823-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="38823-108">Laden Sie die CSV-Vorlage herunter, und verwenden Sie sie zur Massenerstellung oder -bearbeitung von Fragen und Antworten.</span><span class="sxs-lookup"><span data-stu-id="38823-108">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="38823-109">Dies ist auch eine einfache Möglichkeit zum Speichern von Fragen und Antworten des Typs "Entwurf", bei denen zusätzliche Bearbeitungen oder Aktualisierungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="38823-109">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="38823-110">Wenn Sie eine Massenbearbeitung von vorhandenen Fragen und Antworten ausführen müssen, exportieren Sie sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="38823-110">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="38823-111">Klicken Sie in der oberen rechten Ecke des Abschnitts "Fragen und Antworten" auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="38823-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="38823-112">Klicken Sie auf **F & A-Vorlage (CSV) herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="38823-112">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="38823-113">Speichern und öffnen Sie die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="38823-113">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="38823-114">Fügen Sie den F & A-Inhalt und die Einstellungen hinzu, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="38823-114">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="38823-115">Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="38823-115">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="38823-116">Klicken Sie in der oberen rechten Ecke des Abschnitts "Fragen und Antworten" auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="38823-116">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="38823-117">Klicken Sie im Bereich "Fragen und Antworten importieren" auf **Durchsuchen**, und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="38823-117">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="38823-118">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="38823-118">Click **Import**</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="38823-119">Vermeiden von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="38823-119">Prevent import errors</span></span>      
<span data-ttu-id="38823-120">Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38823-120">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="38823-121">Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="38823-121">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="38823-122">Nehmen Sie alle erforderlichen Änderungen vor und versuchen Sie erneut, die Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="38823-122">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="38823-123">Bis alle Fehler behoben wurden, können Sie keine Fragen und Antworten erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="38823-123">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="38823-124">Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="38823-124">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="38823-125">Enthält die Überschriftenzeile aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="38823-125">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="38823-126">Enthält alle Spalten aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="38823-126">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="38823-127">Die Spaltenreihenfolge die gleiche ist wie in der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="38823-127">The column order is the same as the import template</span></span>
- <span data-ttu-id="38823-128">Diese Spalten können leer sein: "ID", "Zuletzt geändert" und "Zuletzt geändert von".</span><span class="sxs-lookup"><span data-stu-id="38823-128">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="38823-129">Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="38823-129">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="38823-130">Auf der Grundlage des Statusfelds werden Fragen und Antworten als "Entwurf", "vorgeschlagen" oder "geplant" gespeichert, oder sie werden automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="38823-130">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="38823-131">Und wenn Sie die ID eines vorhandenen Frage&Antwort-Eintrags angeben, wird dieser durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="38823-131">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="38823-132">Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Q-&aus einer org exportieren und in eine andere importieren.</span><span class="sxs-lookup"><span data-stu-id="38823-132">For partners who manage multiple organizations, you can export your Q&As from one org and import them into another.</span></span> <span data-ttu-id="38823-133">Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.</span><span class="sxs-lookup"><span data-stu-id="38823-133">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="38823-134">Unter [Erstellen von Fragen und Antworten](create-qas.md) erfahren Sie mehr zu erforderlichen und empfohlenen Feldern.</span><span class="sxs-lookup"><span data-stu-id="38823-134">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

