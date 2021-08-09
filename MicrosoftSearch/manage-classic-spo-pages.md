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
description: Verwenden von Microsoft Search auf klassischen SharePoint Seiten
ms.openlocfilehash: 187a8c78b9f1b78cf1c5ad04ede91a38fe88759d34037226949a441034cb13b9
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533599"
---
# <a name="classic-pages-and-microsoft-search"></a>Klassische Seiten und Microsoft Search

SharePoint Websites, die vor modernen Websites erstellt wurden, verwenden ein klassisches Suchfeld und klassische Suchergebnisse. Wir werden ein Feature bereitstellen, das standardmäßig klassische Seiten verwendet, um die moderne Suchumgebung zu verwenden, die Microsoft Search verwendet, die personalisierte Ergebnisse mit höherer Relevanz bereitstellt.

Die Verwendung von Microsoft Search wird für alle Websites empfohlen, einschließlich klassischer Websites. Wenn Ihre klassischen Websites jedoch benutzerdefinierte Gestaltungsvorlagen verwenden und/oder Sie Ihre klassische Suchergebnisse angepasst haben, werden diese Anpassungen automatisch erkannt und nicht zu Microsoft Search gewechselt.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Klassische Websites, die automatisch zu Microsoft Search

Klassische Websites verwenden Microsoft Search, wenn alle folgenden Werte zutreffen:

* Die Website basiert auf der Teamwebsitevorlage (z. B. STS#0 und STS#1).
* Auf der Website ist das Veröffentlichungsfeature nicht aktiviert.
* Die Website verwendet keine benutzerdefinierte Gestaltungsvorlage (eine andere Gestaltungsvorlage als oslo.master oder seattle.master).
* Es gibt keine anderen aktiven Abfrageregeln als die, die höhergestufte Ergebnisse für die Website, die Websitesammlung oder den Mandanten in der Standardergebnisquelle hinzufügen.
* Es gibt keine benutzerdefinierten Ergebnistypen für die Website oder die Websitesammlung in der Standardergebnisquelle.
* Die Website oder die Websitesammlung wird nicht mithilfe der unten beschriebenen *SearchBoxInNavBar-Einstellung* vom Wechsel abgemeldet.

Nach dem Wechsel zu Microsoft Search werden auf klassischen Seiten der Website das Suchfeld in der Suitenavigationsleiste angezeigt, und das klassische Suchfeld wird von der Seite entfernt. Wenn ein Benutzer dann nach einem Begriff sucht, werden die Ergebnisse mithilfe der modernen Suchumgebung von Microsoft Search angezeigt.

## <a name="staying-with-the-classic-search-experience"></a>Mit der klassischen Suchumgebung bleiben

Wenn Ihre Website die oben aufgeführten Kriterien erfüllt, sie jedoch nicht zur Microsoft Search Wechseln soll, können Sie die Verwendung der folgenden Befehle als Website- oder Websitesammlungsbesitzer deaktivieren.

Sie können diesen Befehl jederzeit vor oder nach dem Wechsel verwenden, sodass Sie ganz einfach zur suchumgebung zurückkehren können, die Sie zuvor hatten.

Um die folgenden Befehle auszuführen, verwenden Sie PowerShell mit SharePoint PnP PowerShell-Erweiterungen. Hier können Sie installieren und mehr über die [ersten](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)Schritte erfahren. Sie melden sich mit dem folgenden Befehl bei Ihrer Website oder Websitesammlung an:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

Führen Sie den folgenden Befehl aus, um die klassische Suchumgebung für eine Website zu verwenden:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Wenn Sie sie für alle Websites in einer Websitesammlung festlegen möchten, können Sie alternativ den folgenden Befehl verwenden:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Anmelden bei Microsoft Search

Für Websites, die die oben aufgeführten Kriterien nicht erfüllen, oder für bestimmte Websites in einer Websitesammlung, die sich dafür entschieden haben, klassisch zu bleiben, können Sie die Microsoft Search-Oberfläche manuell aktivieren.

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