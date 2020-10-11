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
ms.openlocfilehash: 5a134116c98b4feea0c04909349ce4b972c59ffe
ms.sourcegitcommit: 0b8c3c57384cecaa93c5cbaf3b3b30f8e20d1a69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408438"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

Nachfolgend finden Sie eine Liste der am häufigsten gestellten Fragen.

> [!TIP]
> Ihre Frage wurde hier nicht beantwortet? Stellen Sie Ihre Frage im Feedback zu diesem Artikel.

## <a name="is-advanced-query-understanding-supported"></a>Wird das Verstehen von erweiterten Abfragen unterstützt?

Ja, die Microsoft-Suche analysiert Abfrage Absicht aus größeren Ausdrücken. Dieses Feature verwendet AI, um allgemeine überflüssige Ausdrücke zu erfahren, die Benutzer zu Ihren Abfragen hinzufügen, die sich nicht auf die suchabsicht auswirken. Wenn ein Benutzer beispielsweise nach " *Weitere Informationen" zum Ändern des Kennworts*sucht, extrahieren wir die weniger wichtigen Wörter aus der Abfrage und dem Auslöser basierend auf den entsprechenden wie das *Kennwort ändern*.
  
Dieses Feature überschreibt keine Stichwörter, die im [Microsoft 365 Admin Center](https://admin.microsoft.com)festgelegt sind.
  
## <a name="can-you-search-for-files-on-premises"></a>Können Sie nach lokalen Dateien suchen?

Ja. Sie können lokale [SharePoint](http://sharepoint.com/) -Dateien durchsuchen, wenn Sie über eine hybridbereitstellung von SharePoint verfügen.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Wie kann ich Bing als Standardsuchmaschine für Personen in meiner Organisation festlegen?

Hier finden Sie die Anweisungen zum Festlegen der standardmäßigen Suchmaschine, der Standardstartseite und des Standardbrowsers, damit Ihre Benutzer die besten Erfahrungen mit der Microsoft-Suche in [Bing](https://Bing.com)erhalten:

- [Festlegen von Microsoft Edge als Standardbrowser](set-default-browser.md)
- [Festlegen von Bing als Standardsuchmaschine](set-default-search-engine.md)
- [Festlegen von Bing.com als Startseite des Unternehmens](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>Wie werden meine Suchergebnisse geschützt?

Für den Zugriff auf Ergebnisse aus der vertrauenswürdigen Cloud ist die [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) -Authentifizierung erforderlich. Authentifizierten Benutzern werden nur Inhalte angezeigt, auf die sie Zugriff haben. Suchabfragen werden nicht identifiziert, und Protokolle werden vom öffentlichen [Bing](https://Bing.com) -Such Datenverkehr getrennt. Ein solcher Grad an Schutz steht sonst in der Branche nicht zur Verfügung.

## <a name="can-i-search-across-federated-organizations"></a>Kann ich in Verbundorganisationen suchen?

Nein.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Wo erhalte ich Informationen zu Office 365 Sicherheit, Compliance und Datenschutz?

Details finden Sie auf den [Vertrauensstellungs Center-Seiten für Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>Können Benutzer mit Ihrem Geschäfts-, Schul- oder Unikonto Microsoft Rewards-Punkte erwerben?

Microsoft Search setzt voraus, dass Unternehmensbenutzer sich mit einem Geschäfts-, Schul- oder Unikonto anmelden. Mit diesen Konten können sich Benutzer aber nicht beim Microsoft Rewards-Programm anmelden oder daran teilnehmen. Allerdings gibt es einen Fall, bei dem Unternehmensbenutzer möglicherweise sehen, dass Prämienpunkte anfallen. Dies kann vorkommen, wenn ein Microsoft Search-Benutzer über ein Rewards-Konto verfügt, das mit einem [Microsoft-Konto](https://www.microsoft.com/welcome?rtc=1) erstellt wurde. (Die mit einem Microsoft-Konto verknüpfte E-Mail-Adresse kann von Outlook.com, Hotmail.com, Gmail, Yahoo oder anderen Anbietern stammen.) Wenn Benutzer sich bei derselben Browsersitzung abwechselnd mit ihrem Geschäfts-, Schul- oder Unikonto und ihrem Microsoft-Konto anmelden, werden möglicherweise Punkte auf dem Rewards-Konto angesammelt. Benutzer können das Ansammeln von Punkten während der Suche mit Microsoft Search beenden, indem sie ihre Cookies löschen.

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>Können Gastbenutzer die Microsoft-Suche in meiner Organisation nutzen?

Microsoft 365 ermöglicht eine umfassende Zusammenarbeit mit Personen außerhalb Ihrer Organisation über [Gastzugriff.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Diese Benutzer können Suchvorgänge für Dokumente, Websites, Gruppen, Listen und Bibliotheken durchführen. Gastbenutzer erhalten jedoch nicht die vollständige, personalisierte Microsoft-Suchumgebung und müssen möglicherweise das Feld "on-page Suchfeld" anstelle des vereinheitlichten Microsoft-Suchfeld in der Kopfzeile nutzen.
