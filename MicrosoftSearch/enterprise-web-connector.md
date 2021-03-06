---
title: Unternehmenswebsites Graph Connector für Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Graph-Connectors für Unternehmenswebsites für Microsoft Search
ms.openlocfilehash: b0ed7cc4148dba6c7555fcf7c9c930184cdbc24c
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508796"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a>Graph-Connector für Unternehmenswebsites

Der Graph-Connector für Unternehmenswebsites ermöglicht Ihrer Organisation das Indizieren von Artikeln und Inhalten von internen **Websites.** Nachdem Sie den Connector konfiguriert und Inhalte von der Website synchronisiert haben, können Endbenutzer über einen beliebigen Microsoft Search-Client nach diesem Inhalt suchen.

> [!NOTE]
> Lesen Sie [**den Artikel Setup your Graph connector,**](configure-connector.md) um die allgemeinen Anweisungen zum Einrichten von Graph Connectors zu verstehen.

Dieser Artikel ist für jeden benutzer, der einen Connector für Unternehmenswebsites konfiguriert, ausgeführt und überwacht. Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Enterprise-Websiteconnector gelten. Dieser Artikel enthält auch Informationen zur [Problembehandlung und](#troubleshooting) [Einschränkungen](#limitations).

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center

Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Um eine Verbindung mit Ihrer Datenquelle herzustellen, müssen Sie die Stamm-URL der Website eingeben, eine Durchforstungsquelle und den Authentifizierungstyp auswählen, den Sie verwenden möchten: Keine, Standardauthentifizierung oder OAuth 2.0 mit [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/) Nachdem Sie diese Informationen abgeschlossen haben, wählen Sie Verbindung testen aus, um Ihre Einstellungen zu überprüfen.

### <a name="url"></a>URL

Verwenden Sie das Feld URL, um den Stamm der Website anzugeben, die Sie durchforsten möchten. Der Connector für Unternehmenswebsites verwendet diese URL als Ausgangspunkt und folgt allen Links aus dieser URL für die Durchforstung.

> [!NOTE]
> Wenn für die Website, die Sie durchforsten möchten, eine Sitemap definiert ist, durchforstet der Connector nur die URLs, die in der Sitemap aufgeführt sind. Wenn keine Sitemap definiert ist, durchforstet der Connector alle Links, die auf der Stamm-URL der Website gefunden wurden, tief.

### <a name="crawl-mode-cloud-or-on-premises-preview"></a>Durchforstungsmodus: Cloud oder Lokal (Vorschau)

Der Durchforstungsmodus bestimmt den Typ der Websites, die Sie indizieren möchten, entweder in der Cloud oder lokal. Wählen Sie für Ihre Cloudwebsites **Cloud** als Durchforstungsmodus aus.

Darüber hinaus unterstützt der Connector jetzt das Crawlen von lokalen Websites. Dieser Modus befindet sich in der Vorschau. Um auf Ihre lokalen Daten zu zugreifen, müssen Sie zuerst den Graph-Connector-Agent installieren und konfigurieren. Weitere Informationen finden Sie unter [Graph Connector Agent](https://docs.microsoft.com/microsoftsearch/on-prem-agent).

Wählen Sie für Ihre lokalen Websites **Agent** als Durchforstungsmodus aus, und wählen Sie im Feld **On-Prem Agent** den Graph-Connector-Agent aus, den Sie zuvor installiert und konfiguriert haben.  

> [!div class="mx-imgBorder"]
> ![Screenshot des Bereichs "Verbindungseinstellungen" für Den Unternehmenswebconnector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)

### <a name="authentication"></a>Authentifizierung

Die Standardauthentifizierung erfordert einen Benutzernamen und ein Kennwort. Erstellen Sie dieses Botkonto mithilfe des [Microsoft 365 Admin Centers](https://admin.microsoft.com).

OAuth 2.0 mit [Azure AD](https://docs.microsoft.com/azure/active-directory/) erfordert eine Ressourcen-ID, Eine Client-ID und einen geheimen Clientgeheimnis. OAuth 2.0 funktioniert nur im Cloudmodus.

Weitere Informationen finden Sie unter [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Registrieren Sie sich mit den folgenden Werten:

**Name:** Microsoft Search <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Um die Werte für die Ressource, client_id und client_secret abzurufen, wechseln Sie zu Verwenden des Autorisierungscodes zum Anfordern eines Zugriffstokens auf der Umleitungs-URL-Webseite. 

Weitere Informationen finden Sie unter [Schnellstart: Registrieren einer](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)Anwendung bei der Microsoft Identity Platform .

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a>Schritt 3a: Hinzufügen von auszuschließender URLs (Optionale Durchforstungseinschränkungen)

Es gibt zwei Möglichkeiten, das Crawlen von Seiten zu verhindern: Sie können sie nicht in Ihrer robots.txt oder der Ausschlussliste hinzufügen.

### <a name="support-for-robotstxt"></a>Unterstützung für robots.txt

Der Connector überprüft, ob eine robots.txt für Ihre Stammwebsite vorhanden ist, und, falls vorhanden, folgt und respektiert die Anweisungen, die in dieser Datei gefunden wurden. Wenn sie nicht möchten, dass der Connector bestimmte Seiten oder Verzeichnisse auf Ihrer Website durchforstet, können Sie diese Seiten oder Verzeichnisse in den Deklarationen "Nicht robots.txt aufrufen.

### <a name="add-urls-to-exclude"></a>Hinzufügen von auszuschließende URLs

Sie können optional  eine Ausschlussliste erstellen, um zu verhindern, dass einige URLs durchforstet werden, wenn dieser Inhalt vertraulich ist oder keine Durchforstung wert ist. Um eine Ausschlussliste zu erstellen, navigieren Sie durch die Stamm-URL. Sie können die ausgeschlossenen URLs während des Konfigurationsprozesses zur Liste hinzufügen.

## <a name="step-4-assign-property-labels"></a>Schritt 4: Zuweisen von Eigenschaftsbezeichnungen

Sie können jeder Bezeichnung eine Quelleigenschaft zuweisen, indem Sie aus einem Menü mit Optionen auswählen. Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaftsbezeichnungen verbessern die Suchrelevanz und stellen genauere Suchergebnisse für Endbenutzer sicher.

## <a name="step-5-manage-schema"></a>Schritt 5: Verwalten des Schemas

Auf dem **Bildschirm Schema verwalten** können Sie die Schemaattribute (die Optionen sind **Query,** **Search,** **Retrieve** und **Refine**) ändern, die den Eigenschaften zugeordnet sind, optionale Aliase hinzufügen und die **Content-Eigenschaft** auswählen.

## <a name="step-6-manage-search-permissions"></a>Schritt 6: Verwalten von Suchberechtigungen

Der Connector für Unternehmenswebsites unterstützt nur Suchberechtigungen, die für **Jeder sichtbar sind.** Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.

## <a name="step-7-set-the-refresh-schedule"></a>Schritt 7: Festlegen des Aktualisierungszeitplans

Der Connector für Unternehmenswebsites unterstützt nur eine vollständige Aktualisierung. Dies bedeutet, dass der Connector bei jeder Aktualisierung alle Inhalte der Website neu durchrawlt. Um sicherzustellen, dass der Connector genügend Zeit zum Durchforsten des Inhalts erhält, wird empfohlen, ein großes Aktualisierungszeitintervall zu legen. Es wird eine geplante Aktualisierung zwischen ein und zwei Wochen empfohlen.

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Befolgen Sie die [allgemeinen Setupanweisungen](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>Problembehandlung

Beim Lesen des Inhalts der Website kann bei der Durchforstung einige Quellfehler auftreten, die durch die unten aufgeführten detaillierten Fehlercodes dargestellt werden. Um weitere Informationen zu den Fehlertypen  zu erhalten, wechseln Sie zur Seite Fehlerdetails, nachdem Sie die Verbindung ausgewählt haben. Wählen Sie den **Fehlercode aus,** um ausführlichere Fehler zu sehen. Weitere Informationen [finden Sie unter Manage your connector.](https://docs.microsoft.com/microsoftsearch/manage-connector)

 Detaillierter Fehlercode | Fehlermeldung
 --- | ---
 6001 | Die Website, die indiziert werden soll, ist nicht erreichbar.
 6005 | Die Quellseite, die indiziert werden soll, wurde nach der Konfiguration robots.txt gesperrt.
 6008 | DNS kann nicht aufgelöst werden
 6009 | Weitere Informationen zu allen clientseitigen Fehlern (mit Ausnahme von HTTP 404, 408) finden Sie unter HTTP 4xx-Fehlercodes.
 6013 | Die Quellseite, die indiziert werden soll, konnte nicht gefunden werden. (HTTP 404-Fehler)
 6018 | Die Quellseite antwortet nicht, und die Anforderung hat ein Zeit-Out. (HTTP 408-Fehler)
 6021 | Die Quellseite, die indiziert werden soll, enthält keinen Textinhalt auf der Seite.
 6023 | Die Quellseite, die indiziert werden soll, wird nicht unterstützt (keine HTML-Seite)
 6024 | Die Quellseite, die indiziert werden soll, enthält nicht unterstützte Inhalte.

* Fehler 6001-6013 treten auf, wenn die Datenquelle aufgrund eines Netzwerkproblems nicht erreichbar ist oder wenn die Datenquelle selbst gelöscht, verschoben oder umbenannt wird. Überprüfen Sie, ob die bereitgestellten Datenquellendetails noch gültig sind.
* Fehler 6021-6024 treten auf, wenn die Datenquelle nicht textbezogene Inhalte auf der Seite enthält oder wenn es sich bei der Seite nicht um einen HTML-Code handelt. Überprüfen Sie die Datenquelle, und fügen Sie diese Seite in der Ausschlussliste hinzu, oder ignorieren Sie den Fehler.

## <a name="limitations"></a>Einschränkungen

Der Connector für Unternehmenswebsites unterstützt das Durchsuchen von Daten auf **dynamischen Webseiten nicht.** Beispiele für diese Webseiten finden Sie in Inhaltsverwaltungssystemen wie [Confluence](https://www.atlassian.com/software/confluence) und [Unily](https://www.unily.com/) oder Datenbanken, in denen Websiteinhalte gespeichert werden.