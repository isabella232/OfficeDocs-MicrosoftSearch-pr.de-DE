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
ms.openlocfilehash: d8aa4a99c353a80f7d3dcf768d8287200b17fdc6
ms.sourcegitcommit: be0c64845477127d73ee24dc727e4583ced3d0e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48206950"
---
# <a name="mediawiki-connector"></a>MediaWiki-Connector

Mit dem MediaWiki-Konnektor kann Ihre Organisation Daten aus einem wiki ermitteln und indizieren, das mit MediaWiki-Software erstellt wurde. Dieser Connector indiziert angegebene Inhalte in Microsoft Search und unterstützt regelmäßige Crawls, um den Index auf dem neuesten Stand zu halten.

Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen MediaWiki-Connector konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle

Geben Sie Ihre MediaWiki-URL und Anmeldeinformationen für die Authentifizierung der Verbindung ein. Sie benötigen die folgenden Informationen: **Mandanten-ID**, **Ressourcen-** ID, **Client-ID**und den **geheimen Client Schlüssel**.

## <a name="manage-the-search-schema"></a>Verwalten des Suchschemas

Konfigurieren Sie nach erfolgreicher Verbindung die Suchschema Zuordnung. Sie können auswählen, welche Eigenschaften **abgefragt**, **durchsuchbar**und **abrufbar**gemacht werden sollen.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen

Der MediaWiki-Connector unterstützt nur Suchberechtigungen, die für **alle**sichtbar sind. Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans

In diesem Zeitplan werden die indizierten Daten aktualisiert, sodass Änderungen am wiki in der Microsoft-Suche wiedergegeben werden. Alle neuen Seiten, gelöschten Seiten, Seiteninhalte oder Metadaten-Änderungen werden nach dem angegebenen Aktualisierungsintervall in den Suchergebnissen angezeigt. Die Durchforstungs Zeit hängt von der Größe des Wikis ab. Der Connector crawlt derzeit um etwa 50 Seiten pro Minute.

## <a name="limitations"></a>Einschränkungen

Der MediaWiki-Konnektor hat diese Einschränkungen in der Preview-Version:

* Unterstützt nur Cloud-basierte Wikis.
* Unterstützt nur Basic oder OAuth 2,0 mit Azure Active Directory oder Azure-Authentifizierung.
* Unterstützt keine Namespace Auswahl für die Indizierung. Indiziert nur **Haupt**-, **Kategorie**-und **Datei** Namespaces.
* Unterstützt keine Zugriffssteuerungslisten (Access Control Lists, ACLs). Daher sind indizierte Seiten für alle Benutzer in der Organisation sichtbar.
