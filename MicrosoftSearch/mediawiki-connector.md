---
title: MediaWiki Connector für Microsoft Search
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
description: Einrichten des MediaWiki-Connectors für Microsoft Search
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905952"
---
# <a name="mediawiki-connector"></a>MediaWiki Connector

Mit dem MediaWiki Connector kann Ihre Organisation Daten aus einem Wiki ermitteln und indizieren, das mit der Software MediaWiki erstellt wurde. Dieser Connector indiziert angegebene Inhalte in Microsoft Search und unterstützt regelmäßige Durchforstungen, um den Index auf dem neuesten Stand zu halten.

Dieser Artikel ist für Microsoft 365-Administratoren oder alle Personen, die einen MediaWiki Graph-Connector konfigurieren, ausgeführt und überwachen. Sie ergänzt die allgemeinen Anweisungen im Artikel ["Einrichten Ihres Graph-Connectors".](configure-connector.md) Wenn Sie dies noch nicht getan haben, lesen Sie den gesamten Artikel zum Einrichten Ihres Graph-Connectors, um den allgemeinen Einrichtungsprozess zu verstehen.

Jeder Schritt im Setupprozess wird unten aufgeführt, zusammen mit einem Hinweis, der angibt, dass Sie die allgemeinen Setupanweisungen oder andere Anweisungen befolgen sollten, die nur für MediaWiki Graph-Connectors gelten. Dieser Artikel enthält auch Informationen zu [Einschränkungen für](#limitations) MediaWiki Graph-Connectors. 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center.
Befolgen Sie die allgemeinen Setupanweisungen.

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen Sie die Verbindung.
Befolgen Sie die allgemeinen Setupanweisungen.
 
## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren Sie die Verbindungseinstellungen.
Geben Sie **Ihre Wiki-URL** ein, und wählen Sie im Dropdownmenü der Optionen den Authentifizierungstyp aus.  Die Optionen sind **None**, **Basic** und **OAuth 2.0 AAD**.

Wenn Sie **"Standard"** als Authentifizierungstyp  auswählen, müssen Sie den Benutzernamen und das **Kennwort für** das Wiki angeben.

Wenn Sie **OAuth 2.0 AAD** als Authentifizierungstyp auswählen, müssen Sie die **Ressourcen-ID** der Wiki-Installation bereitstellen. Sie müssen auch die **Client-ID** und den geheimen **Clientgeheimnis** bereitstellen, die auf der Registrierungsseite der AAD-Anwendung generiert werden. 

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen
Der Connector MediaWiki unterstützt nur Suchberechtigungen, die für jeden **sichtbar sind.** Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.

## <a name="step-5-assign-property-labels"></a>Schritt 5: Zuweisen von Eigenschaftsbezeichnungen
Befolgen Sie die allgemeinen Setupanweisungen.

## <a name="step-6-manage-schema"></a>Schritt 6: Verwalten des Schemas
Befolgen Sie die allgemeinen Setupanweisungen.

## <a name="step-7-choose-refresh-settings"></a>Schritt 7: Auswählen von Aktualisierungseinstellungen
Befolgen Sie die allgemeinen Setupanweisungen.

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung
Befolgen Sie die allgemeinen Setupanweisungen.

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Einschränkungen
Der MediaWiki Connector hat in der Vorschauversion die folgenden Einschränkungen:

* Unterstützt nur cloudbasierte Wikis.
* Unterstützt nur Basic oder OAuth 2.0 mit Azure Active Directory- oder Azure-Authentifizierung.
* Unterstützt keine Namespaceauswahl für die Indizierung. Indiziert nur Die Namespaces "Main", "Category" und "File".
* Unterstützt keine Zugriffssteuerungslisten (Access Control Lists, ACLs). Daher sind indizierte Seiten für alle Benutzer in der Organisation sichtbar.
