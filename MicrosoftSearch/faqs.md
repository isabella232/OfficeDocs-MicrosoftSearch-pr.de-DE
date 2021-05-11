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
ms.openlocfilehash: 614fa241f353533b1c1e181904eb961fd55d0dfa
ms.sourcegitcommit: ea784081bc9c3ae7981a87a493d3a74503859dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306070"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="0e857-103">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="0e857-103">Frequently asked questions</span></span>

<span data-ttu-id="0e857-104">Nachfolgend finden Sie eine Liste der am häufigsten gestellten Fragen.</span><span class="sxs-lookup"><span data-stu-id="0e857-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="0e857-105">Ihre Frage wurde hier nicht beantwortet?</span><span class="sxs-lookup"><span data-stu-id="0e857-105">Don't see your question answered here?</span></span> <span data-ttu-id="0e857-106">Stellen Sie Ihre Frage im Feedback zu diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="0e857-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="0e857-107">Wird das Verstehen von erweiterten Abfragen unterstützt?</span><span class="sxs-lookup"><span data-stu-id="0e857-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="0e857-108">Ja, Microsoft Search analysiert Abfrageabsichten aus größeren Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="0e857-108">Yes, Microsoft Search parses query intent from larger phrases.</span></span> <span data-ttu-id="0e857-109">Dieses Feature verwendet KI, um allgemeine überflüssige Ausdrücke zu lernen, die Benutzer zu ihren Abfragen hinzufügen, die sich nicht auf ihre Suchabsicht auswirken.</span><span class="sxs-lookup"><span data-stu-id="0e857-109">This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent.</span></span> <span data-ttu-id="0e857-110">Wenn ein Benutzer z. B. nach weiteren Informationen zum Ändern meines Kennworts *sucht,* extrahieren wir die weniger wichtigen Wörter aus der Abfrage und lösen sie basierend auf den relevanten Wörtern wie Änderungskennwort *aus.*</span><span class="sxs-lookup"><span data-stu-id="0e857-110">For example, when a user searches for *tell me more about how to change my password*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="0e857-111">Dieses Feature überschreibt keine Schlüsselwörter, die im Microsoft 365 [Admin Center festgelegt sind.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0e857-111">This feature won't override keywords set in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="0e857-112">Können Sie nach lokalen Dateien suchen?</span><span class="sxs-lookup"><span data-stu-id="0e857-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="0e857-113">Ja.</span><span class="sxs-lookup"><span data-stu-id="0e857-113">Yes.</span></span> <span data-ttu-id="0e857-114">Sie können lokale Dateien [SharePoint,](http://sharepoint.com/) wenn Sie über eine Hybridbereitstellung von SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0e857-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="0e857-115">Wie kann ich Bing als Standardsuchmaschine für Personen in meiner Organisation festlegen?</span><span class="sxs-lookup"><span data-stu-id="0e857-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="0e857-116">Hier finden Sie die Anweisungen zum Festlegen der Standardsuchmaschine, der Standardhomepage und des Standardbrowsers, um Ihren Benutzern die beste Erfahrung mit Microsoft Search [in](https://Bing.com)Bing:</span><span class="sxs-lookup"><span data-stu-id="0e857-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="0e857-117">Festlegen Microsoft Edge als Standardbrowser</span><span class="sxs-lookup"><span data-stu-id="0e857-117">Set Microsoft Edge as your default browser</span></span>](/deployedge/edge-default-browser)
- [<span data-ttu-id="0e857-118">Festlegen von Bing als Standardsuchmaschine</span><span class="sxs-lookup"><span data-stu-id="0e857-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="0e857-119">Festlegen von Bing.com als Startseite des Unternehmens</span><span class="sxs-lookup"><span data-stu-id="0e857-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="0e857-120">Wie werden meine Suchergebnisse geschützt?</span><span class="sxs-lookup"><span data-stu-id="0e857-120">How are my search results protected?</span></span>

<span data-ttu-id="0e857-121">Wir benötigen [Azure Active Directory](/azure/active-directory/) Authentifizierung, um auf Ergebnisse aus der vertrauenswürdigen Cloud zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0e857-121">We require [Azure Active Directory](/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="0e857-122">Authentifizierten Benutzern werden nur Inhalte angezeigt, auf die sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="0e857-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="0e857-123">Suchabfragen werden nicht identifiziert, und Protokolle [](https://Bing.com) werden vom Bing öffentlichen Datenverkehr getrennt, wenn Sie Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="0e857-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic when you use Microsoft Search in Bing.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="0e857-124">Kann ich in Verbundorganisationen suchen?</span><span class="sxs-lookup"><span data-stu-id="0e857-124">Can I search across federated organizations?</span></span>

<span data-ttu-id="0e857-125">Nein.</span><span class="sxs-lookup"><span data-stu-id="0e857-125">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="0e857-126">Wo kann ich Informationen zu Office 365, Compliance und Datenschutz erhalten?</span><span class="sxs-lookup"><span data-stu-id="0e857-126">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="0e857-127">Details finden Sie auf den [Trust Center-Seiten für Office 365.](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="0e857-127">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a><span data-ttu-id="0e857-128">Können Gastbenutzer Microsoft Search in meiner Organisation nutzen?</span><span class="sxs-lookup"><span data-stu-id="0e857-128">Can guest users leverage Microsoft Search in my organization?</span></span>

<span data-ttu-id="0e857-129">Microsoft 365 ermöglicht eine umfassende Zusammenarbeit mit Personen außerhalb Ihrer Organisation über [den Gastzugriff.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span><span class="sxs-lookup"><span data-stu-id="0e857-129">Microsoft 365 enables rich collaboration with people outside of your organization through [guest access.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span></span> <span data-ttu-id="0e857-130">Diese Benutzer können Suchvorgänge für Dokumente, Websites, Gruppen, Listen und Bibliotheken ausführen.</span><span class="sxs-lookup"><span data-stu-id="0e857-130">These users will be able to perform search operations on documents, sites, groups, lists, and libraries.</span></span> <span data-ttu-id="0e857-131">Gastbenutzer erhalten jedoch nicht die vollständige, personalisierte Microsoft Search-Erfahrung und müssen möglicherweise das Auf-Seite-Suchfeld anstelle des einheitlichen Microsoft Search-Felds in der Kopfzeile nutzen.</span><span class="sxs-lookup"><span data-stu-id="0e857-131">However, guest users will not get the full, personalized, Microsoft Search experience and may need to leverage the on-page search box instead of the unified Microsoft Search box in the header.</span></span>