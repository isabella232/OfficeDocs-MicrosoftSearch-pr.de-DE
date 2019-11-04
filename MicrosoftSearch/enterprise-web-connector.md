---
title: Enterprise-Websites-Connector für Microsoft Search
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Connectors für die Enterprise-Websites für Microsoft Search
ms.openlocfilehash: 3caca53204bfb2cca4209e048a21173f550e3d39
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949816"
---
# <a name="enterprise-websites-connector"></a>Enterprise-Websites-Connector

Mit dem Enterprise-Website-Konnektor kann Ihre Organisation Artikel und **Inhalte von den internen Websites aus**indizieren. Nachdem Sie den Connector konfiguriert und Inhalte von der Website synchronisiert haben, können Endbenutzer nach diesen Inhalten von einem beliebigen Microsoft Search-Client aus suchen.

Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen Connector für Unternehmenswebsites konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.  

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle 
Zum Herstellen einer Verbindung mit Ihrer Datenquelle benötigen Sie die Stamm-URL und eine Form der Authentifizierung (Standardauthentifizierung oder OAuth 2,0 mit Azure AD).

### <a name="root-url"></a>Stamm-URL
Die Stamm-URL ist das, was die Durchforstung initiiert und für die Authentifizierung verwendet wird. Sie können die URL von der Startseite der Website abrufen, die Sie durchforsten möchten.

### <a name="authentication"></a>Authentifizierung 
Für die Standardauthentifizierung ist ein Benutzername und ein Kennwort erforderlich. Erstellen Sie dieses bot-Konto mithilfe des [Microsoft 365 Admin Center](https://admin.microsoft.com).

OAuth 2,0 mit Azure AD erfordert eine Mandanten-ID, eine Ressourcen-ID, eine Client-ID und einen geheimen Client Schlüssel.
Weitere Informationen finden Sie unter [Autorisieren des Zugriffs auf Azure Active Directory Webanwendungen mithilfe des OAuth 2,0-Code Zuteilungs Flusses](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Registrieren Sie sich mit den folgenden Werten:
* **Name:** Microsoft-Suche
* **Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Um die Werte für benannte Mandanten, Ressourcen, client_id und client_secret abzurufen, wechseln Sie zum **Anfordern eines Zugriffstokens mithilfe des Autorisierungscodes** auf der Webseite der Umleitungs-URL.

Weitere Informationen finden Sie unter [Quick Start: Registrieren einer Anwendung mit der Microsoft Identity-Plattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

### <a name="reverse-proxy-url"></a>Reverse Proxy-URL 
Der Connector für Enterprise-Websites ist Cloud-basiert, sodass kein Zugriff auf lokale Inhalte möglich ist. Um diesen Zugriff bereitzustellen, installieren Sie einen Reverseproxy. Ein Reverse-Proxy bietet sicheren, zuverlässigen Zugriff auf lokale Websites. Wir empfehlen den Azure Application Proxy (AAP).

Die Reverse-Proxyanforderung für die Stamm-URL und-Authentifizierung ist identisch mit dem cloudbasierten Inhalt, mit der Ausnahme, dass die Stamm-URL und die Authentifizierung vom Reverseproxy bereitgestellt werden.

Weitere Informationen finden Sie unter [Sicherheitsüberlegungen für den Remotezugriff auf apps mit Azure AD-Anwendungs Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security).

## <a name="select-the-source-properties"></a>Auswählen der Quelleigenschaften 
Quelleigenschaften werden basierend auf dem Datenformat der Unternehmenswebsite definiert. Sie können jedoch eine **Ausschlussliste** erstellen, um einige URLs von der Durchforstung auszuschließen, da dieser Inhalt möglicherweise vertraulich ist oder nicht durchforstet werden sollte. Um eine Ausschlussliste zu erstellen, navigieren Sie durch die Stamm-URL. Sie haben die Möglichkeit, die ausgeschlossenen URLs während des Konfigurationsprozesses der Liste hinzuzufügen.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen 
Es gibt keine Unterstützung für Zugriffssteuerungslisten (Access Control Lists, ACLs). Es wird daher empfohlen, nur die Websites zu verbinden, die für einen beliebigen Benutzer in Ihrer Organisation sichtbar sind.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans
Der Connector für Unternehmenswebsites unterstützt nur eine vollständige Durchforstung. Dies bedeutet, dass der Connector während jeder Durchforstung alle Inhalte der Website liest. Um sicherzustellen, dass der Connector genügend Zeit zum Lesen des Inhalts erhält, wird empfohlen, ein Intervall für eine große Aktualisierungsplanung festzulegen. Wir empfehlen eine geplante Aktualisierung zwischen drei Tagen und zwei Wochen.

## <a name="limitations"></a>Einschränkungen 
Der Connector für Unternehmenswebsites unterstützt die Suche von Daten auf dynamischen Webseiten nicht. Beispiele für diese Webseiten Leben in Inhaltsverwaltungssystemen wie Confluence und Unily oder in Datenbanken, in denen Websiteinhalte gespeichert sind.