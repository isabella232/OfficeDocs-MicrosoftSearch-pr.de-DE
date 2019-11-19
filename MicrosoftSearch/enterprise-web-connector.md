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
ms.openlocfilehash: 14eef035f4cc054ab87582b573cb6b7e3c12d0c7
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699521"
---
# <a name="enterprise-websites-connector"></a>Enterprise-Websites-Connector

Mit dem Enterprise-Website-Konnektor kann Ihre Organisation Artikel und **Inhalte von den internen Websites aus**indizieren. Nachdem Sie den Connector konfiguriert und Inhalte von der Website synchronisiert haben, können Endbenutzer nach diesen Inhalten von einem beliebigen Microsoft Search-Client aus suchen.

Dieser Artikel richtet sich an [Microsoft 365](https://www.microsoft.com/microsoft-365) -Administratoren oder Personen, die einen Connector für Unternehmenswebsites konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.  

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle 
Zum Herstellen einer Verbindung mit Ihrer Datenquelle benötigen Sie die Stamm-URL und eine Form der Authentifizierung: Standardauthentifizierung oder OAuth 2,0 mit [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).

### <a name="root-url"></a>Stamm-URL
Die Stamm-URL ist das, was die Durchforstung initiiert und für die Authentifizierung verwendet wird. Sie können die URL von der Startseite der Website abrufen, die Sie durchforsten möchten.

### <a name="authentication"></a>Authentifizierung 
Für die Standardauthentifizierung ist ein Benutzername und ein Kennwort erforderlich. Erstellen Sie dieses bot-Konto mithilfe des Microsoft 365 [Admin Center](https://admin.microsoft.com).

OAuth 2,0 mit [Azure AD](https://docs.microsoft.com/azure/active-directory/) erfordert eine Mandanten-ID, eine Ressourcen-ID, eine Client-ID und einen geheimen Client Schlüssel.
Weitere Informationen finden Sie unter [Autorisieren des Zugriffs auf Azure Active Directory Webanwendungen mithilfe des OAuth 2,0-Code Zuteilungs Flusses](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Registrieren Sie sich mit den folgenden Werten:
* **Name:** Microsoft-Suche
* **Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Um die Werte für benannte Mandanten, Ressourcen, client_id und client_secret abzurufen, rufen **Sie den Autorisierungscode zum Anfordern eines Zugriffstokens** auf der Webseite der Umleitungs-URL auf.

Weitere Informationen finden Sie unter [Quick Start: Registrieren einer Anwendung mit der Microsoft Identity-Plattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

### <a name="reverse-proxy-url"></a>Reverse Proxy-URL 
Der Connector für Enterprise-Websites ist Cloud-basiert, sodass kein Zugriff auf lokale Inhalte möglich ist. Um diesen Zugriff bereitzustellen, installieren Sie einen Reverseproxy. Ein Reverse-Proxy bietet sicheren, zuverlässigen Zugriff auf lokale Websites. Wir empfehlen [Azure Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

Die Reverse-Proxyanforderung für die Stamm-URL und-Authentifizierung ist identisch mit dem cloudbasierten Inhalt, mit der Ausnahme, dass die Stamm-URL und die Authentifizierung vom Reverseproxy bereitgestellt werden.

Weitere Informationen finden Sie unter [Sicherheitsüberlegungen für den Remotezugriff auf apps mit Azure AD-Anwendungs Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security).

## <a name="select-the-source-properties"></a>Auswählen der Quelleigenschaften 
Quelleigenschaften werden basierend auf dem Datenformat der Unternehmenswebsite definiert. Sie können jedoch eine **Ausschlussliste** erstellen, um einige URLs von der Durchforstung auszuschließen, wenn dieser Inhalt vertraulich ist oder nicht durchforstet werden kann. Um eine Ausschlussliste zu erstellen, navigieren Sie durch die Stamm-URL. Sie haben die Möglichkeit, die ausgeschlossenen URLs während des Konfigurationsprozesses der Liste hinzuzufügen.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen 
Es gibt keine Unterstützung für Zugriffssteuerungslisten (Access Control Lists, ACLs). Daher wird empfohlen, nur die Websites zu verbinden, die für jeden Benutzer in Ihrer Organisation sichtbar sind.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans
Der Connector für Unternehmenswebsites unterstützt nur eine vollständige Durchforstung. Dies bedeutet, dass der Connector während jeder Durchforstung alle Inhalte der Website liest. Um sicherzustellen, dass der Connector genügend Zeit zum Lesen des Inhalts erhält, wird empfohlen, ein Intervall für eine große Aktualisierungsplanung festzulegen. Wir empfehlen eine geplante Aktualisierung zwischen drei Tagen und zwei Wochen.

## <a name="limitations"></a>Einschränkungen 
Der Connector für Unternehmenswebsites unterstützt die Suche von Daten auf dynamischen Webseiten nicht. Beispiele für diese Webseiten Leben in Inhaltsverwaltungssystemen wie [Confluence](https://www.atlassian.com/software/confluence) und [Unily](https://www.unily.com/) oder in Datenbanken, in denen Websiteinhalte gespeichert sind.