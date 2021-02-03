---
title: Azure Data Lake Graph Connector für Microsoft Search
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
description: Einrichten des Azure Data Lake Storage Gen2 Graph-Connectors für Microsoft Search
ms.openlocfilehash: da508694929d3c83a456c664aa4613b09a1b14a3
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084857"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Azure Data Lake Storage Gen2 Graph Connector

Mit dem Azure Data Lake Storage Gen2 Graph-Connector können Benutzer in Ihrer Organisation nach Dateien suchen, die in [Azure Blob Storage-](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) und [Azure Data Lake Gen 2 -Speicherkonten gespeichert](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) sind.

> [!NOTE]
> Lesen Sie den [**Artikel zum Einrichten ihres Graph-Connectors,**](configure-connector.md) um den allgemeinen Einrichtungsprozess für Graph Connectors zu verstehen.

Dieser Artikel ist für jeden benutzer, der einen Azure Data Lake Storage Gen2-Connector konfiguriert, ausgeführt und überwacht. Sie ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Azure Data Lake Storage Gen2-Connector gelten. Dieser Artikel enthält auch Informationen zu [Einschränkungen.](#limitations)

In diesem Artikel verwenden wir *Azure Storage* als generischen Begriff für Azure [Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) und Azure Data Lake [Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Geben Sie die Primäre Speicherverbindungszeichenfolge ein. Diese Zeichenfolge ist erforderlich, um den Zugriff auf Ihr Speicherkonto zu ermöglichen. Um Ihre Verbindungszeichenfolge zu finden, wechseln Sie zum [Azure-Portal,](https://ms.portal.azure.com/#home) und navigieren Sie zum Abschnitt **"Schlüssel"** Ihres relevanten Azure Storage-Kontos.

Wenn Sie den **AccountKey** (einen Parameter in der primären Speicherverbindungszeichenfolge) nicht bereitstellen möchten, gewähren Sie für die folgenden Rollen Zugriff auf unseren Graph Connectors-Dienst:

* Speicher-BLOB-Datenleser
* Mitwirkender von Speicherwarteschlangendaten
* Speicher-Blob-Delegator

Navigieren Sie zur **Registerkarte "Zugriffssteuerung"** Ihres Azure Storage-Kontos, und folgen Sie dort den Anweisungen, um Zugriff auf die folgende App zu gewähren:

* **First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766
* **Name der Erstpartei-App:** Graph Connector Service

### <a name="storage-account-and-queue-notifications-optional"></a>Speicherkonto und Warteschlangenbenachrichtigungen (optional)

Unterstützung für das Verarbeiten von Änderungen in Echtzeit im Graph-Connectors-Dienst wird möglicherweise in Zukunft hinzugefügt. In diesem Fall überwachen wir Azure Storage-Änderungsbenachrichtigungen, die in einer Warteschlange gespeichert sind. Sie müssen eine Warteschlange im selben Konto wie Ihr Azure Storage-Konto erstellen.

Nachdem Sie eine Warteschlange erstellt  haben, wechseln Sie zur Registerkarte "Ereignisse" auf der Warteschlangenseite, um das **Ereignisabonnement zu konfigurieren.** Wählen Sie alle Blob-Ereignisse aus, die die Warteschlange erhält, und verbinden Sie die Warteschlange mit dem Azure Storage-Konto.

## <a name="step-4-assign-property-labels"></a>Schritt 4: Zuweisen von Eigenschaftsbezeichnungen

Sie können jeder Bezeichnung eine Quelleigenschaft zuweisen, indem Sie aus einem Menü mit Optionen auswählen. Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaftsbezeichnungen verbessern die Suchrelevanz und sorgen für bessere Suchergebnisse für Endbenutzer.

## <a name="step-5-manage-schema"></a>Schritt 5: Verwalten des Schemas

Auf dem **Bildschirm "Schema verwalten"** können Sie die den Eigenschaften zugeordneten Schemaattribute ändern. Die Optionen sind **"Abfrage",** **"Suche",** **"Abrufen"** und "Einschränkung".  Sie können auch optionale Aliase hinzufügen und die Eigenschaft **"Content"** auswählen.

## <a name="step-6-manage-search-permissions"></a>Schritt 6: Verwalten von Suchberechtigungen

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Sie können die Zugriffssteuerungslisten (Access Control Lists, ACLs) aus Ihrem [Azure Data Lake Gen 2 -Speicherkonto ingesten.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) Wenn diese Suchberechtigungen festgelegt sind, wird der Suchinhalt basierend auf den Berechtigungen des in Azure Active Directory angemeldeten [Benutzers gekürzt.](https://docs.microsoft.com/azure/active-directory/) Alternativ können Sie festlegen, dass alle Inhalte, die aus Ihrem Speicherkonto indiziert werden, für alle Benutzer in Ihrer Organisation sichtbar sind. In diesem Fall hat jeder in Ihrer Organisation Zugriff auf alle Daten in Ihrem Speicherkonto.

Der Azure Data Lake Storage Gen2 Graph-Connector unterstützt Suchberechtigungen, die für jeden **sichtbar** sind, oder nur Personen mit Zugriff **auf diese Datenquelle.** Indizierte Daten, die in den Suchergebnissen angezeigt werden, können benutzern in der Organisation angezeigt werden, die Zugriff auf jedes Element haben.

### <a name="azure-blob-storage"></a>Azure Blob Storage

Für eine Verbindung mit [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)sind alle Inhalte, die aus der konfigurierten Quelle indiziert wurden, für alle Benutzer in Ihrer Organisation sichtbar. Zugriffssteuerungslisten werden auf Blobebene in Azure Blob Storage nicht unterstützt.

## <a name="step-7-set-the-refresh-schedule"></a>Schritt 7: Festlegen des Aktualisierungszeitplans

Auf dem **Bildschirm "Aktualisierungseinstellungen"** können Sie das Inkrementelle Durchforstungsintervall und das vollständige Durchforstungsintervall festlegen. Die Standardintervalle für den Azure Data Lake Storage Gen2-Connector sind 15 Minuten für eine inkrementelle Durchforstung und eine Woche für eine vollständige Durchforstung.

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Einschränkungen

Eine veröffentlichte Verbindung für Azure Blob Storage kann nicht für die Azure Data Lake Storage Gen2-Quelle und umgekehrt neu konfiguriert werden. In solchen Szenarien wird empfohlen, eine neue Verbindung zu konfigurieren.

Außerdem muss die Größe der Dateien 4 MB oder weniger betragen, damit sie gecrawlt werden können. Derzeit werden die folgenden Dateitypen unterstützt:

* Word (DOCX, DOCM, DOTX, DOTM)
* PowerPoint (PPTM, PPTX, POTM, POTX, PPAM, PPSM, PPSX)
* Excel (XLSX, XLSM)
* Ältere Office-Formate (DOC, DOT usw.)
* Text (.txt)
* HTML
* PDF

Binärdateien wie Bilder (JPG, BMP usw.) werden nicht unterstützt. Wenn eine DOCX-Datei beispielsweise nur Bilder enthält, wird sie möglicherweise übersprungen, da sie keinen Inhalt zurückgibt.
