---
title: Graph connector für Unternehmenswebsites für Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Enterprise-Websites-Graph-Connectors für Microsoft Search
ms.openlocfilehash: bf706399ec55fafbe96ce53622ce8502c81c2190
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084884"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a>Graph connector für Unternehmenswebsites

Der Graph-Connector für Unternehmenswebsites ermöglicht Ihrer Organisation das Indizieren von Artikeln und Inhalten von ihren **internen Websites.** Nachdem Sie den Connector konfiguriert und Inhalte von der Website synchronisiert haben, können Endbenutzer von einem beliebigen Microsoft Search-Client aus nach diesen Inhalten suchen.

> [!NOTE]
> Lesen Sie den [**Artikel zum Einrichten ihres Graph-Connectors,**](configure-connector.md) um den allgemeinen Einrichtungsprozess für Graph Connectors zu verstehen.

Dieser Artikel ist für jeden benutzer, der einen ServiceNow Graph Connector konfiguriert, ausgeführt und überwacht. Sie ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den ServiceNow Graph-Connector gelten. Dieser Artikel enthält auch Informationen zur [Problembehandlung und](#troubleshooting) [Einschränkungen.](#limitations)

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Um eine Verbindung mit Ihrer Datenquelle herzustellen, müssen Sie die Stamm-URL der Website eingeben, eine Durchforstungsquelle und den Authentifizierungstyp auswählen, den Sie verwenden möchten: Keine, Standardauthentifizierung oder OAuth 2.0 mit [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/). Nachdem Sie diese Informationen abgeschlossen haben, wählen Sie "Verbindung testen" aus, um Ihre Einstellungen zu überprüfen.

### <a name="url"></a>URL

Verwenden Sie das URL-Feld, um den Stamm der Website anzugeben, die Sie crawlen möchten. Der Connector für Unternehmenswebsites verwendet diese URL als Ausgangspunkt und folgt allen Links aus dieser URL für die Durchforstung.

### <a name="crawl-mode-cloud-or-on-premises-preview"></a>Durchforstungsmodus: Cloud oder lokal (Vorschau)

Der Durchforstungsmodus bestimmt den Typ der Websites, die Sie indizieren möchten, entweder in der Cloud oder lokal. Wählen Sie für Ihre Cloudwebsites **Cloud** als Durchforstungsmodus aus.

Außerdem unterstützt der Connector jetzt das Crawlen von lokalen Websites. Dieser Modus befindet sich in der Vorschau. Für den Zugriff auf Ihre lokalen Daten müssen Sie zuerst den Graph-Connector-Agent installieren und konfigurieren. Weitere Informationen finden Sie unter [Graph Connector Agent](https://docs.microsoft.com/microsoftsearch/on-prem-agent).

Wählen Sie für Ihre lokalen Websites **"Agent"** als Durchforstungsmodus aus, und wählen Sie im Feld **"Vor-Ort-Agent"** den Graph-Connector-Agent aus, den Sie zuvor installiert und konfiguriert haben.  

> [!div class="mx-imgBorder"]
> ![Screenshot des Bereichs "Verbindungseinstellungen" für den Unternehmenswebconnector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)

### <a name="authentication"></a>Authentifizierung

Für die Standardauthentifizierung sind ein Benutzername und ein Kennwort erforderlich. Erstellen Sie dieses Botkonto mithilfe des [Microsoft 365 Admin Centers.](https://admin.microsoft.com)

OAuth 2.0 mit [Azure AD](https://docs.microsoft.com/azure/active-directory/) erfordert eine Ressourcen-ID, Client-ID und einen geheimen Client-Schlüssel. OAuth 2.0 funktioniert nur mit dem Cloudmodus.

Weitere Informationen finden Sie unter Autorisieren des Zugriffs auf Azure Active Directory-Webanwendungen mithilfe des [OAuth 2.0-Codeerteilungsflusses.](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code) Registrieren Sie sich mit den folgenden Werten:

**Name:** Microsoft Search <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

To get the values for the resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.

Weitere Informationen finden Sie unter [Schnellstart: Registrieren einer](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)Anwendung bei der Microsoft Identity Platform.

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a>Schritt 3a: Hinzufügen auszuschließender URLs (optionale Durchforstungseinschränkungen)

Es gibt zwei Möglichkeiten, das Crawlen von Seiten zu verhindern: Sie können sie in Ihrer robots.txt oder der Ausschlussliste hinzufügen.

### <a name="support-for-robotstxt"></a>Unterstützung für robots.txt

Der Connector überprüft, ob eine robots.txt für Ihre Stammwebsite vorhanden ist. Wenn eine vorhanden ist, folgt und respektiert er die in dieser Datei gefundenen Anweisungen. Wenn der Connector bestimmte Seiten oder Verzeichnisse auf Ihrer Website nicht durchforsten soll, können Sie diese Seiten oder Verzeichnisse in den Deklarationen "Nicht robots.txt aufrufen.

### <a name="add-urls-to-exclude"></a>Auszuschließende URLs hinzufügen

Sie können optional  eine Ausschlussliste erstellen, um einige URLs von der Durchforstung auszuschließen, wenn dieser Inhalt vertraulich ist oder das Crawlen nicht wert ist. Um eine Ausschlussliste zu erstellen, navigieren Sie durch die Stamm-URL. Sie können die ausgeschlossenen URLs während des Konfigurationsprozesses der Liste hinzufügen.

## <a name="step-4-assign-property-labels"></a>Schritt 4: Zuweisen von Eigenschaftsbezeichnungen

Sie können jeder Bezeichnung eine Quelleigenschaft zuweisen, indem Sie aus einem Menü mit Optionen auswählen. Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaftsbezeichnungen verbessern die Suchrelevanz und stellen für Endbenutzer genauere Suchergebnisse sicher.

## <a name="step-5-manage-schema"></a>Schritt 5: Verwalten des Schemas

Auf dem Bildschirm **Schema verwalten** können Sie die Schemaattribute ändern (die Optionen sind **Abfrage,** **Suche,** Abrufen **und** Verfeinern), die den Eigenschaften zugeordnet sind, optionale Aliase hinzufügen und die Eigenschaft **"Content"** auswählen.

## <a name="step-6-manage-search-permissions"></a>Schritt 6: Verwalten von Suchberechtigungen

Der Connector für Unternehmenswebsites unterstützt nur Suchberechtigungen, die für jeden **sichtbar sind.** Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.

## <a name="step-7-set-the-refresh-schedule"></a>Schritt 7: Festlegen des Aktualisierungszeitplans

Der Connector für Unternehmenswebsites unterstützt nur eine vollständige Aktualisierung. Dies bedeutet, dass der Connector alle Inhalte der Website während jeder Aktualisierung neu durchrawlt. Um sicherzustellen, dass der Connector genügend Zeit zum Durchforsten des Inhalts hat, sollten Sie ein großes Aktualisierungszeitintervall festlegen. Wir empfehlen eine geplante Aktualisierung zwischen einer und zwei Wochen.

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>Problembehandlung

Beim Lesen des Websiteinhalts kann es bei der Durchforstung zu einigen Quellfehlern kommen, die durch die folgenden detaillierten Fehlercodes dargestellt werden. Wenn Sie weitere Informationen zu den Arten  von Fehlern erhalten möchten, wechseln Sie nach dem Auswählen der Verbindung zur Seite mit den Fehlerdetails. Wählen Sie den **Fehlercode aus,** um detailliertere Fehler zu erhalten. Weitere Informationen [finden Sie unter "Verwalten des Connectors".](https://docs.microsoft.com/microsoftsearch/manage-connector)

 Detaillierter Fehlercode | Fehlermeldung
 --- | ---
 6001 | Die Website, die indiziert werden soll, ist nicht erreichbar.
 6005 | Die Quellseite, die indiziert werden soll, wurde wie in der robots.txt blockiert.
 6008 | Dns kann nicht aufgelöst werden
 6009 | Weitere Informationen zu allen clientseitigen Fehlern (mit Ausnahme von HTTP 404, 408) finden Sie unter HTTP 4xx-Fehlercodes.
 6013 | Die Quellseite, die indiziert werden soll, konnte nicht gefunden werden. (HTTP 404-Fehler)
 6018 | Die Quellseite reagiert nicht, und für die Anforderung ist ein Zeit zeitl. (HTTP 408-Fehler)
 6021 | Die Quellseite, die indiziert werden soll, enthält keinen Textinhalt auf der Seite.
 6023 | Die Quellseite, die indiziert werden soll, wird nicht unterstützt (keine HTML-Seite).
 6024 | Die Quellseite, die indiziert werden soll, enthält nicht unterstützte Inhalte.

* Fehler 6001-6013 treten auf, wenn die Datenquelle aufgrund eines Netzwerkproblems nicht erreichbar ist oder wenn die Datenquelle selbst gelöscht, verschoben oder umbenannt wird. Überprüfen Sie, ob die bereitgestellten Datenquellendetails noch gültig sind.
* Fehler 6021-6024 treten auf, wenn die Datenquelle nicht textbezogene Inhalte auf der Seite enthält oder die Seite kein HTML ist. Überprüfen Sie die Datenquelle, und fügen Sie diese Seite der Ausschlussliste hinzu, oder ignorieren Sie den Fehler.

## <a name="limitations"></a>Einschränkungen

Der Connector für Unternehmenswebsites unterstützt das Durchsuchen von Daten auf **dynamischen Webseiten nicht.** Beispiele für diese Webseiten werden in Inhaltsverwaltungssystemen wie ["Confluence"](https://www.atlassian.com/software/confluence) und ["Unily"](https://www.unily.com/) oder in Datenbanken mit Websiteinhalten verwendet.