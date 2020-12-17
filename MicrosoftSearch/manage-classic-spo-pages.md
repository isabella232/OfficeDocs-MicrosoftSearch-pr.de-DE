---
title: Klassische Seiten in SharePoint Online und Microsoft-Suche
ms.author: keremy
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
description: Verwenden der Microsoft-Suche auf klassischen SharePoint-Seiten
ms.openlocfilehash: 605e63a30ad166c63320c7e89e1b2745e628e15d
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700973"
---
# <a name="classic-pages-and-microsoft-search"></a>Klassische Seiten und Microsoft-Suche

SharePoint-Websites, die vor modernen Websites erstellt wurden, verwenden ein klassisches Suchfeld und eine klassische Suchergebnis Erfahrung. Wir werden ein Feature bereitstellen, das standardmäßig die klassischen Seiten verwendet, um die moderne Suchumgebung zu verwenden, die die Microsoft-Suche verwendet, wodurch personalisierte Ergebnisse mit höherer Relevanz bereitgestellt werden.

Die Verwendung von Microsoft Search wird für alle Websites, einschließlich Classic, empfohlen, aber wenn Ihre klassischen Websites benutzerdefinierte Gestaltungsvorlagen verwenden und/oder Sie Ihre klassischen Suchergebnisse angepasst haben, werden wir diese Anpassungen automatisch erkennen und nicht zur Microsoft-Suche wechseln.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Klassische Websites, die automatisch zur Microsoft-Suche gewechselt werden

Bei klassischen Websites wird Microsoft Search verwendet, wenn alle der folgenden Kriterien zutreffen.

* Die Website basiert auf der Vorlage für die Teamwebsite (wie STS # 0 und STS # 1).
* Auf der Website ist das Veröffentlichungsfeature nicht aktiviert.
* Die Website verwendet keine benutzerdefinierte Gestaltungsvorlage (eine andere Gestaltungsvorlage als Oslo. Master oder Seattle. Master).
* Es gibt keine aktiven Abfrageregeln außer denen, die höher gestufte Ergebnisse für die Website, Websitesammlung oder den Mandanten in der Standardergebnis Quelle hinzufügen.
* Es gibt keine benutzerdefinierten Ergebnistypen für die Website oder die Websitesammlung in der Standardergebnis Quelle.
* Die Website oder die Websitesammlung, in der Sie enthalten ist, hat sich nicht aus dem Switch mit der unten beschriebenen SearchBoxInNavBar-Einstellung entschieden.

Nach dem Wechsel zur Microsoft-Suche wird durch die klassischen Seiten der Website das Suchfeld in der Suite-Navigationsleiste angezeigt und das klassische Suchfeld von der Seite entfernt. Wenn ein Benutzer nach einem Begriff sucht, werden die Ergebnisse dann mithilfe der modernen Suchumgebung von Microsoft Search angezeigt.

## <a name="staying-with-the-classic-search-experience"></a>Wohnen mit der klassischen Suchumgebung

Wenn Ihre Website die oben aufgeführten Kriterien erfüllt, Sie jedoch nicht zu der Microsoft-Suchumgebung wechseln möchten, können Sie die folgenden Befehle als Website-oder Websitesammlungsbesitzer deaktivieren.

Sie können diesen Befehl jederzeit verwenden, bevor oder nachdem der Wechsel erfolgt ist, sodass es einfach ist, wieder zu der zuvor verwendeten Suchumgebung zurückzukehren.

Um die folgenden Befehle auszuführen, verwenden Sie PowerShell mit SharePoint PNP PowerShell Extensions. Sie können die ersten Schritte [hier](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)installieren und weitere Informationen dazu erhalten. Sie melden sich bei Ihrer Website oder Websitesammlung mit folgendem Befehl an:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials
```

Führen Sie den folgenden Befehl aus, um mit der klassischen Suchumgebung für eine Website zu bleiben:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Alternativ können Sie diesen Befehl verwenden, wenn Sie ihn für alle Websites in einer Websitesammlung festlegen möchten:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Opting in Microsoft Search

Für Websites, die die oben aufgeführten Kriterien nicht erfüllen, oder für bestimmte Websites in einer Websitesammlung, die sich für den klassischen Aufenthalt entschieden haben, können Sie die Microsoft-Suchumgebung manuell aktivieren.

Um diese Einstellung für eine bestimmte Website zu ändern, können Sie diesen Befehl verwenden:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

Wenn Sie es für alle Websites in einer Websitesammlung festlegen möchten, können Sie diesen Befehl verwenden:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> Sie können Microsoft Search nur für eine Team Website oder eine Veröffentlichungswebsite manuell aktivieren (Vorlagen-IDs, die "STS", "CMSPUBLISHING", "BLANKINTERNET" und "Group" enthalten).
