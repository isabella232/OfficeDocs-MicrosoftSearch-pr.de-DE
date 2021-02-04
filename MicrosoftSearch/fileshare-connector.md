---
title: Dateifreigabe -Graph-Connector für Microsoft Search
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
ROBOTS: NoIndex
description: Einrichten des Dateifreigabe-Graph-Connectors für Microsoft Search
ms.openlocfilehash: e8a68a1c6b9c2c8a8592fb915fe9bf846a758e77
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097421"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a>Dateifreigabe -Graph-Connector

Der Dateifreigabe-Graph-Connector ermöglicht Benutzern in Ihrer Organisation das Durchsuchen von lokalen Windows-Dateifreigaben.

> [!NOTE]
> Lesen Sie [**den Artikel "Setup für Ihren Graph-Connector",**](configure-connector.md) um den allgemeinen Einrichtungsprozess für Graph Connectors zu verstehen.

## <a name="before-you-get-started"></a>Bevor Sie beginnen

### <a name="install-the-graph-connector-agent"></a>Installieren des Graph-Connector-Agents

Um Ihre Windows-Dateifreigaben zu indizieren, müssen Sie den Graph-Connector-Agent installieren und registrieren. Weitere [Informationen finden Sie unter "Installieren des Graph-Connector-Agents".](on-prem-agent.md)  

### <a name="content-requirements"></a>Inhaltsanforderungen

### <a name="file-types"></a>Dateitypen

Inhalte der folgenden Formate können indiziert und durchsucht werden: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLSX, XLSX, XLT, XLXM, XML, XPS und ZIP. Nur der Textinhalt dieser Formate wird indiziert. Alle Multimediainhalte werden ignoriert. Für jede Datei, die nicht zu diesem Format gehört, werden die Metadaten allein indiziert.

### <a name="file-size-limits"></a>Dateigrößenbegrenzungen

Die maximal unterstützte Dateigröße beträgt 100 MB. Dateien, die 100 MB überschreiten, werden nicht indiziert. Die maximale Nachverarbeitungsgröße beträgt 4 MB. Die Verarbeitung wird beendet, wenn die Größe einer Datei 4 MB erreicht. Daher können einige in der Datei enthaltene Ausdrücke möglicherweise nicht für die Suche verwendet werden.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Wählen Sie **auf der Seite "Mit** Datenquelle verbinden" die **Dateifreigabe aus,** und geben Sie den Namen, die Verbindungs-ID und die Beschreibung an. Geben Sie auf der nächsten Seite den Pfad zur Dateifreigabe an, und wählen Sie Ihren zuvor installierten Graph-Connector-Agent aus. Geben Sie die Anmeldeinformationen für ein [Microsoft Windows-Benutzerkonto](https://microsoft.com/windows) mit Lesezugriff auf alle Dateien in der Dateifreigabe ein.

### <a name="preserve-last-access-time"></a>Beibehalten der letzten Zugriffszeit

Wenn der Connector versucht, eine Datei zu durchforsten, wird das Feld "Letzte Zugriffszeit" in den Metadaten aktualisiert. Wenn Sie dieses Feld für Archivierungs- und Sicherungslösungen verwenden und es nicht aktualisieren möchten, wenn der Connector darauf zutritt, können Sie diese Option auf der Seite "Erweiterte Einstellungen" **konfigurieren.**

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen

Sie können die Berechtigung zum Suchen nach einer beliebigen Datei basierend auf Share Access Control Lists oder NTFS (New Technology File System)-Zugriffssteuerungslisten einschränken. Wenn Sie Zugriffssteuerungslisten freigeben möchten, wählen Sie die entsprechende Option auf der Seite **"Erweiterte Einstellungen"** aus. Wenn Sie NTFS-Zugriffssteuerungslisten verwenden möchten, wählen Sie auf der Seite Suchberechtigungen verwalten die **entsprechende Option** aus.

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

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
