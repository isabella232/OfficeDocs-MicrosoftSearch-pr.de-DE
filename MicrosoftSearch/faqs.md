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
# <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

Nachfolgend finden Sie eine Liste der am häufigsten gestellten Fragen.

> [!TIP]
> Ihre Frage wurde hier nicht beantwortet? Stellen Sie Ihre Frage im Feedback zu diesem Artikel.

## <a name="is-advanced-query-understanding-supported"></a>Wird das Verstehen von erweiterten Abfragen unterstützt?

Ja, Microsoft Search analysiert Abfrageabsichten aus größeren Ausdrücken. Dieses Feature verwendet KI, um allgemeine überflüssige Ausdrücke zu lernen, die Benutzer zu ihren Abfragen hinzufügen, die sich nicht auf ihre Suchabsicht auswirken. Wenn ein Benutzer z. B. nach weiteren Informationen zum Ändern meines Kennworts *sucht,* extrahieren wir die weniger wichtigen Wörter aus der Abfrage und lösen sie basierend auf den relevanten Wörtern wie Änderungskennwort *aus.*
  
Dieses Feature überschreibt keine Schlüsselwörter, die im Microsoft 365 [Admin Center festgelegt sind.](https://admin.microsoft.com)
  
## <a name="can-you-search-for-files-on-premises"></a>Können Sie nach lokalen Dateien suchen?

Ja. Sie können lokale Dateien [SharePoint,](http://sharepoint.com/) wenn Sie über eine Hybridbereitstellung von SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Wie kann ich Bing als Standardsuchmaschine für Personen in meiner Organisation festlegen?

Hier finden Sie die Anweisungen zum Festlegen der Standardsuchmaschine, der Standardhomepage und des Standardbrowsers, um Ihren Benutzern die beste Erfahrung mit Microsoft Search [in](https://Bing.com)Bing:

- [Festlegen Microsoft Edge als Standardbrowser](/deployedge/edge-default-browser)
- [Festlegen von Bing als Standardsuchmaschine](set-default-search-engine.md)
- [Festlegen von Bing.com als Startseite des Unternehmens](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>Wie werden meine Suchergebnisse geschützt?

Wir benötigen [Azure Active Directory](/azure/active-directory/) Authentifizierung, um auf Ergebnisse aus der vertrauenswürdigen Cloud zu zugreifen. Authentifizierten Benutzern werden nur Inhalte angezeigt, auf die sie Zugriff haben. Suchabfragen werden nicht identifiziert, und Protokolle [](https://Bing.com) werden vom Bing öffentlichen Datenverkehr getrennt, wenn Sie Microsoft Search in Bing.

## <a name="can-i-search-across-federated-organizations"></a>Kann ich in Verbundorganisationen suchen?

Nein.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Wo kann ich Informationen zu Office 365, Compliance und Datenschutz erhalten?

Details finden Sie auf den [Trust Center-Seiten für Office 365.](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>Können Gastbenutzer Microsoft Search in meiner Organisation nutzen?

Microsoft 365 ermöglicht eine umfassende Zusammenarbeit mit Personen außerhalb Ihrer Organisation über [den Gastzugriff.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Diese Benutzer können Suchvorgänge für Dokumente, Websites, Gruppen, Listen und Bibliotheken ausführen. Gastbenutzer erhalten jedoch nicht die vollständige, personalisierte Microsoft Search-Erfahrung und müssen möglicherweise das Auf-Seite-Suchfeld anstelle des einheitlichen Microsoft Search-Felds in der Kopfzeile nutzen.