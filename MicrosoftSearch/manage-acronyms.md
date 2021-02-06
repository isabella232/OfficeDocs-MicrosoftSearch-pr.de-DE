---
title: Verwalten von Antworten auf Akronyme in Microsoft Search
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
description: Erstellen und Aktualisieren von Antworten auf Akronyme in Microsoft Search
ms.openlocfilehash: 45d3cc7b33f27d2f4e77d8099fbfa91e01aabcbb
ms.sourcegitcommit: ef94ffd6111acb929c8343f0f4f82ea109b68fb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122156"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="eb0f7-103">Verwalten von Antworten auf Akronyme in Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="eb0f7-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="eb0f7-104">Benutzer erhalten häufig unbekannte Akronyme und Abkürzungen, die von ihrer Organisation oder ihrem Team verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="eb0f7-105">Spezifisch für Organisationen oder Teams sind möglicherweise neue Begriffe für Personen, die von einem Team in ein anderes wechseln, mit internen Partnerteams zusammenarbeiten oder neu in der Organisation sind.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="eb0f7-106">Organisationen verfügen nicht immer über einen einzigen Verweis für ihre Standardterminologie.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="eb0f7-107">Das Fehlen eines einzigen Verweises macht es schwierig, Definitionen oder Erweiterungen für diese Akronyme zu finden.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="eb0f7-108">Microsoft Search löst dieses Problem mit Akronymen.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="eb0f7-109">Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="eb0f7-109">What users experience</span></span>

<span data-ttu-id="eb0f7-110">Microsoft Search-Benutzer können Definitionen mit Akronymen in [Bing,](https://Bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)und [Office 365 erhalten.](https://Office.com)</span><span class="sxs-lookup"><span data-stu-id="eb0f7-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="eb0f7-111">Im **Suchfeld** geben Benutzer Abfragen wie die folgenden Beispiele ein:</span><span class="sxs-lookup"><span data-stu-id="eb0f7-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="eb0f7-112">*Was ist* DNN</span><span class="sxs-lookup"><span data-stu-id="eb0f7-112">*What is* DNN</span></span>
- <span data-ttu-id="eb0f7-113">*Definieren* DNN</span><span class="sxs-lookup"><span data-stu-id="eb0f7-113">*Define* DNN</span></span>
- <span data-ttu-id="eb0f7-114">DNN-Definition </span><span class="sxs-lookup"><span data-stu-id="eb0f7-114">DNN *definition*</span></span>
- <span data-ttu-id="eb0f7-115">*Erweitern* DNN</span><span class="sxs-lookup"><span data-stu-id="eb0f7-115">*Expand* DNN</span></span>
- <span data-ttu-id="eb0f7-116">DNN-Erweiterung </span><span class="sxs-lookup"><span data-stu-id="eb0f7-116">DNN *expansion*</span></span>
- <span data-ttu-id="eb0f7-117">*Bedeutung von* DNN</span><span class="sxs-lookup"><span data-stu-id="eb0f7-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="eb0f7-118">DNN *bedeutet*</span><span class="sxs-lookup"><span data-stu-id="eb0f7-118">DNN *means*</span></span>

<span data-ttu-id="eb0f7-119">Das Ergebnis enthält alle Bedeutungen von DNN, die innerhalb der Organisation des Benutzers vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="eb0f7-120">Benutzer müssen eine Abfrage eingeben, die die angegebenen Schlüsselwörter des Akronyms enthält, um *die* entsprechenden Antworten auszulösen.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="eb0f7-121">Bei Akronymabfragen wird die Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="eb0f7-122">Einrichten von Akronymantworten</span><span class="sxs-lookup"><span data-stu-id="eb0f7-122">Set up acronyms answers</span></span>

<span data-ttu-id="eb0f7-123">Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Akronyme,**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)und wählen Sie dann **"Akronym hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="eb0f7-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="eb0f7-124">Microsoft Search fragt zwei Datenquellen ab, um Akronyme antworten auf Benutzersuchen zu liefern:</span><span class="sxs-lookup"><span data-stu-id="eb0f7-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="eb0f7-125">**Admin-curated**.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-125">**Admin-curated**.</span></span> <span data-ttu-id="eb0f7-126">Bereitgestellt von IT-Administratoren im [Admin Center.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)</span><span class="sxs-lookup"><span data-stu-id="eb0f7-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="eb0f7-127">**Systemverkn tzt**.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-127">**System-curated**.</span></span> <span data-ttu-id="eb0f7-128">Von Microsoft Search aus E-Mails und Dokumenten von Benutzern und öffentlich verfügbaren Daten innerhalb der Organisation ermittelt.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="eb0f7-129">Einrichten von vom Administrator verwalteten Akronymen</span><span class="sxs-lookup"><span data-stu-id="eb0f7-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="eb0f7-130">Suchadministratoren können Akronyme auf der Registerkarte ["Akronyme"](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) im [Microsoft Search Admin Center hinzufügen.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)</span><span class="sxs-lookup"><span data-stu-id="eb0f7-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="eb0f7-131">Sie können Akronyme von jeder internen Website oder jedem Repository zum Admin Center hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="eb0f7-132">Diese Akronyme können dem Status **"Veröffentlicht"** oder **"Entwurf" hinzugefügt** werden:</span><span class="sxs-lookup"><span data-stu-id="eb0f7-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="eb0f7-133">**Veröffentlichter Status**.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-133">**Published state**.</span></span> <span data-ttu-id="eb0f7-134">Akronyme stehen den Benutzern der Organisation über Microsoft Search zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="eb0f7-135">Es kann bis zu drei Tage dauern, bis Akronyme, die zum Status "Veröffentlicht" hinzugefügt wurden, in Microsoft Search verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="eb0f7-136">**Entwurfsstatus**.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-136">**Draft state**.</span></span> <span data-ttu-id="eb0f7-137">Wenn Sie ein Akronym überprüfen möchten, bevor Sie es in Microsoft Search zur Verfügung stellen, können Sie das Akronym im Entwurfszustand hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="eb0f7-138">Akronyme im Entwurfsstatus werden in den Suchergebnissen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="eb0f7-139">Sie müssen das Akronym in den Status "Veröffentlicht" verschieben, damit es in den Suchergebnissen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="eb0f7-140">Sie können Akronyme einzeln oder massenimportieren sie in eine CSV-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="eb0f7-141">Laden Sie eine CSV-Datei mit den in der folgenden Tabelle aufgeführten Feldern hoch:</span><span class="sxs-lookup"><span data-stu-id="eb0f7-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="eb0f7-142">Akronym (verpflichtend)</span><span class="sxs-lookup"><span data-stu-id="eb0f7-142">Acronym (Mandatory)</span></span> | <span data-ttu-id="eb0f7-143">Erweiterung (verpflichtend)</span><span class="sxs-lookup"><span data-stu-id="eb0f7-143">Expansion (Mandatory)</span></span> | <span data-ttu-id="eb0f7-144">Url</span><span class="sxs-lookup"><span data-stu-id="eb0f7-144">Url</span></span> | <span data-ttu-id="eb0f7-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb0f7-145">Description</span></span>  | <span data-ttu-id="eb0f7-146">Status (verpflichtend)</span><span class="sxs-lookup"><span data-stu-id="eb0f7-146">State (Mandatory)</span></span> | <span data-ttu-id="eb0f7-147">Zuletzt geändert</span><span class="sxs-lookup"><span data-stu-id="eb0f7-147">Last Modified</span></span> | <span data-ttu-id="eb0f7-148">Zuletzt geändert von</span><span class="sxs-lookup"><span data-stu-id="eb0f7-148">Last Modified By</span></span> | <span data-ttu-id="eb0f7-149">Id</span><span class="sxs-lookup"><span data-stu-id="eb0f7-149">Id</span></span> |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| <span data-ttu-id="eb0f7-150">*XXX*</span><span class="sxs-lookup"><span data-stu-id="eb0f7-150">*XXX*</span></span> | <span data-ttu-id="eb0f7-151">*Kurzschreibkürzung*</span><span class="sxs-lookup"><span data-stu-id="eb0f7-151">*Spelled out abbreviation*</span></span> | <span data-ttu-id="eb0f7-152">*Source*</span><span class="sxs-lookup"><span data-stu-id="eb0f7-152">*Source*</span></span> |  | <span data-ttu-id="eb0f7-153">*Veröffentlicht oder Entwurf*</span><span class="sxs-lookup"><span data-stu-id="eb0f7-153">*Published or Draft*</span></span> |  |  |  |

### <a name="csv-fields"></a><span data-ttu-id="eb0f7-154">CSV-Felder</span><span class="sxs-lookup"><span data-stu-id="eb0f7-154">CSV fields</span></span>

<span data-ttu-id="eb0f7-155">**Akronym**.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-155">**Acronym**.</span></span> <span data-ttu-id="eb0f7-156">Enthält die tatsächliche Kurzform oder das Akronym.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-156">Contains the actual short form or acronym.</span></span> <span data-ttu-id="eb0f7-157">Ein Beispiel ist *DNN*.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-157">An example is *DNN*.</span></span>

<span data-ttu-id="eb0f7-158">**Erweiterung**.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-158">**Expansion**.</span></span> <span data-ttu-id="eb0f7-159">Enthält die Erweiterung des Akronyms.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-159">Contains the expansion of the acronym.</span></span> <span data-ttu-id="eb0f7-160">Ein Beispiel ist *"Deep Neural Network".*</span><span class="sxs-lookup"><span data-stu-id="eb0f7-160">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="eb0f7-161">**Beschreibung**.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-161">**Description**.</span></span> <span data-ttu-id="eb0f7-162">Eine kurze Beschreibung des Akronyms, mit dem Benutzer weitere Informationen über das Akronym und dessen Erweiterung erhalten.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-162">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="eb0f7-163">Ein tiefes neurales Netzwerk ist beispielsweise ein neurales Netzwerk mit einer bestimmten *Komplexitätsstufe,* ein neurales Netzwerk mit mehr als zwei Ebenen.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-163">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="eb0f7-164">**Quelle**.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-164">**Source**.</span></span> <span data-ttu-id="eb0f7-165">Die URL der Seite oder Website, auf der Benutzer weitere Informationen zum Akronym erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-165">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="eb0f7-166">**Status**.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-166">**State**.</span></span> <span data-ttu-id="eb0f7-167">Dieses Feld kann zwei Werte enthalten:</span><span class="sxs-lookup"><span data-stu-id="eb0f7-167">This field can take two values:</span></span>

- <span data-ttu-id="eb0f7-168">**Entwurf**.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-168">**Draft**.</span></span> <span data-ttu-id="eb0f7-169">Fügt das Akronym dem Entwurfsstatus hinzu.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-169">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="eb0f7-170">**Veröffentlicht**</span><span class="sxs-lookup"><span data-stu-id="eb0f7-170">**Published**.</span></span> <span data-ttu-id="eb0f7-171">Fügt das Akronym dem Status "Veröffentlicht" hinzu und stellt es in Microsoft Search zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-171">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="eb0f7-172">Vom System behandelte Akronyme</span><span class="sxs-lookup"><span data-stu-id="eb0f7-172">System-curated acronyms</span></span>

<span data-ttu-id="eb0f7-173">Es kann eine Herausforderung für Administratoren sein, alle in einer Organisation verwendeten Akronyme zu Antworten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-173">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="eb0f7-174">Dieses Feature kann Akronyme finden, die Suchadministratoren nicht einmal kennen.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-174">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="eb0f7-175">Hierzu ermittelt und kuratiert Microsoft Search auch Akronyme aus diesen Quellen:</span><span class="sxs-lookup"><span data-stu-id="eb0f7-175">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="eb0f7-176">E-Mails von Benutzern</span><span class="sxs-lookup"><span data-stu-id="eb0f7-176">Users’ emails</span></span>
- <span data-ttu-id="eb0f7-177">Dokumente in [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)und [Microsoft OneNote](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="eb0f7-177">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="eb0f7-178">Öffentliche Dokumente innerhalb der Organisation, auf die Benutzer in SharePoint, OneDrive oder OneNote Zugriff haben</span><span class="sxs-lookup"><span data-stu-id="eb0f7-178">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="eb0f7-179">Microsoft Search stellt sicher, dass nur Benutzer mit Zugriff und Berechtigungen für ein Dokument die Akronyme sehen können, die von diesem erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-179">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="eb0f7-180">Wenn ein Akronym im Postfach eines Benutzers gefunden wird, kann nur dieser Benutzer dieses Akronym sehen.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-180">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="eb0f7-181">Für vom Administrator verwaltete Akronyme ist kein Setup erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-181">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="eb0f7-182">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="eb0f7-182">Frequently asked questions</span></span>

<span data-ttu-id="eb0f7-183">**F: Wie werden vom Administrator verwaltete und vom System behandelte Daten bewertet?**</span><span class="sxs-lookup"><span data-stu-id="eb0f7-183">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="eb0f7-184">**A:** Die Rangfolge der Ergebnisse kann von Person zu Person variieren, da die Ergebnisse für jeden Benutzer personalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-184">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="eb0f7-185">Keine dieser Kategorien hat immer Vorrang vor der anderen.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-185">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="eb0f7-186">**F: Wie lange dauert es, bis vom Administrator verwaltete Akronyme in Microsoft Search sichtbar sind, nachdem sie veröffentlicht wurden?**</span><span class="sxs-lookup"><span data-stu-id="eb0f7-186">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="eb0f7-187">**A:**  Es dauert bis zu drei Tage, bis Akronyme, die zum Status "Veröffentlicht" hinzugefügt wurden, in Microsoft Search verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-187">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="eb0f7-188">**F: Wie lösen Benutzer Antworten auf Akronyme aus?**</span><span class="sxs-lookup"><span data-stu-id="eb0f7-188">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="eb0f7-189">**A:** Um Antworten auf Akronyme zu erhalten, müssen Benutzer bestimmte Abfragemuster in ein [Bing-,](https://bing.com) [SharePoint-](https://products.office.com/sharepoint/collaboration)oder [Office 365-Suchfeld](https://Office.com)  eingeben.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-189">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="eb0f7-190">**F: Wie lange dauert es, bis vom System behandelte Akronyme angezeigt werden, nachdem Sie eine neue E-Mail oder ein neues Dokument erhalten oder gesendet haben?**</span><span class="sxs-lookup"><span data-stu-id="eb0f7-190">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="eb0f7-191">**A:** Es dauert bis zu sieben Tage, bis Akronyme in einer neuen E-Mail oder einem neuen Dokument in den Microsoft Search-Ergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-191">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="eb0f7-192">**F: Müssen Dokumente in einem bestimmten Format für das Mining vorliegen, um sie wieder auf ihre Bedürfnisse zu nehmen?**</span><span class="sxs-lookup"><span data-stu-id="eb0f7-192">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="eb0f7-193">**A:** Nein.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-193">**A:** No.</span></span> <span data-ttu-id="eb0f7-194">Wir unterstützen alle Dateitypen mit Ausnahme von Bild-, Ordner- und ZIP-Dateien.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-194">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="eb0f7-195">**F: Wird Microsoft Akronyme aus Dokumenten in allen Sprachen entdecken?**</span><span class="sxs-lookup"><span data-stu-id="eb0f7-195">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="eb0f7-196">**A:** Microsoft unterstützt nur das Mining aus Dokumenten in Englisch.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-196">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="eb0f7-197">Unterstützung für andere Sprachen wird in Phasen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-197">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="eb0f7-198">**F: Was passiert, wenn meine Organisation keine systemverkn tzten Akronyme anzeigen möchte? Kann ich die Anzeige dieses Akronymtyps in meinen Suchergebnissen beenden?**</span><span class="sxs-lookup"><span data-stu-id="eb0f7-198">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="eb0f7-199">**A:** Um die Anzeige systemverkn tzter Akronyme in suchergebnissen zu deaktivieren, erstellen Sie ein Kundensupportticket, indem Sie die Anweisungen unter "Kontaktieren des Support für [Geschäftsprodukte" befolgen.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)</span><span class="sxs-lookup"><span data-stu-id="eb0f7-199">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products).</span></span>
<span data-ttu-id="eb0f7-200">Nachdem Sie ein Supportticket erstellt haben, dauert es bis zu 48 Stunden, bis vom System behandelte Akronyme nicht mehr in den Suchergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eb0f7-200">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
