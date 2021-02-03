---
title: MediaWiki Graph Connector für Microsoft Search
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
description: Einrichten des MediaWiki -Graph-Connectors für Microsoft Search
ms.openlocfilehash: 9d9d7a1ef9aeaba079f8cccef1ec4a4836768e8d
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084983"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a>MediaWiki Graph Connector

Mit dem MediaWiki Graph-Connector kann Ihre Organisation Daten aus einem Wiki ermitteln und indizieren, das mit der Software MediaWiki erstellt wurde. Dieser Connector indiziert angegebene Inhalte in Microsoft Search und unterstützt regelmäßige Durchforstungen, um den Index auf dem neuesten Stand zu halten.

> [!NOTE]
> Lesen Sie [**den Artikel "Setup für Ihren Graph-Connector",**](configure-connector.md) um den allgemeinen Einrichtungsprozess für Graph Connectors zu verstehen.

Dieser Artikel ist für jeden benutzer, der einen ServiceNow Graph Connector konfiguriert, ausgeführt und überwacht. Sie ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den MediaWiki Graph-Connector gelten. Dieser Artikel enthält auch Informationen zu [Einschränkungen.](#limitations)

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Geben Sie Ihre **Wiki-URL** ein, und wählen Sie im Dropdownmenü der Optionen den Authentifizierungstyp aus.  Die Optionen sind **None**, **Basic** und **OAuth 2.0 AAD**.

Wenn Sie **"Standard"** als Authentifizierungstyp  auswählen, müssen Sie den Benutzernamen und das **Kennwort für** das Wiki angeben.

Wenn Sie **OAuth 2.0 AAD** als Authentifizierungstyp auswählen, müssen Sie die **Ressourcen-ID** der Wiki-Installation bereitstellen. Sie müssen auch die **Client-ID** und den **geheimen** Clientgeheimnis bereitstellen, die auf der Registrierungsseite der AAD-Anwendung generiert werden.

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen

Der Connector MediaWiki unterstützt nur Suchberechtigungen, die für jeden **sichtbar sind.** Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.

## <a name="step-5-assign-property-labels"></a>Schritt 5: Zuweisen von Eigenschaftsbezeichnungen

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>Schritt 6: Verwalten des Schemas

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>Schritt 7: Auswählen von Aktualisierungseinstellungen

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Einschränkungen

Der MediaWiki Connector hat in der Vorschauversion die folgenden Einschränkungen:

* Unterstützt nur cloudbasierte Wikis.
* Unterstützt nur Basic oder OAuth 2.0 mit Azure Active Directory- oder Azure-Authentifizierung.
* Unterstützt keine Namespaceauswahl für die Indizierung. Indiziert nur Die Namespaces "Main", "Category" und "File".
* Unterstützt keine Zugriffssteuerungslisten (Access Control Lists, ACLs). Daher sind indizierte Seiten für alle Benutzer in der Organisation sichtbar.
