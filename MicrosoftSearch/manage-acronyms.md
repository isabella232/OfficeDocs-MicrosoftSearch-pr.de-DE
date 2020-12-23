---
title: Verwalten von Akronym-Antworten in der Microsoft-Suche
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Antworten zum Erstellen und Aktualisieren von Akronymen in Microsoft Search
ms.openlocfilehash: ff79e3d741e10d401873c29d86739e61c9f53329
ms.sourcegitcommit: e6ceb07cae208648dadd5452a077414ab5a4513f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "49728006"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="1928c-103">Verwalten von Akronymen Antworten in der Microsoft-Suche</span><span class="sxs-lookup"><span data-stu-id="1928c-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="1928c-104">Benutzer führen häufig unbekannte Akronyme und Abkürzungen aus, die von Ihrer Organisation oder Ihrem Team verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1928c-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="1928c-105">Begriffe, die für Organisationen oder Teams spezifisch sind, sind möglicherweise neu für Personen, die von einem Team in ein anderes umziehen, mit internen Partnerteams arbeiten oder neu in der Organisation sind.</span><span class="sxs-lookup"><span data-stu-id="1928c-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="1928c-106">Organisationen haben nicht immer einen einzigen Verweis für Ihre Standardterminologie.</span><span class="sxs-lookup"><span data-stu-id="1928c-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="1928c-107">Durch das Fehlen eines einzelnen Verweises ist es schwer, Definitionen oder Erweiterungen für diese Akronyme zu finden.</span><span class="sxs-lookup"><span data-stu-id="1928c-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="1928c-108">Microsoft Search löst dieses Problem mit Akronymen.</span><span class="sxs-lookup"><span data-stu-id="1928c-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="1928c-109">Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="1928c-109">What users experience</span></span>

<span data-ttu-id="1928c-110">Microsoft Search-Benutzer können Definitionen mit Akronymen in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)und [Office 365](https://Office.com)abrufen.</span><span class="sxs-lookup"><span data-stu-id="1928c-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="1928c-111">In das **Suchfeld** geben Benutzer Abfragen wie diese Beispiele ein:</span><span class="sxs-lookup"><span data-stu-id="1928c-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="1928c-112">*Was ist* DNN</span><span class="sxs-lookup"><span data-stu-id="1928c-112">*What is* DNN</span></span>
- <span data-ttu-id="1928c-113">*Definieren* Sie DNN</span><span class="sxs-lookup"><span data-stu-id="1928c-113">*Define* DNN</span></span>
- <span data-ttu-id="1928c-114">DNN- *Definition*</span><span class="sxs-lookup"><span data-stu-id="1928c-114">DNN *definition*</span></span>
- <span data-ttu-id="1928c-115">*Erweitern* Sie DNN</span><span class="sxs-lookup"><span data-stu-id="1928c-115">*Expand* DNN</span></span>
- <span data-ttu-id="1928c-116">DNN- *Erweiterung*</span><span class="sxs-lookup"><span data-stu-id="1928c-116">DNN *expansion*</span></span>
- <span data-ttu-id="1928c-117">*Bedeutung von* DNN</span><span class="sxs-lookup"><span data-stu-id="1928c-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="1928c-118">DNN *bedeutet*</span><span class="sxs-lookup"><span data-stu-id="1928c-118">DNN *means*</span></span>

<span data-ttu-id="1928c-119">Das Ergebnis enthält alle Bedeutungen von DNN, die in der Organisation des Benutzers vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="1928c-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="1928c-120">Benutzer müssen eine Abfrage eingeben, die die angegebenen *Schlüsselwörter* für das Akronym enthält, um die entsprechenden Antworten auszulösen.</span><span class="sxs-lookup"><span data-stu-id="1928c-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="1928c-121">Bei Akronym-Abfragen wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="1928c-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="1928c-122">Antworten zum Einrichten von Akronymen</span><span class="sxs-lookup"><span data-stu-id="1928c-122">Set up acronyms answers</span></span>

<span data-ttu-id="1928c-123">Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Akronyme**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), und wählen Sie dann **Akronym hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1928c-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="1928c-124">Microsoft Search fragt zwei Datenquellen ab, um Akronyme Antworten auf die Suchvorgänge von Benutzern bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="1928c-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="1928c-125">**Admin-kuratiert**.</span><span class="sxs-lookup"><span data-stu-id="1928c-125">**Admin-curated**.</span></span> <span data-ttu-id="1928c-126">Von IT-Administratoren im [Admin Center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1928c-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="1928c-127">**System-kuratiert**.</span><span class="sxs-lookup"><span data-stu-id="1928c-127">**System-curated**.</span></span> <span data-ttu-id="1928c-128">Von der Microsoft-Suche anhand von e-Mails und Dokumenten sowie öffentlich verfügbaren Daten in der Organisation ermittelt.</span><span class="sxs-lookup"><span data-stu-id="1928c-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="1928c-129">Einrichten von admin-kuratierten Akronymen</span><span class="sxs-lookup"><span data-stu-id="1928c-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="1928c-130">Suchadministratoren können Akronyme auf der [Registerkarte Akronyme](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) im  [Microsoft Search Admin Center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1928c-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="1928c-131">Sie können Akronyme aus einer internen Website oder einem Repository zum Admin Center hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1928c-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="1928c-132">Diese Akronyme können dem **veröffentlichten** oder dem **Entwurfs** Status hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="1928c-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="1928c-133">**Veröffentlichter Status**.</span><span class="sxs-lookup"><span data-stu-id="1928c-133">**Published state**.</span></span> <span data-ttu-id="1928c-134">Akronyme stehen den Benutzern der Organisation über die Microsoft-Suche zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1928c-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="1928c-135">Es kann bis zu drei Tage dauern, bis Akronyme zum veröffentlichten Status hinzugefügt wurden, um in Microsoft Search verfügbar zu sein.</span><span class="sxs-lookup"><span data-stu-id="1928c-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="1928c-136">**Entwurfsstatus**.</span><span class="sxs-lookup"><span data-stu-id="1928c-136">**Draft state**.</span></span> <span data-ttu-id="1928c-137">Wenn Sie ein Akronym überprüfen möchten, bevor Sie es in Microsoft Search verfügbar machen, können Sie das Akronym in einem Entwurfsstatus hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1928c-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="1928c-138">Akronyme im Entwurfsstatus werden in den Suchergebnissen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1928c-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="1928c-139">Sie müssen das Akronym in den veröffentlichten Zustand versetzen, damit es in den Suchergebnissen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1928c-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="1928c-140">Sie können Akronyme einzeln hinzufügen oder Sie in einer CSV-Datei Massenimportieren.</span><span class="sxs-lookup"><span data-stu-id="1928c-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="1928c-141">Laden Sie eine CSV-Datei mit den in der folgenden Tabelle gezeigten Feldern hoch:</span><span class="sxs-lookup"><span data-stu-id="1928c-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="1928c-142">Akronym (obligatorisch)</span><span class="sxs-lookup"><span data-stu-id="1928c-142">Acronym (mandatory)</span></span> | <span data-ttu-id="1928c-143">Expansion (obligatorisch)</span><span class="sxs-lookup"><span data-stu-id="1928c-143">Expansion (mandatory)</span></span> | <span data-ttu-id="1928c-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1928c-144">Description</span></span>  | <span data-ttu-id="1928c-145">Source</span><span class="sxs-lookup"><span data-stu-id="1928c-145">Source</span></span> | <span data-ttu-id="1928c-146">Status (obligatorisch)</span><span class="sxs-lookup"><span data-stu-id="1928c-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="1928c-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="1928c-147">*XXX*</span></span> | <span data-ttu-id="1928c-148">*Abkürzung für buchstabiert*</span><span class="sxs-lookup"><span data-stu-id="1928c-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="1928c-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="1928c-149">*URL*</span></span> | <span data-ttu-id="1928c-150">*Veröffentlicht oder Entwurf*</span><span class="sxs-lookup"><span data-stu-id="1928c-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="1928c-151">CSV-Felder</span><span class="sxs-lookup"><span data-stu-id="1928c-151">CSV fields</span></span>

<span data-ttu-id="1928c-152">**Akronym**.</span><span class="sxs-lookup"><span data-stu-id="1928c-152">**Acronym**.</span></span> <span data-ttu-id="1928c-153">Enthält das tatsächliche kurze Formular oder Akronym.</span><span class="sxs-lookup"><span data-stu-id="1928c-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="1928c-154">Ein Beispiel ist *DNN*.</span><span class="sxs-lookup"><span data-stu-id="1928c-154">An example is *DNN*.</span></span>

<span data-ttu-id="1928c-155">**Erweiterung**.</span><span class="sxs-lookup"><span data-stu-id="1928c-155">**Expansion**.</span></span> <span data-ttu-id="1928c-156">Enthält die Erweiterung des Akronyms.</span><span class="sxs-lookup"><span data-stu-id="1928c-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="1928c-157">Ein Beispiel ist ein *tiefes neuronales Netzwerk*.</span><span class="sxs-lookup"><span data-stu-id="1928c-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="1928c-158">**Beschreibung**.</span><span class="sxs-lookup"><span data-stu-id="1928c-158">**Description**.</span></span> <span data-ttu-id="1928c-159">Eine kurze Beschreibung des Akronyms, mit der Benutzer weitere Informationen zum Akronym und seiner Erweiterung erhalten.</span><span class="sxs-lookup"><span data-stu-id="1928c-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="1928c-160">*Ein tiefes neuronales Netzwerk ist beispielsweise ein neuronales Netzwerk mit einem gewissen Grad an Komplexität, ein neuronales Netzwerk mit mehr als zwei Schichten*.</span><span class="sxs-lookup"><span data-stu-id="1928c-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="1928c-161">**Quelle**.</span><span class="sxs-lookup"><span data-stu-id="1928c-161">**Source**.</span></span> <span data-ttu-id="1928c-162">Die URL der Seite oder Website, auf der Benutzer weitere Informationen zum Akronym erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="1928c-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="1928c-163">**State**.</span><span class="sxs-lookup"><span data-stu-id="1928c-163">**State**.</span></span> <span data-ttu-id="1928c-164">Dieses Feld kann zwei Werte annehmen:</span><span class="sxs-lookup"><span data-stu-id="1928c-164">This field can take two values:</span></span>

- <span data-ttu-id="1928c-165">**Entwurf**.</span><span class="sxs-lookup"><span data-stu-id="1928c-165">**Draft**.</span></span> <span data-ttu-id="1928c-166">Das Akronym wird dem Status Entwurf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1928c-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="1928c-167">**Veröffentlicht**</span><span class="sxs-lookup"><span data-stu-id="1928c-167">**Published**.</span></span> <span data-ttu-id="1928c-168">Das Akronym wird dem veröffentlichten Zustand hinzugefügt und wird in der Microsoft-Suche zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="1928c-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="1928c-169">Vom System kuratierte Akronyme</span><span class="sxs-lookup"><span data-stu-id="1928c-169">System-curated acronyms</span></span>

<span data-ttu-id="1928c-170">Es kann eine Herausforderung für Administratoren sein, alle in einer Organisation verwendeten Akronyme für Antworten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1928c-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="1928c-171">Dieses Feature kann Akronyme finden, von denen die Suchadministratoren gar nicht wissen.</span><span class="sxs-lookup"><span data-stu-id="1928c-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="1928c-172">Dafür erkennt und kuratiert Microsoft Search auch Akronyme aus diesen Quellen:</span><span class="sxs-lookup"><span data-stu-id="1928c-172">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="1928c-173">Benutzer-e-Mails</span><span class="sxs-lookup"><span data-stu-id="1928c-173">Users’ emails</span></span>
- <span data-ttu-id="1928c-174">Dokumente in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)und [Microsoft OneNote](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="1928c-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="1928c-175">Öffentliche Dokumente in der Organisation, auf die Benutzer in SharePoint, OneDrive oder OneNote zugreifen können</span><span class="sxs-lookup"><span data-stu-id="1928c-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="1928c-176">Bei der Microsoft-Suche wird sichergestellt, dass nur Benutzer mit Zugriff und Berechtigungen für ein Dokument die von ihm ermittelten Akronyme sehen können.</span><span class="sxs-lookup"><span data-stu-id="1928c-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="1928c-177">Wenn ein Akronym im Postfach eines Benutzers gefunden wird, kann nur dieser Benutzer dieses Akronym sehen.</span><span class="sxs-lookup"><span data-stu-id="1928c-177">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="1928c-178">Für vom Administrator kuratierte Akronyme ist kein Setup erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1928c-178">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="1928c-179">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="1928c-179">Frequently asked questions</span></span>

<span data-ttu-id="1928c-180">**F.: wie werden die vom Administrator kuratierten und die System kuratierten Daten bewertet?**</span><span class="sxs-lookup"><span data-stu-id="1928c-180">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="1928c-181">**A:** Die Rangfolge der Ergebnisse kann von Person zu Person variieren, da die Ergebnisse für jeden Benutzer personalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1928c-181">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="1928c-182">Keine dieser Kategorien hat immer Vorrang vor der anderen Kategorie.</span><span class="sxs-lookup"><span data-stu-id="1928c-182">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="1928c-183">**F.: wie lange dauert es, bis admin-kuratierte Akronyme in der Microsoft-Suche sichtbar sind, nachdem Sie veröffentlicht wurden?**</span><span class="sxs-lookup"><span data-stu-id="1928c-183">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="1928c-184">**A:**  Es dauert bis zu drei Tage, bis Akronyme zum veröffentlichten Status hinzugefügt wurden, um in Microsoft Search verfügbar zu sein.</span><span class="sxs-lookup"><span data-stu-id="1928c-184">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="1928c-185">**F.: wie lösen Benutzer Akronyme Antworten aus?**</span><span class="sxs-lookup"><span data-stu-id="1928c-185">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="1928c-186">**A**: um Akronyme Antworten zu erhalten, müssen Benutzer bestimmte Abfragemuster in ein [Bing](https://bing.com)-, [SharePoint](https://products.office.com/sharepoint/collaboration)-oder [Office 365](https://Office.com) **Suchfeld** eingeben.</span><span class="sxs-lookup"><span data-stu-id="1928c-186">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="1928c-187">**F.: wie lange dauert es, bis die vom System kuratierten Akronyme angezeigt werden, nachdem Sie eine neue e-Mail oder ein neues Dokument empfangen oder gesendet haben?**</span><span class="sxs-lookup"><span data-stu-id="1928c-187">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="1928c-188">**A:** In einer neuen e-Mail oder einem Dokument gefundene Akronyme benötigen bis zu sieben Tage, um in Microsoft-Suchergebnissen angezeigt zu werden.</span><span class="sxs-lookup"><span data-stu-id="1928c-188">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="1928c-189">**F.: müssen Dokumente in einem bestimmten Format vorliegen, damit Sie von Mining abgeholt werden können?**</span><span class="sxs-lookup"><span data-stu-id="1928c-189">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="1928c-190">**A:** Nein.</span><span class="sxs-lookup"><span data-stu-id="1928c-190">**A:** No.</span></span> <span data-ttu-id="1928c-191">Wir unterstützen alle Dateitypen außer Bild, Ordner und ZIP-Dateien.</span><span class="sxs-lookup"><span data-stu-id="1928c-191">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="1928c-192">**F.: wird Microsoft Akronyme aus Dokumenten in allen Sprachen ermitteln?**</span><span class="sxs-lookup"><span data-stu-id="1928c-192">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="1928c-193">**A**: Microsoft unterstützt nur das Mining von Dokumenten in englischer Sprache.</span><span class="sxs-lookup"><span data-stu-id="1928c-193">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="1928c-194">Unterstützung für andere Sprachen wird in Phasen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1928c-194">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="1928c-195">**F.: Was geschieht, wenn meine Organisation keine vom System kuratierten Akronyme anzeigen möchte? Kann ich die Anzeige dieser Art von Akronym in meinen Suchergebnissen beenden?**</span><span class="sxs-lookup"><span data-stu-id="1928c-195">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="1928c-196">**A**: um das Anzeigen von System-kuratierten Akronymen in Suchergebnissen zu deaktivieren, erstellen Sie ein Kundensupport Ticket, indem Sie den Anweisungen unter [Contact Support for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)folgen.</span><span class="sxs-lookup"><span data-stu-id="1928c-196">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="1928c-197">Nachdem Sie ein Support Ticket erstellt haben, dauert es bis zu 48 Stunden, damit die vom System kuratierten Akronyme nicht mehr in den Suchergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1928c-197">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
