---
title: Enterprise-Websites-Connector für Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Connectors für die Enterprise-Websites für Microsoft Search
ms.openlocfilehash: 443e903e0fa371d2a056fd4bf06310eb2627b11c
ms.sourcegitcommit: 031e7c595496d9faed9038725b04f3c8b5f9ccbd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604773"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a>Enterprise-Websites-Connector

Mit dem Enterprise-Website-Konnektor kann Ihre Organisation Artikel und **Inhalte von den internen Websites aus** indizieren. Nachdem Sie den Connector konfiguriert und Inhalte von der Website synchronisiert haben, können Endbenutzer nach diesen Inhalten von einem beliebigen Microsoft Search-Client aus suchen.

Dieser Artikel richtet sich an [Microsoft 365](https://www.microsoft.com/microsoft-365) -Administratoren oder Personen, die einen Connector für Unternehmenswebsites konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.  

## <a name="connection-settings"></a>Verbindungseinstellungen

Um eine Verbindung mit Ihrer Datenquelle herzustellen, müssen Sie die Stamm-URL der Website ausfüllen, eine Durchforstungs Quelle und die Art der Authentifizierung auswählen, die Sie verwenden möchten: None, Standardauthentifizierung oder OAuth 2,0 mit [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/). Nachdem Sie diese Informationen abgeschlossen haben, klicken Sie auf Verbindung testen, um die Einstellungen zu überprüfen.

### <a name="url"></a>URL

Verwenden Sie das Feld URL, um den Stamm der Website anzugeben, die Sie crawlen möchten. Der Connector für Unternehmenswebsites verwendet diese URL als Ausgangspunkt und befolgt alle Links von dieser URL für die Durchforstung.

### <a name="crawl-mode-cloud-or-on-premises-preview"></a>Durchforstungs Modus: Cloud oder lokal (Vorschau)

Der Durchforstungs Modus bestimmt den Typ der Websites, die Sie indizieren möchten, entweder Cloud oder lokal. Wählen Sie für Ihre Cloud-Websites als Durchforstungs Modus die Option **Cloud** aus.

Außerdem unterstützt der Connector jetzt das Crawlen von lokalen Websites. Dieser Modus befindet sich in der Vorschau. Um auf Ihre lokalen Daten zuzugreifen, müssen Sie zuerst den Graph Connector-Agent installieren und konfigurieren. Weitere Informationen finden Sie unter [Graph Connector Agent](https://docs.microsoft.com/microsoftsearch/on-prem-agent).

Wählen Sie für Ihre lokalen Websites **Agent** als Durchforstungs Modus aus, und wählen Sie im Feld **on-Prem Agent** den Graph Connector-Agent aus, den Sie zuvor installiert und konfiguriert haben.  

![Screenshot des Bereichs "Verbindungseinstellungen" für Enterprise-WebConnector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)

### <a name="authentication"></a>Authentifizierung

Für die Standardauthentifizierung ist ein Benutzername und ein Kennwort erforderlich. Erstellen Sie dieses bot-Konto mithilfe des [Microsoft 365 Admin Center](https://admin.microsoft.com).

OAuth 2,0 mit [Azure AD](https://docs.microsoft.com/azure/active-directory/) erfordert eine Ressourcen-ID, eine Client-ID und einen geheimen Client Schlüssel. OAuth 2,0 funktioniert nur im Cloud-Modus.

Weitere Informationen finden Sie unter [Autorisieren des Zugriffs auf Azure Active Directory Webanwendungen mithilfe des OAuth 2,0-Code Zuteilungs Flusses](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Registrieren Sie sich mit den folgenden Werten:

**Name:** Microsoft-Suche <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Um die Werte für die Ressource, client_id und client_secret abzurufen, wechseln Sie zum **Anfordern eines Zugriffstokens mithilfe des Autorisierungscodes** auf der Webseite der Umleitungs-URL.

Weitere Informationen finden Sie unter [Quick Start: Registrieren einer Anwendung mit der Microsoft Identity-Plattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="support-for-robotstxt"></a>Unterstützung für robots.txt

Der Connector überprüft, ob es eine robots.txt Datei für die Stammwebsite gibt, und wenn eine vorhanden ist, befolgt Sie die in der Datei gefundenen Anweisungen und respektiert sie. Wenn Sie nicht möchten, dass der Connector bestimmte Seiten oder Verzeichnisse auf Ihrer Website durchforstet, können Sie diese Seiten oder Verzeichnisse in den "Disallow"-Deklarationen in ihrer robots.txt Datei aufrufen.

## <a name="add-urls-to-exclude"></a>Hinzufügen von URLs zum Ausschließen

Sie können optional eine **Ausschlussliste** erstellen, um einige URLs von der Durchforstung auszuschließen, wenn dieser Inhalt vertraulich ist oder nicht durchforstet werden sollte. Um eine Ausschlussliste zu erstellen, navigieren Sie durch die Stamm-URL. Sie haben die Möglichkeit, die ausgeschlossenen URLs während des Konfigurationsprozesses der Liste hinzuzufügen.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen

Der Connector für Unternehmenswebsites unterstützt nur Suchberechtigungen, die für **alle** sichtbar sind. Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.

## <a name="assign-property-labels"></a>Zuweisen von Eigenschaften Bezeichnungen

Sie können jeder Beschriftung eine Source-Eigenschaft zuweisen, indem Sie in einem Menü mit Optionen auswählen. Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaften Bezeichnungen verbessern die Suchrelevanz und stellen genauere Suchergebnisse für Endbenutzer sicher.

## <a name="manage-schema"></a>Schema verwalten

Auf dem Bildschirm " **Schema verwalten** " haben Sie die Möglichkeit, die den Eigenschaften zugeordneten Schema **Attribute (** abfragbar, **durchsuchbar**, **abrufbar** und **verfeinernd**) zu ändern, optionale Aliase hinzuzufügen und die **Content** -Eigenschaft auszuwählen.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans

Der Connector für Unternehmenswebsites unterstützt nur eine vollständige Aktualisierung. Dies bedeutet, dass der Connector während jeder Aktualisierung alle Inhalte der Website erneut crawlt. Um sicherzustellen, dass der Connector genügend Zeit zum durchforsten des Inhalts erhält, wird empfohlen, ein Intervall für eine große Aktualisierungsplanung festzulegen. Wir empfehlen eine geplante Aktualisierung zwischen einer und zwei Wochen.

## <a name="troubleshooting"></a>Problembehandlung

Beim Lesen des Inhalts der Website kann bei der Durchforstung einige Quellfehler auftreten, die durch die detaillierten Fehlercodes unten dargestellt werden. Wenn Sie weitere Informationen zu den Fehlertypen erhalten möchten, wechseln Sie zur Seite **Fehlerdetails** , nachdem Sie die Verbindung ausgewählt haben. Klicken Sie auf den **Fehlercode** , um ausführlichere Fehler anzuzeigen. Weitere Informationen finden Sie auch unter [Manage Your Connector](https://docs.microsoft.com/microsoftsearch/manage-connector) .

 Detaillierter Fehlercode | Fehlermeldung
 --- | ---
 6001 | Die Website, die zum Indizieren versucht wird, ist nicht erreichbar
 6005 | Die Quellseite, die versucht wird, den Index zu indizieren, wurde gemäß robots.txt Konfiguration blockiert.
 6008 | DNS konnte nicht aufgelöst werden
 6009 | Für alle clientseitigen Fehler (mit Ausnahme von HTTP 404, 408) finden Sie weitere Informationen in den HTTP-4xx-Fehlercodes.
 6013 | Die Quellseite, die zum Indizieren versucht wird, konnte nicht gefunden werden. (HTTP 404-Fehler)
 6018 | Die Quellseite reagiert nicht, und für die Anforderung ist ein Timeout aufgetreten. (Http 408-Fehler)
 6021 | Auf der Quellseite, die versucht wird, zu indizieren, sind keine Textinhalte auf der Seite zu finden.
 6023 | Die Quellseite, die versucht wird, zu indizieren, wird nicht unterstützt (keine HTML-Seite)
 6024 | Die Quellseite, die versucht wird, zu indizieren, enthält nicht unterstützte Inhalte.

* Fehler 6001-6013 tritt auf, wenn die Datenquelle aufgrund eines Netzwerkproblems nicht erreichbar ist oder wenn die Datenquelle selbst gelöscht, verschoben oder umbenannt wird. Überprüfen, ob die bereitgestellten Datenquellendetails noch gültig sind.
* Fehler 6021-6024 tritt auf, wenn die Datenquelle nicht textliche Inhalte auf der Seite enthält oder wenn es sich bei der Seite nicht um einen HTML-Code handelt. Überprüfen Sie die Datenquelle, und fügen Sie diese Seite in Ausschlussliste hinzu, oder ignorieren Sie den Fehler.

## <a name="limitations"></a>Einschränkungen

Der Connector für Unternehmenswebsites unterstützt die Suche von Daten auf **dynamischen** Webseiten nicht. Beispiele für diese Webseiten Leben in Inhaltsverwaltungssystemen wie [Confluence](https://www.atlassian.com/software/confluence) und [Unily](https://www.unily.com/) oder in Datenbanken, in denen Websiteinhalte gespeichert sind.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Verbindung veröffentlicht haben, müssen Sie die Suchergebnisseite anpassen. Informationen zum Anpassen von Suchergebnissen finden Sie unter [Anpassen der Suchergebnisseite](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).
