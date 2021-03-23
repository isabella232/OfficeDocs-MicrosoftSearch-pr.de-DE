---
title: Erstellen einer benutzerdefinierten Suchergebnissetseite in SharePoint Online
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Erstellen Einer eigenen Suchergebnissetseite für eine SharePoint Online-Website
ms.openlocfilehash: b5abb25f15795389dd8b6d5683ac336af7422e0a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031638"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Erstellen einer benutzerdefinierten Suchergebnissetseite in SharePoint Online

Eine Möglichkeit zum Anpassen der Sucherfahrung in SharePoint besteht in der Erstellung einer benutzerdefinierten Suchergebnissetseite für eine Website. Auf diese Weise können Sie eine von Ihnen erstellte Seite anstelle der Standardeinstellung auf der Microsoft Search-Ergebnisseite verwenden. Dies bietet Ihnen mehr Flexibilität bei der Suche nach Suchergebnissen für Ihre Benutzer.

>[!NOTE]
> Informationen zum Vornehmen von Änderungen an der standardmäßig verfügbaren Microsoft Search-Ergebnisseite finden Sie unter [Anpassen der Suchergebnisseite](customize-search-page.md).

Mit einer benutzerdefinierten Ergebnisseite können Sie eine neue Seite erstellen, die zum Steuern des Layouts und Entwurfs von Suchergebnissen verwendet werden kann, um die Anforderungen Ihrer Organisation zu unterstützen. Sie können alle integrierten Webparts, Open-Source-Suchwebparts aus der SharePoint Patterns and Practices-Community sowie benutzerdefinierte Webparts verwenden, die Sie möglicherweise mit SharePoint Framework entwickelt haben.

## <a name="configure-a-results-page"></a>Konfigurieren einer Ergebnisseite

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Ergebnisseite in SharePoint Online zu konfigurieren:

1. Navigieren Sie zu der Website, auf der Sie eine benutzerdefinierte Ergebnisseite konfigurieren möchten, und wechseln Sie zu Websiteeinstellungen > Websitesammlungseinstellungen **> Sucheinstellungen**.

2. Deaktivieren Sie in Sucheinstellungen die Auswahl unter **Verwenden** Der gleichen Ergebnisseiteneinstellungen wie bei meinem übergeordneten Element, wählen Sie **Abfragen** an eine benutzerdefinierte Ergebnisseite senden aus, und geben Sie einen Wert für die Url der **Ergebnisseite an:** an. Speichern Sie dann Ihre Änderungen. Die url, die Sie hier verwenden, sollte für die Seite sein, die Sie als benutzerdefinierte Ergebnisseite erstellt haben.

>[!NOTE]
> Die benutzerdefinierte Ergebnisseite muss sich in derselben Domäne wie Ihre Website befinden, muss sich jedoch nicht in derselben Websitesammlung befinden.  

Alternativ können Sie den [Befehl Set-PnPSearchSettings SharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) verwenden, um den Wert anstelle der Seite Websiteeinstellungen zu verwenden.

Nach dem Festlegen wird die benutzerdefinierte Suchergebnissetseite angezeigt, wenn Sie mithilfe des Microsoft Search-Felds suchen, das in der Navigationsleiste oben auf der Seite angezeigt wird und verwendet wird, wenn Sie die Suche von Websiteseiten oder der Homepage der Website eingeben. Sie wird nicht verwendet, wenn Sie in einer Liste, Bibliothek oder der Websiteinhaltsseite suchen. Sie können den Link verwenden, um Ihre Suche von Suchergebnissen in Listen und Bibliotheken zu erweitern, um zur benutzerdefinierten Ergebnisseite zu gelangen.

## <a name="change-the-layout-of-your-custom-results-page"></a>Ändern des Layouts der benutzerdefinierten Ergebnisseite

Ein Seitenlayout mit dem Namen **HeaderlessSearchResults** kann verwendet werden, um die Suchergebnissetseite näher an unsere Out-of-Box-Suchergebnisse zu bringen. Dieses neue Layout kann nur für die Seiten aktiv sein, die als benutzerdefinierte Suchergebnissetseite festgelegt sind.

Zum Festlegen des Seitenlayouts können Sie den [Befehl Set-PnPClientSidePageSharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) mit -LayoutType HeaderlessSearchResults verwenden.

## <a name="use-sharepoint-framework-query-extensions"></a>Verwenden von SharePoint-Framework-Abfrageerweiterungen

Benutzerdefinierte Suchergebnisseseiten können auch die [SharePoint-Framework-Abfrageerweiterung](/sharepoint/dev/spfx/building-search-extensions) verwenden, um die Abfrage zu ändern, bevor sie an die Suchmaschine gesendet wird.

## <a name="additional-resources"></a>Weitere Ressourcen

Weitere Informationen zur benutzerdefinierten Ergebnisseite finden Sie in unserer [Ignite 2019 Search Customization and Development-Sitzung.](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)

For open source projects, getting started with our Microsoft Search APIs, and more customization and extensibility samples, visit [Microsoft Search on GitHub](https://github.com/microsoft-search).