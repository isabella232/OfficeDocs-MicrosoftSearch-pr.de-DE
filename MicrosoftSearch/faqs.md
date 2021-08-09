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
ms.openlocfilehash: 94161d3ac53ca72a9f8298674a53fdaa0a80caaf5ca3802d47ea693043a30530
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533932"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

Nachfolgend finden Sie eine Liste der am häufigsten gestellten Fragen.

> [!TIP]
> Ihre Frage wurde hier nicht beantwortet? Stellen Sie Ihre Frage im Feedback zu diesem Artikel.

## <a name="is-advanced-query-understanding-supported"></a>Wird das Verstehen von erweiterten Abfragen unterstützt?

Ja, Microsoft Search die Abfrageabsicht anhand größerer Ausdrücke analysiert. Dieses Feature verwendet KI, um allgemeine überflüssige Ausdrücke zu lernen, die Benutzer zu ihren Abfragen hinzufügen, die sich nicht auf ihre Suchabsicht auswirken. For example, when a user searches for *tell me more about how to change my password*, we extract the less important words from the query and trigger based on the relevant ones like change *password*.
  
Dieses Feature setzt schlüsselwörter, die im [Microsoft 365 Admin Center](https://admin.microsoft.com)festgelegt sind, nicht außer Kraft.
  
## <a name="can-you-search-for-files-on-premises"></a>Können Sie nach lokalen Dateien suchen?

Ja. Sie können lokale [SharePoint](http://sharepoint.com/) Dateien durchsuchen, wenn Sie über eine Hybridbereitstellung von SharePoint verfügen.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Wie kann ich Bing als Standardsuchmaschine für Personen in meiner Organisation festlegen?

Nachfolgend finden Sie die Anweisungen zum Festlegen der Standardsuchmaschine, der Standardstartseite und des Standardbrowsers, um Ihren Benutzern die bestmögliche Erfahrung mit Microsoft Search in [Bing](https://Bing.com)zu bieten:

- [Festlegen Microsoft Edge als Standardbrowser](/deployedge/edge-default-browser)
- [Festlegen von Bing als Standardsuchmaschine](set-default-search-engine.md)
- [Festlegen von Bing.com als Startseite des Unternehmens](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>Wie werden meine Suchergebnisse geschützt?

Wir benötigen [Azure Active Directory](/azure/active-directory/) Authentifizierung, um auf Ergebnisse aus der vertrauenswürdigen Cloud zuzugreifen. Authentifizierten Benutzern werden nur Inhalte angezeigt, auf die sie Zugriff haben. Suchabfragen werden anonymisiert, und Protokolle werden von öffentlichem [Bing](https://Bing.com) Suchdatenverkehr getrennt, wenn Sie Microsoft Search in Bing verwenden.

## <a name="can-i-search-across-federated-organizations"></a>Kann ich in Verbundorganisationen suchen?

Nein.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Wo erhalte ich Informationen zu Office 365 Sicherheit, Compliance und Datenschutz?

Details finden Sie auf den [Trust Center-Seiten für Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>Können Gastbenutzer Microsoft Search in meiner Organisation nutzen?

Microsoft 365 ermöglicht eine umfassende Zusammenarbeit mit Personen außerhalb Ihrer Organisation durch [Gastzugriff.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Diese Benutzer können Suchvorgänge für Dokumente, Websites, Gruppen, Listen und Bibliotheken ausführen. Gastbenutzer erhalten jedoch nicht die vollständige, personalisierte Microsoft Search Erfahrung und müssen möglicherweise das Suchfeld auf der Seite anstelle des einheitlichen Microsoft Search felds in der Kopfzeile nutzen.