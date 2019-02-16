---
title: Massenerstellung von Q&As
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
ms.openlocfilehash: 53f1d167948f6b621ad139620553df51b0cb91c2
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068394"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="3e2d9-103">Massenerstellung von Q&As</span><span class="sxs-lookup"><span data-stu-id="3e2d9-103">Bulk create Q&As</span></span>

<span data-ttu-id="3e2d9-p101">Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie, um Q&As massenweise zu erstellen oder zu bearbeiten. Es ist auch eine einfache Möglichkeit zum Massenspeichern von Entwurfs-Q&As, die zusätzliche Änderungen oder Aktualisierungen erfordern. Wenn Sie vorhandene Q&As massenweise bearbeiten müssen, exportieren Sie Sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="3e2d9-p101">Download and use the .csv template to bulk create or bulk edit Q&As. It's also a simple way to bulk save draft Q&As that need additional edits or updates. If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="3e2d9-107">Klicken Sie in der oberen rechten Ecke des Abschnitts Q&As auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="3e2d9-107">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="3e2d9-108">Klicken Sie auf **Q&A-Vorlage herunterladen (. CSV)**</span><span class="sxs-lookup"><span data-stu-id="3e2d9-108">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="3e2d9-109">Speichern und Öffnen der CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="3e2d9-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="3e2d9-110">Hinzufügen des Q&A-Inhalts und der Einstellungen und Speichern der Datei</span><span class="sxs-lookup"><span data-stu-id="3e2d9-110">Add the Q&A content and settings and save the file</span></span>
    
5. <span data-ttu-id="3e2d9-111">Klicken Sie in der oberen rechten Ecke des Abschnitts Q&As auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="3e2d9-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="3e2d9-112">Klicken Sie im Bereich Q&As importieren auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3e2d9-112">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="3e2d9-113">Klicken Sie auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="3e2d9-113">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="3e2d9-114">Verhindern von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="3e2d9-114">Prevent import errors</span></span>      
<span data-ttu-id="3e2d9-p102">Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3e2d9-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="3e2d9-118">Sie können keine Q&As erstellen oder bearbeiten, bis alle Fehler aufgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="3e2d9-118">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="3e2d9-119">Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="3e2d9-119">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="3e2d9-120">Enthält die Überschriftenzeile, die sich in der Importvorlage befand</span><span class="sxs-lookup"><span data-stu-id="3e2d9-120">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="3e2d9-121">Enthält alle Spalten, die in der Importvorlage enthalten waren.</span><span class="sxs-lookup"><span data-stu-id="3e2d9-121">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="3e2d9-122">Die Reihenfolge der Spalten ist identisch mit der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="3e2d9-122">The column order is the same as the import template</span></span>
- <span data-ttu-id="3e2d9-123">Diese Spalten können leer sein: ID, zuletzt geändert und zuletzt geändert von</span><span class="sxs-lookup"><span data-stu-id="3e2d9-123">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="3e2d9-124">Die Spalte Status kann nicht leer sein, diese Informationen sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3e2d9-124">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="3e2d9-125">Basierend auf dem Feld Status wird Q&As als Entwurf, vorgeschlagen, geplant gespeichert oder automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="3e2d9-125">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="3e2d9-126">Wenn Sie auch die ID eines vorhandenen Q&A-Objekt hinzufügen, wird es durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3e2d9-126">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="3e2d9-p103">Für Organisationen mit mehreren Stand-Mandanten können Sie Ihre Q&As aus einem Mandanten exportieren und in einen anderen importieren. Sie müssen jedoch vor dem Importieren alle Daten in der Spalte "ID" entfernen.</span><span class="sxs-lookup"><span data-stu-id="3e2d9-p103">For organizations with mulitple tenants, you can export your Q&As from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="3e2d9-129">Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Create Q&As](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="3e2d9-129">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

