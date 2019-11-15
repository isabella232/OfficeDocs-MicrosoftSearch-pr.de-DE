---
title: Einrichten von Microsoft Search
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Erstmaliges Einrichten von Microsoft Search.
ms.openlocfilehash: 94ee7ece8a56d599778b151d5b836240d8832762
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626909"
---
# <a name="set-up-microsoft-search"></a><span data-ttu-id="3c83c-103">Einrichten von Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="3c83c-103">Set up Microsoft Search</span></span>

<span data-ttu-id="3c83c-104">Microsoft Search bietet eine benutzerfreundliche Oberfläche, die Benutzern das Auffinden von Informationen erleichtert (z. B. Dateien und Dokumente, interne Websites und Unternehmenstools, Personen und Gruppen, Orte und Wegbeschreibungen, Gespräche und Antworten), indem sie in der Organisation des Benutzers sicher auf alle Datenquellen, einschließlich E-Mails, Dateien, SharePoint-Dateien, OneDrive-Inhalte und andere gemeinsam genutzte Ressourcen sowie auf das Internet zugreift.</span><span class="sxs-lookup"><span data-stu-id="3c83c-104">Microsoft Search provides a user-friendly interface to help users find information, like files and documents, internal sites and business tools, people and groups, locations and directions, conversations and answers by securely accessing all data sources, including emails, files, SharePoint files, OneDrive content, and other shared resources as well as the internet in the user’s organization.</span></span>

<span data-ttu-id="3c83c-105">Weitere Informationen zu den Microsoft Search-Features finden Sie unter [Übersicht über Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="3c83c-105">To learn more about Microsoft Search features, see [Microsoft Search Overview](overview-microsoft-search.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="3c83c-106">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="3c83c-106">Get Started</span></span>

<span data-ttu-id="3c83c-107">Microsoft Search ist im Rahmen von Microsoft 365 standardmäßig für alle Microsoft-Apps aktiviert, die das Feature unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3c83c-107">Microsoft Search is turned on by default for all Microsoft apps that supports it, as a part of Microsoft 365.</span></span> <span data-ttu-id="3c83c-108">Es ist kein Setup erforderlich, aber Sie können die allgemeine Microsoft-Suchumgebung durch einige grundlegende administrative Aufgaben verbessern.</span><span class="sxs-lookup"><span data-stu-id="3c83c-108">There is no setup required,but you can improve the overall Microsoft Search experience through some basic administrative tasks.</span></span>

<span data-ttu-id="3c83c-109">Sie können Microsoft Search vom Microsoft 365 Admin Center aus verwalten.</span><span class="sxs-lookup"><span data-stu-id="3c83c-109">You manage Microsoft Search from Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="3c83c-110">Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Microsoft Search**.</span><span class="sxs-lookup"><span data-stu-id="3c83c-110">In Microsoft 365 admin center, go to **Settings** > **Microsoft Search**.</span></span>

<span data-ttu-id="3c83c-111">**Bitte beachten:** Wenn Microsoft Search unter **Einstellungen** NICHT angezeigt wird, aktivieren Sie den Schalter für **Preview testen** (Try the preview) in der rechten oberen Ecke einer beliebigen Admin Center-Seite.</span><span class="sxs-lookup"><span data-stu-id="3c83c-111">**Note:** If you are NOT seeing Microsoft Search under **Settings**, turn on the **Try the preview** switch in the right top corner of any admin center page.</span></span>

<span data-ttu-id="3c83c-112">Als Administrator sollten Sie einige Dinge berücksichtigen, durch die Sie die Microsoft Search-Nutzererfahrung in Ihrer Organisation effizient und benutzerfreundlich gestalten können.</span><span class="sxs-lookup"><span data-stu-id="3c83c-112">As an admin you should consider a few things that can make the Microsoft Search experience efficient and user friendly in your organization.</span></span>

## <a name="step-1-assign-search-admin-and-search-editor"></a><span data-ttu-id="3c83c-113">Schritt 1: Zuweisen von Such-admin und Such-Editor</span><span class="sxs-lookup"><span data-stu-id="3c83c-113">Step 1: Assign Search admin and Search editor</span></span>

<span data-ttu-id="3c83c-114">In Microsoft Search können Sie die Sucheinstellungen und Inhalte Ihrer Organisation mitverwalten, indem Sie den Benutzern diese Rollen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="3c83c-114">In Microsoft Search, you can manage your organization’s search settings and content by assigning these roles to users:</span></span>

1. <span data-ttu-id="3c83c-115">**Suchadministrator**: Diese Rolle kann Suchergebnisinhalte erstellen und verwalten sowie Abfrageeinstellungen für verbesserte Suchergebnisse innerhalb der Organisation definieren.</span><span class="sxs-lookup"><span data-stu-id="3c83c-115">**Search admin:** This role can create and manage search result content and define query settings for improved search results within the organization.</span></span> <span data-ttu-id="3c83c-116">Der Suchadministrator verwaltet die Microsoft Search-Konfiguration und kann alle Inhaltsverwaltungsaufgaben ausführen, die ein Such-Editor durchführen darf.</span><span class="sxs-lookup"><span data-stu-id="3c83c-116">Search admin manages the Microsoft Search configuration and can perform all of the content-management tasks a Search editor can.</span></span>
2. <span data-ttu-id="3c83c-117">**Such-Editor:** Erstellt, verwaltet und löscht Inhalte für Microsoft Search im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="3c83c-117">**Search editor:** Creates, manages, and deletes content for Microsoft Search in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3c83c-118">Diese Rolle kann redaktionelle Inhalte wie häufig gestellte Fragen und Antworten, wichtige Orte, häufig gesuchte und genutzte Websites und Apps erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="3c83c-118">This role can create and manage editorial content, such as frequently asked questions and answers, important places and locations, frequently searched and used sites and apps.</span></span>

<span data-ttu-id="3c83c-119">Aktuell müssen die Rollen „Suchadministrator“ und „Such-Editor“ von einem globalen Administrator zugewiesen werden. Weitere Informationen finden Sie unter [Administrator-Rollen zuweisen](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide) (Assign admin roles).</span><span class="sxs-lookup"><span data-stu-id="3c83c-119">Currently, the Search admin and Search editor roles must be assigned by a global admin. For more information, see [Assign admin roles](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>

<span data-ttu-id="3c83c-120">Microsoft Search-Administratoren können die Suchoberfläche für Endbenutzer direkt beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="3c83c-120">Search administrators directly influence the search experience for end users.</span></span> <span data-ttu-id="3c83c-121">Dazu gehört die Auswahl der Ergebnistypen, die Sie Ihren Benutzern zur Verfügung stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="3c83c-121">This includes choosing the types of results you want to surface to your users.</span></span> <span data-ttu-id="3c83c-122">Es kann für eine Person schwierig sein, maßgebliche Inhalte zu vielen verschiedenen Themen, nach denen Benutzer in einer Organisation suchen, auszuwählen und zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c83c-122">It may be difficult for one person to choose and create authoritative content on many different topics that users search for in an organization.</span></span> <span data-ttu-id="3c83c-123">Es wird empfohlen, dass Sie die Expertise und das Wissen von Experten (SMEs) und anderen Benutzern nutzen, indem Sie sie als Such-Editoren hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3c83c-123">We recommend that you leverage the expertise and knowledge of subject matter experts (SME) and other users by adding them as Search editors.</span></span>

## <a name="step-2-create-answers"></a><span data-ttu-id="3c83c-124">Schritt 2: Antworten erstellen</span><span class="sxs-lookup"><span data-stu-id="3c83c-124">Step 2: Create answers</span></span>

<span data-ttu-id="3c83c-125">Microsoft Search stellt Administratoren Tools zur Verfügung, mit denen sie eine robuste Suchoberfläche für ihre Benutzer erstellen können.</span><span class="sxs-lookup"><span data-stu-id="3c83c-125">Microsoft Search provides administrators with tools that they can use to build a robust search experience for their users.</span></span> <span data-ttu-id="3c83c-126">In der Microsoft-Suche verfügen Administratoren über drei verschiedene Suchinhalte, die Sie für eine bessere Suchumgebung erstellen und die "Auffindbarkeit" des Inhalts verbessern können:</span><span class="sxs-lookup"><span data-stu-id="3c83c-126">In Microsoft Search, administrators have three different search contents that they can create for a better search experience and to improve the "findability" of content:</span></span>

<span data-ttu-id="3c83c-127">Lesezeichen sind die am häufigsten verwendeten Antworttypen.</span><span class="sxs-lookup"><span data-stu-id="3c83c-127">Bookmarks are the most commonly used answer type.</span></span> <span data-ttu-id="3c83c-128">Sie fördern die bestmöglichen Ergebnisse für die Abfragen Ihrer Benutzer oben in den Suchergebnissen und erleichtern Ihren Benutzern die Suche nach dem, was Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="3c83c-128">They promote the best possible results for your users’ queries to the top of the search results and make it easy for your users to find what they are looking for.</span></span>
<span data-ttu-id="3c83c-129">Informationsinhalte, die für alle Benutzer verfügbar sind; beispielsweise Informationen über das Unternehmen, Hilfe für Windows und Office-Apps usw. Inhalte, nach denen Personen in der Organisation im Allgemeinen in ihrer täglichen Arbeit suchen.</span><span class="sxs-lookup"><span data-stu-id="3c83c-129">Informational content that is available for everyone; for example, information about the company, help for Windows and Office apps, etc. Content that people in the organization generally search for in their day-to-day work.</span></span> <span data-ttu-id="3c83c-130">Allgemeine arbeitsbezogene Suchen sind z. B. Mitarbeitervergütungen, Arbeitszeit- und Spesenabrechnung, Übermittlung von Bestellungen und Hilfe von IT-Diensten.</span><span class="sxs-lookup"><span data-stu-id="3c83c-130">Common work-related searches include employee benefits, time and expense reporting, submitting purchase orders, and getting help from IT services.</span></span>

<span data-ttu-id="3c83c-131">Informationen zum Erstellen und Verwalten von Antworten finden Sie unter [Planen von Inhalten](plan-your-content.md).</span><span class="sxs-lookup"><span data-stu-id="3c83c-131">For creating and managing answers, see [Plan your content](plan-your-content.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3c83c-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3c83c-132">Next steps</span></span>

<span data-ttu-id="3c83c-133">Wenn Sie mehr darüber erfahren möchten, wie Ihre Benutzer die Microsoft-Suche verwenden, lesen Sie die folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="3c83c-133">If you'd like to learn more about how your users will use Microsoft Search, see the following articles:</span></span>

- [<span data-ttu-id="3c83c-134">Finden erforderlicher Informationen in Office mit Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="3c83c-134">Find what you need with Microsoft Search in Office</span></span>](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446)
- [<span data-ttu-id="3c83c-135">Office 365-Schulungscenter</span><span class="sxs-lookup"><span data-stu-id="3c83c-135">Office 365 Training Center</span></span>](https://support.office.com/office-training-center)
- [<span data-ttu-id="3c83c-136">Microsoft Search Center</span><span class="sxs-lookup"><span data-stu-id="3c83c-136">Microsoft Search Center</span></span>](https://support.office.com/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc)
