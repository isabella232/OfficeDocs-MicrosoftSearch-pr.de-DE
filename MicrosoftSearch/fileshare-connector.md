---
title: Dateifreigabe-Konnektor
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Einrichten des Dateifreigabe-Konnektors für Microsoft Search
ms.openlocfilehash: a95cfe90ca35a385bb9ce3a4c565c18c5a42ec80
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408933"
---
# <a name="file-share-connector"></a>Dateifreigabe-Konnektor

Mit dem File Share Graph-Konnektor können Benutzer in Ihrer Organisation lokale Windows-Dateifreigaben durchsuchen.

Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen Dateifreigabe-Konnektor konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.

## <a name="install-graph-connector-agent"></a>Installieren des Graph Connector-Agents

Um Ihre Windows-Dateifreigaben zu indizieren, müssen Sie die [Graph Connector Agent](on-prem-agent.md) -Software installieren und registrieren.

## <a name="content-requirements"></a>Inhaltsanforderungen

### <a name="file-types"></a>Dateitypen

Der Inhalt der folgenden Formate kann indiziert und durchsucht werden: doc, DOCM, docx, dot, DOTX, eml, GIF, HTML, JPEG, MHT, MHTML, msg, nws, OBD, OBT, Odp, ODS, ODT, One, PDF, Pot, PPS, PPT, PPTM, PPTX, txt, XLB, XLC, xlsb, xls, xlsx, XLT, XLXM, XML, XPS und zip. Nur der Textinhalt dieser Formate wird indiziert. Alle Multimedia-Inhalte werden ignoriert. Für alle Dateien, die nicht zu diesem Format gehören, werden die Metadaten allein indiziert.

### <a name="file-size-limits"></a>Dateigrößenbegrenzungen

Die maximal unterstützte Dateigröße beträgt 100 MB. Dateien, die 100 MB überschreiten, werden nicht indiziert. Der maximale Grenzwert für die Post verarbeitete Größe beträgt 4 MB. Die Verarbeitung wird angehalten, wenn die Größe einer Datei 4 MB erreicht. Einige in der Datei vorhandene Ausdrücke funktionieren daher möglicherweise nicht für die Suche.

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle

Wählen Sie auf der Seite mit **Datenquelle verbinden** die Option **Dateifreigabe** aus, und geben Sie den Namen, die Verbindungs-ID und die Beschreibung an. Geben Sie auf der nächsten Seite den Pfad zur Dateifreigabe an, und wählen Sie den zuvor installierten Graph Connector-Agent aus. Geben Sie die Anmeldeinformationen für ein [Microsoft Windows](https://microsoft.com/windows) -Benutzerkonto mit Lesezugriff auf alle Dateien in der Dateifreigabe ein.

## <a name="preserve-last-access-time"></a>Beibehalten der letzten Zugriffszeit

Wenn der Connector versucht, eine Datei zu durchforsten, wird das Feld "Letzter Zugriffszeit" in den zugehörigen Metadaten aktualisiert. Wenn Sie dieses Feld für Archivierungs-und Sicherungslösungen benötigen und es nicht aktualisieren möchten, wenn der Connector darauf zugreift, können Sie diese Option auf der Seite **Erweiterte Einstellungen** konfigurieren.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen

Sie können die Berechtigung für die Suche nach beliebigen Dateien einschränken, die auf Freigabe-Zugriffssteuerungslisten oder NTFS-Zugriffssteuerungslisten (Access Control Lists) für neue Technologie-Dateisysteme basieren. Wenn Sie Zugriffssteuerungslisten freigeben verwenden möchten, wählen Sie die entsprechende Option auf der Seite **Erweiterte Einstellungen** aus. Wenn Sie NTFS-Zugriffssteuerungslisten verwenden möchten, wählen Sie die entsprechende Option auf der Seite **Suchberechtigungen verwalten** aus.

## <a name="assign-property-labels"></a>Zuweisen von Eigenschaften Bezeichnungen

Sie können jeder Beschriftung eine Source-Eigenschaft zuweisen, indem Sie in einem Menü mit Optionen auswählen. Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaften Bezeichnungen verbessern die Suchrelevanz und stellen genauere Suchergebnisse für Endbenutzer sicher.

## <a name="manage-schema"></a>Schema verwalten

Auf dem Bildschirm " **Schema verwalten** " haben Sie die Möglichkeit, die den Eigenschaften zugeordneten Schema **Attribute (** abfragbar, **durchsuchbar**, **abrufbar** und **verfeinernd**) zu ändern, optionale Aliase hinzuzufügen und die **Content** -Eigenschaft auszuwählen.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans

Das empfohlene Standardintervall für die Aktualisierungsplanung beträgt 15 Minuten, Sie können es jedoch basierend auf Ihren Einstellungen ändern.
