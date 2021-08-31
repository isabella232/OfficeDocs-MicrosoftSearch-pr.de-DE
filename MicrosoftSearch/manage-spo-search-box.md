---
title: Verwalten des Suchfelds in SharePoint Websites
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: So passen Sie die Suchfeldoberfläche auf SharePoint Websites an
ms.openlocfilehash: b5d58dd5a241ccf2ada556c44ec0ea5479ea2e2b
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701976"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>Suchfeldeinstellungen auf SharePoint Websites

Eine der verschiedenen Möglichkeiten, Microsoft Search auf SharePoint Websites angepasst werden können, besteht darin, die Funktionsweise des Suchfelds in der Suitenavigationsleiste in SharePoint Websites so anzupassen, dass es Ihren Anforderungen am besten entspricht.

Weitere Anpassungsoptionen finden Sie unter [Ändern der Microsoft Search Ergebnisseite, um benutzerdefinierte Vertikale, Ergebnistypen und Layouts hinzuzufügen,](customize-search-page.md)und [Erstellen einer benutzerdefinierten Suchergebnisseite.](create-search-results-pages.md)

> [!NOTE]
> Das Suchfeld der Suiten-Navigationsleiste ist derzeit nicht für alle Kunden verfügbar, aber diese Optionen können jetzt noch festgelegt werden, und sie werden wirksam, wenn es verfügbar wird.

Für die unten aufgeführten Aufgaben verwenden Sie PowerShell mit SharePoint PnP PowerShell-Erweiterungen. Hier können Sie installieren und mehr über die [ersten](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)Schritte erfahren. Sie melden sich mit dem folgenden Befehl bei Ihrer Website oder Websitesammlung an:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>Ändern des Suchbereichs

Wenn Sie heute in SharePoint Online eine neue Website erstellen und in das Suchfeld eingeben, gelangen Sie zur Microsoft Search Ergebnisseite. Diese Seite zeigt standardmäßig Ergebnisse von Ihrer aktuellen Website und ermöglicht es Ihnen, den Umfang Ihrer Suche auf den Hub zu erweitern, dem die aktuelle Website zugeordnet ist (sofern vorhanden) oder auf die gesamte Organisation.

Der Bereich, den das Suchfeld standardmäßig verwendet, hängt vom Typ der Website ab.

* Regelmäßige Websitesuche über die aktuelle Website.
* Hubwebsites durchsuchen alle Websites im Hub.
* Homepages durchsuchen alle Inhalte.

In einigen Fällen empfiehlt es sich, diese Standardeinstellungen so zu ändern, dass immer die gesamte Organisation oder der Hub durchsucht wird, dem eine Website zugeordnet ist, ohne dass ein zusätzlicher Klick erforderlich ist.

Als Websitebesitzer können Sie diese Standardwerte mit dem folgenden Befehl ändern:

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

Nach dem Ausführen dieses Befehls wird die Website, auf der zuvor standardmäßig Ergebnisse von der aktuellen Website angezeigt wurden, mit der Anzeige von Ergebnissen aus der gesamten Organisation gestartet.

Führen Sie den Befehl erneut mit dem Wert "DefaultScope" aus, um zur Standardeinstellung zurückzukehren. Verwenden Sie zum Durchsuchen des Hubs "Hub" als SearchScope-Wert.

Diese Einstellung gilt auf der Ebene einzelner Websites. Es gibt keine entsprechende Einstellung für Websitesammlungen.

## <a name="show-or-hide-the-search-box"></a>Ein- oder Ausblenden des Suchfelds

Sie können das Suchfeld der Suitennavigationsleiste ausblenden, wenn Sie verhindern möchten, dass Ihre Benutzer suchen oder eine benutzerdefinierte Suchfeldimplementierungen verwenden.

Um diese Einstellung für eine bestimmte Website zu ändern, verwenden Sie diesen Befehl:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Wenn Sie sie für alle Websites in einer Websitesammlung festlegen möchten, können Sie alternativ den folgenden Befehl verwenden:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Nachdem Sie diese Befehle ausgeführt haben, wird das Suchfeld nicht mehr in der Navigationsleiste oben auf der Seite angezeigt. Um zum Anzeigen des Suchfelds zurückzukehren, führen Sie die Befehle erneut aus, wobei der Wert für den Parameter "SearchBoxInNavBar" auf "Inherit" festgelegt ist.

Es gibt mehrere Punkte, die Sie berücksichtigen sollten:

* Diese Einstellung gilt nur für das Suchfeld in der Suitenavigationsleiste. Sie gilt nicht für Suchfelder, die sich auf der Seite befinden, oder für Suchfelder auf klassischen Seiten.

* Nachdem Sie das Suchfeld in der Navigationsleiste deaktiviert haben, müssen Sie es selbst mithilfe eines benutzerdefinierten Webparts oder einer SharePoint-Framework Erweiterung bereitstellen, wenn Sie Suchfunktionen auf Ihrer Website wünschen.

* Mit dieser Lösung wird das Suchfeld auch aus Listen und Bibliotheken für Ihre Website entfernt. Ihre benutzerdefinierte Suchlösung muss zusätzlich zur websiteweiten Suche kontextbezogene Suchen nach SharePoint Listen und Bibliotheken berücksichtigen.

* Wenn Sie die Einstellung auf die Stammwebsite Ihrer Domäne anwenden, wird auf der SharePoint Startseite auch das Suchfeld nicht mehr angezeigt.

## <a name="changing-the-hint-displayed-in-the-search-box"></a>Ändern des im Suchfeld angezeigten Hinweises

Sie können den Hinweis ändern, der im Suchfeld für eine bestimmte Website oder Websitesammlung angezeigt wird. Dies ist der Text, der im Suchfeld angezeigt wird, bevor sie mit der Eingabe beginnen. Dies kann Ihren Benutzern helfen, zu erfahren, was Sie von der Suche erwarten können, wenn Sie eine benutzerdefinierte Ergebnisseite konfiguriert oder das Suchverhalten auf andere Weise geändert haben.

> [!NOTE]
> Um diese Änderung vornehmen zu können, müssen Sie das Ausführen von benutzerdefinierten Skripts auf der betreffenden Website als Mandantenadministrator zulassen, was standardmäßig nicht zulässig ist. Weitere Informationen finden Sie https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script unter. Sie können das Ausführen von benutzerdefinierten Skripts zulassen, die Änderung vornehmen und dann bei Bedarf die Ausführung von Skripts für die Website verhindern.

Führen Sie den folgenden Befehl aus, um diese Einstellung für eine bestimmte Website zu ändern:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

Wenn Sie sie für alle Websites in einer Websitesammlung festlegen möchten, können Sie alternativ den folgenden Befehl verwenden:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

Um zum Standardplatzhaltertext zurückzukehren, legen Sie den Wert auf leer ("") fest.