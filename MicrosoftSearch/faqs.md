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
ms.openlocfilehash: 84f53755625e65328f8ffe8aabf78f93a9a36a22
ms.sourcegitcommit: 5151bcd8fd929ef37239b7c229e2fa33b1e0e0b7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235867"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

Nachfolgend finden Sie eine Liste der am häufigsten gestellten Fragen.

> [!TIP]
> Ihre Frage wurde hier nicht beantwortet? Stellen Sie Ihre Frage im Feedback zu diesem Artikel.

## <a name="is-advanced-query-understanding-supported"></a>Wird das Verstehen von erweiterten Abfragen unterstützt?

Ja, Microsoft Search analysiert die Abfrageabsicht anhand größerer Ausdrücke. Dieses Feature verwendet KI, um allgemeine überflüssige Ausdrücke zu lernen, die Benutzer zu ihren Abfragen hinzufügen, die sich nicht auf ihre Suchabsicht auswirken. For example, when a user searches for *tell me more about how to change my password*, we extract the less important words from the query and trigger based on the relevant ones like change *password*.
  
Dieses Feature setzt schlüsselwörter, die im [Microsoft 365 Admin Center](https://admin.microsoft.com)festgelegt sind, nicht außer Kraft.
  
## <a name="can-you-search-for-files-on-premises"></a>Können Sie nach lokalen Dateien suchen?

Ja. Sie können lokale [SharePoint](http://sharepoint.com/) Dateien durchsuchen, wenn Sie über eine Hybridbereitstellung von SharePoint verfügen.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Wie kann ich Bing als Standardsuchmaschine für Personen in meiner Organisation festlegen?

Nachfolgend finden Sie die Anweisungen zum Festlegen der Standardsuchmaschine, der Standardstartseite und des Standardbrowsers, um Ihren Benutzern die bestmögliche Erfahrung mit Microsoft Search in [Bing](https://Bing.com)zu bieten:

- [Festlegen Microsoft Edge als Standardbrowser](/deployedge/edge-default-browser)
- [Festlegen von Bing als Standardsuchmaschine](set-default-search-engine.md)
- [Festlegen von Bing.com als Startseite des Unternehmens](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>Wie werden meine Suchergebnisse geschützt?

Wir benötigen [Azure Active Directory](/azure/active-directory/) Authentifizierung, um auf Ergebnisse aus der vertrauenswürdigen Cloud zuzugreifen. Authentifizierten Benutzern werden nur Inhalte angezeigt, auf die sie Zugriff haben. Bei Verwendung von Microsoft Search in Bing werden Suchabfragen entfernt, und Protokolle werden vom öffentlichen [Bing](https://Bing.com) Suchdatenverkehr getrennt.

## <a name="can-i-search-across-federated-organizations"></a>Kann ich in Verbundorganisationen suchen?

Nein.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Wo erhalte ich Informationen zu Office 365 Sicherheit, Compliance und Datenschutz?

Details finden Sie auf den [Trust Center-Seiten für Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-guest-users-access-microsoft-search-in-my-organization"></a>Können Gastbenutzer in meiner Organisation auf Microsoft Search zugreifen?

Microsoft 365 ermöglicht eine umfassende Zusammenarbeit mit Personen außerhalb Ihrer Organisation durch [Gastzugriff.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Diese Benutzer können nach Dokumenten, Websites, Gruppen, Listen und Bibliotheken suchen. Gastbenutzer erhalten jedoch nicht die vollständige, personalisierte Microsoft Search Oberfläche und müssen möglicherweise das Suchfeld auf der Seite anstelle des einheitlichen Microsoft Search felds in der Kopfzeile verwenden.

## <a name="how-do-i-turn-microsoft-search-in-bing-on-or-off"></a>Wie kann ich Microsoft Search in Bing ein- oder ausschalten?

Für die meisten Organisationen, einschließlich Unternehmen und Bildungseinrichtungen, ist Microsoft Search in Bing standardmäßig aktiviert. Um Microsoft Search in Bing zu aktivieren, wechseln Sie zur Seite ["Konfigurationen"](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/configurations) im Microsoft 365 Admin Center. Wählen Sie unter Microsoft Search in Bing Einstellungen die Option **"Einstellungen ändern"** aus, und aktivieren Sie **"Zulassen, dass Ihre Organisation Microsoft Search in Bing verwendet.** Es dauert bis zu 24 Stunden, bis diese Änderung wirksam wird.

Wenn diese Einstellung deaktiviert ist, erhalten Benutzer keine internen Ergebnisse, wenn sie nach Bing, Windows Suche oder in Microsoft Edge suchen. Das Deaktivieren Microsoft Search in Bing beendet oder verhindert nicht, dass interne Inhalte zu Ihrem Suchindex hinzugefügt werden. Es deaktiviert nur Bing Einstiegspunkte für Microsoft Search. Um Antworten und interne Ergebnisse zu finden, müssen Benutzer andere Einstiegspunkte verwenden, z. B. SharePoint Online oder eine Office 365-App.
