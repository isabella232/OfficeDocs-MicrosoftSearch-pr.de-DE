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
# <a name="security-for-microsoft-search"></a>Sicherheit für die Microsoft-Suche

Mit der Unternehmensklasse Sicherheit behält Microsoft Search immer Ihren Benutzern und Daten geschützt.
  
## <a name="secure-by-default"></a>Standardmäßig sicher

Microsoft Search wird immer sichergestellt, dass Anforderungen über HTTPS vorgenommen werden. Diese Sicherheitsvorkehrung wird sichergestellt, dass der verschlüsselten End-to-End für eine erweiterte Sicherheit ist.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Authentifizierung und Autorisierung mit Azure Active Directory

Authentifizierung für Microsoft Search ist mit Azure Active Directory verbunden. Beim Microsoft Search Benutzer auf Bing die Bing Anmeldeoptionen für ein Microsoft-Konto als Kopfzeile angezeigt sowie eine Arbeit oder Schule Konto. Wenn Bing nicht bestimmen kann, ob ein Benutzer bei einem berechtigte Teilnehmer ist, können Benutzer auf der Seite [Erkunden Sie Microsoft Search](https://www.bing.com/business/explore) wechseln, werden sie automatisch zu Ihrer Organisation-Anmeldeseite weitergeleitet werden. 
  
Benutzer können nur über ein Konto arbeiten oder Schule Microsoft Search zugreifen. Sie müssen sich mit denselben Anmeldeinformationen anzumelden, die sie Zugriff auf Office 365-Dienste wie SharePoint oder Outlook verwenden. Ein persönliches Microsoft-Konto kann nicht verwendet werden, zur Anmeldung bei Microsoft Search.
  
Benutzer können nicht bei Bing mit einem Microsoft-Konto und ein Konto arbeiten oder Schule gleichzeitig angemeldet sein.
  
## <a name="single-sign-on"></a>Einmaliges Anmelden

Wenn ein Benutzer bereits, ihre Arbeit oder Schule Konto in einen anderen Dienst, wie Outlook oder SharePoint authentifiziert ist, werden sie automatisch auf Microsoft Search angemeldet werden Wenn sie in den gleichen Browser auf Bing zugreifen. Auch wenn der Benutzer Microsoft Search abmeldet, werden sie automatisch von anderen Diensten im gleichen Browser abgemeldet.
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>Kommuniziert mit der Cloud vertrauenswürdige vom browser

Wenn ein Benutzer anmeldet mit ihrer Arbeit oder Schule Bing-Konto wird die erforderlichen Client-Bibliotheken an den Browser So aktivieren Sie Microsoft Search Results herunterladen. Klicken Sie dann bei der Suche, ruft der Code im Browser die Office 365-Cloud um Arbeit Ergebnisse zu erhalten. Zu diesem Zweck verwendet Microsoft Search eine dedizierte API, die Tier C (SOC2 type1) nach Office 365 [Compliance-Framework für Branchenstandards und Vorschriften](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF-Datei zum Herunterladen) kompatibel ist. Dies bedeutet, dass die Ergebnisse von Arbeit und Arbeitsdaten flow nie über nicht kompatible Bing-Systeme. 
  
## <a name="permissions"></a>Berechtigungen

Arbeit Ergebnisse von Office 365-Arbeitslasten abgerufen, wie SharePoint und OneDrive für Unternehmen Sicherheit werden abgeschnitten an der Quelle. Benutzer Ressourcen wie Word-Dokumente oder PowerPoint-Präsentationen keine finden Sie unter, und greifen Sie auf über Office 365 nicht angezeigt werden. Sie können nur sehen, ihre eigenen Dateien und Dateien, die mit diesen vom Autor implizit oder explizit freigegeben wurden (über eine Gruppenmitgliedschaft beispielsweise) in SharePoint.
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Schützt Benutzerabfragen aus dem öffentlichen Bereich der Bing

Da arbeitsbezogene Suchvorgänge vertrauliche sein können, hat Microsoft Search implementiert eine Reihe von Vertrauensstellung Maßnahmen zur wie dies vom öffentlichen Ergebnisse Webpart der Bing behandelt werden.
  
Unabhängig davon, ob eine Benutzerabfrage eines oder mehrere Arbeit Ergebnisse in der zurückgegebenen Antwort enthält werden folgende Maßnahmen ergriffen:
  
- Protokollierung
    
  - Alle Microsoft Search-Datenverkehr zur Suche-Protokolle sind Aufhebung der identifiziert und getrennt von öffentlichen, nicht - Microsoft Search Datenverkehr gespeichert werden. Sie sind 18 Monate beibehalten, und der Zugriff ist nur zu Debuggingzwecken eingeschränkt.
    
  - Die Abfragen in diese Protokolle werden nicht auf Model oder Zug öffentliche Features wie etwa AutoVorschlagen oder verwandte Suchvorgänge für das öffentliche Internet verwendet.
    
  - Eingeschränkter Zugriff wird über verschiedene sichere Mechanismen, einschließlich der Sicherheitsgruppen und anderen Ebenen in das Entwicklungssystem verwaltet.
    
- Suchverlauf
    
  - Wenn eine Signatur mit einem Konto arbeiten oder Schule wird nicht Suchverlauf eines Benutzers auf anderen Computern oder Geräten verfügbar sein.
    
- Werbung
    
  - Enterprise Search-Abfragen sind niemals freigegeben oder um Werbekunden vorgeschlagen.
    
  - Suche Ads-Protokolle für Microsoft Search werden separat von öffentlichen Datenverkehr gespeichert.
    
  - ADS werden nie auf einen Benutzer basierend auf ihrer arbeitsidentität oder Organisation abgestimmt.
    
## <a name="gdpr"></a>DSGVO

Der [Blogbeitrag von 21 Mai 2018,](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) von Microsoft enthät unser Engagement für GDPR Compliance und Microsoft Unternehmen und Organisationen mit ihren eigenen GDPR Auflagen Schutzmechanismen in. Weitere Einzelheiten finden Sie in der Microsoft- [Trust Center häufig gestellte Fragen](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search-Abfragen, die gegen Organisationseinheit Kunden Kundendaten innerhalb der Online-Dienste ausgeführt werden, werden auch die Prozessor Zusagen beschriebenen Artikel 28 im [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)erfüllen. Microsoft in Bezug auf Abfragen von Microsoft Search, die an öffentliche Bing umgeleitet wird, ist ein Controller Daten und wurde implementiert, um die Abfragen identifizieren Aufhebung der gemäß GDPR Maßnahmen.


