---
title: Dateifreigabe-Graph-Connector für Microsoft Search
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
description: Einrichten des Dateifreigabe-Graph-Connectors für Microsoft Search
ms.openlocfilehash: af4c3996fdc8ac753404f4b4519175a9054fa18bce3862b0c5841c7bd5369cdd
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533024"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a>Dateifreigabe Graph Connector

Mit dem Connector für die Dateifreigabe Graph können Benutzer in Ihrer Organisation lokale Windows Dateifreigaben durchsuchen.

> [!NOTE]
> Lesen Sie den Artikel [**"Setup for your Graph connector",**](configure-connector.md) um den allgemeinen Setupprozess für Graph Connectors zu verstehen.

## <a name="before-you-get-started"></a>Bevor Sie beginnen

### <a name="install-the-graph-connector-agent"></a>Installieren des Graph Connector-Agents

Um Ihre Windows Dateifreigaben zu indizieren, müssen Sie den Graph Connector-Agent installieren und registrieren. Weitere Informationen finden Sie unter [Installieren des Graph Connector-Agents.](graph-connector-agent.md)  

### <a name="content-requirements"></a>Inhaltsanforderungen

### <a name="file-types"></a>Dateitypen

Inhalte der folgenden Formate können indiziert und durchsucht werden: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS und ZIP. Nur der Textinhalt dieser Formate wird indiziert. Alle Multimediainhalte werden ignoriert. Für jede Datei, die nicht zu diesem Format gehört, werden die Metadaten allein indiziert.

### <a name="file-size-limits"></a>Dateigrößenbegrenzungen

Die maximal unterstützte Dateigröße beträgt 100 MB. Dateien, die 100 MB überschreiten, werden nicht indiziert. Die maximale Größe nach der Verarbeitung beträgt 4 MB. Die Verarbeitung wird beendet, wenn die Größe einer Datei 4 MB erreicht. Daher funktionieren einige Ausdrücke, die in der Datei vorhanden sind, möglicherweise nicht für die Suche.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph Connectors im Microsoft 365 Admin Center

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Wählen Sie auf der Seite **Verbinden zur Datenquelle** die **Dateifreigabe aus,** und geben Sie den Namen, die Verbindungs-ID und die Beschreibung an. Geben Sie auf der nächsten Seite den Pfad zur Dateifreigabe an, und wählen Sie Ihren zuvor installierten Graph Connector-Agent aus. Geben Sie die Anmeldeinformationen für ein [Microsoft Windows](https://microsoft.com/windows) Benutzerkonto mit Lesezugriff auf alle Dateien in der Dateifreigabe ein.

### <a name="preserve-last-access-time"></a>Beibehalten der letzten Zugriffszeit

Wenn der Connector versucht, eine Datei zu durchforsten, wird das Feld "Zeitpunkt des letzten Zugriffs" in den Metadaten aktualisiert. Wenn Sie für Archivierungs- und Sicherungslösungen von diesem Feld abhängig sind und es nicht aktualisieren möchten, wenn der Connector darauf zugreift, können Sie diese Option auf der Seite **"Erweiterte Einstellungen"** konfigurieren.

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen

Sie können die Berechtigung zum Suchen nach einer beliebigen Datei basierend auf Listen für die Zugriffssteuerung für freigabebasierte Zugriffssteuerungen oder NTFS-Zugriffssteuerungslisten (New Technology File System, NTFS) einschränken, indem Sie auf der Seite **"Suchberechtigungen verwalten"** die gewünschte Option auswählen. Die in diesen Zugriffssteuerungslisten bereitgestellten Benutzerkonten und Gruppen müssen von Active Directory (AD) verwaltet werden. Wenn Sie ein anderes System für die Benutzerkontenverwaltung verwenden, können Sie die Option "Jeder" auswählen, mit der Benutzer ohne Zugriffseinschränkungen nach allen Dateien suchen können. Wenn Benutzer jedoch versuchen, die Datei zu öffnen, gelten die an der Quelle festgelegten Zugriffssteuerelemente.

Beachten Sie, dass Windows standardmäßig die Berechtigung "Lesen" für "Jeder" in AcLs freigeben bereitstellt, wenn ein Ordner im Netzwerk freigegeben wird. Wenn Sie acls freigeben in **"Suchberechtigungen verwalten"** auswählen, können Benutzer durch die Erweiterung nach allen Dateien suchen. Wenn Sie den Zugriff einschränken möchten, entfernen Sie "Lesezugriff" für "Jeder" in Dateifreigaben, und gewähren Sie nur den gewünschten Benutzern und Gruppen Zugriff. Der Connector liest dann diese Zugriffseinschränkungen und wendet sie auf die Suche an.

Sie können Share ACLs nur auswählen, wenn der angegebene Freigabepfad dem UNC-Pfadformat entspricht. Sie können einen Pfad im UNC-Format erstellen, indem Sie unter "Freigabe" zu "Erweiterte Freigabe" wechseln.

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

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
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->