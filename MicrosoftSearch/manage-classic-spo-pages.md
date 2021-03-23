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
ms.openlocfilehash: 33215c730d34c14f8ce1d55e93730615688f1e2a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031431"
---
# <a name="classic-pages-and-microsoft-search"></a>Klassische Seiten und Microsoft Search

SharePoint-Websites, die vor modernen Websites erstellt wurden, verwenden ein klassisches Suchfeld und klassische Suchergebnisse. Wir werden ein Feature mit klassischen Standardseiten für die Verwendung der modernen Suchfunktion mit Microsoft Search verwenden, die personalisierte Ergebnisse mit höherer Relevanz bietet.

Die Verwendung von Microsoft Search wird für alle Websites empfohlen, auch für klassische Websites, aber wenn Ihre klassischen Websites benutzerdefinierte Gestaltungsseiten verwenden und/oder Sie Ihre klassische Suchergebnisseindung angepasst haben, erkennen wir diese Anpassungen automatisch und wechseln nicht zu Microsoft Search.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Klassische Websites, die automatisch zu Microsoft Search wechseln

Klassische Websites beginnen mit der Verwendung von Microsoft Search, wenn folgendes zutrifft:

* Die Website basiert auf der Teamwebsitevorlage (z. B. STS#0 und STS#1).
* Auf der Website ist das Veröffentlichungsfeature nicht aktiviert.
* Die Website verwendet keine benutzerdefinierte Masterseite (eine andere Masterseite als oslo.master oder seattle.master).
* Es gibt keine anderen aktiven Abfrageregeln als das Hinzufügen höhergestufter Ergebnisse für die Website, Websitesammlung oder den Mandanten in der Standardergebnisquelle.
* Es gibt keine benutzerdefinierten Ergebnistypen für die Website oder websitesammlung in der Standardergebnisquelle.
* Die Website oder die Websitesammlung wird mit der unten beschriebenen *Einstellung SearchBoxInNavBar* nicht von der Option ausgeschlossen.

Nach dem Wechsel zu Microsoft Search beginnen klassische Seiten auf der Website, das Suchfeld in der Suitennavigationsleiste zu zeigen und das klassische Suchfeld von der Seite zu entfernen. Wenn ein Benutzer dann nach einem Ausdruck sucht, werden die Ergebnisse mithilfe der modernen Suchfunktion von Microsoft Search angezeigt.

## <a name="staying-with-the-classic-search-experience"></a>Bei der klassischen Sucherfahrung bleiben

Wenn Ihre Website die oben aufgeführten Kriterien erfüllt, sie jedoch nicht zur Microsoft Search-Erfahrung wechseln soll, können Sie dies mit den folgenden Befehlen als Website- oder Websitesammlungsbesitzer abmelden.

Sie können diesen Befehl jederzeit vor oder nach dem Wechsel verwenden, sodass Sie problemlos wieder zu der zuvor verwendeten Sucherfahrung wechseln können.

Zum Ausführen der folgenden Befehle verwenden Sie PowerShell mit SharePoint PnP PowerShell-Erweiterungen. Sie können hier installieren und mehr über die ersten Schritte [erfahren.](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps) Mit diesem Befehl melden Sie sich bei Ihrer Website oder Websitesammlung an:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

Führen Sie den folgenden Befehl aus, um bei der klassischen Suchfunktion für eine Website zu bleiben:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Wenn Sie es für alle Websites in einer Websitesammlung festlegen möchten, können Sie den folgenden Befehl verwenden:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Opting in Microsoft Search

Für Websites, die die oben aufgeführten Kriterien nicht erfüllen, oder für bestimmte Websites in einer Websitesammlung, die sich für den klassischen Aufenthalt entschieden haben, können Sie die Microsoft Search-Erfahrung manuell aktivieren.

Um diese Einstellung für eine bestimmte Website zu ändern, können Sie den folgenden Befehl verwenden:

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