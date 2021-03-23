---
title: Dateifreigabe Graph Connector für Microsoft Search
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
ROBOTS: NoIndex
description: Einrichten des Graph-Connectors für die Dateifreigabe für Microsoft Search
ms.openlocfilehash: 792e853e5d2b7a23835dc031ff4ba4c09d619f9c
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031611"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a>Dateifreigabe Graph-Connector

Mit dem Graph-Connector für Dateifreigaben können Benutzer in Ihrer Organisation lokale Windows-Dateifreigaben durchsuchen.

> [!NOTE]
> Lesen Sie [**den Artikel Setup für Ihren Graph-Connector,**](configure-connector.md) um den allgemeinen Setupprozess für Graph Connectors zu verstehen.

## <a name="before-you-get-started"></a>Bevor Sie beginnen

### <a name="install-the-graph-connector-agent"></a>Installieren des Graph-Connector-Agents

Zum Indizieren Ihrer Windows-Dateifreigaben müssen Sie den Graph-Connector-Agent installieren und registrieren. Weitere Informationen finden Sie unter [Installieren des Graph-Connector-Agents.](on-prem-agent.md)  

### <a name="content-requirements"></a>Inhaltsanforderungen

### <a name="file-types"></a>Dateitypen

Inhalte der folgenden Formate können indiziert und durchsucht werden: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLSB, XLSX, XLT, XLXM, XML, XPS und ZIP. Nur der Textinhalt dieser Formate wird indiziert. Alle Multimediainhalte werden ignoriert. Für alle Dateien, die nicht zu diesem Format gehören, werden die Metadaten allein indiziert.

### <a name="file-size-limits"></a>Dateigrößenbegrenzungen

Die maximale unterstützte Dateigröße beträgt 100 MB. Dateien, die 100 MB überschreiten, werden nicht indiziert. Die maximale Nachverarbeitungsgröße beträgt 4 MB. Die Verarbeitung wird beendet, wenn die Dateigröße 4 MB erreicht. Daher können einige in der Datei enthaltene Ausdrücke möglicherweise nicht für die Suche verwendet werden.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Wählen Sie **auf der Seite** Mit Datenquelle verbinden die Option **Dateifreigabe aus,** und geben Sie den Namen, die Verbindungs-ID und die Beschreibung an. Geben Sie auf der nächsten Seite den Pfad zur Dateifreigabe an, und wählen Sie Den zuvor installierten Graph-Connector-Agent aus. Geben Sie die Anmeldeinformationen für ein [Microsoft Windows-Benutzerkonto](https://microsoft.com/windows) mit Lesezugriff auf alle Dateien in der Dateifreigabe ein.

### <a name="preserve-last-access-time"></a>Beibehalten der letzten Zugriffszeit

Wenn der Connector versucht, eine Datei zu durchforsten, wird das Feld "Letzte Zugriffszeit" in den Metadaten aktualisiert. Wenn Sie für Archivierungs- und Sicherungslösungen auf dieses Feld angewiesen sind und es nicht aktualisieren möchten, wenn der Connector darauf zutritt, können Sie diese Option auf der Seite Erweiterte Einstellungen **konfigurieren.**

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen

Sie können die Berechtigung zum Suchen nach einer beliebigen Datei basierend auf Zugriffssteuerungslisten für freigabebasierte Oder NTFS-Zugriffssteuerungslisten (New Technology File System) einschränken, indem Sie auf der Seite Suchberechtigungen verwalten die gewünschte Option **auswählen.** Die in diesen Zugriffssteuerungslisten bereitgestellten Benutzerkonten und Gruppen müssen von Active Directory (AD) verwaltet werden. Wenn Sie ein anderes System für die Benutzerkontenverwaltung verwenden, können Sie die Option "Jeder" auswählen, mit der Benutzer nach allen Dateien ohne Zugriffseinschränkungen suchen können. Wenn Benutzer jedoch versuchen, die Datei zu öffnen, gelten die an der Quelle festgelegten Zugriffssteuerelemente.

Beachten Sie, dass Windows standardmäßig die Berechtigung "Lesen" für "Jeder" in Freigabe-ACLs bietet, wenn ein Ordner im Netzwerk freigegeben wird. Wenn Sie in Verwalten von Suchberechtigungen Freigabe-ACLs **auswählen,** können Benutzer nach allen Dateien suchen. Wenn Sie den Zugriff einschränken möchten, entfernen Sie "Lesezugriff" für "Jeder" in Dateifreigaben, und stellen Sie nur den gewünschten Benutzern und Gruppen Zugriff zur Verfügung. Der Connector liest dann diese Zugriffseinschränkungen und wendet diese auf die Suche an.

Sie können nur dann Freigabe-ACLs auswählen, wenn der von Ihnen bereitgestellte Freigabepfad dem UNC-Pfadformat folgt. Sie können einen Pfad im UNC-Format erstellen, indem Sie unter "Freigabe" zu "Erweiterte Freigabe" gehen.

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-5-assign-property-labels"></a>Schritt 5: Zuweisen von Eigenschaftsbezeichnungen

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>Schritt 6: Verwalten des Schemas

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>Schritt 7: Auswählen von Aktualisierungseinstellungen

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->