---
title: Enterprise-Websites-Connector für Microsoft Search
ms.author: mounika.narayanan
author: monaray
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
ms.openlocfilehash: fcda5db9b294e3d70bb27879f1bb0efb43ad6936
ms.sourcegitcommit: 0b5e3764822f64532c8a8e14b8e56e35141a558d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127641"
---
# <a name="enterprise-websites-connector"></a>Enterprise-Websites-Connector

Mit dem Enterprise-Website-Konnektor kann Ihre Organisation Artikel und **Inhalte von den internen Websites aus**indizieren. Nachdem Sie den Connector konfiguriert und Inhalte von der Website synchronisiert haben, können Endbenutzer nach diesen Inhalten von einem beliebigen Microsoft Search-Client aus suchen.

Dieser Artikel richtet sich an [Microsoft 365](https://www.microsoft.com/microsoft-365) -Administratoren oder Personen, die einen Connector für Unternehmenswebsites konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.  

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle 
Zum Herstellen einer Verbindung mit Ihrer Datenquelle benötigen Sie die Stamm-URL und eine Form der Authentifizierung: None, Standardauthentifizierung oder OAuth 2,0 mit [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).

### <a name="authentication"></a>Authentifizierung 
Für die Standardauthentifizierung ist ein Benutzername und ein Kennwort erforderlich. Erstellen Sie dieses bot-Konto mithilfe des Microsoft 365 [Admin Center](https://admin.microsoft.com).

OAuth 2,0 mit [Azure AD](https://docs.microsoft.com/azure/active-directory/) erfordert eine Ressourcen-ID, eine Client-ID und einen geheimen Client Schlüssel.

Weitere Informationen finden Sie unter [Autorisieren des Zugriffs auf Azure Active Directory Webanwendungen mithilfe des OAuth 2,0-Code Zuteilungs Flusses](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Registrieren Sie sich mit den folgenden Werten:

**Name:** Microsoft-Suche <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Um die Werte für die Ressource, client_id und client_secret abzurufen, wechseln Sie zum **Anfordern eines Zugriffstokens mithilfe des Autorisierungscodes** auf der Webseite der Umleitungs-URL.

Weitere Informationen finden Sie unter [Quick Start: Registrieren einer Anwendung mit der Microsoft Identity-Plattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

### <a name="root-url"></a>Stamm-URL
Die Stamm-URL ist das, was die Durchforstung initiiert und für die Authentifizierung verwendet wird. Sie können die URL von der Startseite der Website abrufen, die Sie durchforsten möchten.

## <a name="select-the-source-properties"></a>Auswählen der Quelleigenschaften 
Quelleigenschaften werden basierend auf dem Datenformat der Unternehmenswebsite definiert. Sie können jedoch eine **Ausschlussliste** erstellen, um einige URLs von der Durchforstung auszuschließen, wenn dieser Inhalt vertraulich ist oder nicht durchforstet werden kann. Um eine Ausschlussliste zu erstellen, navigieren Sie durch die Stamm-URL. Sie haben die Möglichkeit, die ausgeschlossenen URLs während des Konfigurationsprozesses der Liste hinzuzufügen.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen 
Es gibt keine Unterstützung für Zugriffssteuerungslisten (Access Control Lists, ACLs). Daher wird empfohlen, nur die Websites zu verbinden, die für jeden Benutzer in Ihrer Organisation sichtbar sind.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans
Der Connector für Unternehmenswebsites unterstützt nur eine vollständige Durchforstung. Dies bedeutet, dass der Connector während jeder Durchforstung alle Inhalte der Website liest. Um sicherzustellen, dass der Connector genügend Zeit zum Lesen des Inhalts erhält, wird empfohlen, ein Intervall für eine große Aktualisierungsplanung festzulegen. Wir empfehlen eine geplante Aktualisierung zwischen einer und zwei Wochen.

## <a name="troubleshooting"></a>Problembehandlung
Beim Lesen des Inhalts der Website kann bei der Durchforstung einige Quellfehler auftreten, die durch die detaillierten Fehlercodes unten dargestellt werden. Wenn Sie weitere Informationen zu den Fehlertypen erhalten möchten, wechseln Sie zur Seite **Fehlerdetails** , nachdem Sie die Verbindung ausgewählt haben. Klicken Sie auf den **Fehlercode** , um ausführlichere Fehler anzuzeigen. Weitere Informationen finden Sie auch unter [Manage Your Connector](https://docs.microsoft.com/microsoftsearch/manage-connector) .

 Detaillierter Fehlercode | Fehlermeldung
 --- | --- 
 6001   | Die Website, die zum Indizieren versucht wird, ist nicht erreichbar 
 6005 | Die Quellseite, die versucht wird, den Index zu indizieren, wurde gemäß robots.txt Konfiguration blockiert.
 6008 | DNS konnte nicht aufgelöst werden
 6009 | Für alle clientseitigen Fehler (mit Ausnahme von HTTP 404, 408) finden Sie weitere Informationen unter http 4xx-Fehlercodes.
 6013 | Die Quellseite, die zum Indizieren versucht wird, konnte nicht gefunden werden. (HTTP 404-Fehler)
 6018 | Die Quellseite reagiert nicht, und für die Anforderung ist ein Timeout aufgetreten. (Http 408-Fehler)
 6021 | Auf der Quellseite, die versucht wird, zu indizieren, sind keine Textinhalte auf der Seite zu finden.
 6023 | Die Quellseite, die versucht wird, zu indizieren, wird nicht unterstützt (keine HTML-Seite)
 6024 | Die Quellseite, die versucht wird, zu indizieren, enthält nicht unterstützte Inhalte.

* Fehler 6001-6013 tritt auf, wenn die Datenquelle aufgrund eines Netzwerkproblems nicht erreichbar ist oder wenn die Datenquelle selbst gelöscht, verschoben oder umbenannt wird. Überprüfen, ob die bereitgestellten Datenquellendetails noch gültig sind.
* Fehler 6021-6024 Fehler tritt auf, wenn die Datenquelle nicht textliche Inhalte auf der Seite enthält oder wenn es sich bei der Seite nicht um einen HTML-Code handelt. Überprüfen Sie die Datenquelle, und fügen Sie diese Seite in Ausschlussliste hinzu, oder ignorieren Sie den Fehler.

## <a name="limitations"></a>Einschränkungen
Der Connector für Unternehmenswebsites unterstützt die Suche von Daten auf **dynamischen**Webseiten nicht. Beispiele für diese Webseiten Leben in Inhaltsverwaltungssystemen wie [Confluence](https://www.atlassian.com/software/confluence) und [Unily](https://www.unily.com/) oder in Datenbanken, in denen Websiteinhalte gespeichert sind.
