---
title: Sicherheit und Datenschutz für Microsoft Search in Bing
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Schützen Sie die Daten und Endbenutzer Ihres Unternehmens, während Sie autorisierten Benutzern Informationen mit Microsoft Search in Bing
ms.openlocfilehash: 181a06ecb9c009d03c71e3e7f8ecfc7d675faa659967bc6a6c1560513a45a5ac
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532677"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Sicherheit und Datenschutz für Microsoft Search in Bing

Mit erweiterten Datenschutz- und Sicherheitsmaßnahmen trägt Microsoft Search in Bing zum Schutz Ihrer Benutzer- und Arbeitsplatzdaten bei.

## <a name="secure-by-default"></a>Standardmäßige Sicherheit

Microsoft Search in Bing Anforderungen erfolgen über HTTPS. Die Verbindung wird end-to-end verschlüsselt, um die Sicherheit zu erhöhen.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Authentifizierung und Autorisierung mit Azure Active Directory

Die Authentifizierung für Microsoft Search in Bing ist an Azure Active Directory gebunden. Wenn Microsoft Search Benutzer zu Bing wechseln, werden im Bing-Header Anmeldeoptionen für ein Microsoft-Konto sowie ein Geschäfts-, Schul- oder Unikonto angezeigt. Wenn Bing nicht feststellen können, ob ein Benutzer ein berechtigter Teilnehmer ist, können Benutzer die Seite ["Microsoft Search erkunden"](https://www.bing.com/business/explore) aufrufen, auf der sie automatisch zur Anmeldeseite Ihrer Organisation umgeleitet werden.

Benutzer können nur über ein Geschäfts- oder Schulkonto auf Microsoft Search zugreifen. Sie müssen sich mit denselben Anmeldeinformationen anmelden, mit denen sie auch Zugriff auf Office 365-Dienste wie SharePoint oder Outlook erhalten. Ein persönliches Microsoft-Konto kann nicht zum Anmelden bei Microsoft Search verwendet werden.

## <a name="single-sign-on"></a>Single Sign-On

Wenn ein Benutzer bereits mit dem Geschäfts-, Schul- oder Unikonto in einem anderen Dienst authentifiziert ist, z. B. Outlook oder SharePoint, wird er automatisch beim gleichen Geschäfts-, Schul- oder Unikonto angemeldet, wenn er im selben Browser zu Bing wechselt. Wenn sich der Benutzer von dem Geschäfts-, Schul- oder Unikonto abmeldet, wird er automatisch von anderen Microsoft Office Diensten im selben Browser abgemeldet.
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>Kommuniziert über den Browser mit der Microsoft-Cloud

Wenn sich ein Benutzer mit dem Geschäfts-, Schul- oder Unikonto anmeldet, lädt Bing die erforderlichen Clientbibliotheken in den Browser herunter, um Microsoft Search Ergebnisse zu ermöglichen. Bei der Suche ruft der browserinterne Code dann die Office 365 Cloud auf, um Arbeitsergebnisse zu erhalten. Hierzu verwendet Microsoft Search eine dedizierte API, die gemäß den Kontrollzielen von SSAE 18 SOC2 Typ 1 betrieben wird. Dies bedeutet, dass Arbeitsergebnisse und Arbeitsdaten nicht durch Bing Systeme fließen, die weniger strengen Kontrollzielen für die Datenverarbeitung unterliegen als die Arbeitsergebnisse selbst unterliegen, wenn sie in Office 365 Core Online Services verarbeitet werden.
  
## <a name="permissions"></a>Berechtigungen

Arbeitsergebnisse, die über Office 365-Workloads wie SharePoint und OneDrive for Business abgerufen werden, werden in der Quelle einer Sicherheitskürzung unterzogen. Benutzer können Ressourcen wie Word-Dokumente oder PowerPoint-Präsentationen, die sie nicht über Office 365 anzeigen oder auf die sie nicht über Office 365 zugreifen können, nicht anzeigen. Sie können nur ihre eigenen Dateien und Dateien anzeigen, die der Autor explizit oder implizit (z. B. über eine Gruppenmitgliedschaft) in SharePoint für sie freigegeben hat.

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Microsoft Search in Bing schützt die Arbeitsplatzsuchen

Wenn ein Benutzer eine Suchabfrage in Microsoft Search in Bing eingibt, treten zwei gleichzeitige Suchanforderungen auf:

- Eine Suche der internen Ressourcen Ihrer Organisation.
- Eine separate Suche nach öffentlichen Ergebnissen von Bing.com.

Da Die Arbeitsplatzsuchen möglicherweise vertraulich sind, hat Microsoft Search eine Reihe von Vertrauensmaßnahmen implementiert, die beschreiben, wie die separate Suche nach öffentlichen Ergebnissen von Bing.com behandelt wird.

### <a name="logging"></a>Protokollierung

- Alle Bing.com-Suchprotokolle, die sich auf Microsoft Search in Bing Datenverkehr beziehen, werden von Ihrer Arbeitsplatzidentität getrennt.
- Wenn eine Reihe von Einschränkungen oder Häufigkeitsschwellenwerten erreicht werden, die uns vertrauen, dass die Abfrage nicht spezifisch für eine bestimmte Organisation ist, wird die Abfrage wie im Abschnitt "Suche und künstliche Intelligenz" der [Datenschutzerklärung](https://privacy.microsoft.com/privacystatement)beschrieben behandelt. Solche Abfragen werden z. B. zum Modellieren und Trainieren öffentlicher Features verwendet, z. B. autouggest oder verwandte Suchvorgänge.
- Abfragen, die diese Einschränkungen oder Häufigkeitsschwellenwerte nicht erfüllen, werden getrennt vom öffentlichen, Nicht-Microsoft Search-Datenverkehr gespeichert.

### <a name="advertising"></a>Werbung

Werbung, die auf Bing.com in Verbindung mit Arbeitsplatzsuchen angezeigt wird, bezieht sich ausschließlich auf den Inhalt der Suchabfragen. Anzeigen sind niemals an Benutzer basierend auf Ihrer Arbeitsplatzidentität gerichtet.

## <a name="gdpr"></a>DSGVO

Der Blogbeitrag vom [21. Mai 2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) von Microsoft spiegelt unser Engagement für die Einhaltung der DSGVO wider und zeigt, wie Microsoft Unternehmen und Organisationen bei ihren eigenen DSGVO-Complianceverpflichtungen unterstützt. Weitere Details finden Sie in den [häufig gestellten Fragen](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)zum Microsoft Trust Center.

Microsoft Search Abfragen, die für die internen Ressourcen und Ergebnisse eines Kunden ausgeführt werden, gelten als Kundendaten und erfüllen daher auch die in Artikel 28 beschriebenen Verpflichtungen des Auftragsverarbeiters, wie in den häufig gestellten Fragen zum [Trust Center dargestellt.](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs) Im Hinblick auf Abfragen von Microsoft Search, die an öffentliche Bing gehen, hält Microsoft seine DSGVO-Verpflichtungen als Datenverantwortlicher ein.
