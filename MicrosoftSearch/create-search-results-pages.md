---
title: Erstellen einer benutzerdefinierten Suchergebnisseite in SharePoint Online
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
description: Erstellen Einer eigenen Suchergebnisseite für eine SharePoint Onlinewebsite
ms.openlocfilehash: df99287dbdd9a82c1a8bc66b39e67a37fcb22da8
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702202"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Erstellen einer benutzerdefinierten Suchergebnisseite in SharePoint Online

Eine Möglichkeit zum Anpassen der Suchumgebung in SharePoint ist das Erstellen einer benutzerdefinierten Suchergebnisseite für eine Website. Auf diese Weise können Sie eine Seite verwenden, die Sie erstellt haben, und nicht die Standardseite in Microsoft Search Ergebnisseite. Dadurch erhalten Sie mehr Flexibilität, wie die Suchergebnisse für Ihre Benutzer aussehen.

>[!NOTE]
> Wenn Sie Änderungen an der Standardmäßigen Microsoft Search Ergebnisseite vornehmen möchten, die standardmäßig verfügbar ist, lesen Sie ["Anpassen der Suchergebnisseite".](customize-search-page.md)

Mit einer benutzerdefinierten Ergebnisseite können Sie eine neue Seite erstellen, die zum Steuern des Layouts und Designs von Suchergebnissen verwendet werden kann, um die Anforderungen Ihrer Organisation zu erfüllen. Sie können alle integrierten Webparts, Open Source-Such-Webparts aus SharePoint Patterns and Practices-Community sowie alle benutzerdefinierten Webparts verwenden, die Sie möglicherweise mit SharePoint-Framework entwickelt haben.

## <a name="configure-a-results-page"></a>Konfigurieren einer Ergebnisseite

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Ergebnisseite in SharePoint Online zu konfigurieren:

1. Navigieren Sie zu der Website, auf der Sie eine benutzerdefinierte Ergebnisseite konfigurieren möchten, und wechseln Sie zu **Site Einstellungen > Site Collection Einstellungen > Search Einstellungen.**

2. Deaktivieren Sie im Such-Einstellungen die Auswahl unter **"Verwenden derselben Ergebnisseiteneinstellungen wie mein übergeordnetes Element",** wählen Sie **"Abfragen an eine benutzerdefinierte Ergebnisseite senden"** aus, und geben Sie einen Wert für die URL der **Ergebnisseite an:**. Speichern Sie dann Ihre Änderungen. Die URL, die Sie hier verwenden, sollte für die Seite, die Sie erstellt haben, als benutzerdefinierte Ergebnisseite verwendet werden.

>[!NOTE]
> Die benutzerdefinierte Ergebnisseite muss sich in derselben Domäne wie Ihre Website befinden, muss sich jedoch nicht in derselben Websitesammlung befinden.  

Alternativ können Sie den [PowerShell-Befehl "Set-PnPSearchSettings SharePoint PnP"](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) verwenden, um den Wert festzulegen, anstatt die Seite "Site Einstellungen" zu verwenden.

Nach dem Festlegen wird die benutzerdefinierte Suchergebnisseite angezeigt, wenn Sie mithilfe des Microsoft Search Felds suchen, das in der Navigationsleiste oben auf der Seite angezeigt wird und verwendet wird, wenn Sie die Suche von Websiteseiten oder der Startseite der Website eingeben. Es wird nicht verwendet, wenn Sie in einer Liste, Bibliothek oder der Websiteinhaltsseite suchen. Sie können den Link verwenden, um Ihre Suche aus Suchergebnissen in Listen und Bibliotheken zu erweitern, um zur benutzerdefinierten Ergebnisseite zu gelangen.

## <a name="change-the-layout-of-your-custom-results-page"></a>Ändern des Layouts der benutzerdefinierten Ergebnisseite

Ein Seitenlayout mit dem Namen **HeaderlessSearchResults** kann verwendet werden, damit die Suchergebnisseite näher an unserem Out-of-Box-Suchergebnisse angezeigt wird. Dieses neue Layout kann nur für die Seiten aktiv sein, die als benutzerdefinierte Suchergebnisseite festgelegt sind.

Zum Festlegen des Seitenlayouts können Sie den [PowerShell-Befehl "Set-PnPClientSidePageSharePoint PnP"](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) mit "-LayoutType HeaderlessSearchResults" verwenden.

## <a name="use-sharepoint-framework-query-extensions"></a>Verwenden SharePoint-Framework Abfrageerweiterungen

Benutzerdefinierte Suchergebnisseite können auch die [SharePoint-Framework Abfrageerweiterung](/sharepoint/dev/spfx/building-search-extensions) verwenden, um die Abfrage zu ändern, bevor sie an die Suchmaschine gesendet wird.

## <a name="additional-resources"></a>Weitere Ressourcen

Weitere Informationen zu benutzerdefinierten Ergebnisseiten finden Sie in der [Ignite 2019 Search Customization and Development-Sitzung.](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)

Informationen zu Open Source-Projekten, den ersten Schritten mit unseren Microsoft Search-APIs und weiteren Anpassungs- und Erweiterbarkeitsbeispielen finden Sie [Microsoft Search auf GitHub.](https://github.com/microsoft-search)