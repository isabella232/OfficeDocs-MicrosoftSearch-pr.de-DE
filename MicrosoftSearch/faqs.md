---
title: FAQs
ms.author: anfowler
author: adefowler
manager: shohara
ms.date: 10/19/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: cd3ee09d-58ab-4b8a-8822-fa11a1399672
ROBOTS: NoIndex
description: Erhalten Sie Antworten auf häufig gestellte Fragen zur Unternehmenssuche und zu Microsoft Search
ms.openlocfilehash: 3b30980c76915405767381fb3b6397468bdd1b68
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639501"
---
# <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

Nachfolgend finden Sie eine Liste der am häufigsten gestellten Fragen.

> [!TIP]
> Ihre Frage wurde hier nicht beantwortet? Stellen Sie Ihre Frage im Feedback zu diesem Artikel.

## <a name="is-advanced-query-understanding-supported"></a>Wird das Verstehen von erweiterten Abfragen unterstützt?

Ja, bei umfangreicheren Ausdrücken analysiert Microsoft Search die Abfrageabsicht. Dieses Feature verwendet KI, um häufig von Benutzern hinzugefügte, überflüssige Ausdrücke zu lernen, die für die Absicht der Suche nicht relevant sind. Wenn ein Benutzer z. B. die Suche "Gib mir bitte Informationen dazu, wie ich mein Kennwort ändern kann" eingibt, werden die weniger wichtigen Wörter aus der Abfrage entfernt. Die Abfrage wird dann basierend auf den relevanten Wörtern, wie z. B. "Kennwort ändern", durchgeführt.
  
Dieses Feature setzt im Admin Center festgelegte Schlüsselwörter nicht außer Kraft.
  
## <a name="can-you-search-for-files-on-premises"></a>Können Sie nach lokalen Dateien suchen?

Ja. Sie können lokale SharePoint-Dateien durchsuchen, wenn Sie über eine Hybridbereitstellung von SharePoint verfügen.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Wie kann ich Bing als Standardsuchmaschine für Personen in meiner Organisation festlegen?

Hier finden Sie die Anweisungen zum Festlegen der Standardsuchmaschine, der Standardstartseite und des Standardbrowsers, um Ihren Benutzern die optimale Erfahrung mit Microsoft Search in Bing zu ermöglichen:

- [Festlegen von Edge als Standardbrowser](set-default-browser.md)
- [Festlegen von Bing als Standardsuchmaschine](set-default-search-engine.md)
- [Festlegen von Bing.com als Startseite des Unternehmens](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a>Wie werden meine Suchergebnisse geschützt?

Für den Zugriff auf Ergebnisse aus der vertrauenswürdigen Cloud ist Azure Active Directory-Authentifizierung erforderlich. Authentifizierten Benutzern werden nur Inhalte angezeigt, auf die sie Zugriff haben. Suchabfragen werden anonymisiert und Protokolle vom Datenverkehr öffentlicher Bing-Suchen getrennt. Ein solcher Grad an Schutz steht sonst in der Branche nicht zur Verfügung.

## <a name="can-i-search-across-federated-organizations"></a>Kann ich in Verbundorganisationen suchen?

Nein.

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a>Wo erhalte ich Informationen zu Office 365- und Microsoft 365 -Compliance-Ebenen und -Kategorien?

Details finden Sie in der [Compliance-Framework für Branchenstandards und gesetzliche Vorschriften](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF-Download).