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
# <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

Nachfolgend finden Sie eine Liste der am häufigsten gestellten Fragen.

> [!TIP]
> Ihre Frage wurde hier nicht beantwortet? Stellen Sie Ihre Frage im Feedback zu diesem Artikel.

## <a name="is-advanced-query-understanding-supported"></a>Wird das Verstehen von erweiterten Abfragen unterstützt?

Ja, Microsoft Search analysiert die Abfrageabsicht aus größeren Ausdrücken. Dieses Feature verwendet KI, um allgemeine überflüssige Ausdrücke zu erlernen, die Benutzer zu ihren Abfragen hinzufügen, die sich nicht auf ihre Suchabsicht auswirken. Wenn ein Benutzer z. B. nach informationen zum Ändern meines Kennworts *sucht,* extrahieren wir die weniger wichtigen Wörter aus der Abfrage und lösen sie basierend auf den relevanten Wörtern wie Kennwortänderung *aus.*
  
Mit diesem Feature werden im [Microsoft 365 Admin Center](https://admin.microsoft.com)festgelegte Schlüsselwörter nicht überschrieben.
  
## <a name="can-you-search-for-files-on-premises"></a>Können Sie nach lokalen Dateien suchen?

Ja. Sie können lokale [SharePoint-Dateien](http://sharepoint.com/) durchsuchen, wenn Sie über eine Hybridbereitstellung von SharePoint verfügen.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Wie kann ich Bing als Standardsuchmaschine für Personen in meiner Organisation festlegen?

Hier sind die Anweisungen zum Festlegen der Standardsuchmaschine, der Standardhomepage und des Standardbrowsers, um Ihren Benutzern die beste Erfahrung mit Microsoft Search in [Bing zu bieten:](https://Bing.com)

- [Festlegen von Microsoft Edge als Standardbrowser](/deployedge/edge-default-browser)
- [Festlegen von Bing als Standardsuchmaschine](set-default-search-engine.md)
- [Festlegen von Bing.com als Startseite des Unternehmens](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>Wie werden meine Suchergebnisse geschützt?

Für den Zugriff auf Ergebnisse aus der vertrauenswürdigen Cloud ist die [Azure Active](https://docs.microsoft.com/azure/active-directory/) Directory-Authentifizierung erforderlich. Authentifizierten Benutzern werden nur Inhalte angezeigt, auf die sie Zugriff haben. Suchabfragen werden nicht identifiziert, und Protokolle werden vom öffentlichen [Bing](https://Bing.com) -Suchdatenverkehr getrennt, wenn Sie Microsoft Search in Bing verwenden.

## <a name="can-i-search-across-federated-organizations"></a>Kann ich in Verbundorganisationen suchen?

Nein.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Wo finde ich Informationen zu Sicherheit, Compliance und Datenschutz in Office 365?

Details finden Sie auf den Seiten des [Trust Centers für Office 365.](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>Können Benutzer mit Ihrem Geschäfts-, Schul- oder Unikonto Microsoft Rewards-Punkte erwerben?

Microsoft Search setzt voraus, dass Unternehmensbenutzer sich mit einem Geschäfts-, Schul- oder Unikonto anmelden. Mit diesen Konten können sich Benutzer aber nicht beim Microsoft Rewards-Programm anmelden oder daran teilnehmen. Allerdings gibt es einen Fall, bei dem Unternehmensbenutzer möglicherweise sehen, dass Prämienpunkte anfallen. Dies kann vorkommen, wenn ein Microsoft Search-Benutzer über ein Rewards-Konto verfügt, das mit einem [Microsoft-Konto](https://www.microsoft.com/welcome?rtc=1) erstellt wurde. (Die mit einem Microsoft-Konto verknüpfte E-Mail-Adresse kann von Outlook.com, Hotmail.com, Gmail, Yahoo oder anderen Anbietern stammen.) Wenn Benutzer sich bei derselben Browsersitzung abwechselnd mit ihrem Geschäfts-, Schul- oder Unikonto und ihrem Microsoft-Konto anmelden, werden möglicherweise Punkte auf dem Rewards-Konto angesammelt. Benutzer können das Ansammeln von Punkten während der Suche mit Microsoft Search beenden, indem sie ihre Cookies löschen.

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>Können Gastbenutzer Microsoft Search in meiner Organisation nutzen?

Microsoft 365 ermöglicht eine umfassende Zusammenarbeit mit Personen außerhalb Ihrer Organisation durch [Gastzugriff.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Diese Benutzer können Suchvorgänge für Dokumente, Websites, Gruppen, Listen und Bibliotheken ausführen. Gastbenutzer erhalten jedoch nicht die vollständige, personalisierte Microsoft Search-Erfahrung und müssen möglicherweise das auf der Seite angezeigte Suchfeld anstelle des einheitlichen Microsoft Search-Felds in der Kopfzeile nutzen.
