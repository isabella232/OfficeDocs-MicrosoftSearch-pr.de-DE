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
ms.openlocfilehash: d8b796e0ff61972f3e244c1a5af98319884769dc
ms.sourcegitcommit: ef1eb2bdf31dccd34f0fdc4aa7a0841ebd44f211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2019
ms.locfileid: "39663060"
---
# <a name="set-up-microsoft-search"></a><span data-ttu-id="318c1-103">Einrichten von Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="318c1-103">Set up Microsoft Search</span></span>

<span data-ttu-id="318c1-104">Die Microsoft-Suche bietet eine benutzerfreundliche Oberfläche, mit der Benutzerinformationen wie Dateien und Dokumente, interne Websites und Geschäftstools, Personen und Gruppen, Orte und Richtungen, Unterhaltungen und Antworten suchen können.</span><span class="sxs-lookup"><span data-stu-id="318c1-104">Microsoft Search provides a user-friendly interface to help users find information like files and documents, internal sites and business tools, people and groups, locations and directions, conversations and answers.</span></span> <span data-ttu-id="318c1-105">Dies geschieht durch sicheren Zugriff auf alle Datenquellen, einschließlich e-Mails, Dateien, SharePoint-Dateien, OneDrive-Inhalte und andere freigegebene Ressourcen sowie das Internet in der Organisation des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="318c1-105">It does this by securely accessing all data sources, including emails, files, SharePoint files, OneDrive content, and other shared resources as well as the internet in the user’s organization.</span></span>

<span data-ttu-id="318c1-106">Weitere Informationen zu den Microsoft Search-Features finden Sie unter [Übersicht über Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="318c1-106">To learn more about Microsoft Search features, see [Microsoft Search Overview](overview-microsoft-search.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="318c1-107">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="318c1-107">Get Started</span></span>

<span data-ttu-id="318c1-108">Microsoft Search ist im Rahmen von Microsoft 365 standardmäßig für alle Microsoft-Apps aktiviert, die das Feature unterstützen.</span><span class="sxs-lookup"><span data-stu-id="318c1-108">Microsoft Search is turned on by default for all Microsoft apps that supports it, as a part of Microsoft 365.</span></span> <span data-ttu-id="318c1-109">Es ist kein Setup erforderlich, aber Sie können die allgemeine Microsoft-Suchumgebung durch einige grundlegende administrative Aufgaben verbessern.</span><span class="sxs-lookup"><span data-stu-id="318c1-109">There is no setup required, but you can improve the overall Microsoft Search experience through some basic administrative tasks.</span></span>

<span data-ttu-id="318c1-110">Sie können Microsoft Search vom Microsoft 365 Admin Center aus verwalten.</span><span class="sxs-lookup"><span data-stu-id="318c1-110">You manage Microsoft Search from Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="318c1-111">Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Microsoft Search**.</span><span class="sxs-lookup"><span data-stu-id="318c1-111">In Microsoft 365 admin center, go to **Settings** > **Microsoft Search**.</span></span>

<span data-ttu-id="318c1-112">**Bitte beachten:** Wenn Microsoft Search unter **Einstellungen** NICHT angezeigt wird, aktivieren Sie den Schalter für **Preview testen** (Try the preview) in der rechten oberen Ecke einer beliebigen Admin Center-Seite.</span><span class="sxs-lookup"><span data-stu-id="318c1-112">**Note:** If you are NOT seeing Microsoft Search under **Settings**, turn on the **Try the preview** switch in the right top corner of any admin center page.</span></span>

<span data-ttu-id="318c1-113">Als Administrator sollten Sie einige Dinge berücksichtigen, durch die Sie die Microsoft Search-Nutzererfahrung in Ihrer Organisation effizient und benutzerfreundlich gestalten können.</span><span class="sxs-lookup"><span data-stu-id="318c1-113">As an admin you should consider a few things that can make the Microsoft Search experience efficient and user friendly in your organization.</span></span>

## <a name="step-1-assign-search-admin-and-search-editor"></a><span data-ttu-id="318c1-114">Schritt 1: Zuweisen von Such-admin und Such-Editor</span><span class="sxs-lookup"><span data-stu-id="318c1-114">Step 1: Assign Search admin and Search editor</span></span>

<span data-ttu-id="318c1-115">In Microsoft Search können Sie die Sucheinstellungen und Inhalte Ihrer Organisation mitverwalten, indem Sie den Benutzern diese Rollen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="318c1-115">In Microsoft Search, you can manage your organization’s search settings and content by assigning these roles to users:</span></span>

1. <span data-ttu-id="318c1-116">**Suchadministrator**: Diese Rolle kann Suchergebnisinhalte erstellen und verwalten sowie Abfrageeinstellungen für verbesserte Suchergebnisse innerhalb der Organisation definieren.</span><span class="sxs-lookup"><span data-stu-id="318c1-116">**Search admin:** This role can create and manage search result content and define query settings for improved search results within the organization.</span></span> <span data-ttu-id="318c1-117">Der Suchadministrator verwaltet die Microsoft Search-Konfiguration und kann alle Inhaltsverwaltungsaufgaben ausführen, die ein Such-Editor durchführen darf.</span><span class="sxs-lookup"><span data-stu-id="318c1-117">Search admin manages the Microsoft Search configuration and can perform all of the content-management tasks a Search editor can.</span></span>
2. <span data-ttu-id="318c1-118">**Such-Editor:** Erstellt, verwaltet und löscht Inhalte für Microsoft Search im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="318c1-118">**Search editor:** Creates, manages, and deletes content for Microsoft Search in the Microsoft 365 admin center.</span></span> <span data-ttu-id="318c1-119">Diese Rolle kann redaktionelle Inhalte wie häufig gestellte Fragen und Antworten, wichtige Orte, häufig gesuchte und genutzte Websites und Apps erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="318c1-119">This role can create and manage editorial content, such as frequently asked questions and answers, important places and locations, frequently searched and used sites and apps.</span></span>

<span data-ttu-id="318c1-120">Aktuell müssen die Rollen „Suchadministrator“ und „Such-Editor“ von einem globalen Administrator zugewiesen werden. Weitere Informationen finden Sie unter [Administrator-Rollen zuweisen](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide) (Assign admin roles).</span><span class="sxs-lookup"><span data-stu-id="318c1-120">Currently, the Search admin and Search editor roles must be assigned by a global admin. For more information, see [Assign admin roles](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>

<span data-ttu-id="318c1-121">Microsoft Search-Administratoren können die Suchoberfläche für Endbenutzer direkt beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="318c1-121">Search administrators directly influence the search experience for end users.</span></span> <span data-ttu-id="318c1-122">Dazu gehört die Auswahl der Ergebnistypen, die Sie Ihren Benutzern zur Verfügung stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="318c1-122">This includes choosing the types of results you want to surface to your users.</span></span> <span data-ttu-id="318c1-123">Es kann für eine Person schwierig sein, maßgebliche Inhalte zu vielen verschiedenen Themen, nach denen Benutzer in einer Organisation suchen, auszuwählen und zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="318c1-123">It may be difficult for one person to choose and create authoritative content on many different topics that users search for in an organization.</span></span> <span data-ttu-id="318c1-124">Es wird empfohlen, dass Sie die Expertise und das Wissen von Experten (SMEs) und anderen Benutzern nutzen, indem Sie sie als Such-Editoren hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="318c1-124">We recommend that you leverage the expertise and knowledge of subject matter experts (SME) and other users by adding them as Search editors.</span></span>

## <a name="step-2-create-answers"></a><span data-ttu-id="318c1-125">Schritt 2: Antworten erstellen</span><span class="sxs-lookup"><span data-stu-id="318c1-125">Step 2: Create answers</span></span>

<span data-ttu-id="318c1-126">Microsoft Search stellt Administratoren Tools zur Verfügung, mit denen sie eine robuste Suchoberfläche für ihre Benutzer erstellen können.</span><span class="sxs-lookup"><span data-stu-id="318c1-126">Microsoft Search provides administrators with tools that they can use to build a robust search experience for their users.</span></span> <span data-ttu-id="318c1-127">In der Microsoft-Suche verfügen Administratoren über drei verschiedene Suchinhalte, die Sie für eine bessere Suchumgebung erstellen und die "Auffindbarkeit" des Inhalts verbessern können:</span><span class="sxs-lookup"><span data-stu-id="318c1-127">In Microsoft Search, administrators have three different search contents that they can create for a better search experience and to improve the "findability" of content:</span></span>

<span data-ttu-id="318c1-128">Lesezeichen sind die am häufigsten verwendeten Antworttypen.</span><span class="sxs-lookup"><span data-stu-id="318c1-128">Bookmarks are the most commonly used answer type.</span></span> <span data-ttu-id="318c1-129">Sie fördern die bestmöglichen Ergebnisse für die Abfragen Ihrer Benutzer oben in den Suchergebnissen und erleichtern Ihren Benutzern die Suche nach dem, was Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="318c1-129">They promote the best possible results for your users’ queries to the top of the search results and make it easy for your users to find what they are looking for.</span></span>
<span data-ttu-id="318c1-130">Informationsinhalte, die für alle Benutzer verfügbar sind; beispielsweise Informationen über das Unternehmen, Hilfe für Windows und Office-Apps usw. Inhalte, nach denen Personen in der Organisation im Allgemeinen in ihrer täglichen Arbeit suchen.</span><span class="sxs-lookup"><span data-stu-id="318c1-130">Informational content that is available for everyone; for example, information about the company, help for Windows and Office apps, etc. Content that people in the organization generally search for in their day-to-day work.</span></span> <span data-ttu-id="318c1-131">Allgemeine arbeitsbezogene Suchen sind z. B. Mitarbeitervergütungen, Arbeitszeit- und Spesenabrechnung, Übermittlung von Bestellungen und Hilfe von IT-Diensten.</span><span class="sxs-lookup"><span data-stu-id="318c1-131">Common work-related searches include employee benefits, time and expense reporting, submitting purchase orders, and getting help from IT services.</span></span>

<span data-ttu-id="318c1-132">Informationen zum Erstellen und Verwalten von Antworten finden Sie unter [Planen von Inhalten](plan-your-content.md).</span><span class="sxs-lookup"><span data-stu-id="318c1-132">For creating and managing answers, see [Plan your content](plan-your-content.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="318c1-133">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="318c1-133">Next steps</span></span>

<span data-ttu-id="318c1-134">Wenn Sie mehr darüber erfahren möchten, wie Ihre Benutzer die Microsoft-Suche verwenden, lesen Sie die folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="318c1-134">If you'd like to learn more about how your users will use Microsoft Search, see the following articles:</span></span>

- [<span data-ttu-id="318c1-135">Finden erforderlicher Informationen in Office mit Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="318c1-135">Find what you need with Microsoft Search in Office</span></span>](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446)
- [<span data-ttu-id="318c1-136">Office 365-Schulungscenter</span><span class="sxs-lookup"><span data-stu-id="318c1-136">Office 365 Training Center</span></span>](https://support.office.com/office-training-center)
- [<span data-ttu-id="318c1-137">Microsoft Search Center</span><span class="sxs-lookup"><span data-stu-id="318c1-137">Microsoft Search Center</span></span>](https://support.office.com/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc)
