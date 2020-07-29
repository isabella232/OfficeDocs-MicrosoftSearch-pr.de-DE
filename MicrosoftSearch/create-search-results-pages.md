---
title: Erstellen einer benutzerdefinierten Suchergebnisseite in SharePoint Online
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Erstellen einer eigenen Suchergebnisseite für eine SharePoint Online Website
ms.openlocfilehash: 9b168dccaa6126148c877b5841b91c63f7bdc2ac
ms.sourcegitcommit: 5fb46a04e86fb49477f8ce7ab3caa1b503215b8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503239"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Erstellen einer benutzerdefinierten Suchergebnisseite in SharePoint Online

Eine Möglichkeit zum Anpassen der Suchumgebung in SharePoint besteht darin, eine benutzerdefinierte Suchergebnisseite für eine Website zu erstellen. Auf diese Weise können Sie eine von Ihnen erstellte Seite anstelle der Standardeinstellung auf der Microsoft-Suchergebnisseite verwenden. Dadurch erhalten Sie mehr Flexibilität darüber, wie die Suchergebnisse für Ihre Benutzer aussehen.

>[!NOTE]
> Wenn Sie Änderungen an der standardmäßigen Microsoft Search-Suchergebnisseite vornehmen möchten, die standardmäßig verfügbar ist, lesen Sie [Anpassen der Suchergebnisseite](customize-search-page.md).

Mit einer benutzerdefinierten Ergebnisseite können Sie eine neue Seite erstellen, die verwendet werden kann, um das Layout und den Entwurf von Suchergebnissen zu steuern, um die Anforderungen Ihrer Organisation zu unterstützen. Sie können beliebige integrierte Webparts, Open-Source-Suchwebparts von SharePoint Patterns and Practices Community sowie alle benutzerdefinierten Webparts verwenden, die Sie möglicherweise mithilfe von SharePoint Framework entwickelt haben.

## <a name="configure-a-results-page"></a>Konfigurieren einer Ergebnisseite

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Ergebnisseite in SharePoint Online zu konfigurieren:

1. Wechseln Sie zu der Website, auf der Sie eine benutzerdefinierte Ergebnisseite konfigurieren möchten, und wechseln Sie zu **Websiteeinstellungen > Einstellungen für Websitesammlungen > Sucheinstellungen**.

2. Wählen Sie in Sucheinstellungen die Option Auswahl aus **dieselben Ergebnisseiten Einstellungen wie mein übergeordnetes Element**aus, wählen Sie **Senden von Abfragen an eine benutzerdefinierte Ergebnisseite**aus, und geben Sie einen Wert für die **URL der Ergebnisseite an:**.Speichern Sie dann die Änderungen. Die hier verwendete URL sollte für die Seite verwendet werden, die Sie als benutzerdefinierte Ergebnisseite verwendet haben.

>[!NOTE]
> Die Seite benutzerdefinierte Ergebnisse muss sich in derselben Domäne wie Ihre Website befinden, muss sich jedoch nicht in derselben Websitesammlung befinden.  

Alternativ können Sie den [SharePoint PNP-PowerShell-Befehl "PnPSearchSettings](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) " verwenden, um den Wert anstelle der Seite "Websiteeinstellungen" festzulegen.

Sobald diese Option festgelegt wurde, wird die Seite benutzerdefinierte Suchergebnisse angezeigt, wenn Sie die Suche mit dem Microsoft-Suchfeld durchführen, das in der Navigationsleiste oben auf der Seite angezeigt wird und verwendet wird, wenn Sie die Suche auf Website Seiten oder auf der Homepage der Website eingeben. Sie wird nicht verwendet, wenn Sie in einer Liste, Bibliothek oder auf der Seite "Websiteinhalte" suchen. Sie können den Link verwenden, um die Suche von Suchergebnissen in Listen und Bibliotheken zu erweitern, um zur Seite benutzerdefinierte Ergebnisse zu gelangen.

## <a name="change-the-layout-of-your-custom-results-page"></a>Ändern des Layouts Ihrer benutzerdefinierten Ergebnisseite

Ein Seitenlayout mit dem Namen **HeaderlessSearchResults** kann verwendet werden, damit die Suchergebnisseite näher an unserer out-of-Box-Suchergebnis Oberfläche angezeigt wird.Dieses neue Layout kann nur für die Seiten aktiviert werden, die als benutzerdefinierte Suchergebnisseite festgelegt sind.

Um das Seitenlayout festzulegen, können Sie den [PnP-PowerShell-Befehl von PnPClientSidePageSharePoint](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) mit-LayoutType HeaderlessSearchResults verwenden.

## <a name="use-sharepoint-framework-query-extensions"></a>Verwenden von SharePoint Framework-Abfrage Erweiterungen

Benutzerdefinierte Suchergebnisseiten können auch die [SharePoint Framework-Abfrageerweiterung](https://docs.microsoft.com/sharepoint/dev/spfx/building-search-extensions) verwenden, um die Abfrage zu ändern, bevor Sie an die Suchmaschine gesendet wird.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zur Seite "benutzerdefinierte Ergebnisse" finden Sie in unserer [Ignite 2019-Such Anpassungs-und-Entwicklungs Sitzung](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions).

Für Open Source-Projekte, erste Schritte mit unseren Microsoft-Such-APIs und weitere Beispiele für Anpassungen und Erweiterbarkeit, besuchen Sie die [Microsoft-Suche auf GitHub](https://github.com/microsoft-search).
