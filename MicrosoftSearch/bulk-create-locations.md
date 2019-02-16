---
title: Massenerstellen von Speicherorten
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
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
description: Hinzufügen von vielen Standorten gleichzeitig mit Importtools für das Microsoft Search-Verwaltungsportal
ms.openlocfilehash: eb51b93ceaa560e5142ac46d316ba745c614fe34
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068410"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="dbab9-103">Massenerstellen von Speicherorten</span><span class="sxs-lookup"><span data-stu-id="dbab9-103">Bulk create locations</span></span>

<span data-ttu-id="dbab9-104">Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie zum Massen erstellen, bearbeiten und Speichern von Speicherorten.</span><span class="sxs-lookup"><span data-stu-id="dbab9-104">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="dbab9-105">Klicken Sie in der oberen rechten Ecke des Abschnitts Standorte auf **importieren** .</span><span class="sxs-lookup"><span data-stu-id="dbab9-105">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="dbab9-106">Klicken Sie auf **Download Speicherorte Vorlage (. CSV)**</span><span class="sxs-lookup"><span data-stu-id="dbab9-106">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="dbab9-107">Speichern und Öffnen der CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="dbab9-107">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="dbab9-108">Hinzufügen des Standort Inhalts und Speichern der Datei</span><span class="sxs-lookup"><span data-stu-id="dbab9-108">Add the location content and save the file</span></span>
    
5. <span data-ttu-id="dbab9-109">Klicken Sie in der oberen rechten Ecke des Abschnitts Standorte auf **importieren** .</span><span class="sxs-lookup"><span data-stu-id="dbab9-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="dbab9-110">Klicken Sie im Bereich Speicherorte importieren auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="dbab9-110">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="dbab9-111">Klicken Sie auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="dbab9-111">Click **Import**</span></span>

<span data-ttu-id="dbab9-p101">Die Felder in den Import-und Exportspeicherort Vorlagen sind identisch. Sie können die Bearbeitungen exportieren, Massen bearbeiten und importieren oder mit einer leeren Vorlage beginnen, um massenweise neue Speicherorte zu erstellen. Zum Massen Bearbeiten vorhandener Speicherorte, exportieren Sie diese aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="dbab9-p101">The fields in the import and export locations templates are the same. You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations. To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="dbab9-115">Verhindern von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="dbab9-115">Prevent import errors</span></span>  
<span data-ttu-id="dbab9-p102">Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind. Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen. Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dbab9-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dbab9-119">Sie können keine Speicherorte erstellen oder bearbeiten, bis alle Fehler aufgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="dbab9-119">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="dbab9-120">Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="dbab9-120">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="dbab9-121">Enthält die Überschriftenzeile, die sich in der Importvorlage befand</span><span class="sxs-lookup"><span data-stu-id="dbab9-121">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="dbab9-122">Enthält alle Spalten, die in der Importvorlage enthalten waren.</span><span class="sxs-lookup"><span data-stu-id="dbab9-122">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="dbab9-123">Die Reihenfolge der Spalten ist identisch mit der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="dbab9-123">The column order is the same as the import template</span></span>
- <span data-ttu-id="dbab9-124">Diese Spalten können leer sein: ID, zuletzt geändert, zuletzt geändert von und lat/long</span><span class="sxs-lookup"><span data-stu-id="dbab9-124">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="dbab9-125">Wir versuchen, lat/long basierend auf der Adresse zu ermitteln, wenn das Feld leer ist.</span><span class="sxs-lookup"><span data-stu-id="dbab9-125">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="dbab9-126">Die Spalte Status kann nicht leer sein, diese Informationen sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dbab9-126">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="dbab9-127">Basierend auf dem Feld Status werden Speicherorte als Entwurf, vorgeschlagen oder geplant gespeichert, oder Sie werden automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="dbab9-127">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="dbab9-128">Wenn Sie die ID eines vorhandenen Speicherorts angeben, wird Sie auch durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="dbab9-128">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="dbab9-p103">Für Organisationen mit mehreren Stand-Mandanten können Sie Ihre Standorte aus einem Mandanten exportieren und in einen anderen importieren. Sie müssen jedoch vor dem Importieren alle Daten in der Spalte "ID" entfernen.</span><span class="sxs-lookup"><span data-stu-id="dbab9-p103">For organizations with mulitple tenants, you can export your locations from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="dbab9-131">Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Hinzufügen eines Standorts](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="dbab9-131">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

