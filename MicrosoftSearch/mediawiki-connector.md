---
title: MediaWiki Graph Connector für Microsoft Search
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
description: Einrichten des MediaWiki-Graph-Connectors für Microsoft Search
ms.openlocfilehash: fff24ce918e3eab6a50d78977749a030ef17d0aef235e6d98e02bdf54fc63a0c
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532694"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a>MediaWiki Graph Connector

Der MediaWiki Graph Connector ermöglicht Es Ihrer Organisation, Daten aus einem Wiki zu ermitteln und zu indizieren, das mithilfe der MediaWiki-Software erstellt wurde. Dieser Connector indiziert angegebene Inhalte in Microsoft Search und unterstützt regelmäßige Durchforstungen, um den Index auf dem neuesten Stand zu halten.

> [!NOTE]
> Lesen Sie den Artikel [**"Setup for your Graph connector",**](configure-connector.md) um die allgemeinen Anweisungen zum Einrichten Graph Connectors zu verstehen.

Dieser Artikel richtet sich an alle Benutzer, die einen MediaWiki Graph Connector konfigurieren, ausführen und überwachen. Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den MediaWiki Graph Connector gelten. Dieser Artikel enthält auch Informationen zu [Einschränkungen.](#limitations)

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph Connectors im Microsoft 365 Admin Center

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Geben Sie Ihre **Wiki-URL** ein, und wählen Sie den **Authentifizierungstyp** aus dem Dropdownmenü der Optionen aus. Die Optionen sind **None**, **Basic** und **OAuth 2.0 AAD**.

Wenn Sie **"Standard"** als Authentifizierungstyp auswählen, müssen Sie den **Benutzernamen** und **das Kennwort** für das Wiki angeben.

Wenn Sie **OAuth 2.0 AAD** als Authentifizierungstyp auswählen, müssen Sie die **Ressourcen-ID** der Wiki-Installation angeben. Sie müssen auch die **Client-ID** und den **geheimen Clientschlüssel** angeben, die auf der Registrierungsseite der AAD-Anwendung generiert werden.

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen

Der MediaWiki-Connector unterstützt nur Suchberechtigungen, die für jeden sichtbar **sind.** Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.

## <a name="step-5-assign-property-labels"></a>Schritt 5: Zuweisen von Eigenschaftenbeschriftungen

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>Schritt 6: Verwalten des Schemas

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>Schritt 7: Auswählen von Aktualisierungseinstellungen

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Einschränkungen

Für den MediaWiki-Connector gelten die folgenden Einschränkungen in der Vorschauversion:

* Unterstützt nur cloudbasierte Wikis.
* Unterstützt nur Basic oder OAuth 2.0 mit Azure Active Directory oder Azure-Authentifizierung.
* Die Namespaceauswahl für die Indizierung wird nicht unterstützt. Indiziert nur Main-, Category- und File-Namespaces.
* Unterstützt keine Zugriffssteuerungslisten (Access Control Lists, ACLs). Daher sind indizierte Seiten für alle Benutzer in der Organisation sichtbar.