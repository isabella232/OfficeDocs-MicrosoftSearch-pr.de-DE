---
title: Sicherheit und Datenschutz für die Microsoft-Suche in Bing
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
description: Schützen der Daten Ihres Unternehmens und der Endbenutzer bei der Bereitstellung von Informationen für autorisierte Benutzer mit Microsoft Search in Bing
ms.openlocfilehash: 1cc00a3b14b1918903c9aa34a24f13b1761b64b6
ms.sourcegitcommit: 5946fe6aad2331c023bedda8faf826c0248651f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41711752"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Sicherheit und Datenschutz für die Microsoft-Suche in Bing

Mit verbesserten Datenschutz-und Sicherheitsmaßnahmen hilft Microsoft Search in Bing, Ihre Benutzer und Arbeitsplatzdaten zu schützen.

## <a name="secure-by-default"></a>Standardmäßige Sicherheit

Die Microsoft-Suche in Bing-Anforderungen erfolgt über HTTPS. Die Verbindung ist durchgängig verschlüsselt, um die Sicherheit zu erhöhen.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Authentifizierung und Autorisierung mit Azure Active Directory

Die Authentifizierung für Microsoft Search in Bing ist an Azure Active Directory gebunden. Wenn Microsoft Search-Benutzer zu Bing wechseln, werden in der Bing-Kopfzeile Anmeldeoptionen für ein Microsoft-Konto sowie ein Arbeits-oder Schulkonto angezeigt. Wenn Bing nicht ermitteln kann, ob ein Benutzer ein berechtigter Teilnehmer ist, können Benutzer zur Seite [Microsoft-Suche durch](https://www.bing.com/business/explore) suchen wechseln, auf der Sie automatisch zur Anmeldeseite Ihrer Organisation umgeleitet werden.

Benutzer können nur über ein Geschäfts- oder Schulkonto auf Microsoft Search zugreifen. Sie müssen sich mit denselben Anmeldeinformationen anmelden, mit denen sie auch Zugriff auf Office 365-Dienste wie SharePoint oder Outlook erhalten. Ein persönliches Microsoft-Konto kann nicht zum Anmelden bei Microsoft Search verwendet werden.

## <a name="single-sign-on"></a>Einmaliges Anmelden

Wenn ein Benutzer bereits mit seinem Arbeits-oder Schulkonto in einem anderen Dienst wie Outlook oder SharePoint authentifiziert ist, wird er automatisch beim gleichen Arbeits-oder Schulkonto angemeldet, wenn er im selben Browser zu Bing geht. Wenn sich der Benutzer von seinem geschäftlichen oder Schulkonto abmeldet, wird er auch automatisch von anderen Microsoft Office Diensten im gleichen Browser abgemeldet.
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>Kommuniziert mit der Microsoft-Cloud aus dem Browser

Wenn sich ein Benutzer mit seinem geschäftlichen oder Schulkonto anmeldet, lädt Bing die erforderlichen Clientbibliotheken in den Browser herunter, um die Microsoft-Suchergebnisse zu aktivieren. Bei der Suche ruft der in-Browser-Code die Office 365 Cloud auf, um Arbeitsergebnisse zu erhalten. Zu diesem Zweck verwendet Microsoft Search eine dedizierte API, die gemäß den Steuerungs Zielen von SSAE 18 SOC2 Typ 1 betrieben wird. Dies bedeutet, dass Arbeitsergebnisse und Arbeitsdaten nicht durch Bing-Systeme fließen, die weniger strengen Steuerungs Zielen für die Datenverarbeitung unterliegen als die Arbeitsergebnisse, die bei der Verarbeitung in Office 365 Kern Online Dienste unterliegen.
  
## <a name="permissions"></a>Berechtigungen

Arbeitsergebnisse, die über Office 365-Workloads wie SharePoint und OneDrive for Business abgerufen werden, werden in der Quelle einer Sicherheitskürzung unterzogen. Benutzer können Ressourcen wie Word-Dokumente oder PowerPoint-Präsentationen, die sie nicht über Office 365 anzeigen oder auf die sie nicht über Office 365 zugreifen können, nicht anzeigen. Sie können nur ihre eigenen Dateien und Dateien anzeigen, die der Autor explizit oder implizit (z. B. über eine Gruppenmitgliedschaft) in SharePoint für sie freigegeben hat.

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Microsoft-Suche in Bing schützt Arbeitsplatzsuche

Wenn ein Benutzer in Bing eine Suchabfrage in Microsoft Search eingibt, treten zwei gleichzeitige Suchanforderungen auf:

- Eine Suche nach internen Ressourcen Ihrer Organisation.
- Eine getrennte Suche nach öffentlichen Ergebnissen aus Bing.com.

Da Arbeitsplatz suchen möglicherweise vertraulich sind, hat Microsoft Search eine Reihe von Vertrauensmaßnahmen implementiert, in denen beschrieben wird, wie die getrennte Suche nach öffentlichen Ergebnissen aus Bing.com behandelt wird.

### <a name="logging"></a>Protokollierung

- Alle Bing.com-Suchprotokolle, die sich auf die Microsoft-Suche in Bing-Datenverkehr beziehen, werden von der Identität Ihres Arbeitsplatzes nicht zugeordnet.
- Wenn eine Reihe von Einschränkungen oder Frequenz Schwellenwerten erfüllt werden, die uns Vertrauen, dass die Abfrage nicht für eine bestimmte Organisation spezifisch ist, wird die Abfrage wie im Abschnitt Suchen und künstliche Intelligenz der [Datenschutz](https://privacy.microsoft.com/privacystatement)Richtlinie beschrieben behandelt. Beispielsweise werden solche Abfragen verwendet, um öffentliche Features wie Autosuggestion oder Verwandte Suchvorgänge zu modellieren und zu trainieren.
- Abfragen, die diese Einschränkungen oder Häufigkeitsschwellenwerte nicht erfüllen, werden getrennt vom öffentlichen, Nicht-Microsoft Search-Datenverkehr gespeichert.

### <a name="advertising"></a>Werbung

Werbung, die in Bing.com im Zusammenhang mit der Arbeitsplatzsuche angezeigt wird, bezieht sich ausschließlich auf den Inhalt der Suchabfragen. Anzeigen sind niemals an Benutzer basierend auf Ihrer Arbeitsplatzidentität gerichtet.

## <a name="gdpr"></a>DSGVO

Der [Blogbeitrag von Microsoft vom 21. Mai 2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) spiegelt unser Engagement für dsgvo Compliance wider und wie Microsoft Unternehmen und Organisationen mit ihren eigenen dsgvo-Compliance-Verpflichtungen hilft. Weitere Informationen finden Sie im Microsoft [Trust Center-FAQ](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs).

Microsoft-Suchabfragen, die für die internen Ressourcen eines Kunden ausgeführt werden und zurückgegebene Ergebnisse werden als Kundendaten betrachtet und erfüllen daher auch die in Artikel 28 beschriebenen Prozessor Zusagen, wie Sie in den [Trust Center-häufig](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)gestellten Fragen beschrieben werden. In Bezug auf Abfragen von Microsoft Search, die zu Public Bing wechseln, erfüllt Microsoft die dsgvo-Verpflichtungen als Daten Verantwortlicher.
