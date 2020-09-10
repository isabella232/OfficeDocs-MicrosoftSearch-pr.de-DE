---
title: F & As verwalten
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Suchen und aktualisieren Sie die Antworten einzeln, oder verwenden Sie die verfügbaren Microsoft-Such Tools, um Q&als alle gleichzeitig zu bearbeiten.
ms.openlocfilehash: 2a8b0727ef3540a35d617cf6c8bae7b0d99767a8
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47423000"
---
# <a name="manage-qas"></a><span data-ttu-id="754dd-103">F & As verwalten</span><span class="sxs-lookup"><span data-stu-id="754dd-103">Manage Q&As</span></span>

<span data-ttu-id="754dd-104">Die Erstellung von Fragen und Antworten ist vergleichbar mit der Erstellung von Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="754dd-104">Creating a Q&A is similar to creating bookmarks.</span></span> <span data-ttu-id="754dd-105">Q&, damit Sie die Fragen des Benutzers beantworten können, anstatt lediglich einen Link zu einer Webseite bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="754dd-105">Q&As allow you to answer the user's questions instead of just providing a link to a webpage.</span></span> <span data-ttu-id="754dd-106">Sie können die Antwort auch in Rich-Text formatieren.</span><span class="sxs-lookup"><span data-stu-id="754dd-106">You can also format the answer in rich text.</span></span> <span data-ttu-id="754dd-107">Wenn ein Lesezeichen und ein Q&a dasselbe Stichwort verwenden, wird zuerst das Ergebnis der Textmarke angezeigt.</span><span class="sxs-lookup"><span data-stu-id="754dd-107">If a bookmark and a Q&A share the same keyword, the bookmark result is shown first.</span></span> <span data-ttu-id="754dd-108">Wie bei Lesezeichen wird das q&ein Index unmittelbar nach dem Hinzufügen oder Ändern eines q&a aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="754dd-108">Like bookmarks, the Q&A index is refreshed immediately after a Q&A is added or changed.</span></span>

## <a name="add-or-edit-a-single-qa"></a><span data-ttu-id="754dd-109">Hinzufügen oder Bearbeiten einer einzelnen Frage und Antwort</span><span class="sxs-lookup"><span data-stu-id="754dd-109">Add or edit a single Q&A</span></span>

1. <span data-ttu-id="754dd-110">Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Q&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)</span><span class="sxs-lookup"><span data-stu-id="754dd-110">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Q&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)</span></span>
1. <span data-ttu-id="754dd-111">Um ein Q&a hinzuzufügen, wählen Sie **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="754dd-111">To add a Q&A, select **Add**.</span></span>
<span data-ttu-id="754dd-112">Wählen Sie zum Bearbeiten einer Frage und Antwort die Frage und Antwort in der entsprechenden F&A-Liste aus.</span><span class="sxs-lookup"><span data-stu-id="754dd-112">To edit a Q&A, select the Q&A in the relevant Q&A list.</span></span> <span data-ttu-id="754dd-113">Während Sie die Informationen hinzufügen oder bearbeiten, wird die Vorschau automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="754dd-113">As you add or edit the information, the preview automatically updates.</span></span>
1. <span data-ttu-id="754dd-114">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="754dd-114">Save your changes.</span></span>

### <a name="supported-html-tags"></a><span data-ttu-id="754dd-115">Unterstützte HTML-Tags</span><span class="sxs-lookup"><span data-stu-id="754dd-115">Supported HTML tags</span></span>

<span data-ttu-id="754dd-116">Sie können vorhandene HTML-Inhalte verwenden oder ihrer Antwort (Beschreibung) HTML-Tags hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="754dd-116">You can use existing HTML content or add HTML tags to your answer (description).</span></span> <span data-ttu-id="754dd-117">Nicht unterstützte Tags werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="754dd-117">Unsupported tags are ignored.</span></span>

<span data-ttu-id="754dd-118">Die folgenden HTML-Tags werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="754dd-118">The following HTML tags are supported:</span></span>

- <span data-ttu-id="754dd-119">blockquote</span><span class="sxs-lookup"><span data-stu-id="754dd-119">blockquote</span></span>
- <span data-ttu-id="754dd-120">div</span><span class="sxs-lookup"><span data-stu-id="754dd-120">div</span></span>
- <span data-ttu-id="754dd-121">em</span><span class="sxs-lookup"><span data-stu-id="754dd-121">em</span></span>
- <span data-ttu-id="754dd-122">h1, h2, h3 und h4</span><span class="sxs-lookup"><span data-stu-id="754dd-122">h1, h2, h3, and h4</span></span>
- <span data-ttu-id="754dd-123">ol, ul und li</span><span class="sxs-lookup"><span data-stu-id="754dd-123">ol, ul, and li</span></span>
- <span data-ttu-id="754dd-124">p</span><span class="sxs-lookup"><span data-stu-id="754dd-124">p</span></span>
- <span data-ttu-id="754dd-125">pre</span><span class="sxs-lookup"><span data-stu-id="754dd-125">pre</span></span>
- <span data-ttu-id="754dd-126">span</span><span class="sxs-lookup"><span data-stu-id="754dd-126">span</span></span>
- <span data-ttu-id="754dd-127">strong</span><span class="sxs-lookup"><span data-stu-id="754dd-127">strong</span></span>
- <span data-ttu-id="754dd-128">table, thead, tbody, tr, th und td</span><span class="sxs-lookup"><span data-stu-id="754dd-128">table, thead, tbody, tr, th, and td</span></span>
- <span data-ttu-id="754dd-129">u</span><span class="sxs-lookup"><span data-stu-id="754dd-129">u</span></span>
- <span data-ttu-id="754dd-130">a</span><span class="sxs-lookup"><span data-stu-id="754dd-130">a</span></span>
- <span data-ttu-id="754dd-131">code</span><span class="sxs-lookup"><span data-stu-id="754dd-131">code</span></span>
- <span data-ttu-id="754dd-132">br</span><span class="sxs-lookup"><span data-stu-id="754dd-132">br</span></span>
- <span data-ttu-id="754dd-133">hr</span><span class="sxs-lookup"><span data-stu-id="754dd-133">hr</span></span>
- <span data-ttu-id="754dd-134">img</span><span class="sxs-lookup"><span data-stu-id="754dd-134">img</span></span>

## <a name="add-or-edit-qas-using-browser-extensions"></a><span data-ttu-id="754dd-135">Hinzufügen oder Bearbeiten von Q&als Verwendung von Browsererweiterungen</span><span class="sxs-lookup"><span data-stu-id="754dd-135">Add or edit Q&As using browser extensions</span></span>

<span data-ttu-id="754dd-136">Suchadministratoren können Suchinhalte mühelos mithilfe von Browsererweiterungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="754dd-136">Search administrators can create search content easily by using browser extensions.</span></span> <span data-ttu-id="754dd-137">Installieren Sie die Browser Erweiterung, und wechseln Sie dann zu der Website, von der Sie ein Q&a generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="754dd-137">Install the browser extension, and then go to the site from which you want to generate a Q&A.</span></span> <span data-ttu-id="754dd-138">Anschließend können Sie Q&a erstellen und einen Link zur Quellwebsite hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="754dd-138">You can then create the Q&A and include a link to the source site.</span></span>

<span data-ttu-id="754dd-139">Derzeit stehen Browsererweiterungen für Microsoft Edge und Chrome zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="754dd-139">Currently, browser extensions are available for Microsoft Edge and Chrome.</span></span>

- <span data-ttu-id="754dd-140">Um Erweiterungen für Edge (Legacy) herunterzuladen, wechseln Sie zu [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).</span><span class="sxs-lookup"><span data-stu-id="754dd-140">To download extensions for Edge (Legacy), go to [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).</span></span>
- <span data-ttu-id="754dd-141">Um Extensions Chrome oder Edge (Chromium) herunterzuladen, wechseln Sie zum [Chrome-Webstore](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).</span><span class="sxs-lookup"><span data-stu-id="754dd-141">To download extensions Chrome or Edge (Chromium), go to the [Chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).</span></span>

## <a name="bulk-add-or-edit-qas"></a><span data-ttu-id="754dd-142">Massenhinzufügen oder -bearbeiten von F & As</span><span class="sxs-lookup"><span data-stu-id="754dd-142">Bulk add or edit Q&As</span></span>

<span data-ttu-id="754dd-143">Administratoren können die Funktionen zum Importieren und Exportieren zum Massen erstellen oder Bearbeiten von Q&as verwenden.</span><span class="sxs-lookup"><span data-stu-id="754dd-143">Administrators can use the Import and Export features to bulk create or edit Q&As.</span></span>

<span data-ttu-id="754dd-144">Verwenden Sie die Funktion zum Importieren/Exportieren für:</span><span class="sxs-lookup"><span data-stu-id="754dd-144">Use the Import/Export feature to:</span></span>

- <span data-ttu-id="754dd-145">Massen Hinzufügen von q&as – fügen Sie Details im q-&einer Vorlagendatei hinzu, und importieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="754dd-145">Bulk add Q&As - Add details in the Q&A template file, and then import it.</span></span>
- <span data-ttu-id="754dd-146">Massenbearbeitung q&as-Export q&als CSV-Datei, bearbeiten Sie die q #d2 Details in der exportierten Datei, und importieren Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="754dd-146">Bulk edit Q&As - Export Q&As to a .csv file, edit the Q&A details in the exported file, and then import the file.</span></span>
- <span data-ttu-id="754dd-147">Sichern Sie q&as-Export q&als CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="754dd-147">Back up Q&As - Export Q&As to a .csv file.</span></span>

<span data-ttu-id="754dd-148">So importieren oder exportieren Sie Q&wie:</span><span class="sxs-lookup"><span data-stu-id="754dd-148">To import or export Q&As:</span></span>

1. <span data-ttu-id="754dd-149">Wählen Sie in der oberen rechten Ecke der Registerkarte „F&A“ **Importieren** aus.</span><span class="sxs-lookup"><span data-stu-id="754dd-149">In the upper-right corner of the Q&A tab, select **Import**.</span></span>
<span data-ttu-id="754dd-150">Wählen Sie **exportieren** aus, um alle vorhandenen Q-&wie in einer CSV-Datei herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="754dd-150">Select **Export** to download all the existing Q&As in a .csv file.</span></span>
1. <span data-ttu-id="754dd-151">Wählen Sie im rechten Bereich die Option zum Importieren mithilfe einer CSV-Datei aus.</span><span class="sxs-lookup"><span data-stu-id="754dd-151">In the right pane, select the option to import by using a .csv file.</span></span> <span data-ttu-id="754dd-152">Laden Sie die Vorlagendatei herunter, um eine Liste der erforderlichen Felder und Details zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="754dd-152">Download the template file to get a list of the required fields and details.</span></span>
1. <span data-ttu-id="754dd-153">Fügen oder bearbeiten Sie Q&Details in der Vorlagendatei, und speichern Sie Sie auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="754dd-153">Add or edit Q&A details in the template file, and save it on your computer.</span></span>
1. <span data-ttu-id="754dd-154">Wählen Sie im Bereich **Q importieren&einen** **Durchsuchen**aus, und wählen Sie dann die CSV-Datei aus, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="754dd-154">In the **Import Q&A** pane, select **Browse**, and then select the .csv file that you want to import.</span></span>
1. <span data-ttu-id="754dd-155">Wählen Sie **Importieren** aus.</span><span class="sxs-lookup"><span data-stu-id="754dd-155">Select **Import**.</span></span>

<span data-ttu-id="754dd-156">Wichtige Vorlagendatei Tipps:</span><span class="sxs-lookup"><span data-stu-id="754dd-156">Important template file tips:</span></span>

- <span data-ttu-id="754dd-157">Bearbeiten Sie niemals Daten in diesen Feldern: **ID**, **Zuletzt geändert** und **Zuletzt geändert von**.</span><span class="sxs-lookup"><span data-stu-id="754dd-157">Never edit data in these fields: **Id**, **Last Modified**, and **Last Modified By**</span></span>
- <span data-ttu-id="754dd-158">Wenn Sie die **ID** eines vorhandenen Lesezeichens angeben, wird sie durch die Informationen in der Importdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="754dd-158">If you include the **Id** of an existing bookmark, it will be replaced with the information in the import file.</span></span>
- <span data-ttu-id="754dd-159">Wenn ein Lesezeichen mit dem gleichen Titel oder der gleichen URL vorhanden ist, wird das Lesezeichen mit Informationen in der Importdatei aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="754dd-159">If there's an existing bookmark that has the same title or URL, the bookmark will be updated with information in the import file.</span></span>
- <span data-ttu-id="754dd-160">Nicht alle Felder in der Vorlagendatei sind erforderlich, und die erforderlichen Felder sind je nach Lesezeichen Status unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="754dd-160">Not all fields in the template file are required, and the required fields vary depending on the bookmark state.</span></span>
- <span data-ttu-id="754dd-161">Basierend auf dem Feld **Status** werden Lesezeichen als *Entwurf*, *vorgeschlagen*oder *geplant*gespeichert, oder Sie werden automatisch veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="754dd-161">Based on the **State** field, bookmarks are saved as *draft*, *suggested*, or *scheduled*, or they are published automatically.</span></span>
- <span data-ttu-id="754dd-162">Für Partner, die mehrere Organisationen verwalten: Sie können Ihre Lesezeichen aus einer org exportieren und in eine andere importieren.</span><span class="sxs-lookup"><span data-stu-id="754dd-162">For partners who manage multiple organizations: You can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="754dd-163">Sie müssen jedoch die Daten in der Spalte **ID** vor dem Import entfernen.</span><span class="sxs-lookup"><span data-stu-id="754dd-163">But you must remove the data in the **Id** column before you import.</span></span>

> [!NOTE]
> <span data-ttu-id="754dd-164">Sie können Q&nicht als Fehler in der Vorlagendatei importieren.</span><span class="sxs-lookup"><span data-stu-id="754dd-164">You can't import Q&As if there are any errors in the template file.</span></span> <span data-ttu-id="754dd-165">Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und alle erforderlichen Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="754dd-165">To prevent errors, make sure your import file is properly formatted, and include all the required information.</span></span>

<span data-ttu-id="754dd-166">Weitere Informationen zum Vermeiden von Fehlern finden Sie unter [Prevent Import Errors](manage-bookmarks.md#prevent-import-errors).</span><span class="sxs-lookup"><span data-stu-id="754dd-166">For more information about avoiding errors, see [Prevent import errors](manage-bookmarks.md#prevent-import-errors).</span></span>
