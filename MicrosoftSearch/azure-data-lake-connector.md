---
title: Azure Data Lake-Connector für Microsoft-Suche
ms.author: mounika.narayanan
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Azure Data Lake Storage Gen2 Connectors für Microsoft Search
ms.openlocfilehash: d6adabc6ea40b4385059f80375f49fb73e63e65b
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996094"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Azure Data Lake-Speicher Gen2-Connector

Mit dem Azure Data Lake Storage Gen2-Connector können Benutzer in Ihrer Organisation nach Dateien suchen, die in [Azure BLOB Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) -und [Azure Data Lake Gene 2-Speicher](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) Konten gespeichert sind.

Dieser Artikel richtet sich an [Microsoft 365](https://www.microsoft.com/microsoft-365) -Administratoren oder Personen, die einen Azure Data Lake-Gen2-Connector konfigurieren, ausführen und überwachen. Es bietet eine Übersicht über die Connector-Konfiguration, Funktionen, Einschränkungen und Techniken zur Problembehandlung. Im Artikel wird *Azure Storage* als allgemeiner Ausdruck für Azure-BLOB- [Speicher](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) und [Azure Data Lake Gen 2-Speicher](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)verwendet.

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle
### <a name="primary-storage-connection-string"></a>Primäre Speicher Verbindungszeichenfolge 
Geben Sie auf dem Bildschirm **Authentifizierung und Konfiguration** die primäre Speicher Verbindungszeichenfolge an. Diese Zeichenfolge ist erforderlich, um den Zugriff auf Ihr Speicherkonto zuzulassen. Navigieren Sie zum [Azure-Portal](https://ms.portal.azure.com/#home) zum **Schlüssel** Abschnitt Ihres relevanten Azure-speicherkontos, um die Verbindungszeichenfolge zu finden. Kopieren Sie die Verbindungszeichenfolge, und fügen Sie Sie in das entsprechende Feld auf dem Bildschirm ein.

Wenn Sie das **AccountKey** (einen Parameter in der primären Speicher Verbindungszeichenfolge) nicht bereitstellen möchten, müssen Sie unserem Graph Connectors-Dienst Lesezugriff gewähren. Navigieren Sie zur Registerkarte **Zugriffssteuerung** Ihres Azure-speicherkontos, und befolgen Sie die Anweisungen dort, um Zugriff auf die folgende APP zu gewähren:
* **Erste Partei-APP-ID:** 56c1da01-2129-48f7-9355-af6d59d42766
* **Name der ersten Partei-App:** Graph Connector-Dienst

### <a name="storage-account-and-queue-notifications-optional"></a>Speicherkonto-und Warteschlangen Benachrichtigungen (optional)
Unterstützung für das Verarbeiten von Änderungen in Echtzeit im Graph Connectors-Dienst kann in Zukunft hinzugefügt werden. In diesem Fall werden die in einer Warteschlange gespeicherten Änderungsbenachrichtigungen für Azure-Speicher überwacht. Sie müssen eine Warteschlange in demselben Konto wie Ihr Azure-Speicherkonto erstellen.

Nachdem Sie eine Warteschlange erstellt haben, wechseln Sie zur Registerkarte **Ereignisse** auf der Warteschlangen Seite, um das **Ereignisabonnement**zu konfigurieren. Wählen Sie alle BLOB-Ereignisse aus, die von der Warteschlange empfangen werden, und verbinden Sie die Warteschlange mit dem Azure-Speicherkonto.

## <a name="manage-the-search-schema"></a>Verwalten des Suchschemas
Auf dem Bildschirm " **Schema verwalten** " können Sie die Schema Attribute (**abgefragt**, **durchsuchbar**und **abrufbar**) ändern, die den verwalteten Eigenschaften zugeordnet sind. Diese Attribute verwalteter Eigenschaften sind Daten, die aus Ihrem Azure-Datenspeicher Konto indiziert werden.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen
### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2
Auf dem Bildschirm **Suchberechtigungen verwalten** können Sie die Zugriffssteuerungslisten (Access Control Lists, ACLs) aus dem Speicherkonto des [Azure Data Lake Generation 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) aufnehmen. Wenn diese Suchberechtigungen festgelegt sind, wird der Such Inhalt basierend auf den Berechtigungen gekürzt, die dem angemeldeten [Azure-Active Directory](https://docs.microsoft.com/azure/active-directory/) Benutzer zugewiesen sind, der den Inhalt durchsucht. Alternativ können Sie festlegen, dass alle von Ihrem Speicherkonto indizierten Inhalte für alle Benutzer in Ihrer Organisation sichtbar gemacht werden sollen. In diesem Fall können alle Benutzer in Ihrer Organisation auf alle Daten in Ihrem Speicherkonto zugreifen.

### <a name="azure-blob-storage"></a>Azure Blob Storage
Für eine Verbindung mit dem [Azure-BLOB-Speicher](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)sind alle Inhalte, die von der konfigurierten Quelle indiziert werden, für alle Benutzer in Ihrer Organisation sichtbar. Zugriffssteuerungslisten werden auf der BLOB-Ebene im Azure-BLOB-Speicher nicht unterstützt.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans
Auf dem Bildschirm **Einstellungen aktualisieren** können Sie das Intervall für inkrementelle Durchforstung und das vollständige Durchforstungs Intervall festlegen. Die Standardintervalle für den Azure Data Lake-Speicher Gen2-Connector liegen bei einer inkrementellen Durchforstung und einer Woche für eine vollständige Durchforstung bei 15 Minuten.

## <a name="limitations"></a>Einschränkungen
Eine veröffentlichte Verbindung für den Azure-BLOB-Speicher kann nicht für die Azure Data Lake-Speicher Gen2-Quelle und umgekehrt konfiguriert werden. In solchen Szenarien wird empfohlen, eine neue Verbindung zu konfigurieren.