---
title: Verwalten des Such Felds in SharePoint-Websites
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
description: Vorgehensweise Anpassen des Such Feld Erlebnisses auf SharePoint-Websites
ms.openlocfilehash: 6ebd084aadb38acb5475b7e43d7c4092ffc09eb8
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700964"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>Such Feld Einstellungen auf SharePoint-Websites

Eine der verschiedenen Möglichkeiten, auf denen die Microsoft-Suche auf SharePoint-Websites angepasst werden kann, besteht darin, die Funktionsweise des Suchfelds in der Suite-Navigationsleiste auf SharePoint-Websites zu optimieren und Ihren Anforderungen optimal anzupassen.

Weitere Anpassungsoptionen finden Sie unter [Ändern der Microsoft-Suchergebnisseite, um benutzerdefinierte vertikalen, Ergebnistypen und Layouts hinzuzufügen](customize-search-page.md)und [eine benutzerdefinierte Suchergebnisseite zu erstellen](create-search-results-pages.md).

> [!NOTE]
> Das Suchfeld für die Suite-Navigationsleiste steht derzeit nicht für alle Kunden zur Verfügung, aber diese Optionen können jetzt noch festgelegt werden, und Sie werden wirksam, sobald Sie verfügbar sind.

Für die unten aufgeführten Aufgaben verwenden Sie PowerShell mit SharePoint PNP PowerShell-Erweiterungen. Sie können die ersten Schritte [hier](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)installieren und weitere Informationen dazu erhalten. Sie melden sich bei Ihrer Website oder Websitesammlung mit folgendem Befehl an:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>Ändern des Suchbereichs

Wenn Sie eine neue Website in SharePoint Online heute erstellen und in das Suchfeld eingeben, gelangen Sie zur Microsoft-Suchergebnisseite. Auf dieser Seite werden die Ergebnisse Ihrer aktuellen Website standardmäßig angezeigt, und Sie können den Suchbereich auf den Hub erweitern, dem die aktuelle Website zugeordnet ist (sofern vorhanden), oder für die gesamte Organisation.

Der Bereich, den das Suchfeld verwendet, hängt standardmäßig vom Typ der Website ab.

* Durchsuchen regulärer Websites über die aktuelle Website.
* Hub-Standorte suchen über alle Standorte im Hub.
* Home Websites-Suche über alle Inhalte.

In einigen Fällen möchten Sie möglicherweise diese Standardwerte so ändern, dass Sie immer über die gesamte Organisation oder über den Hub hinweg suchen, dem eine Website zugeordnet ist, ohne dass ein zusätzlicher Mausklick erforderlich ist.

Als Websitebesitzer können Sie diese Standardeinstellungen mit dem folgenden Befehl ändern:

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

Nachdem Sie diesen Befehl ausführen, zeigt die Website, auf der zuvor Ergebnisse der aktuellen Website standardmäßig angezeigt werden, die Ergebnisse der gesamten Organisation an.

Wenn Sie zur Standardeinstellung zurückkehren möchten, führen Sie den Befehl erneut mit dem Wert "DefaultScope" aus. Verwenden Sie "Hub" als SearchScope-Wert, um die Suche im Hub durchführen zu können.

Diese Einstellung gilt für die jeweilige Websiteebene. Für Websitesammlungen gibt es keine entsprechende Einstellung.

## <a name="show-or-hide-the-search-box"></a>Anzeigen oder Ausblenden des Suchfelds

Sie können das Suchfeld der Suite-Navigationsleiste ausblenden, wenn Sie verhindern möchten, dass Ihre Benutzer suchen oder eine benutzerdefinierte Such Feld Implementierung verwenden.

Verwenden Sie diesen Befehl, um diese Einstellung für eine bestimmte Website zu ändern:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Alternativ können Sie diesen Befehl verwenden, wenn Sie ihn für alle Websites in einer Websitesammlung festlegen möchten:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Nach dem Ausführen dieser Befehle wird das Suchfeld nicht mehr in der Navigationsleiste oben auf der Seite angezeigt. Wenn Sie zum Anzeigen des Suchfeld zurückkehren möchten, führen Sie die Befehle erneut aus, wobei der Wert für den Parameter "SearchBoxInNavBar" auf "Inherit" festgelegt ist.

Es gibt mehrere Punkte, die beachtet werden sollten:

* Diese Einstellung gilt nur für das Suchfeld in der Suite-Navigationsleiste. Sie gilt nicht für Suchfelder auf der Seite oder für Suchfelder auf klassischen Seiten.

* Wenn Sie das Suchfeld in der Navigationsleiste deaktiviert haben, müssen Sie es selbst mithilfe eines benutzerdefinierten Webparts oder einer SharePoint-Framework-Erweiterung bereitstellen, wenn Sie Suchfunktionen auf Ihrer Website benötigen.

* Mit dieser Lösung wird das Suchfeld auch aus Listen und Bibliotheken für Ihre Website entfernt. Ihre benutzerdefinierte Suchlösung muss neben der websiteweiten Suche auch kontextbezogene Suchvorgänge für SharePoint-Listen und-Bibliotheken in Frage stellen.

* Wenn Sie die Einstellung auf die Stammwebsite Ihrer Domäne anwenden, wird auch auf der SharePoint-Startseite das Suchfeld angezeigt.

## <a name="changing-the-hint-displayed-in-the-search-box"></a>Ändern des in das Suchfeld angezeigten antipps

Sie können den Hinweis ändern, der im Suchfeld für eine bestimmte Website oder Websitesammlung angezeigt wird. Dies ist der Text, der im Suchfeld angezeigt wird, bevor Sie mit der Eingabe beginnen. Dies kann dazu führen, dass Ihre Benutzer über die von der Suche erwarteten Ergebnisse erfahren, wenn Sie eine benutzerdefinierte Ergebnisseite oder ein geändertes Suchverhalten auf andere Weise konfiguriert haben.

> [!NOTE]
> Um diese Änderung vornehmen zu können, müssen Sie das Ausführen benutzerdefinierter Skripts auf der fraglichen Website als mandantenadministrator zulassen, was standardmäßig nicht zulässig ist. Weitere Informationen finden Sie unter https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script . Sie können das Ausführen benutzerdefinierter Skripts zulassen, die Änderung vornehmen und dann bei Bedarf zu nicht zulässigen Skripts für die Website zurückkehren.

Führen Sie den folgenden Befehl aus, um diese Einstellung für eine bestimmte Website zu ändern:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

Alternativ können Sie diesen Befehl verwenden, wenn Sie ihn für alle Websites in einer Websitesammlung festlegen möchten:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

Wenn Sie zum Standardplatz Halter Text zurückkehren möchten, legen Sie den Wert auf leer ("") fest.
