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
ms.openlocfilehash: 3ff2aabae4e09170b6b0380d520bfc620d5de5d8
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626255"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="6da99-103">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="6da99-103">Frequently asked questions</span></span>

<span data-ttu-id="6da99-104">Nachfolgend finden Sie eine Liste der am häufigsten gestellten Fragen.</span><span class="sxs-lookup"><span data-stu-id="6da99-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="6da99-105">Ihre Frage wurde hier nicht beantwortet?</span><span class="sxs-lookup"><span data-stu-id="6da99-105">Don't see your question answered here?</span></span> <span data-ttu-id="6da99-106">Stellen Sie Ihre Frage im Feedback zu diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="6da99-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="6da99-107">Wird das Verstehen von erweiterten Abfragen unterstützt?</span><span class="sxs-lookup"><span data-stu-id="6da99-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="6da99-p102">Ja, bei umfangreicheren Ausdrücken analysiert Microsoft Search die Abfrageabsicht. Dieses Feature verwendet KI, um häufig von Benutzern hinzugefügte, überflüssige Ausdrücke zu lernen, die für die Absicht der Suche nicht relevant sind. Wenn ein Benutzer z. B. die Suche "Gib mir bitte Informationen dazu, wie ich mein Kennwort ändern kann" eingibt, werden die weniger wichtigen Wörter aus der Abfrage entfernt. Die Abfrage wird dann basierend auf den relevanten Wörtern, wie z. B. "Kennwort ändern", durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="6da99-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for 'tell me more about how to change my password please' we extract the less important words from the query and trigger based on the relevant ones like 'change password.'</span></span>
  
<span data-ttu-id="6da99-111">Dieses Feature setzt im Admin Center festgelegte Schlüsselwörter nicht außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="6da99-111">This feature will not override keywords set in the admin center.</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="6da99-112">Können Sie nach lokalen Dateien suchen?</span><span class="sxs-lookup"><span data-stu-id="6da99-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="6da99-113">Ja.</span><span class="sxs-lookup"><span data-stu-id="6da99-113">Yes.</span></span> <span data-ttu-id="6da99-114">Sie können lokale SharePoint-Dateien durchsuchen, wenn Sie über eine Hybridbereitstellung von SharePoint verfügen.</span><span class="sxs-lookup"><span data-stu-id="6da99-114">You can search on-premises SharePoint files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="6da99-115">Wie kann ich Bing als Standardsuchmaschine für Personen in meiner Organisation festlegen?</span><span class="sxs-lookup"><span data-stu-id="6da99-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="6da99-116">Hier finden Sie die Anweisungen zum Festlegen der Standardsuchmaschine, der Standardstartseite und des Standardbrowsers, um Ihren Benutzern die optimale Erfahrung mit Microsoft Search in Bing zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="6da99-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in Bing:</span></span>

- [<span data-ttu-id="6da99-117">Festlegen von Edge als Standardbrowser</span><span class="sxs-lookup"><span data-stu-id="6da99-117">Set Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="6da99-118">Festlegen von Bing als Standardsuchmaschine</span><span class="sxs-lookup"><span data-stu-id="6da99-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="6da99-119">Festlegen von Bing.com als Startseite des Unternehmens</span><span class="sxs-lookup"><span data-stu-id="6da99-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="6da99-120">Wie werden meine Suchergebnisse geschützt?</span><span class="sxs-lookup"><span data-stu-id="6da99-120">How are my search results protected?</span></span>

<span data-ttu-id="6da99-121">Für den Zugriff auf Ergebnisse aus der vertrauenswürdigen Cloud ist Azure Active Directory-Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6da99-121">We require Azure Active Directory (AAD) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="6da99-122">Authentifizierten Benutzern werden nur Inhalte angezeigt, auf die sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="6da99-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="6da99-123">Suchabfragen werden anonymisiert und Protokolle vom Datenverkehr öffentlicher Bing-Suchen getrennt.</span><span class="sxs-lookup"><span data-stu-id="6da99-123">Search queries are de-identified and logs are separated from public Bing search traffic.</span></span> <span data-ttu-id="6da99-124">Ein solcher Grad an Schutz steht sonst in der Branche nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6da99-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="6da99-125">Kann ich in Verbundorganisationen suchen?</span><span class="sxs-lookup"><span data-stu-id="6da99-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="6da99-126">Nein.</span><span class="sxs-lookup"><span data-stu-id="6da99-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a><span data-ttu-id="6da99-127">Wo erhalte ich Informationen zu Office 365- und Microsoft 365 -Compliance-Ebenen und -Kategorien?</span><span class="sxs-lookup"><span data-stu-id="6da99-127">Where can I get info about Office 365 and Microsoft 365 compliance tiers and categories?</span></span>

<span data-ttu-id="6da99-128">Details finden Sie in der [Compliance-Framework für Branchenstandards und gesetzliche Vorschriften](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF-Download).</span><span class="sxs-lookup"><span data-stu-id="6da99-128">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="6da99-129">Können Benutzer mit Ihrem Geschäfts-, Schul- oder Unikonto Microsoft Rewards-Punkte erwerben?</span><span class="sxs-lookup"><span data-stu-id="6da99-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="6da99-130">Microsoft Search setzt voraus, dass Unternehmensbenutzer sich mit einem Geschäfts-, Schul- oder Unikonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="6da99-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="6da99-131">Mit diesen Konten können sich Benutzer aber nicht beim Microsoft Rewards-Programm anmelden oder daran teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="6da99-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="6da99-132">Allerdings gibt es einen Fall, bei dem Unternehmensbenutzer möglicherweise sehen, dass Prämienpunkte anfallen.</span><span class="sxs-lookup"><span data-stu-id="6da99-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="6da99-133">Dies kann vorkommen, wenn ein Microsoft Search-Benutzer über ein Rewards-Konto verfügt, das mit einem <a href="https://www.microsoft.com/en-us/welcome?rtc=1">Microsoft-Konto</a> erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6da99-133">This can happen when a Microsoft Search user has a Rewards account that was created with a <a href="https://www.microsoft.com/en-us/welcome?rtc=1">Microsoft account</a>.</span></span> <span data-ttu-id="6da99-134">(Die mit einem Microsoft-Konto verknüpfte E-Mail-Adresse kann von Outlook.com, Hotmail.com, Gmail, Yahoo oder anderen Anbietern stammen.) Wenn Benutzer sich bei derselben Browsersitzung abwechselnd mit ihrem Geschäfts-, Schul- oder Unikonto und ihrem Microsoft-Konto anmelden, werden möglicherweise Punkte auf dem Rewards-Konto angesammelt.</span><span class="sxs-lookup"><span data-stu-id="6da99-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="6da99-135">Benutzer können das Ansammeln von Punkten während der Suche mit Microsoft Search beenden, indem sie ihre Cookies löschen.</span><span class="sxs-lookup"><span data-stu-id="6da99-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span> 

