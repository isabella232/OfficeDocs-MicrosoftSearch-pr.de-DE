---
title: ServiceNow Connector für Microsoft Search
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des ServiceNow Connectors für Microsoft Search
ms.openlocfilehash: 78b2831e9a52b6bf0204b5a6b2aba147b529b3f5
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626954"
---
# <a name="servicenow-connector"></a>ServiceNow-Connector

Mit dem ServiceNow-Connector kann Ihre Organisation Knowledge Base-Artikel indizieren, die für alle Benutzer in Ihrer Organisation sichtbar sind. Nachdem Sie den Connector-und den Index Inhalt von ServiceNow konfiguriert haben, können Endbenutzer nach diesen Artikeln von einem beliebigen Microsoft Search-Client aus suchen.  

Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen ServiceNow-Connector konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle
Zum Herstellen einer Verbindung mit ihren ServiceNow-Daten benötigen Sie die **ServiceNow-Instanz-URL**Ihrer Organisation, Anmeldeinformationen für dieses Konto sowie die Client-ID und den geheimen Client Schlüssel für die OAuth-Authentifizierung.  

Die ServiceNow- **Instanz-URL** Ihrer Organisation sieht in der Regel wie **https://&lt;ihrer-Organisations-Domain>. Service-now.com**aus. Zusammen mit dieser URL benötigen Sie ein Konto zum Einrichten der Verbindung mit ServiceNow sowie dazu, dass Microsoft Search die Artikel aus ServiceNow regelmäßig basierend auf dem Aktualisierungszeitplan aktualisieren kann.

Wählen Sie eine von zwei unterstützten Methoden aus, um Inhalte von ServiceNow zu authentifizieren und zu synchronisieren: 
1. Standardauthentifizierung 
2. OAuth (empfohlen)

> [!Note]
> Um OAuth für die Authentifizierung zu verwenden, muss ein ServiceNow-Administrator einen Endpunkt in ihrer ServiceNow-Instanz bereitstellen, damit die Microsoft Search-App auf die Instanz zugreifen kann. Weitere Informationen finden Sie unter [Erstellen eines Endpunkts für Clients für den Zugriff auf die Instanz](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in der ServiceNow-Dokumentation.

Die folgende Tabelle enthält Anleitungen zum Ausfüllen des Endpunkts-erstellungsformulars:

**Field** | **Beschreibung** | **Empfohlener Wert**
--- | --- | ---
Name | Dieser eindeutige Wert identifiziert die Anwendung, für die Sie OAuth-Zugriff benötigen. | Microsoft Search
Client-ID | Eine schreibgeschützte, automatisch generierte eindeutige ID für die Anwendung. Die Instanz verwendet die Client-ID, wenn Sie ein Zugriffstoken anfordert. | –
Geheimer Client Schlüssel | Mit dieser freigegebenen geheimen Zeichenfolge autorisieren die ServiceNow-Instanz und die Microsoft Search die Kommunikation miteinander. | Beachten Sie bewährte Methoden für die Sicherheit, indem Sie dies als Kennwort behandeln.
Umleitungs-URL | Eine erforderliche Rückruf-URL, an die der autorisierungsserver umgeleitet wird. | Siehe [OAuth-Rückruf](https://gcs.office.com/v1.0/admin/oauth/callback).
Logo-URL | Eine URL, die das Bild für das Anwendungslogo enthält. | –
Aktiv | Aktivieren Sie das Kontrollkästchen, um die Anwendungsregistrierung aktiv zu machen. | Auf aktiv festlegen
Lebensdauer des Aktualisierungs Tokens | Die Anzahl der Sekunden, die ein Aktualisierungstoken gültig ist. Standardmäßig laufen Aktualisierungstoken in 100 Tagen (8640000 Sekunden) ab. | 31.536.000 (1 Jahr)
Lebensdauer des Zugriffstokens | Die Anzahl der Sekunden, die ein Zugriffstoken gültig ist. | 43.200 (12 Stunden)

## <a name="set-a-sync-filter"></a>Festlegen eines Synchronisierungsfilters 
Mit einem Synchronisierungsfilter können Sie Bedingungen für die Synchronisierung von Artikeln angeben. Es ist wie eine **Where** -Klausel in einer **SQL-SELECT** -Anweisung. Beispielsweise können Sie auswählen, nur veröffentlichte und aktive Artikel zu indizieren. Auf der SyncNow-Konfigurationsseite wird beschrieben, wie ein Synchronisierungsfilter erfasst und festgelegt wird.

## <a name="manage-the-search-schema"></a>Verwalten des Suchschemas
Konfigurieren Sie nach erfolgreicher Verbindung die Suchschema Zuordnung. Sie können auswählen, welche Eigenschaften **abgefragt**, **durchsuchbar**und **abrufbar**gemacht werden sollen.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen
Der ServiceNow-Connector unterstützt nur Suchberechtigungen, die für **alle**sichtbar sind. Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.
 
## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans 
Der ServiceNow-Connector unterstützt Aktualisierungs Zeitpläne für vollständige und inkrementelle Crawls. Es wird empfohlen, beides festzulegen.

Ein vollständiger durchforstungszeitplan findet gelöschte Artikel, die zuvor mit dem Microsoft-Suchindex synchronisiert wurden, sowie alle Artikel, die aus dem Synchronisierungsfilter verschoben wurden. Wenn Sie zum ersten Mal eine Verbindung mit ServiceNow herstellen, wird eine vollständige Durchforstung ausgeführt, um alle Knowledge Base-Artikel zu synchronisieren. Sie müssen inkrementelle Crawls planen, um neue Elemente zu synchronisieren und Aktualisierungen vorzunehmen.

Der empfohlene Standardwert ist ein Tag für eine vollständige Durchforstung und vier Stunden für eine inkrementelle Durchforstung.
