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
ms.openlocfilehash: b7b62173dc61d271a4953adbf20a6cf48b122694
ms.sourcegitcommit: 4eeb78066fd13e906daed3add003398bd9d0f6ca
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2019
ms.locfileid: "35917569"
---
# <a name="security-for-microsoft-search"></a>Sicherheit für Microsoft Search

Mit Sicherheit auf Unternehmensniveau sorgt Microsoft Search immer dafür, dass Ihre Benutzer und Daten geschützt sind.


## <a name="secure-by-default"></a>Standardmäßige Sicherheit

Microsoft Search stellt immer sicher, dass Anfragen über HTTPS vorgenommen werden. Diese Schutzmaßnahme erhöht mit einer End-to-End-Verschlüsselung die Sicherheit.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Authentifizierung und Autorisierung mit Azure Active Directory

Die Authentifizierung für Microsoft Search ist mit Azure Active Directory verbunden. Wenn Microsoft Search-Benutzer zu Bing wechseln, werden in der Bing-Kopfzeile Anmeldeoptionen für ein Microsoft- und ein Geschäfts- oder Schulkonto angezeigt. Wenn Bing nicht ermitteln kann, ob ein Benutzer ein berechtigter Teilnehmer ist, können Benutzer die Seite [Microsoft Search erkunden](https://www.bing.com/business/explore) aufrufen, auf der sie automatisch auf die Anmeldeseite Ihrer Organisation umgeleitet werden.
  
Benutzer können nur über ein Geschäfts- oder Schulkonto auf Microsoft Search zugreifen. Sie müssen sich mit denselben Anmeldeinformationen anmelden, mit denen sie auch Zugriff auf Office 365-Dienste wie SharePoint oder Outlook erhalten. Ein persönliches Microsoft-Konto kann nicht zum Anmelden bei Microsoft Search verwendet werden.
  
Benutzer können sich nicht gleichzeitig mit einem Microsoft-Konto und einem Geschäfts- oder Schulkonto bei Bing anmelden.
  
## <a name="single-sign-on"></a>Einmaliges Anmelden

Wenn ein Benutzer sich bereits mit seinem Geschäfts- oder Schulkonto bei einem anderen Dienst, z. B. Outlook oder SharePoint, authentifiziert hat, wird er automatisch bei Microsoft Search angemeldet, wenn er im selben Browser auf Bing zugreift. Wenn sich der Benutzer bei Microsoft Search abmeldet, wird er automatisch von anderen Diensten im gleichen Browser abgemeldet.
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>Kommunizieren mit der vertrauenswürdigen Cloud im Browser

Wenn sich ein Benutzer mit seinem Geschäfts- oder Schulkonto anmeldet, lädt Bing die notwendigen Client-Bibliotheken in den Browser, um Ergebnisse von Microsoft Search zu aktivieren. Bei der Suche ruft der Code des Browsers Arbeitsergebnisse von der Office 365-Cloud ab. Dazu verwendet Microsoft Search eine dedizierte API, die zur Ebene C (SOC2 Typ 1) kompatibel ist und der [Compliance-Framework für Branchenstandards und gesetzliche Vorschriften](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF-Download) für Office 365 entspricht. Dies bedeutet, dass Arbeitsergebnisse und Arbeitsdaten nie über nicht kompatible Bing-Systeme fließen. 
  
## <a name="permissions"></a>Berechtigungen

Arbeitsergebnisse, die über Office 365-Workloads wie SharePoint und OneDrive for Business abgerufen werden, werden in der Quelle einer Sicherheitskürzung unterzogen. Benutzer können Ressourcen wie Word-Dokumente oder PowerPoint-Präsentationen, die sie nicht über Office 365 anzeigen oder auf die sie nicht über Office 365 zugreifen können, nicht anzeigen. Sie können nur ihre eigenen Dateien und Dateien anzeigen, die der Autor explizit oder implizit (z. B. über eine Gruppenmitgliedschaft) in SharePoint für sie freigegeben hat.
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Schützen von Benutzerabfragen vor dem öffentlichen Bereich von Bing

Da arbeitsbezogene Suchvorgänge vertraulich sein können, hat Microsoft Search eine Reihe von Vertrauensmaßnahmen für den Bereich der öffentlichen Webergebnisse von Bing implementiert.
  
Unabhängig davon, ob eine Benutzerabfrage ein Arbeitsergebnis oder mehrere in der zurückgegebenen Antwort enthält, werden folgende Maßnahmen getroffen:
  
- Protokollierung 
  - Alle Suchprotokolle, die sich auf den Microsoft-Such-Datenverkehr beziehen, werden in einen nicht-identifizierbaren Zustand versetzt. Sie werden für 18 Monate aufbewahrt.
  - Abfragen, die in diesen Systemprotokollen gespeichert werden, werden lediglich zum Modellieren und Trainieren von öffentlichen Features wie der Vorschlagssuche oder bei verwandten Suchvorgängen für öffentliche Webergebnisse verwendet, wenn eine Reihe von Einschränkungen und Frequenz-Schwellenwerten erfüllt sind, was uns das Vertrauen gibt, dass diese Abfragen allgemein und nicht für eine bestimmte Organisation spezifisch sind. Die Abfrage muss in einer bedeutenden Anzahl von Fällen in Verbindung mit Daten von Benutzern vorkommen, welche die Microsoft Suchfunktion nicht verwenden und die Abfrage darf nicht ausschließlich Enterprise-Suchergebnisse auslösen. Abfragen, die diese Anforderungen nicht erfüllen, werden getrennt vom öffentlichen, nicht von Microsoft durchgeführten Such Datenverkehr gespeichert.
  - Der eingeschränkte Zugriff wird über verschiedene Sicherheitsmechanismen verwaltet, einschließlich Sicherheitsgruppen und anderen Ebenen innerhalb des Engineering-Systems.
- Suchverlauf    
  - Wenn Sie mit einem Geschäfts- oder Schulkonto angemeldet sind, steht der Suchverlauf eines Benutzers nicht auf anderen Computern oder Geräten zur Verfügung.
 
- Werbung   
  - Suchabfragen von Unternehmen werden nie für Werbetreibende freigegeben und diesen auch nicht vorgeschlagen.
  - Werbung wird nie basierend auf der Arbeitsidentität oder Organisation eines Benutzers ausgerichtet.
    
## <a name="gdpr"></a>DSGVO

Der [Blogbeitrag vom 21. Mai 2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) von Microsoft bekräftigt unsere Verpflichtung zur Einhaltung der DSGVO und zeigt, wie Microsoft Unternehmen und Organisationen hilft, die eigenen DSGVO-Auflagen einzuhalten. Weitere Details finden Sie im Microsoft [Trust Center-FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search-Abfragen, die sich auf Kundendaten von Unternehmenskunden in Onlinediensten ungünstig auswirken, erfüllen ebenfalls die Verarbeitungspflichten aus Artikel 28, wie im [Trust Center-FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs) beschrieben. Im Hinblick auf Abfragen von Microsoft Search, die im öffentlichen Bing verwendet werden, gilt Microsoft als Datenverantwortlicher und hat Maßnahmen implementiert, um die Abfragen wie in der DSGVO beschrieben, unkenntlich zu machen.