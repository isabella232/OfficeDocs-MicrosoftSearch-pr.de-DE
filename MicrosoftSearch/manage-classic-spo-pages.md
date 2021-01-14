---
title: Klassische Seiten in SharePoint Online und Microsoft Search
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
description: Verwenden von Microsoft Search auf klassischen SharePoint-Seiten
ms.openlocfilehash: 9a5aeb2e683297faccfb55d3407653c1791b3961
ms.sourcegitcommit: 7133d46ca9c3a5216ee9159db781febd17e5a831
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49863174"
---
# <a name="classic-pages-and-microsoft-search"></a>Klassische Seiten und Microsoft Search

SharePoint-Websites, die vor modernen Websites erstellt wurden, verwenden ein klassisches Suchfeld und klassische Suchergebnisse. Wir werden ein Feature zur Standardeinstellung klassischer Seiten für die Verwendung der modernen Suchfunktion mit Microsoft Search verwenden, die personalisierte Ergebnisse mit höherer Relevanz bietet.

Die Verwendung von Microsoft Search wird für alle Websites empfohlen, einschließlich der klassischen, aber wenn Ihre klassischen Websites benutzerdefinierte Gestaltungsseiten verwenden und/oder Sie Ihre klassische Suchergebnisse angepasst haben, erkennen wir diese Anpassungen automatisch und wechseln nicht zu Microsoft Search.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Klassische Websites, die automatisch zu Microsoft Search wechseln

Klassische Websites beginnen mit der Verwendung von Microsoft Search, wenn alle folgenden Bedingungen erfüllt sind:

* Die Website basiert auf der Teamwebsitevorlage (z. B. STS#0 und STS#1).
* Auf der Website ist das Veröffentlichungsfeature nicht aktiviert.
* Die Website verwendet keine benutzerdefinierte Masterseite (eine andere Masterseite als oslo.master oder seattle.master).
* Es gibt keine aktiven Abfrageregeln, mit denen höhergestufte Ergebnisse für die Website, Websitesammlung oder den Mandanten in der Standardergebnisquelle hinzugefügt werden.
* Es gibt keine benutzerdefinierten Ergebnistypen für die Website oder die Websitesammlung in der Standardergebnisquelle.
* Die Website oder die Websitesammlung wird mit der unten beschriebenen *Einstellung "SearchBoxInNavBar"* nicht von der Option ausgeschlossen.

Nach dem Wechsel zu Microsoft Search wird auf klassischen Seiten der Website das Suchfeld in der Suitenavigationsleiste angezeigt, und das klassische Suchfeld wird von der Seite entfernt. Wenn ein Benutzer dann nach einem Ausdruck sucht, werden die Ergebnisse mithilfe der modernen Suchfunktion von Microsoft Search angezeigt.

## <a name="staying-with-the-classic-search-experience"></a>Mit der klassischen Sucherfahrung bleiben

Wenn Ihre Website die oben aufgeführten Kriterien erfüllt, Sie jedoch nicht möchten, dass sie zur Microsoft Search-Erfahrung wechselt, können Sie sich mit den folgenden Befehlen als Website- oder Websitesammlungsbesitzer abmelden.

Sie können diesen Befehl jederzeit verwenden, bevor oder nachdem der Wechsel erfolgt ist. Daher ist es einfach, wieder zu der Sucherfahrung zurückwechseln, die Sie zuvor hatten.

Um die folgenden Befehle auszuführen, verwenden Sie PowerShell mit SharePoint PnP PowerShell-Erweiterungen. Hier können Sie die ersten Schritte installieren und weitere Informationen [dazu erhalten.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps) Mit dem folgenden Befehl melden Sie sich bei Ihrer Website oder Websitesammlung an:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

Führen Sie den folgenden Befehl aus, um mit der klassischen Sucherfahrung für eine Website zu bleiben:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Alternativ können Sie diesen Befehl verwenden, wenn Sie ihn für alle Websites in einer Websitesammlung festlegen möchten:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Opting to Microsoft Search

Für Websites, die die oben aufgeführten Kriterien nicht erfüllen, oder für bestimmte Websites in einer Websitesammlung, die sich für die klassische Verwendung entschieden haben, können Sie die Microsoft Search-Erfahrung manuell aktivieren.

Um diese Einstellung für einen bestimmten Standort zu ändern, können Sie diesen Befehl verwenden:

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
> Sie können Microsoft Search nur für eine Teamwebsite oder Veröffentlichungswebsite manuell aktivieren (Vorlagen-IDs, die "STS", "CMSPUBLISHING", "BLANKINTERNET" und "GROUP" enthalten).
