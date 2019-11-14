---
title: Sicherheit für Microsoft Search
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
description: Schützen Sie Ihre Unternehmensdaten und Benutzer, während Sie mit Microsoft Search Informationen für autorisierte Benutzer bereitstellen
ms.openlocfilehash: a41059d529645d8ee7ffc99bad1b1f55c0e42aee
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311659"
---
# <a name="security-for-microsoft-search"></a><span data-ttu-id="d1647-103">Sicherheit für Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="d1647-103">Security for Microsoft Search</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1647-104">Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal.</span><span class="sxs-lookup"><span data-stu-id="d1647-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="d1647-105">Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird Microsoft Search im Bing-Portal entfernt.</span><span class="sxs-lookup"><span data-stu-id="d1647-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="d1647-106">Wir empfehlen, für die ersten Schritte das Microsoft 365 Admin Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d1647-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="d1647-107">[Übersicht über Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="d1647-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>

<span data-ttu-id="d1647-108">Mit Sicherheit auf Unternehmensniveau sorgt Microsoft Search immer dafür, dass Ihre Benutzer und Daten geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="d1647-108">With enterprise-grade security, Microsoft Search always keeps your users and data protected.</span></span>


## <a name="secure-by-default"></a><span data-ttu-id="d1647-109">Standardmäßige Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d1647-109">Secure by default</span></span>

<span data-ttu-id="d1647-p102">Microsoft Search stellt immer sicher, dass Anfragen über HTTPS vorgenommen werden. Diese Schutzmaßnahme erhöht mit einer End-to-End-Verschlüsselung die Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="d1647-p102">Microsoft Search always ensures requests are made over HTTPS. This safeguard ensures the connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="d1647-112">Authentifizierung und Autorisierung mit Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d1647-112">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="d1647-p103">Die Authentifizierung für Microsoft Search ist mit Azure Active Directory verbunden. Wenn Microsoft Search-Benutzer zu Bing wechseln, werden in der Bing-Kopfzeile Anmeldeoptionen für ein Microsoft- und ein Geschäfts- oder Schulkonto angezeigt. Wenn Bing nicht ermitteln kann, ob ein Benutzer ein berechtigter Teilnehmer ist, können Benutzer die Seite [Microsoft Search erkunden](https://www.bing.com/business/explore) aufrufen, auf der sie automatisch auf die Anmeldeseite Ihrer Organisation umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="d1647-p103">Authentication for Microsoft Search is tied to Azure Active Directory. When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account. If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span>
  
<span data-ttu-id="d1647-p104">Benutzer können nur über ein Geschäfts- oder Schulkonto auf Microsoft Search zugreifen. Sie müssen sich mit denselben Anmeldeinformationen anmelden, mit denen sie auch Zugriff auf Office 365-Dienste wie SharePoint oder Outlook erhalten. Ein persönliches Microsoft-Konto kann nicht zum Anmelden bei Microsoft Search verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d1647-p104">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
  
<span data-ttu-id="d1647-119">Benutzer können sich nicht gleichzeitig mit einem Microsoft-Konto und einem Geschäfts- oder Schulkonto bei Bing anmelden.</span><span class="sxs-lookup"><span data-stu-id="d1647-119">Users can't be signed in to Bing with both a Microsoft account and a work or school account at the same time.</span></span>
  
## <a name="single-sign-on"></a><span data-ttu-id="d1647-120">Einmaliges Anmelden</span><span class="sxs-lookup"><span data-stu-id="d1647-120">Single sign-on</span></span>

<span data-ttu-id="d1647-p105">Wenn ein Benutzer sich bereits mit seinem Geschäfts- oder Schulkonto bei einem anderen Dienst, z. B. Outlook oder SharePoint, authentifiziert hat, wird er automatisch bei Microsoft Search angemeldet, wenn er im selben Browser auf Bing zugreift. Wenn sich der Benutzer bei Microsoft Search abmeldet, wird er automatisch von anderen Diensten im gleichen Browser abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="d1647-p105">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed in to Microsoft Search when they go to Bing in the same browser. Also, when the user signs out of Microsoft Search, they'll be automatically signed out from other services in the same browser.</span></span>
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a><span data-ttu-id="d1647-123">Kommunizieren mit der vertrauenswürdigen Cloud im Browser</span><span class="sxs-lookup"><span data-stu-id="d1647-123">Communicates with the Trusted Cloud from the browser</span></span>

<span data-ttu-id="d1647-p106">Wenn sich ein Benutzer mit seinem Geschäfts- oder Schulkonto anmeldet, lädt Bing die notwendigen Client-Bibliotheken in den Browser, um Ergebnisse von Microsoft Search zu aktivieren. Bei der Suche ruft der Code des Browsers Arbeitsergebnisse von der Office 365-Cloud ab. Dazu verwendet Microsoft Search eine dedizierte API, die zur Ebene C (SOC2 Typ 1) kompatibel ist und der [Compliance-Framework für Branchenstandards und gesetzliche Vorschriften](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF-Download) für Office 365 entspricht. Dies bedeutet, dass Arbeitsergebnisse und Arbeitsdaten nie über nicht kompatible Bing-Systeme fließen.</span><span class="sxs-lookup"><span data-stu-id="d1647-p106">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results. Then, when they search, the in-browser code calls the Office 365 cloud to get work results. To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download). This means work results and work data never flow through non-compliant Bing systems.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="d1647-128">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d1647-128">Permissions</span></span>

<span data-ttu-id="d1647-p107">Arbeitsergebnisse, die über Office 365-Workloads wie SharePoint und OneDrive for Business abgerufen werden, werden in der Quelle einer Sicherheitskürzung unterzogen. Benutzer können Ressourcen wie Word-Dokumente oder PowerPoint-Präsentationen, die sie nicht über Office 365 anzeigen oder auf die sie nicht über Office 365 zugreifen können, nicht anzeigen. Sie können nur ihre eigenen Dateien und Dateien anzeigen, die der Autor explizit oder implizit (z. B. über eine Gruppenmitgliedschaft) in SharePoint für sie freigegeben hat.</span><span class="sxs-lookup"><span data-stu-id="d1647-p107">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a><span data-ttu-id="d1647-132">Schützen von Benutzerabfragen vor dem öffentlichen Bereich von Bing</span><span class="sxs-lookup"><span data-stu-id="d1647-132">Protects user queries from the public portion of Bing</span></span>

<span data-ttu-id="d1647-133">Da arbeitsbezogene Suchvorgänge vertraulich sein können, hat Microsoft Search eine Reihe von Vertrauensmaßnahmen für den Bereich der öffentlichen Webergebnisse von Bing implementiert.</span><span class="sxs-lookup"><span data-stu-id="d1647-133">Because work-related searches may be sensitive, Microsoft Search has implemented a set of trust measures for how these are handled by the public web results part of Bing.</span></span>
  
<span data-ttu-id="d1647-134">Unabhängig davon, ob eine Benutzerabfrage ein Arbeitsergebnis oder mehrere in der zurückgegebenen Antwort enthält, werden folgende Maßnahmen getroffen:</span><span class="sxs-lookup"><span data-stu-id="d1647-134">Regardless of whether a user query contains one or more work results in the returned response, the following measures are taken:</span></span>
  
- <span data-ttu-id="d1647-135">Protokollierung</span><span class="sxs-lookup"><span data-stu-id="d1647-135">Logging</span></span> 
  - <span data-ttu-id="d1647-136">Alle Suchprotokolle, die sich auf den Microsoft Search-Datenverkehr beziehen, werden in einen nicht-identifizierbaren Zustand versetzt.</span><span class="sxs-lookup"><span data-stu-id="d1647-136">All search logs pertaining to Microsoft Search traffic are de-identified.</span></span> <span data-ttu-id="d1647-137">Sie werden für 18 Monate aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="d1647-137">They're retained for 18 months.</span></span>
  - <span data-ttu-id="d1647-138">Abfragen, die in diesen Systemprotokollen gespeichert werden, werden lediglich zum Modellieren und Trainieren von öffentlichen Features wie der Vorschlagssuche oder bei verwandten Suchvorgängen für öffentliche Webergebnisse verwendet, wenn eine Reihe von Einschränkungen und Frequenz-Schwellenwerten erfüllt sind, was uns das Vertrauen gibt, dass diese Abfragen allgemein und nicht für eine bestimmte Organisation spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="d1647-138">Queries stored in these system logs will only be used to model and train public features such as autosuggest or related searches for public web results when a set of restrictions and frequency thresholds are met, which gives us confidence that these queries are common and not specific to a particular organization.</span></span> <span data-ttu-id="d1647-139">Die Abfrage muss in einer bedeutenden Anzahl von Fällen in Verbindung mit Daten von Benutzern vorkommen, welche die Microsoft Suchfunktion nicht verwenden und die Abfrage darf nicht ausschließlich Enterprise-Suchergebnisse auslösen.</span><span class="sxs-lookup"><span data-stu-id="d1647-139">The query must appear a significant amount of times in corelating data from non-Microsoft Search users, and the query must not trigger exclusively enterprise search results.</span></span> <span data-ttu-id="d1647-140">Abfragen, die diese Anforderungen nicht erfüllen, werden getrennt vom öffentlichen, nicht von Microsoft durchgeführten Such Datenverkehr gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d1647-140">Queries that do not meet these requirements will be stored separately from public, non-Microsoft Search traffic.</span></span>
  - <span data-ttu-id="d1647-141">Der eingeschränkte Zugriff wird über verschiedene Sicherheitsmechanismen verwaltet, einschließlich Sicherheitsgruppen und anderen Ebenen innerhalb des Engineering-Systems.</span><span class="sxs-lookup"><span data-stu-id="d1647-141">Restricted access is managed via various secure mechanisms, including security groups and other layers within the engineering system.</span></span>
- <span data-ttu-id="d1647-142">Suchverlauf</span><span class="sxs-lookup"><span data-stu-id="d1647-142">Search history</span></span>    
  - <span data-ttu-id="d1647-143">Wenn Sie mit einem Geschäfts- oder Schulkonto angemeldet sind, steht der Suchverlauf eines Benutzers nicht auf anderen Computern oder Geräten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d1647-143">When signed in with a work or school account, a user's search history won't be available on other computers or devices.</span></span>
 
- <span data-ttu-id="d1647-144">Werbung</span><span class="sxs-lookup"><span data-stu-id="d1647-144">Advertising</span></span>   
  - <span data-ttu-id="d1647-145">Suchabfragen von Unternehmen werden nie für Werbetreibende freigegeben und diesen auch nicht vorgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="d1647-145">Enterprise search queries are never shared with or suggested to advertisers.</span></span>
  - <span data-ttu-id="d1647-146">Werbung wird nie basierend auf der Arbeitsidentität oder Organisation eines Benutzers ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="d1647-146">Ads are never targeted to a user based on their work identity or organization.</span></span>
    
## <a name="gdpr"></a><span data-ttu-id="d1647-147">DSGVO</span><span class="sxs-lookup"><span data-stu-id="d1647-147">GDPR</span></span>

<span data-ttu-id="d1647-p110">Der [Blogbeitrag vom 21. Mai 2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) von Microsoft bekräftigt unsere Verpflichtung zur Einhaltung der DSGVO und zeigt, wie Microsoft Unternehmen und Organisationen hilft, die eigenen DSGVO-Auflagen einzuhalten. Weitere Details finden Sie im Microsoft [Trust Center-FAQ](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search-Abfragen, die sich auf Kundendaten von Unternehmenskunden in Onlinediensten ungünstig auswirken, erfüllen ebenfalls die Verarbeitungspflichten aus Artikel 28, wie im [Trust Center-FAQ](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs) beschrieben. Im Hinblick auf Abfragen von Microsoft Search, die im öffentlichen Bing verwendet werden, gilt Microsoft als Datenverantwortlicher und hat Maßnahmen implementiert, um die Abfragen wie in der DSGVO beschrieben, unkenntlich zu machen.</span><span class="sxs-lookup"><span data-stu-id="d1647-p110">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations. You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search queries that operate against organizational customers' Customer Data within the Online Services will also meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs). With respect to queries from Microsoft Search that go to public Bing, Microsoft is a data controller and has implemented measures to de-identify the queries as outlined under GDPR.</span></span>