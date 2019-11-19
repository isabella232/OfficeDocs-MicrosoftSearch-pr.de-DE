---
title: FAQs
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Erhalten Sie Antworten auf häufig gestellte Fragen zur Unternehmenssuche und zu Microsoft Search
ms.openlocfilehash: edfb8346263d60184d8655afa24118ed4b3e3bca
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699793"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="3483f-103">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="3483f-103">Frequently asked questions</span></span>

<span data-ttu-id="3483f-104">Nachfolgend finden Sie eine Liste der am häufigsten gestellten Fragen.</span><span class="sxs-lookup"><span data-stu-id="3483f-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="3483f-105">Ihre Frage wurde hier nicht beantwortet?</span><span class="sxs-lookup"><span data-stu-id="3483f-105">Don't see your question answered here?</span></span> <span data-ttu-id="3483f-106">Stellen Sie Ihre Frage im Feedback zu diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="3483f-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="3483f-107">Wird das Verstehen von erweiterten Abfragen unterstützt?</span><span class="sxs-lookup"><span data-stu-id="3483f-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="3483f-p102">Ja, die Microsoft-Suche analysiert Abfrage Absicht aus größeren Ausdrücken. Dieses Feature verwendet AI, um allgemeine überflüssige Ausdrücke zu erfahren, die Benutzer zu Ihren Abfragen hinzufügen, die sich nicht auf die suchabsicht auswirken. Wenn ein Benutzer beispielsweise nach " *Weitere Informationen" zum Ändern des Kennworts*sucht, extrahieren wir die weniger wichtigen Wörter aus der Abfrage und dem Auslöser basierend auf den entsprechenden wie das *Kennwort ändern*.</span><span class="sxs-lookup"><span data-stu-id="3483f-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for *tell me more about how to change my password please*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="3483f-111">Dieses Feature überschreibt keine Stichwörter, die im Microsoft 365 [Admin Center](https://admin.microsoft.com)festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="3483f-111">This feature won't override keywords set in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="3483f-112">Können Sie nach lokalen Dateien suchen?</span><span class="sxs-lookup"><span data-stu-id="3483f-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="3483f-113">Ja.</span><span class="sxs-lookup"><span data-stu-id="3483f-113">Yes.</span></span> <span data-ttu-id="3483f-114">Sie können lokale [SharePoint](http://sharepoint.com/) -Dateien durchsuchen, wenn Sie über eine hybridbereitstellung von SharePoint verfügen.</span><span class="sxs-lookup"><span data-stu-id="3483f-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="3483f-115">Wie kann ich Bing als Standardsuchmaschine für Personen in meiner Organisation festlegen?</span><span class="sxs-lookup"><span data-stu-id="3483f-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="3483f-116">Hier finden Sie die Anweisungen zum Festlegen der standardmäßigen Suchmaschine, der Standardstartseite und des Standardbrowsers, damit Ihre Benutzer die besten Erfahrungen mit der Microsoft-Suche in [Bing](https://Bing.com)erhalten:</span><span class="sxs-lookup"><span data-stu-id="3483f-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="3483f-117">Festlegen von Microsoft Edge als Standardbrowser</span><span class="sxs-lookup"><span data-stu-id="3483f-117">Set Microsoft Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="3483f-118">Festlegen von Bing als Standardsuchmaschine</span><span class="sxs-lookup"><span data-stu-id="3483f-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="3483f-119">Festlegen von Bing.com als Startseite des Unternehmens</span><span class="sxs-lookup"><span data-stu-id="3483f-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="3483f-120">Wie werden meine Suchergebnisse geschützt?</span><span class="sxs-lookup"><span data-stu-id="3483f-120">How are my search results protected?</span></span>

<span data-ttu-id="3483f-121">Für den Zugriff auf Ergebnisse aus der vertrauenswürdigen Cloud ist die [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) -Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3483f-121">We require [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="3483f-122">Authentifizierten Benutzern werden nur Inhalte angezeigt, auf die sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="3483f-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="3483f-123">Suchabfragen werden nicht identifiziert, und Protokolle werden vom öffentlichen [Bing](https://Bing.com) -Such Datenverkehr getrennt.</span><span class="sxs-lookup"><span data-stu-id="3483f-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic.</span></span> <span data-ttu-id="3483f-124">Ein solcher Grad an Schutz steht sonst in der Branche nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3483f-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="3483f-125">Kann ich in Verbundorganisationen suchen?</span><span class="sxs-lookup"><span data-stu-id="3483f-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="3483f-126">Nein.</span><span class="sxs-lookup"><span data-stu-id="3483f-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a><span data-ttu-id="3483f-127">Wo erhalte ich Informationen zu Office 365- und Microsoft 365 -Compliance-Ebenen und -Kategorien?</span><span class="sxs-lookup"><span data-stu-id="3483f-127">Where can I get info about Office 365 and Microsoft 365 compliance tiers and categories?</span></span>

<span data-ttu-id="3483f-128">Details finden Sie in der [Compliance-Framework für Branchenstandards und gesetzliche Vorschriften](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF-Download).</span><span class="sxs-lookup"><span data-stu-id="3483f-128">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="3483f-129">Können Benutzer mit Ihrem Geschäfts-, Schul- oder Unikonto Microsoft Rewards-Punkte erwerben?</span><span class="sxs-lookup"><span data-stu-id="3483f-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="3483f-130">Microsoft Search setzt voraus, dass Unternehmensbenutzer sich mit einem Geschäfts-, Schul- oder Unikonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="3483f-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="3483f-131">Mit diesen Konten können sich Benutzer aber nicht beim Microsoft Rewards-Programm anmelden oder daran teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="3483f-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="3483f-132">Allerdings gibt es einen Fall, bei dem Unternehmensbenutzer möglicherweise sehen, dass Prämienpunkte anfallen.</span><span class="sxs-lookup"><span data-stu-id="3483f-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="3483f-133">Dies kann vorkommen, wenn ein Microsoft Search-Benutzer über ein Rewards-Konto verfügt, das mit einem <a href="https://www.microsoft.com/welcome?rtc=1">Microsoft-Konto</a> erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3483f-133">This can happen when a Microsoft Search user has a Rewards account that was created with a <a href="https://www.microsoft.com/welcome?rtc=1">Microsoft account</a>.</span></span> <span data-ttu-id="3483f-134">(Die mit einem Microsoft-Konto verknüpfte E-Mail-Adresse kann von Outlook.com, Hotmail.com, Gmail, Yahoo oder anderen Anbietern stammen.) Wenn Benutzer sich bei derselben Browsersitzung abwechselnd mit ihrem Geschäfts-, Schul- oder Unikonto und ihrem Microsoft-Konto anmelden, werden möglicherweise Punkte auf dem Rewards-Konto angesammelt.</span><span class="sxs-lookup"><span data-stu-id="3483f-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="3483f-135">Benutzer können das Ansammeln von Punkten während der Suche mit Microsoft Search beenden, indem sie ihre Cookies löschen.</span><span class="sxs-lookup"><span data-stu-id="3483f-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span> 

