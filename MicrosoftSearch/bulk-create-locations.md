---
title: Massenerstellen von Standorten
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
description: Fügen Sie mit den Importtools für das Microsoft Search-Verwaltungsportal sehr viele Standorte gleichzeitig hinzu.
ms.openlocfilehash: 1d360fda2851083def0bcbd8fcffd77cfa15240e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968291"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="1237f-103">Massenerstellen von Standorten</span><span class="sxs-lookup"><span data-stu-id="1237f-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1237f-104">Die Einstellungen für Microsoft Search in Bing sind nun im Microsoft 365 Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1237f-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1237f-105">Beginnen Sie, indem Sie [Suchadministratoren](https://docs.microsoft.com/de-DE/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in Ihrem Admin Center zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1237f-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="1237f-106">Laden Sie die CSV-Vorlage herunter, und verwenden Sie sie zur Massenerstellung, -bearbeitung und -speicherung von Standorten.</span><span class="sxs-lookup"><span data-stu-id="1237f-106">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="1237f-107">Klicken Sie in der oberen rechten Ecke des Abschnitts "Standorte" auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="1237f-107">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
2. <span data-ttu-id="1237f-108">Klicken Sie auf **Standortvorlage (CSV) herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="1237f-108">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="1237f-109">Speichern und öffnen Sie die CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="1237f-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="1237f-110">Hinzufügen des Standortinhalts und Speichern der Datei</span><span class="sxs-lookup"><span data-stu-id="1237f-110">Add the location content and save the file</span></span>

    <span data-ttu-id="1237f-111">Die CSV-Datei sollte als CSV UTF-8-Datei gespeichert werden, andere Dateitypen und/oder Codierungen können zu Importfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="1237f-111">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="1237f-112">Klicken Sie in der oberen rechten Ecke des Abschnitts "Standorte" auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="1237f-112">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
6. <span data-ttu-id="1237f-113">Klicken Sie im Bereich "Standorte importieren" auf **Durchsuchen**, und navigieren Sie zu der CSV-Datei, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1237f-113">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="1237f-114">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="1237f-114">Click **Import**.</span></span>

<span data-ttu-id="1237f-115">Die Felder in den Vorlagen zum Importieren und Exportieren von Standortvorlagen sind identisch.</span><span class="sxs-lookup"><span data-stu-id="1237f-115">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="1237f-116">Sie können die Änderungen exportieren, in einem Massenvorgang bearbeiten und importieren, oder Sie können mit einer leeren Vorlage beginnen, um neue Standorte in einem Massenvorgang zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1237f-116">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="1237f-117">Wenn Sie eine Massenbearbeitung von vorhandenen Standorten ausführen möchten, exportieren Sie sie aus dem Verwaltungsportal, nehmen Sie die erforderlichen Änderungen vor, und importieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="1237f-117">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="1237f-118">Vermeiden von Importfehlern</span><span class="sxs-lookup"><span data-stu-id="1237f-118">Prevent import errors</span></span>  
<span data-ttu-id="1237f-119">Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1237f-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="1237f-120">Je nach Fehler wird möglicherweise eine Protokolldatei mit weiteren Informationen zu den Zeilen und Spalten generiert, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1237f-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="1237f-121">Nehmen Sie alle erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut importieren.</span><span class="sxs-lookup"><span data-stu-id="1237f-121">Make necessary edits and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1237f-122">Bis alle Fehler behoben wurden, können Sie keine Standorte erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1237f-122">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="1237f-123">Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist:</span><span class="sxs-lookup"><span data-stu-id="1237f-123">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="1237f-124">Enthält die Überschriftenzeile aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="1237f-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="1237f-125">Enthält alle Spalten aus der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="1237f-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="1237f-126">Die Spaltenreihenfolge die gleiche ist wie in der Importvorlage.</span><span class="sxs-lookup"><span data-stu-id="1237f-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="1237f-127">Diese Spalten können leer sein: "ID", "Zuletzt geändert", "Zuletzt geändert von" und "Längen-/Breitengrad".</span><span class="sxs-lookup"><span data-stu-id="1237f-127">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="1237f-128">Wir werden versuchen, den Längen- und Breitengrad anhand der Adresse zu ermitteln, wenn dieses Feld leer ist.</span><span class="sxs-lookup"><span data-stu-id="1237f-128">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="1237f-129">Die Spalte "Status" darf nicht leer sein, da diese Informationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1237f-129">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="1237f-130">Auf der Grundlage des Felds „Status“ werden Standorte als „Entwurf“, „vorgeschlagen“ oder „geplant“ gespeichert, oder sie werden automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="1237f-130">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="1237f-131">Und wenn Sie die ID eines vorhandenen Standorts angeben, wird sie durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1237f-131">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="1237f-132">Bei Organisationen mit mehreren Mandanten können Sie Ihre Standorte von einem Mandanten exportieren und zu einem anderen importieren.</span><span class="sxs-lookup"><span data-stu-id="1237f-132">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="1237f-133">Sie müssen jedoch alle Daten in der Spalte "ID" vor dem Import entfernen.</span><span class="sxs-lookup"><span data-stu-id="1237f-133">But you must remove the data in the Id column before you import.</span></span>
  
<span data-ttu-id="1237f-134">Unter [Hinzufügen eines Standorts](add-a-location.md) erfahren Sie mehr zu erforderlichen und empfohlenen Feldern.</span><span class="sxs-lookup"><span data-stu-id="1237f-134">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

