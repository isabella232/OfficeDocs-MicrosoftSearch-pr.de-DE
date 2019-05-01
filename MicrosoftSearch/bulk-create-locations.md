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
ms.openlocfilehash: 3c7e43b03b97b46769d5e73f20ddae47b3459b59
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508561"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="4766d-103">Massenerstellen von Speicherorten</span><span class="sxs-lookup"><span data-stu-id="4766d-103">Bulk create locations</span></span>

<span data-ttu-id="4766d-104">Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie zum Massen erstellen, bearbeiten und Speichern von Speicherorten.</span><span class="sxs-lookup"><span data-stu-id="4766d-104">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="4766d-105">Klicken Sie in der oberen rechten Ecke des Abschnitts Standorte auf **importieren** .</span><span class="sxs-lookup"><span data-stu-id="4766d-105">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="4766d-106">Klicken Sie auf **Download Speicherorte Vorlage (. CSV)**</span><span class="sxs-lookup"><span data-stu-id="4766d-106">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="4766d-107">Speichern und Öffnen der CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="4766d-107">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="4766d-108">Hinzufügen des Standort Inhalts und Speichern der Datei</span><span class="sxs-lookup"><span data-stu-id="4766d-108">Add the location content and save the file</span></span>

    <span data-ttu-id="4766d-109">Die CSV-Datei sollte als CSV-UTF-8-Datei gespeichert werden, andere Dateitypen und Codierungen können zu Importfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="4766d-109">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="4766d-110">Klicken Sie in der oberen rechten Ecke des Abschnitts Standorte auf **importieren** .</span><span class="sxs-lookup"><span data-stu-id="4766d-110">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="4766d-111">Klicken Sie im Bereich Speicherorte importieren auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4766d-111">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="4766d-112">Klicken Sie auf **importieren**</span><span class="sxs-lookup"><span data-stu-id="4766d-112">Click **Import**</span></span>

<span data-ttu-id="4766d-113">Die Felder in den Import-und Exportspeicherort Vorlagen sind identisch.</span><span class="sxs-lookup"><span data-stu-id="4766d-113">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="4766d-114">Sie können die Bearbeitungen exportieren, Massen bearbeiten und importieren oder mit einer leeren Vorlage beginnen, um massenweise neue Speicherorte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4766d-114">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="4766d-115">Zum Massen Bearbeiten vorhandener Speicherorte, exportieren Sie diese aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="4766d-115">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="4766d-116">Verhindern von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="4766d-116">Prevent import errors</span></span>  
<span data-ttu-id="4766d-117">Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="4766d-117">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="4766d-118">Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4766d-118">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="4766d-119">Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren.</span><span class="sxs-lookup"><span data-stu-id="4766d-119">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4766d-120">Sie können keine Speicherorte erstellen oder bearbeiten, bis alle Fehler aufgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="4766d-120">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="4766d-121">Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="4766d-121">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="4766d-122">Enthält die Überschriftenzeile, die sich in der Importvorlage befand</span><span class="sxs-lookup"><span data-stu-id="4766d-122">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="4766d-123">Enthält alle Spalten, die in der Importvorlage enthalten waren.</span><span class="sxs-lookup"><span data-stu-id="4766d-123">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="4766d-124">Die Reihenfolge der Spalten ist identisch mit der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="4766d-124">The column order is the same as the import template</span></span>
- <span data-ttu-id="4766d-125">Diese Spalten können leer sein: ID, zuletzt geändert, zuletzt geändert von und lat/long</span><span class="sxs-lookup"><span data-stu-id="4766d-125">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="4766d-126">Wir versuchen, lat/long basierend auf der Adresse zu ermitteln, wenn das Feld leer ist.</span><span class="sxs-lookup"><span data-stu-id="4766d-126">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="4766d-127">Die Spalte Status kann nicht leer sein, diese Informationen sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4766d-127">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="4766d-128">Basierend auf dem Feld Status werden Speicherorte als Entwurf, vorgeschlagen oder geplant gespeichert, oder Sie werden automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="4766d-128">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="4766d-129">Wenn Sie die ID eines vorhandenen Speicherorts angeben, wird Sie auch durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="4766d-129">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="4766d-130">Für Organisationen mit mehreren Stand-Mandanten können Sie Ihre Standorte aus einem Mandanten exportieren und in einen anderen importieren.</span><span class="sxs-lookup"><span data-stu-id="4766d-130">For organizations with mulitple tenants, you can export your locations from one tenant and import it into another.</span></span> <span data-ttu-id="4766d-131">Sie müssen jedoch vor dem Importieren alle Daten in der Spalte "ID" entfernen.</span><span class="sxs-lookup"><span data-stu-id="4766d-131">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="4766d-132">Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Hinzufügen eines Standorts](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="4766d-132">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

