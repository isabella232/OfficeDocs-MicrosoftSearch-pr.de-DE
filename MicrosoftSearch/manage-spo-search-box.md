---
title: Verwalten des Suchfelds auf SharePoint-Websites
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
description: Anpassen der Suchfelderfahrung auf SharePoint-Websites
ms.openlocfilehash: c58e7cf0a47d22fa9c6fd3abd93cc97087625690
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031359"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>Suchfeldeinstellungen auf SharePoint-Websites

Eine der verschiedenen Möglichkeiten, mit der Microsoft Search auf SharePoint-Websites angepasst werden kann, besteht in der Anpassung der Funktionsweise des Suchfelds in der Suitennavigationsleiste auf SharePoint-Websites an Ihre Anforderungen.

Weitere Anpassungsoptionen finden Sie unter Ändern der Microsoft Search-Ergebnisseite, um benutzerdefinierte [Vertikalen,](customize-search-page.md)Ergebnistypen und Layouts hinzuzufügen, und Erstellen einer benutzerdefinierten [Suchergebnissetseite](create-search-results-pages.md).

> [!NOTE]
> Das Suchfeld suitenavigationsleiste ist derzeit nicht für alle Kunden verfügbar, aber diese Optionen können jetzt noch festgelegt werden und werden wirksam, wenn es verfügbar wird.

Für die unten aufgeführten Aufgaben verwenden Sie PowerShell mit SharePoint PnP PowerShell-Erweiterungen. Sie können hier installieren und mehr über die ersten Schritte [erfahren.](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps) Mit diesem Befehl melden Sie sich bei Ihrer Website oder Websitesammlung an:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>Ändern des Suchbereichs

Wenn Sie heute eine neue Website in SharePoint Online erstellen und in das Suchfeld eingeben, werden Sie zur Microsoft Search-Ergebnisseite weitergeleitet. Diese Seite zeigt standardmäßig Ergebnisse ihrer aktuellen Website und ermöglicht Es Ihnen, den Suchbereich auf den Hub zu erweitern, dem die aktuelle Website zugeordnet ist (sofern vorhanden), oder auf die gesamte Organisation.

Der vom Suchfeld verwendete Bereich hängt standardmäßig vom Typ der Website ab.

* Reguläre Websites suchen über die aktuelle Website.
* Hubwebsites suchen über alle Websites im Hub.
* Startseiten suchen über alle Inhalte.

In einigen Fällen können Sie diese Standardeinstellungen so ändern, dass sie immer über die gesamte Organisation oder über den Hub, dem eine Website zugeordnet ist, durchsucht werden, ohne dass sie einen zusätzlichen Klick benötigen.

Als Websitebesitzer können Sie diese Standardwerte mithilfe des folgenden Befehls ändern:

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

Nachdem Sie diesen Befehl ausgeführt haben, werden auf der Website, auf der zuvor standardmäßig Ergebnisse der aktuellen Website angezeigt wurden, Ergebnisse aus der gesamten Organisation angezeigt.

Um zur Standardeinstellung zurück zu wechseln, führen Sie den Befehl erneut mit dem Wert "DefaultScope" aus. Verwenden Sie zum Durchsuchen des Hubs "Hub" als SearchScope-Wert.

Diese Einstellung gilt für die einzelnen Websiteebenen. Es gibt keine entsprechende Einstellung für Websitesammlungen.

## <a name="show-or-hide-the-search-box"></a>Ein- oder Ausblenden des Suchfelds

Sie können das Suchfeld der Suitenavigationsleiste ausblenden, wenn Sie verhindern möchten, dass Benutzer suchen oder eine benutzerdefinierte Suchfeldimplementierung verwenden.

Verwenden Sie diesen Befehl, um diese Einstellung für eine bestimmte Website zu ändern:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Wenn Sie es für alle Websites in einer Websitesammlung festlegen möchten, können Sie den folgenden Befehl verwenden:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Nach dem Ausführen dieser Befehle wird das Suchfeld nicht mehr in der Navigationsleiste oben auf der Seite angezeigt. Um zum Anzeigen des Suchfelds zurück zu wechseln, führen Sie die Befehle erneut mit dem Wert aus, der für den Parameter "SearchBoxInNavBar" in "Inherit" angegeben ist.

Es gibt mehrere Punkte, die Sie berücksichtigen sollten:

* Diese Einstellung gilt nur für das Suchfeld in der Suitenavigationsleiste. Sie gilt nicht für Suchfelder, die sich auf der Seite befinden, oder für Suchfelder auf klassischen Seiten.

* Nachdem Sie das Suchfeld in der Navigationsleiste deaktiviert haben, müssen Sie es selbst mithilfe eines benutzerdefinierten Web teils oder einer SharePoint-Framework-Erweiterung bereitstellen, wenn Sie Suchfunktionen in Ihrer Website benötigen.

* Mit dieser Lösung wird das Suchfeld auch aus Listen und Bibliotheken für Ihre Website entfernt. Ihre benutzerdefinierte Suchlösung muss neben der websiteweiten Suche auch kontextbezogene Suchen nach SharePoint-Listen und -Bibliotheken berücksichtigen.

* Wenn Sie die Einstellung auf die Stammwebsite Ihrer Domäne anwenden, wird auf der SharePoint-Startseite auch das Suchfeld nicht mehr angezeigt.

## <a name="changing-the-hint-displayed-in-the-search-box"></a>Ändern des im Suchfeld angezeigten Hinweises

Sie können den Hinweis ändern, der im Suchfeld für eine bestimmte Website oder Websitesammlung angezeigt wird. Dies ist der Text, der im Suchfeld angezeigt wird, bevor sie mit der Eingabe beginnen. Dies kann Ihren Benutzern helfen, zu verstehen, was sie von der Suche erwarten können, wenn Sie eine benutzerdefinierte Ergebnisseite konfiguriert oder das Suchverhalten auf andere Weise geändert haben.

> [!NOTE]
> Um diese Änderung ausführen zu können, müssen Sie die Ausführung von benutzerdefinierten Skripts auf der in Frage 2013 in Frage gestellten Website als Mandantenadministrator zulassen, was standardmäßig nicht zulässig ist. Weitere Informationen https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script finden Sie unter. Sie können das Ausführen von benutzerdefinierten Skripts zulassen, die Änderung ausführen und dann bei Bedarf auf nicht zulässige Skripts für die Website zurücksetzen.

Führen Sie den folgenden Befehl aus, um diese Einstellung für eine bestimmte Website zu ändern:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

Wenn Sie es für alle Websites in einer Websitesammlung festlegen möchten, können Sie den folgenden Befehl verwenden:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

Um zum Standardplatzhaltertext zurück zu wechseln, legen Sie den Wert auf leer ("") festgelegt.