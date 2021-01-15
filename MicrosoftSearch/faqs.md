---
title: FAQs
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Erhalten Sie Antworten auf häufig gestellte Fragen zur Unternehmenssuche und zu Microsoft Search
ms.openlocfilehash: abaa1a232b08ba586dd6cd777f7e54c323159dee
ms.sourcegitcommit: aa7774d2bdff2bd9e1b7f51fcda90fa6b0c3a5ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867378"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="74328-103">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="74328-103">Frequently asked questions</span></span>

<span data-ttu-id="74328-104">Nachfolgend finden Sie eine Liste der am häufigsten gestellten Fragen.</span><span class="sxs-lookup"><span data-stu-id="74328-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="74328-105">Ihre Frage wurde hier nicht beantwortet?</span><span class="sxs-lookup"><span data-stu-id="74328-105">Don't see your question answered here?</span></span> <span data-ttu-id="74328-106">Stellen Sie Ihre Frage im Feedback zu diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="74328-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="74328-107">Wird das Verstehen von erweiterten Abfragen unterstützt?</span><span class="sxs-lookup"><span data-stu-id="74328-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="74328-p102">Ja, Microsoft Search analysiert die Abfrageabsicht aus größeren Ausdrücken. Dieses Feature verwendet KI, um allgemeine überflüssige Ausdrücke zu erlernen, die Benutzer zu ihren Abfragen hinzufügen, die sich nicht auf ihre Suchabsicht auswirken. Wenn ein Benutzer z. B. nach informationen zum Ändern meines Kennworts *sucht,* extrahieren wir die weniger wichtigen Wörter aus der Abfrage und lösen sie basierend auf den relevanten Wörtern wie Kennwortänderung *aus.*</span><span class="sxs-lookup"><span data-stu-id="74328-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for *tell me more about how to change my password*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="74328-111">Mit diesem Feature werden im [Microsoft 365 Admin Center](https://admin.microsoft.com)festgelegte Schlüsselwörter nicht überschrieben.</span><span class="sxs-lookup"><span data-stu-id="74328-111">This feature won't override keywords set in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="74328-112">Können Sie nach lokalen Dateien suchen?</span><span class="sxs-lookup"><span data-stu-id="74328-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="74328-113">Ja.</span><span class="sxs-lookup"><span data-stu-id="74328-113">Yes.</span></span> <span data-ttu-id="74328-114">Sie können lokale [SharePoint-Dateien](http://sharepoint.com/) durchsuchen, wenn Sie über eine Hybridbereitstellung von SharePoint verfügen.</span><span class="sxs-lookup"><span data-stu-id="74328-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="74328-115">Wie kann ich Bing als Standardsuchmaschine für Personen in meiner Organisation festlegen?</span><span class="sxs-lookup"><span data-stu-id="74328-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="74328-116">Hier sind die Anweisungen zum Festlegen der Standardsuchmaschine, der Standardhomepage und des Standardbrowsers, um Ihren Benutzern die beste Erfahrung mit Microsoft Search in [Bing zu bieten:](https://Bing.com)</span><span class="sxs-lookup"><span data-stu-id="74328-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="74328-117">Festlegen von Microsoft Edge als Standardbrowser</span><span class="sxs-lookup"><span data-stu-id="74328-117">Set Microsoft Edge as your default browser</span></span>](/deployedge/edge-default-browser)
- [<span data-ttu-id="74328-118">Festlegen von Bing als Standardsuchmaschine</span><span class="sxs-lookup"><span data-stu-id="74328-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="74328-119">Festlegen von Bing.com als Startseite des Unternehmens</span><span class="sxs-lookup"><span data-stu-id="74328-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="74328-120">Wie werden meine Suchergebnisse geschützt?</span><span class="sxs-lookup"><span data-stu-id="74328-120">How are my search results protected?</span></span>

<span data-ttu-id="74328-121">Für den Zugriff auf Ergebnisse aus der vertrauenswürdigen Cloud ist die [Azure Active](https://docs.microsoft.com/azure/active-directory/) Directory-Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="74328-121">We require [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="74328-122">Authentifizierten Benutzern werden nur Inhalte angezeigt, auf die sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="74328-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="74328-123">Suchabfragen werden nicht identifiziert, und Protokolle werden vom öffentlichen [Bing](https://Bing.com) -Suchdatenverkehr getrennt, wenn Sie Microsoft Search in Bing verwenden.</span><span class="sxs-lookup"><span data-stu-id="74328-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic when you use Microsoft Search in Bing.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="74328-124">Kann ich in Verbundorganisationen suchen?</span><span class="sxs-lookup"><span data-stu-id="74328-124">Can I search across federated organizations?</span></span>

<span data-ttu-id="74328-125">Nein.</span><span class="sxs-lookup"><span data-stu-id="74328-125">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="74328-126">Wo finde ich Informationen zu Sicherheit, Compliance und Datenschutz in Office 365?</span><span class="sxs-lookup"><span data-stu-id="74328-126">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="74328-127">Details finden Sie auf den Seiten des [Trust Centers für Office 365.](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="74328-127">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="74328-128">Können Benutzer mit Ihrem Geschäfts-, Schul- oder Unikonto Microsoft Rewards-Punkte erwerben?</span><span class="sxs-lookup"><span data-stu-id="74328-128">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="74328-129">Microsoft Search setzt voraus, dass Unternehmensbenutzer sich mit einem Geschäfts-, Schul- oder Unikonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="74328-129">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="74328-130">Mit diesen Konten können sich Benutzer aber nicht beim Microsoft Rewards-Programm anmelden oder daran teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="74328-130">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="74328-131">Allerdings gibt es einen Fall, bei dem Unternehmensbenutzer möglicherweise sehen, dass Prämienpunkte anfallen.</span><span class="sxs-lookup"><span data-stu-id="74328-131">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="74328-132">Dies kann vorkommen, wenn ein Microsoft Search-Benutzer über ein Rewards-Konto verfügt, das mit einem [Microsoft-Konto](https://www.microsoft.com/welcome?rtc=1) erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="74328-132">This can happen when a Microsoft Search user has a Rewards account that was created with a [Microsoft account](https://www.microsoft.com/welcome?rtc=1).</span></span> <span data-ttu-id="74328-133">(Die mit einem Microsoft-Konto verknüpfte E-Mail-Adresse kann von Outlook.com, Hotmail.com, Gmail, Yahoo oder anderen Anbietern stammen.) Wenn Benutzer sich bei derselben Browsersitzung abwechselnd mit ihrem Geschäfts-, Schul- oder Unikonto und ihrem Microsoft-Konto anmelden, werden möglicherweise Punkte auf dem Rewards-Konto angesammelt.</span><span class="sxs-lookup"><span data-stu-id="74328-133">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="74328-134">Benutzer können das Ansammeln von Punkten während der Suche mit Microsoft Search beenden, indem sie ihre Cookies löschen.</span><span class="sxs-lookup"><span data-stu-id="74328-134">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span>

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a><span data-ttu-id="74328-135">Können Gastbenutzer Microsoft Search in meiner Organisation nutzen?</span><span class="sxs-lookup"><span data-stu-id="74328-135">Can guest users leverage Microsoft Search in my organization?</span></span>

<span data-ttu-id="74328-136">Microsoft 365 ermöglicht eine umfassende Zusammenarbeit mit Personen außerhalb Ihrer Organisation durch [Gastzugriff.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span><span class="sxs-lookup"><span data-stu-id="74328-136">Microsoft 365 enables rich collaboration with people outside of your organization through [guest access.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span></span> <span data-ttu-id="74328-137">Diese Benutzer können Suchvorgänge für Dokumente, Websites, Gruppen, Listen und Bibliotheken ausführen.</span><span class="sxs-lookup"><span data-stu-id="74328-137">These users will be able to perform search operations on documents, sites, groups, lists, and libraries.</span></span> <span data-ttu-id="74328-138">Gastbenutzer erhalten jedoch nicht die vollständige, personalisierte Microsoft Search-Erfahrung und müssen möglicherweise das auf der Seite angezeigte Suchfeld anstelle des einheitlichen Microsoft Search-Felds in der Kopfzeile nutzen.</span><span class="sxs-lookup"><span data-stu-id="74328-138">However, guest users will not get the full, personalized, Microsoft Search experience and may need to leverage the on-page search box instead of the unified Microsoft Search box in the header.</span></span>
