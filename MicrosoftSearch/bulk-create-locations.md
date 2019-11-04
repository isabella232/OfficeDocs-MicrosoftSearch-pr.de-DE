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
ROBOTS: NoIndex
description: Fügen Sie viele Orte gleichzeitig mit Importtools für das Microsoft Search-Verwaltungsportal hinzu.
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948971"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="5ee87-103">Massenerstellen von Speicherorten</span><span class="sxs-lookup"><span data-stu-id="5ee87-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ee87-104">Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal.</span><span class="sxs-lookup"><span data-stu-id="5ee87-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="5ee87-105">Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird das Microsoft Search im Bing-Portal entfernt.</span><span class="sxs-lookup"><span data-stu-id="5ee87-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="5ee87-106">Es wird empfohlen, dass Sie für die ersten Schritte das Microsoft 365 Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ee87-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="5ee87-107">[Übersicht über Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="5ee87-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="5ee87-108">Laden Sie die CSV-Vorlage herunter, und verwenden Sie Sie zum Massen erstellen, bearbeiten und Speichern von Speicherorten.</span><span class="sxs-lookup"><span data-stu-id="5ee87-108">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="5ee87-109">Klicken Sie in der oberen rechten Ecke des Abschnitts Speicherorte auf **importieren** .</span><span class="sxs-lookup"><span data-stu-id="5ee87-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="5ee87-110">Klicken Sie auf **Download Speicherorte Vorlage (. CSV)**</span><span class="sxs-lookup"><span data-stu-id="5ee87-110">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="5ee87-111">Speichern und öffnen Sie die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="5ee87-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="5ee87-112">Hinzufügen des Standort Inhalts und Speichern der Datei</span><span class="sxs-lookup"><span data-stu-id="5ee87-112">Add the location content and save the file</span></span>

    <span data-ttu-id="5ee87-113">Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="5ee87-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="5ee87-114">Klicken Sie in der oberen rechten Ecke des Abschnitts Speicherorte auf **importieren** .</span><span class="sxs-lookup"><span data-stu-id="5ee87-114">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="5ee87-115">Klicken Sie im Bereich Import Speicherorte auf **Durchsuchen** , und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5ee87-115">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="5ee87-116">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="5ee87-116">Click **Import**</span></span>

<span data-ttu-id="5ee87-117">Die Felder in den Vorlagen für das Importieren und Exportieren von Speicherorten sind identisch.</span><span class="sxs-lookup"><span data-stu-id="5ee87-117">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="5ee87-118">Sie können die Bearbeitungsvorgänge exportieren, Massen bearbeiten und importieren oder mit einer leeren Vorlage beginnen, um massenhaft neue Speicherorte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ee87-118">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="5ee87-119">Wenn Sie vorhandene Speicherorte massenweise bearbeiten möchten, exportieren Sie Sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie Sie dann.</span><span class="sxs-lookup"><span data-stu-id="5ee87-119">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="5ee87-120">Vermeiden von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="5ee87-120">Prevent import errors</span></span>  
<span data-ttu-id="5ee87-121">Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ee87-121">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="5ee87-122">Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5ee87-122">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="5ee87-123">Nehmen Sie alle erforderlichen Änderungen vor und versuchen Sie erneut, die Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="5ee87-123">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ee87-124">Bis alle Fehler behoben sind, können Sie keine Speicherorte erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5ee87-124">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="5ee87-125">Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="5ee87-125">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="5ee87-126">Enthält die Überschriftenzeile aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="5ee87-126">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="5ee87-127">Enthält alle Spalten aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="5ee87-127">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="5ee87-128">Die Spaltenreihenfolge die gleiche ist wie in der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="5ee87-128">The column order is the same as the import template</span></span>
- <span data-ttu-id="5ee87-129">Diese Spalten können leer sein: ID, zuletzt geändert, zuletzt geändert von und lat/long</span><span class="sxs-lookup"><span data-stu-id="5ee87-129">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="5ee87-130">Wir versuchen, lat/long basierend auf der Adresse zu bestimmen, wenn das Feld leer ist.</span><span class="sxs-lookup"><span data-stu-id="5ee87-130">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="5ee87-131">Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5ee87-131">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="5ee87-132">Basierend auf dem Feld State werden die Standorte als Entwurf, vorgeschlagen, geplant oder automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="5ee87-132">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="5ee87-133">Wenn Sie die ID eines vorhandenen Speicherorts einschließen, wird dieser auch durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="5ee87-133">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="5ee87-134">Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Standorte aus einer Organisation exportieren und in eine andere importieren.</span><span class="sxs-lookup"><span data-stu-id="5ee87-134">For partners who manage multiple organizations, you can export your locations from one org and import them into another.</span></span> <span data-ttu-id="5ee87-135">Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.</span><span class="sxs-lookup"><span data-stu-id="5ee87-135">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="5ee87-136">Weitere Informationen zu den erforderlichen und empfohlenen Feldern finden Sie unter [Hinzufügen eines Standorts](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="5ee87-136">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

