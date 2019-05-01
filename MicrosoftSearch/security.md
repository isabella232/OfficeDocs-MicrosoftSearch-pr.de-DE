---
title: Sicherheit für Microsoft Search
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
description: Schützen Sie Ihre Unternehmensdaten und Benutzer, während Sie mit Microsoft Search Informationen für autorisierte Benutzer bereitstellen
ms.openlocfilehash: 5f59e0e2969ef829d7c14b07ecb47d645cc63013
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508709"
---
# <a name="security-for-microsoft-search"></a><span data-ttu-id="b94f3-103">Sicherheit für Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="b94f3-103">Security for Microsoft Search</span></span>

<span data-ttu-id="b94f3-104">Mit Sicherheit auf Unternehmensniveau sorgt Microsoft Search immer dafür, dass Ihre Benutzer und Daten geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="b94f3-104">With enterprise-grade security, Microsoft Search always keeps your users and data protected.</span></span>
  
## <a name="secure-by-default"></a><span data-ttu-id="b94f3-105">Standardmäßige Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b94f3-105">Secure by default</span></span>

<span data-ttu-id="b94f3-p101">Microsoft Search stellt immer sicher, dass Anfragen über HTTPS vorgenommen werden. Diese Schutzmaßnahme erhöht mit einer End-to-End-Verschlüsselung die Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="b94f3-p101">Microsoft Search always ensures requests are made over HTTPS. This safeguard ensures the connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="b94f3-108">Authentifizierung und Autorisierung mit Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b94f3-108">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="b94f3-p102">Die Authentifizierung für Microsoft Search ist mit Azure Active Directory verbunden. Wenn Microsoft Search-Benutzer zu Bing wechseln, werden in der Bing-Kopfzeile Anmeldeoptionen für ein Microsoft- und ein Geschäfts- oder Schulkonto angezeigt. Wenn Bing nicht ermitteln kann, ob ein Benutzer ein berechtigter Teilnehmer ist, können Benutzer die Seite [Microsoft Search erkunden](https://www.bing.com/business/explore) aufrufen, auf der sie automatisch auf die Anmeldeseite Ihrer Organisation umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b94f3-p102">Authentication for Microsoft Search is tied to Azure Active Directory. When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account. If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span> 
  
<span data-ttu-id="b94f3-p103">Benutzer können nur über ein Geschäfts- oder Schulkonto auf Microsoft Search zugreifen. Sie müssen sich mit denselben Anmeldeinformationen anmelden, mit denen sie auch Zugriff auf Office 365-Dienste wie SharePoint oder Outlook erhalten. Ein persönliches Microsoft-Konto kann nicht zum Anmelden bei Microsoft Search verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b94f3-p103">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
  
<span data-ttu-id="b94f3-115">Benutzer können sich nicht gleichzeitig mit einem Microsoft-Konto und einem Geschäfts- oder Schulkonto bei Bing anmelden.</span><span class="sxs-lookup"><span data-stu-id="b94f3-115">Users can't be signed in to Bing with both a Microsoft account and a work or school account at the same time.</span></span>
  
## <a name="single-sign-on"></a><span data-ttu-id="b94f3-116">Einmaliges Anmelden</span><span class="sxs-lookup"><span data-stu-id="b94f3-116">Single sign-on</span></span>

<span data-ttu-id="b94f3-p104">Wenn ein Benutzer sich bereits mit seinem Geschäfts- oder Schulkonto bei einem anderen Dienst, z. B. Outlook oder SharePoint, authentifiziert hat, wird er automatisch bei Microsoft Search angemeldet, wenn er im selben Browser auf Bing zugreift. Wenn sich der Benutzer bei Microsoft Search abmeldet, wird er automatisch von anderen Diensten im gleichen Browser abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="b94f3-p104">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed in to Microsoft Search when they go to Bing in the same browser. Also, when the user signs out of Microsoft Search, they'll be automatically signed out from other services in the same browser.</span></span>
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a><span data-ttu-id="b94f3-119">Kommunizieren mit der vertrauenswürdigen Cloud im Browser</span><span class="sxs-lookup"><span data-stu-id="b94f3-119">Communicates with the Trusted Cloud from the browser</span></span>

<span data-ttu-id="b94f3-p105">Wenn sich ein Benutzer mit seinem Geschäfts- oder Schulkonto anmeldet, lädt Bing die notwendigen Client-Bibliotheken in den Browser, um Ergebnisse von Microsoft Search zu aktivieren. Bei der Suche ruft der Code des Browsers Arbeitsergebnisse von der Office 365-Cloud ab. Dazu verwendet Microsoft Search eine dedizierte API, die zur Ebene C (SOC2 Typ 1) kompatibel ist und der [Compliance-Framework für Branchenstandards und gesetzliche Vorschriften](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF-Download) für Office 365 entspricht. Dies bedeutet, dass Arbeitsergebnisse und Arbeitsdaten nie über nicht kompatible Bing-Systeme fließen.</span><span class="sxs-lookup"><span data-stu-id="b94f3-p105">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results. Then, when they search, the in-browser code calls the Office 365 cloud to get work results. To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download). This means work results and work data never flow through non-compliant Bing systems.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="b94f3-124">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b94f3-124">Permissions</span></span>

<span data-ttu-id="b94f3-p106">Arbeitsergebnisse, die über Office 365-Workloads wie SharePoint und OneDrive for Business abgerufen werden, werden in der Quelle einer Sicherheitskürzung unterzogen. Benutzer können Ressourcen wie Word-Dokumente oder PowerPoint-Präsentationen, die sie nicht über Office 365 anzeigen oder auf die sie nicht über Office 365 zugreifen können, nicht anzeigen. Sie können nur ihre eigenen Dateien und Dateien anzeigen, die der Autor explizit oder implizit (z. B. über eine Gruppenmitgliedschaft) in SharePoint für sie freigegeben hat.</span><span class="sxs-lookup"><span data-stu-id="b94f3-p106">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a><span data-ttu-id="b94f3-128">Schützen von Benutzerabfragen vor dem öffentlichen Bereich von Bing</span><span class="sxs-lookup"><span data-stu-id="b94f3-128">Protects user queries from the public portion of Bing</span></span>

<span data-ttu-id="b94f3-129">Da arbeitsbezogene Suchvorgänge vertraulich sein können, hat Microsoft Search eine Reihe von Vertrauensmaßnahmen für den Bereich der öffentlichen Webergebnisse von Bing implementiert.</span><span class="sxs-lookup"><span data-stu-id="b94f3-129">Because work-related searches may be sensitive, Microsoft Search has implemented a set of trust measures for how these are handled by the public web results part of Bing.</span></span>
  
<span data-ttu-id="b94f3-130">Unabhängig davon, ob eine Benutzerabfrage ein Arbeitsergebnis oder mehrere in der zurückgegebenen Antwort enthält, werden folgende Maßnahmen getroffen:</span><span class="sxs-lookup"><span data-stu-id="b94f3-130">Regardless of whether a user query contains one or more work results in the returned response, the following measures are taken:</span></span>
  
- <span data-ttu-id="b94f3-131">Protokollierung</span><span class="sxs-lookup"><span data-stu-id="b94f3-131">Logging</span></span>
    
  - <span data-ttu-id="b94f3-p107">Alle Suchprotokolle im Zusammenhang mit Microsoft Search-Datenverkehr werden unkenntlich gemacht und separat vom öffentlichen Nicht-Microsoft Search-Datenverkehr gespeichert. Sie werden 18 Monate lang aufbewahrt, und der Zugriff ist nur für Debugging-Zwecke erlaubt.</span><span class="sxs-lookup"><span data-stu-id="b94f3-p107">All search logs pertaining to Microsoft Search traffic are de-identified and stored separately from public, non-Microsoft Search traffic. They're retained for 18 months, and access is restricted for debugging purposes only.</span></span>
    
  - <span data-ttu-id="b94f3-134">Die Abfragen in diesen Protokollen werden nicht zur Entwicklung oder Schulung öffentlicher Funktionen verwendet, wie z. B. die Vorschlagssuche oder verwandte Suchen im öffentlichen Web.</span><span class="sxs-lookup"><span data-stu-id="b94f3-134">The queries in these logs are not used to model or train public features such as autosuggest or related searches for the public web.</span></span>
    
  - <span data-ttu-id="b94f3-135">Der eingeschränkte Zugriff wird über verschiedene Sicherheitsmechanismen verwaltet, einschließlich Sicherheitsgruppen und anderen Ebenen innerhalb des Engineering-Systems.</span><span class="sxs-lookup"><span data-stu-id="b94f3-135">Restricted access is managed via various secure mechanisms, including security groups and other layers within the engineering system.</span></span>
    
- <span data-ttu-id="b94f3-136">Suchverlauf</span><span class="sxs-lookup"><span data-stu-id="b94f3-136">Search history</span></span>
    
  - <span data-ttu-id="b94f3-137">Wenn Sie mit einem Geschäfts- oder Schulkonto angemeldet sind, steht der Suchverlauf eines Benutzers nicht auf anderen Computern oder Geräten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b94f3-137">When signed in with a work or school account, a user's search history won't be available on other computers or devices.</span></span>
    
- <span data-ttu-id="b94f3-138">Werbung</span><span class="sxs-lookup"><span data-stu-id="b94f3-138">Advertising</span></span>
    
  - <span data-ttu-id="b94f3-139">Suchabfragen von Unternehmen werden nie für Werbetreibende freigegeben und diesen auch nicht vorgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="b94f3-139">Enterprise search queries are never shared with or suggested to advertisers.</span></span>
    
  - <span data-ttu-id="b94f3-140">Protokolle von Suchmaschinenwerbung im Zusammenhang mit Microsoft Search werden separat vom öffentlichen Datenverkehr gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b94f3-140">Search Ads logs pertaining to Microsoft Search are stored separately from public traffic.</span></span>
    
  - <span data-ttu-id="b94f3-141">Werbung wird nie basierend auf der Arbeitsidentität oder Organisation eines Benutzers ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="b94f3-141">Ads are never targeted to a user based on their work identity or organization.</span></span>
    
## <a name="gdpr"></a><span data-ttu-id="b94f3-142">DSGVO</span><span class="sxs-lookup"><span data-stu-id="b94f3-142">GDPR</span></span>

<span data-ttu-id="b94f3-p108">Der [Blogbeitrag vom 21. Mai 2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) von Microsoft bekräftigt unsere Verpflichtung zur Einhaltung der DSGVO und zeigt, wie Microsoft Unternehmen und Organisationen hilft, die eigenen DSGVO-Auflagen einzuhalten. Weitere Details finden Sie im Microsoft [Trust Center-FAQ](https://www.microsoft.com/de-DE/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search-Abfragen, die sich auf Kundendaten von Unternehmenskunden in Onlinediensten ungünstig auswirken, erfüllen ebenfalls die Verarbeitungspflichten aus Artikel 28, wie im [Trust Center-FAQ](https://www.microsoft.com/de-DE/trustcenter/privacy/gdpr/gdpr-faqs) beschrieben. Im Hinblick auf Abfragen von Microsoft Search, die im öffentlichen Bing verwendet werden, gilt Microsoft als Datenverantwortlicher und hat Maßnahmen implementiert, um die Abfragen wie in der DSGVO beschrieben, unkenntlich zu machen.</span><span class="sxs-lookup"><span data-stu-id="b94f3-p108">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations. You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/de-DE/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search queries that operate against organizational customers' Customer Data within the Online Services will also meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/de-DE/trustcenter/privacy/gdpr/gdpr-faqs). With respect to queries from Microsoft Search that go to public Bing, Microsoft is a data controller and has implemented measures to de-identify the queries as outlined under GDPR.</span></span>


