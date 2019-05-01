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
description: Schnelles Hinzufügen von Antworten auf häufig gestellte Fragen mit Importtools im Microsoft Search Admin Portal
ms.openlocfilehash: 28fcf57c44f809e7f9b0c1b27042f4549067a0f8
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508673"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="b9d2a-103">Massenerstellung von Fragen und Antworten</span><span class="sxs-lookup"><span data-stu-id="b9d2a-103">Bulk create Q&As</span></span>

<span data-ttu-id="b9d2a-104">Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie, um Q&As massenweise zu erstellen oder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-104">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="b9d2a-105">Es ist auch eine einfache Möglichkeit zum Massenspeichern von Entwurfs-Q&As, die zusätzliche Änderungen oder Aktualisierungen erfordern.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-105">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="b9d2a-106">Wenn Sie vorhandene Q&As massenweise bearbeiten müssen, exportieren Sie Sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-106">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="b9d2a-107">Klicken Sie in der oberen rechten Ecke des Abschnitts Q&As auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="b9d2a-107">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="b9d2a-108">Klicken Sie auf **Q&A-Vorlage herunterladen (. CSV)**</span><span class="sxs-lookup"><span data-stu-id="b9d2a-108">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="b9d2a-109">Speichern und Öffnen der CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="b9d2a-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="b9d2a-110">Hinzufügen des Q&A-Inhalts und der Einstellungen und Speichern der Datei</span><span class="sxs-lookup"><span data-stu-id="b9d2a-110">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="b9d2a-111">Die CSV-Datei sollte als CSV-UTF-8-Datei gespeichert werden, andere Dateitypen und Codierungen können zu Importfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-111">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="b9d2a-112">Klicken Sie in der oberen rechten Ecke des Abschnitts Q&As auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="b9d2a-112">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="b9d2a-113">Klicken Sie im Bereich Q&As importieren auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-113">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="b9d2a-114">Klicken Sie auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="b9d2a-114">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="b9d2a-115">Verhindern von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="b9d2a-115">Prevent import errors</span></span>      
<span data-ttu-id="b9d2a-116">Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-116">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="b9d2a-117">Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-117">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="b9d2a-118">Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-118">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="b9d2a-119">Sie können keine Q&As erstellen oder bearbeiten, bis alle Fehler aufgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-119">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="b9d2a-120">Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="b9d2a-120">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="b9d2a-121">Enthält die Überschriftenzeile, die sich in der Importvorlage befand</span><span class="sxs-lookup"><span data-stu-id="b9d2a-121">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="b9d2a-122">Enthält alle Spalten, die in der Importvorlage enthalten waren.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-122">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="b9d2a-123">Die Reihenfolge der Spalten ist identisch mit der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-123">The column order is the same as the import template</span></span>
- <span data-ttu-id="b9d2a-124">Diese Spalten können leer sein: ID, zuletzt geändert und zuletzt geändert von</span><span class="sxs-lookup"><span data-stu-id="b9d2a-124">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="b9d2a-125">Die Spalte Status kann nicht leer sein, diese Informationen sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-125">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="b9d2a-126">Basierend auf dem Feld Status wird Q&As als Entwurf, vorgeschlagen, geplant gespeichert oder automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-126">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="b9d2a-127">Wenn Sie auch die ID eines vorhandenen Q&A-Objekt hinzufügen, wird es durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-127">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="b9d2a-128">Für Organisationen mit mehreren Stand-Mandanten können Sie Ihre Q&As aus einem Mandanten exportieren und in einen anderen importieren.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-128">For organizations with mulitple tenants, you can export your Q&As from one tenant and import it into another.</span></span> <span data-ttu-id="b9d2a-129">Sie müssen jedoch vor dem Importieren alle Daten in der Spalte "ID" entfernen.</span><span class="sxs-lookup"><span data-stu-id="b9d2a-129">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="b9d2a-130">Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Create Q&As](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="b9d2a-130">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

