---
title: Sicherheit für die Microsoft-Suche
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
description: Schützen Sie Ihre Enterprise-Daten und Benutzer und Bereitstellen von Informationen für autorisierte Benutzer mit Microsoft Search
ms.openlocfilehash: 65cf1d49e32edbb8061a06f8da7ba644c2145e24
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378789"
---
# <a name="security-for-microsoft-search"></a><span data-ttu-id="b9430-103">Sicherheit für die Microsoft-Suche</span><span class="sxs-lookup"><span data-stu-id="b9430-103">Security for Microsoft Search</span></span>

<span data-ttu-id="b9430-104">Mit der Unternehmensklasse Sicherheit behält Microsoft Search immer Ihren Benutzern und Daten geschützt.</span><span class="sxs-lookup"><span data-stu-id="b9430-104">With enterprise-grade security, Microsoft Search always keeps your users and data protected.</span></span>
  
## <a name="secure-by-default"></a><span data-ttu-id="b9430-105">Standardmäßig sicher</span><span class="sxs-lookup"><span data-stu-id="b9430-105">Secure by default</span></span>

<span data-ttu-id="b9430-p101">Microsoft Search wird immer sichergestellt, dass Anforderungen über HTTPS vorgenommen werden. Diese Sicherheitsvorkehrung wird sichergestellt, dass der verschlüsselten End-to-End für eine erweiterte Sicherheit ist.</span><span class="sxs-lookup"><span data-stu-id="b9430-p101">Microsoft Search always ensures requests are made over HTTPS. This safeguard ensures the connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="b9430-108">Authentifizierung und Autorisierung mit Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b9430-108">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="b9430-p102">Authentifizierung für Microsoft Search ist mit Azure Active Directory verbunden. Beim Microsoft Search Benutzer auf Bing die Bing Anmeldeoptionen für ein Microsoft-Konto als Kopfzeile angezeigt sowie eine Arbeit oder Schule Konto. Wenn Bing nicht bestimmen kann, ob ein Benutzer bei einem berechtigte Teilnehmer ist, können Benutzer auf der Seite [Erkunden Sie Microsoft Search](https://www.bing.com/business/explore) wechseln, werden sie automatisch zu Ihrer Organisation-Anmeldeseite weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b9430-p102">Authentication for Microsoft Search is tied to Azure Active Directory. When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account. If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span> 
  
<span data-ttu-id="b9430-p103">Benutzer können nur über ein Konto arbeiten oder Schule Microsoft Search zugreifen. Sie müssen sich mit denselben Anmeldeinformationen anzumelden, die sie Zugriff auf Office 365-Dienste wie SharePoint oder Outlook verwenden. Ein persönliches Microsoft-Konto kann nicht verwendet werden, zur Anmeldung bei Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="b9430-p103">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
  
<span data-ttu-id="b9430-115">Benutzer können nicht bei Bing mit einem Microsoft-Konto und ein Konto arbeiten oder Schule gleichzeitig angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="b9430-115">Users can't be signed in to Bing with both a Microsoft account and a work or school account at the same time.</span></span>
  
## <a name="single-sign-on"></a><span data-ttu-id="b9430-116">Einmaliges Anmelden</span><span class="sxs-lookup"><span data-stu-id="b9430-116">Single sign-on</span></span>

<span data-ttu-id="b9430-p104">Wenn ein Benutzer bereits, ihre Arbeit oder Schule Konto in einen anderen Dienst, wie Outlook oder SharePoint authentifiziert ist, werden sie automatisch auf Microsoft Search angemeldet werden Wenn sie in den gleichen Browser auf Bing zugreifen. Auch wenn der Benutzer Microsoft Search abmeldet, werden sie automatisch von anderen Diensten im gleichen Browser abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="b9430-p104">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed in to Microsoft Search when they go to Bing in the same browser. Also, when the user signs out of Microsoft Search, they'll be automatically signed out from other services in the same browser.</span></span>
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a><span data-ttu-id="b9430-119">Kommuniziert mit der Cloud vertrauenswürdige vom browser</span><span class="sxs-lookup"><span data-stu-id="b9430-119">Communicates with the Trusted Cloud from the browser</span></span>

<span data-ttu-id="b9430-p105">Wenn ein Benutzer anmeldet mit ihrer Arbeit oder Schule Bing-Konto wird die erforderlichen Client-Bibliotheken an den Browser So aktivieren Sie Microsoft Search Results herunterladen. Klicken Sie dann bei der Suche, ruft der Code im Browser die Office 365-Cloud um Arbeit Ergebnisse zu erhalten. Zu diesem Zweck verwendet Microsoft Search eine dedizierte API, die Tier C (SOC2 type1) nach Office 365 [Compliance-Framework für Branchenstandards und Vorschriften](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF-Datei zum Herunterladen) kompatibel ist. Dies bedeutet, dass die Ergebnisse von Arbeit und Arbeitsdaten flow nie über nicht kompatible Bing-Systeme.</span><span class="sxs-lookup"><span data-stu-id="b9430-p105">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results. Then, when they search, the in-browser code calls the Office 365 cloud to get work results. To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download). This means work results and work data never flow through non-compliant Bing systems.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="b9430-124">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b9430-124">Permissions</span></span>

<span data-ttu-id="b9430-p106">Arbeit Ergebnisse von Office 365-Arbeitslasten abgerufen, wie SharePoint und OneDrive für Unternehmen Sicherheit werden abgeschnitten an der Quelle. Benutzer Ressourcen wie Word-Dokumente oder PowerPoint-Präsentationen keine finden Sie unter, und greifen Sie auf über Office 365 nicht angezeigt werden. Sie können nur sehen, ihre eigenen Dateien und Dateien, die mit diesen vom Autor implizit oder explizit freigegeben wurden (über eine Gruppenmitgliedschaft beispielsweise) in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b9430-p106">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a><span data-ttu-id="b9430-128">Schützt Benutzerabfragen aus dem öffentlichen Bereich der Bing</span><span class="sxs-lookup"><span data-stu-id="b9430-128">Protects user queries from the public portion of Bing</span></span>

<span data-ttu-id="b9430-129">Da arbeitsbezogene Suchvorgänge vertrauliche sein können, hat Microsoft Search implementiert eine Reihe von Vertrauensstellung Maßnahmen zur wie dies vom öffentlichen Ergebnisse Webpart der Bing behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="b9430-129">Because work-related searches may be sensitive, Microsoft Search has implemented a set of trust measures for how these are handled by the public web results part of Bing.</span></span>
  
<span data-ttu-id="b9430-130">Unabhängig davon, ob eine Benutzerabfrage eines oder mehrere Arbeit Ergebnisse in der zurückgegebenen Antwort enthält werden folgende Maßnahmen ergriffen:</span><span class="sxs-lookup"><span data-stu-id="b9430-130">Regardless of whether a user query contains one or more work results in the returned response, the following measures are taken:</span></span>
  
- <span data-ttu-id="b9430-131">Protokollierung</span><span class="sxs-lookup"><span data-stu-id="b9430-131">Logging</span></span>
    
  - <span data-ttu-id="b9430-p107">Alle Microsoft Search-Datenverkehr zur Suche-Protokolle sind Aufhebung der identifiziert und getrennt von öffentlichen, nicht - Microsoft Search Datenverkehr gespeichert werden. Sie sind 18 Monate beibehalten, und der Zugriff ist nur zu Debuggingzwecken eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="b9430-p107">All search logs pertaining to Microsoft Search traffic are de-identified and stored separately from public, non-Microsoft Search traffic. They're retained for 18 months, and access is restricted for debugging purposes only.</span></span>
    
  - <span data-ttu-id="b9430-134">Die Abfragen in diese Protokolle werden nicht auf Model oder Zug öffentliche Features wie etwa AutoVorschlagen oder verwandte Suchvorgänge für das öffentliche Internet verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9430-134">The queries in these logs are not used to model or train public features such as autosuggest or related searches for the public web.</span></span>
    
  - <span data-ttu-id="b9430-135">Eingeschränkter Zugriff wird über verschiedene sichere Mechanismen, einschließlich der Sicherheitsgruppen und anderen Ebenen in das Entwicklungssystem verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b9430-135">Restricted access is managed via various secure mechanisms, including security groups and other layers within the engineering system.</span></span>
    
- <span data-ttu-id="b9430-136">Suchverlauf</span><span class="sxs-lookup"><span data-stu-id="b9430-136">Search history</span></span>
    
  - <span data-ttu-id="b9430-137">Wenn eine Signatur mit einem Konto arbeiten oder Schule wird nicht Suchverlauf eines Benutzers auf anderen Computern oder Geräten verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="b9430-137">When signed in with a work or school account, a user's search history won't be available on other computers or devices.</span></span>
    
- <span data-ttu-id="b9430-138">Werbung</span><span class="sxs-lookup"><span data-stu-id="b9430-138">Advertising</span></span>
    
  - <span data-ttu-id="b9430-139">Enterprise Search-Abfragen sind niemals freigegeben oder um Werbekunden vorgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="b9430-139">Enterprise search queries are never shared with or suggested to advertisers.</span></span>
    
  - <span data-ttu-id="b9430-140">Suche Ads-Protokolle für Microsoft Search werden separat von öffentlichen Datenverkehr gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b9430-140">Search Ads logs pertaining to Microsoft Search are stored separately from public traffic.</span></span>
    
  - <span data-ttu-id="b9430-141">ADS werden nie auf einen Benutzer basierend auf ihrer arbeitsidentität oder Organisation abgestimmt.</span><span class="sxs-lookup"><span data-stu-id="b9430-141">Ads are never targeted to a user based on their work identity or organization.</span></span>
    
## <a name="gdpr"></a><span data-ttu-id="b9430-142">DSGVO</span><span class="sxs-lookup"><span data-stu-id="b9430-142">GDPR</span></span>

<span data-ttu-id="b9430-p108">Der [Blogbeitrag von 21 Mai 2018,](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) von Microsoft enthät unser Engagement für GDPR Compliance und Microsoft Unternehmen und Organisationen mit ihren eigenen GDPR Auflagen Schutzmechanismen in. Weitere Einzelheiten finden Sie in der Microsoft- [Trust Center häufig gestellte Fragen](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search-Abfragen, die gegen Organisationseinheit Kunden Kundendaten innerhalb der Online-Dienste ausgeführt werden, werden auch die Prozessor Zusagen beschriebenen Artikel 28 im [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)erfüllen. Microsoft in Bezug auf Abfragen von Microsoft Search, die an öffentliche Bing umgeleitet wird, ist ein Controller Daten und wurde implementiert, um die Abfragen identifizieren Aufhebung der gemäß GDPR Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="b9430-p108">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations. You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search queries that operate against organizational customers' Customer Data within the Online Services will also meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). With respect to queries from Microsoft Search that go to public Bing, Microsoft is a data controller and has implemented measures to de-identify the queries as outlined under GDPR.</span></span>


