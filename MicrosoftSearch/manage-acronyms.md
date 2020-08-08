---
title: Verwalten von Akronym-Antworten in der Microsoft-Suche
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
description: Antworten zum Erstellen und Aktualisieren von Akronymen in Microsoft Search
ms.openlocfilehash: 68e62884898e3aa081fc32438ad9a80068092738
ms.sourcegitcommit: b3738f5ab02bfba9dedf099e035f3850607be480
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "46591508"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="c8f01-103">Verwalten von Akronymen Antworten in der Microsoft-Suche</span><span class="sxs-lookup"><span data-stu-id="c8f01-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="c8f01-104">Benutzer führen häufig unbekannte Akronyme und Abkürzungen aus, die von Ihrer Organisation oder Ihrem Team verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8f01-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="c8f01-105">Begriffe, die für Organisationen oder Teams spezifisch sind, sind möglicherweise neu für Personen, die von einem Team in ein anderes umziehen, mit internen Partnerteams arbeiten oder neu in der Organisation sind.</span><span class="sxs-lookup"><span data-stu-id="c8f01-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="c8f01-106">Organisationen haben nicht immer einen einzigen Verweis für Ihre Standardterminologie.</span><span class="sxs-lookup"><span data-stu-id="c8f01-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="c8f01-107">Durch das Fehlen eines einzelnen Verweises ist es schwer, Definitionen oder Erweiterungen für diese Akronyme zu finden.</span><span class="sxs-lookup"><span data-stu-id="c8f01-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="c8f01-108">Microsoft Search löst dieses Problem mit Akronymen.</span><span class="sxs-lookup"><span data-stu-id="c8f01-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="c8f01-109">Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="c8f01-109">What users experience</span></span>

<span data-ttu-id="c8f01-110">Microsoft Search-Benutzer können Definitionen mit Akronymen in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)und [Office 365](https://Office.com)abrufen.</span><span class="sxs-lookup"><span data-stu-id="c8f01-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="c8f01-111">In das **Suchfeld** geben Benutzer Abfragen wie diese Beispiele ein:</span><span class="sxs-lookup"><span data-stu-id="c8f01-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="c8f01-112">*Was ist* DNN</span><span class="sxs-lookup"><span data-stu-id="c8f01-112">*What is* DNN</span></span>
- <span data-ttu-id="c8f01-113">*Definieren* Sie DNN</span><span class="sxs-lookup"><span data-stu-id="c8f01-113">*Define* DNN</span></span>
- <span data-ttu-id="c8f01-114">DNN- *Definition*</span><span class="sxs-lookup"><span data-stu-id="c8f01-114">DNN *definition*</span></span>
- <span data-ttu-id="c8f01-115">*Erweitern* Sie DNN</span><span class="sxs-lookup"><span data-stu-id="c8f01-115">*Expand* DNN</span></span>
- <span data-ttu-id="c8f01-116">DNN- *Erweiterung*</span><span class="sxs-lookup"><span data-stu-id="c8f01-116">DNN *expansion*</span></span>
- <span data-ttu-id="c8f01-117">*Bedeutung von* DNN</span><span class="sxs-lookup"><span data-stu-id="c8f01-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="c8f01-118">DNN *bedeutet*</span><span class="sxs-lookup"><span data-stu-id="c8f01-118">DNN *means*</span></span>

<span data-ttu-id="c8f01-119">Das Ergebnis enthält alle Bedeutungen von DNN, die in der Organisation des Benutzers vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c8f01-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="c8f01-120">Benutzer müssen eine Abfrage eingeben, die die angegebenen *Schlüsselwörter* für das Akronym enthält, um die entsprechenden Antworten auszulösen.</span><span class="sxs-lookup"><span data-stu-id="c8f01-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="c8f01-121">Bei Akronym-Abfragen wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="c8f01-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="c8f01-122">Antworten zum Einrichten von Akronymen</span><span class="sxs-lookup"><span data-stu-id="c8f01-122">Set up Acronyms answers</span></span>

<span data-ttu-id="c8f01-123">Wechseln Sie im Microsoft 365 [Admin Center](https://admin.microsoft.com)zu **Einstellungen**  >  **Microsoft Search**  >  **Answers**  >  [**Akronyme**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), und wählen Sie dann **Akronyme hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="c8f01-123">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** > **Answers** > [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronyms**.</span></span>

<span data-ttu-id="c8f01-124">Microsoft Search fragt zwei Datenquellen ab, um Akronyme Antworten auf die Suchvorgänge von Benutzern bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="c8f01-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="c8f01-125">**Redaktionelle Akronyme**.</span><span class="sxs-lookup"><span data-stu-id="c8f01-125">**Editorial acronyms**.</span></span> <span data-ttu-id="c8f01-126">Von IT-Administratoren im [Admin Center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c8f01-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="c8f01-127">**Verminte Akronyme**.</span><span class="sxs-lookup"><span data-stu-id="c8f01-127">**Mined acronyms**.</span></span> <span data-ttu-id="c8f01-128">Durch die Microsoft-Suche von den persönlichen e-Mails und Dokumenten und öffentlich verfügbaren Daten innerhalb der Organisation abgebaut.</span><span class="sxs-lookup"><span data-stu-id="c8f01-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="c8f01-129">Einrichten von redaktionellen Akronymen</span><span class="sxs-lookup"><span data-stu-id="c8f01-129">Set up editorial acronyms</span></span>

<span data-ttu-id="c8f01-130">Suchadministratoren können redaktionelle Akronyme auf der [Registerkarte Akronyme](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) im [Microsoft Search Admin Center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)einrichten.</span><span class="sxs-lookup"><span data-stu-id="c8f01-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="c8f01-131">Sie können Akronyme aus einer internen Website oder einem Repository zum Admin Center hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c8f01-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="c8f01-132">Redaktionelle Akronyme können dem **veröffentlichten** oder dem **Entwurfs** Status hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="c8f01-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="c8f01-133">**Veröffentlichter Status**.</span><span class="sxs-lookup"><span data-stu-id="c8f01-133">**Published state**.</span></span> <span data-ttu-id="c8f01-134">Akronyme stehen den Mitarbeitern der Organisation über die Microsoft-Suche zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c8f01-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="c8f01-135">Es kann bis zu drei Tage dauern, bis Akronyme zum veröffentlichten Status hinzugefügt wurden, um in Microsoft Search verfügbar zu sein.</span><span class="sxs-lookup"><span data-stu-id="c8f01-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="c8f01-136">**Entwurfsstatus**.</span><span class="sxs-lookup"><span data-stu-id="c8f01-136">**Draft state**.</span></span> <span data-ttu-id="c8f01-137">Wenn Administratoren Akronyme Antworten überprüfen möchten, bevor Sie in Microsoft Search verfügbar gemacht werden, können Sie die Akronyme dem Entwurfsstatus hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c8f01-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="c8f01-138">Akronyme, die dem Entwurfsstatus hinzugefügt werden, sind in der Microsoft-Suche nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c8f01-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="c8f01-139">Administratoren müssen die Akronyme dem veröffentlichten Status hinzufügen, damit Sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c8f01-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="c8f01-140">Administratoren können Akronyme einzeln hinzufügen oder Sie in einer CSV-Datei Massenimportieren.</span><span class="sxs-lookup"><span data-stu-id="c8f01-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="c8f01-141">Laden Sie eine CSV-Datei mit den in der folgenden Tabelle gezeigten Feldern hoch:</span><span class="sxs-lookup"><span data-stu-id="c8f01-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="c8f01-142">Akronym (obligatorisch)</span><span class="sxs-lookup"><span data-stu-id="c8f01-142">Acronym (mandatory)</span></span> | <span data-ttu-id="c8f01-143">Expansion (obligatorisch)</span><span class="sxs-lookup"><span data-stu-id="c8f01-143">Expansion (mandatory)</span></span> | <span data-ttu-id="c8f01-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8f01-144">Description</span></span>  | <span data-ttu-id="c8f01-145">Quelle</span><span class="sxs-lookup"><span data-stu-id="c8f01-145">Source</span></span> | <span data-ttu-id="c8f01-146">Status (obligatorisch)</span><span class="sxs-lookup"><span data-stu-id="c8f01-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="c8f01-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="c8f01-147">*XXX*</span></span> | <span data-ttu-id="c8f01-148">*Abkürzung für buchstabiert*</span><span class="sxs-lookup"><span data-stu-id="c8f01-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="c8f01-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="c8f01-149">*URL*</span></span> | <span data-ttu-id="c8f01-150">*Veröffentlicht oder Entwurf*</span><span class="sxs-lookup"><span data-stu-id="c8f01-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="c8f01-151">CSV-Felder</span><span class="sxs-lookup"><span data-stu-id="c8f01-151">CSV fields</span></span>

<span data-ttu-id="c8f01-152">**Akronym**.</span><span class="sxs-lookup"><span data-stu-id="c8f01-152">**Acronym**.</span></span> <span data-ttu-id="c8f01-153">Enthält das tatsächliche kurze Formular oder Akronym.</span><span class="sxs-lookup"><span data-stu-id="c8f01-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="c8f01-154">Ein Beispiel ist *DNN*.</span><span class="sxs-lookup"><span data-stu-id="c8f01-154">An example is *DNN*.</span></span>

<span data-ttu-id="c8f01-155">**Erweiterung**.</span><span class="sxs-lookup"><span data-stu-id="c8f01-155">**Expansion**.</span></span> <span data-ttu-id="c8f01-156">Enthält die Erweiterung des Akronyms.</span><span class="sxs-lookup"><span data-stu-id="c8f01-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="c8f01-157">Ein Beispiel ist ein *tiefes neuronales Netzwerk*.</span><span class="sxs-lookup"><span data-stu-id="c8f01-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="c8f01-158">**Beschreibung**.</span><span class="sxs-lookup"><span data-stu-id="c8f01-158">**Description**.</span></span> <span data-ttu-id="c8f01-159">Eine kurze Beschreibung des Akronyms, mit der Benutzer weitere Informationen zum Akronym und seiner Erweiterung erhalten.</span><span class="sxs-lookup"><span data-stu-id="c8f01-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="c8f01-160">*Ein tiefes neuronales Netzwerk ist beispielsweise ein neuronales Netzwerk mit einem gewissen Grad an Komplexität, ein neuronales Netzwerk mit mehr als zwei Schichten*.</span><span class="sxs-lookup"><span data-stu-id="c8f01-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="c8f01-161">**Source**.</span><span class="sxs-lookup"><span data-stu-id="c8f01-161">**Source**.</span></span> <span data-ttu-id="c8f01-162">Die URL der Seite oder Website, auf der Benutzer weitere Informationen zum Akronym erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="c8f01-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="c8f01-163">**State**.</span><span class="sxs-lookup"><span data-stu-id="c8f01-163">**State**.</span></span> <span data-ttu-id="c8f01-164">Dieses Feld kann zwei Werte annehmen:</span><span class="sxs-lookup"><span data-stu-id="c8f01-164">This field can take two values:</span></span>

- <span data-ttu-id="c8f01-165">**Entwurf**.</span><span class="sxs-lookup"><span data-stu-id="c8f01-165">**Draft**.</span></span> <span data-ttu-id="c8f01-166">Das Akronym wird dem Status Entwurf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c8f01-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="c8f01-167">**Veröffentlicht**</span><span class="sxs-lookup"><span data-stu-id="c8f01-167">**Published**.</span></span> <span data-ttu-id="c8f01-168">Das Akronym wird dem veröffentlichten Zustand hinzugefügt und wird in der Microsoft-Suche zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="c8f01-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="c8f01-169">Verminte Akronyme</span><span class="sxs-lookup"><span data-stu-id="c8f01-169">Mined acronyms</span></span>

<span data-ttu-id="c8f01-170">Es kann eine Herausforderung für Administratoren sein, alle in einer Organisation verwendeten Akronyme für Antworten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c8f01-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="c8f01-171">Dieses Feature kann Akronyme finden, von denen die Suchadministratoren gar nicht wissen.</span><span class="sxs-lookup"><span data-stu-id="c8f01-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="c8f01-172">Dafür werden in Microsoft Search auch Akronyme aus folgenden Quellen untersucht:</span><span class="sxs-lookup"><span data-stu-id="c8f01-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="c8f01-173">Benutzer-e-Mails.</span><span class="sxs-lookup"><span data-stu-id="c8f01-173">Users’ emails.</span></span>
- <span data-ttu-id="c8f01-174">Dokumente in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)und [Microsoft OneNote](https://www.onenote.com/).</span><span class="sxs-lookup"><span data-stu-id="c8f01-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/).</span></span>
- <span data-ttu-id="c8f01-175">Öffentliche Dokumente innerhalb der Organisation, auf die Benutzer in SharePoint, OneDrive oder OneNote zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c8f01-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="c8f01-176">Die Microsoft-Suche stellt sicher, dass nur Benutzer mit Zugriff und Berechtigungen für ein Dokument die von dieser abgebauten Akronyme sehen können.</span><span class="sxs-lookup"><span data-stu-id="c8f01-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="c8f01-177">Wenn ein Akronym aus dem Postfach eines Benutzers abgebaut wird, kann nur dieser Benutzer dieses Akronym sehen.</span><span class="sxs-lookup"><span data-stu-id="c8f01-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="c8f01-178">Für verminte Akronyme ist kein Setup erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c8f01-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c8f01-179">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="c8f01-179">Frequently asked questions</span></span>

<span data-ttu-id="c8f01-180">**F.: wie werden redaktionelle und verminte Daten bewertet?**</span><span class="sxs-lookup"><span data-stu-id="c8f01-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="c8f01-181">**A:** Das Feature zählt derzeit redaktionelle Akronyme oberhalb der abgebauten Akronyme.</span><span class="sxs-lookup"><span data-stu-id="c8f01-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="c8f01-182">**F.: wie lange dauert es, bis redaktionelle Akronyme in der Microsoft-Suche sichtbar sind, nachdem Sie veröffentlicht wurden?**</span><span class="sxs-lookup"><span data-stu-id="c8f01-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="c8f01-183">**A:**  Es dauert bis zu drei Tage, bis Akronyme zum veröffentlichten Status hinzugefügt wurden, um in Microsoft Search verfügbar zu sein.</span><span class="sxs-lookup"><span data-stu-id="c8f01-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="c8f01-184">**F.: wie lösen Benutzer Akronyme Antworten aus?**</span><span class="sxs-lookup"><span data-stu-id="c8f01-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="c8f01-185">**A**: um Akronyme Antworten zu erhalten, müssen Benutzer bestimmte Abfragemuster in ein [Bing](https://bing.com)-, [SharePoint](https://products.office.com/sharepoint/collaboration)-oder [Office 365](https://Office.com) **Suchfeld** eingeben.</span><span class="sxs-lookup"><span data-stu-id="c8f01-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="c8f01-186">**F.: wie lange dauert es, bis abgebaute Akronyme angezeigt werden, nachdem Sie eine neue e-Mail oder ein neues Dokument empfangen oder gesendet haben?**</span><span class="sxs-lookup"><span data-stu-id="c8f01-186">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="c8f01-187">**A:** Verminte Akronyme aus einer neuen e-Mail oder einem Dokument benötigen bis zu sieben Tage, um in Microsoft-Suchergebnissen angezeigt zu werden.</span><span class="sxs-lookup"><span data-stu-id="c8f01-187">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="c8f01-188">**F.: müssen Dokumente in einem bestimmten Format vorliegen, damit Sie von Mining abgeholt werden können?**</span><span class="sxs-lookup"><span data-stu-id="c8f01-188">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="c8f01-189">**A:** Nein.</span><span class="sxs-lookup"><span data-stu-id="c8f01-189">**A:** No.</span></span> <span data-ttu-id="c8f01-190">Wir unterstützen alle Dateitypen außer Bild, Ordner und ZIP-Dateien.</span><span class="sxs-lookup"><span data-stu-id="c8f01-190">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="c8f01-191">**F.: werden Microsoft-Akronyme aus Dokumenten in allen Sprachen erhalten?**</span><span class="sxs-lookup"><span data-stu-id="c8f01-191">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="c8f01-192">**A**: Microsoft unterstützt nur das Mining von Dokumenten in englischer Sprache.</span><span class="sxs-lookup"><span data-stu-id="c8f01-192">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="c8f01-193">Unterstützung für andere Sprachen wird in Phasen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c8f01-193">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="c8f01-194">**F.: Was geschieht, wenn meine Organisation keine verminten Akronyme anzeigen möchte? Kann ich das Anzeigen von verminten Akronymen in Suchergebnissen beenden?**</span><span class="sxs-lookup"><span data-stu-id="c8f01-194">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="c8f01-195">**A**: um die Anzeige von verminten Akronymen in Suchergebnissen zu deaktivieren, erstellen Sie ein Kundensupport Ticket, indem Sie die Anweisungen unter [Contact Support for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)befolgen.</span><span class="sxs-lookup"><span data-stu-id="c8f01-195">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="c8f01-196">Nachdem Sie ein Support Ticket erstellt haben, dauert es bis zu 48 Stunden, damit verminte Akronyme nicht mehr in den Suchergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c8f01-196">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>
