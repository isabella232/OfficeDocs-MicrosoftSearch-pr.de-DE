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
description: Einrichten von MediaWiki Connector für Microsoft Search
ms.openlocfilehash: 7f6b34dcafc4b82ab3778ec1d7a4921383e44a44
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367640"
---
# <a name="mediawiki-connector"></a>MediaWiki-Connector

Mit dem MediaWiki-Konnektor kann Ihre Organisation Daten aus einem wiki ermitteln und indizieren, das mit MediaWiki-Software erstellt wurde. Dieser Connector indiziert angegebene Inhalte in Microsoft Search und unterstützt regelmäßige Crawls, um den Index auf dem neuesten Stand zu halten.

Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen MediaWiki-Connector konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle

Geben Sie Ihre MediaWiki-URL und Anmeldeinformationen für die Authentifizierung der Verbindung ein. Sie benötigen die folgenden Informationen: **Mandanten-ID**, **Ressourcen-** ID, **Client-ID** und den **geheimen Client Schlüssel**.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen

Der MediaWiki-Connector unterstützt nur Suchberechtigungen, die für **alle** sichtbar sind. Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.

## <a name="assign-property-labels"></a>Zuweisen von Eigenschaften Bezeichnungen

Sie können jeder Beschriftung eine Source-Eigenschaft zuweisen, indem Sie in einem Menü mit Optionen auswählen. Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaften Bezeichnungen verbessern die Suchrelevanz und stellen genauere Suchergebnisse für Endbenutzer sicher.

## <a name="manage-schema"></a>Schema verwalten

Auf dem Bildschirm " **Schema verwalten** " haben Sie die Möglichkeit, die den Eigenschaften zugeordneten Schema **Attribute (** abfragbar, **durchsuchbar**, **abrufbar** und **verfeinernd**) zu ändern, optionale Aliase hinzuzufügen und die **Content** -Eigenschaft auszuwählen.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans

In diesem Zeitplan werden die indizierten Daten aktualisiert, sodass Änderungen am wiki in der Microsoft-Suche wiedergegeben werden. Alle neuen Seiten, gelöschten Seiten, Seiteninhalte oder Metadaten-Änderungen werden nach dem angegebenen Aktualisierungsintervall in den Suchergebnissen angezeigt. Die Durchforstungs Zeit hängt von der Größe des Wikis ab. Der Connector crawlt derzeit um etwa 50 Seiten pro Minute.

## <a name="limitations"></a>Einschränkungen

Der MediaWiki-Konnektor hat diese Einschränkungen in der Preview-Version:

* Unterstützt nur Cloud-basierte Wikis.
* Unterstützt nur Basic oder OAuth 2,0 mit Azure Active Directory oder Azure-Authentifizierung.
* Unterstützt keine Namespace Auswahl für die Indizierung. Indiziert nur **Haupt**-, **Kategorie**-und **Datei** Namespaces.
* Unterstützt keine Zugriffssteuerungslisten (Access Control Lists, ACLs). Daher sind indizierte Seiten für alle Benutzer in der Organisation sichtbar.
