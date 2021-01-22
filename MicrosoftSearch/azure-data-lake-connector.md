---
title: Azure Data Lake Connector für Microsoft Search
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Azure Data Lake Storage Gen2-Connectors für Microsoft Search
ms.openlocfilehash: 8891c9a1fdf5397c397a941b5131f014db9e7a54
ms.sourcegitcommit: 597c338bf9c1c425747ac74a9a1ae57c5e8957ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49920722"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Azure Data Lake Storage Gen2 Connector

Mit dem Azure Data Lake Storage Gen2-Connector können Benutzer in Ihrer Organisation nach Dateien suchen, die in [Azure Blob Storage-](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) und [Azure Data Lake Gen 2 -Speicherkonten gespeichert](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) sind.

Dieser Artikel ist für [Microsoft 365-Administratoren](https://www.microsoft.com/microsoft-365) oder alle Personen, die einen Azure Data Lake Storage Gen2-Connector konfigurieren, ausgeführt und überwachen. Es bietet eine Übersicht über die Connectorkonfiguration, Funktionen, Einschränkungen und Problembehandlungstechniken. In diesem Artikel verwenden wir *Azure Storage* als generischen Begriff für Azure [Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) und Azure Data Lake [Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle

### <a name="primary-storage-connection-string"></a>Primäre Speicherverbindungszeichenfolge

Geben Sie **auf dem Bildschirm "Authentifizierung und Konfiguration"** die primäre Speicherverbindungszeichenfolge an. Diese Zeichenfolge ist erforderlich, um den Zugriff auf Ihr Speicherkonto zu ermöglichen. Um Ihre Verbindungszeichenfolge zu finden, wechseln Sie zum [Azure-Portal,](https://ms.portal.azure.com/#home) und navigieren Sie zum Abschnitt **"Schlüssel"** Ihres relevanten Azure Storage-Kontos. Kopieren Sie die Verbindungszeichenfolge, und fügen Sie sie in das entsprechende Feld auf dem Bildschirm ein.

Wenn Sie den **AccountKey** (einen Parameter in der primären Speicherverbindungszeichenfolge) nicht bereitstellen möchten, müssen Sie den Zugriff auf unseren Graph Connectors Service für die folgenden Rollen gewähren. (Dieses Feature wird nur für hierarchischen Speicher unterstützt. Herkömmlicher Blobspeicher muss AccountKey bereitstellen.)
* Speicher-BLOB-Datenleser
* Mitwirkender von Speicherwarteschlangendaten
* Speicher-Blob-Delegator

Navigieren Sie zur **Registerkarte "Zugriffssteuerung"** Ihres Azure Storage-Kontos, und folgen Sie dort den Anweisungen, um Zugriff auf die folgende App zu gewähren:

* **First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766
* **Name der Erstpartei-App:** Graph Connector Service

### <a name="storage-account-and-queue-notifications-optional"></a>Speicherkonto und Warteschlangenbenachrichtigungen (optional)

Unterstützung für das Verarbeiten von Änderungen in Echtzeit im Graph-Connectors-Dienst wird möglicherweise in Zukunft hinzugefügt. In diesem Fall überwachen wir Azure Storage-Änderungsbenachrichtigungen, die in einer Warteschlange gespeichert sind. Sie müssen eine Warteschlange im selben Konto wie Ihr Azure Storage-Konto erstellen.

Nachdem Sie eine Warteschlange erstellt  haben, wechseln Sie zur Registerkarte "Ereignisse" auf der Warteschlangenseite, um das **Ereignisabonnement zu konfigurieren.** Wählen Sie alle Blob-Ereignisse aus, die die Warteschlange erhält, und verbinden Sie die Warteschlange mit dem Azure Storage-Konto.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Auf dem **Bildschirm "Suchberechtigungen** verwalten" können Sie auswählen, ob Die Zugriffssteuerungslisten (Access Control Lists, ACLs) aus Ihrem [Azure Data Lake Gen 2 -Speicherkonto aufgenommen](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) werden. Wenn diese Suchberechtigungen festgelegt sind, wird der Suchinhalt basierend auf den Berechtigungen gekürzt, die dem angemeldeten [Azure Active](https://docs.microsoft.com/azure/active-directory/) Directory-Benutzer, der den Inhalt durchsucht, zugewiesen sind. Alternativ können Sie festlegen, dass alle Inhalte, die aus Ihrem Speicherkonto indiziert wurden, für alle Benutzer in Ihrer Organisation sichtbar sind. In diesem Fall hat jeder in Ihrer Organisation Zugriff auf alle Daten in Ihrem Speicherkonto.

### <a name="azure-blob-storage"></a>Azure Blob Storage

Für eine Verbindung mit [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)sind alle Inhalte, die aus der konfigurierten Quelle indiziert wurden, für alle Benutzer in Ihrer Organisation sichtbar. Zugriffssteuerungslisten werden auf Blobebene in Azure Blob Storage nicht unterstützt.

## <a name="search-permissions"></a>Suchberechtigungen

Der Azure Data Lake Storage Gen2-Connector unterstützt Suchberechtigungen, die für alle oder nur Personen mit Zugriff **auf diese Datenquelle sichtbar sind.**  Indizierte Daten, die in den Suchergebnissen angezeigt werden, können für alle Benutzer in der Organisation oder nur für Benutzer sichtbar sein, die Zugriff auf jedes Element haben.

## <a name="assign-property-labels"></a>Zuweisen von Eigenschaftsbezeichnungen

Sie können jeder Bezeichnung eine Quelleigenschaft zuweisen, indem Sie aus einem Menü mit Optionen auswählen. Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaftsbezeichnungen verbessern die Suchrelevanz und stellen für Endbenutzer genauere Suchergebnisse sicher.

## <a name="manage-schema"></a>Schema verwalten

Auf dem Bildschirm **"Schema** verwalten" können Sie die Schemaattribute **(** abfragbar, durchsuchbar, abrufbar und **einlesbar)** ändern, die den Eigenschaften zugeordnet sind, optionale Aliase hinzufügen und die Eigenschaft **"Content"** auswählen.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans

Auf dem **Bildschirm "Aktualisierungseinstellungen"** können Sie das Inkrementelle Durchforstungsintervall und das vollständige Durchforstungsintervall festlegen. Die Standardintervalle für den Azure Data Lake Storage Gen2-Connector sind 15 Minuten für eine inkrementelle Durchforstung und eine Woche für eine vollständige Durchforstung.

## <a name="limitations"></a>Einschränkungen

Eine veröffentlichte Verbindung für Azure Blob Storage kann nicht für die Azure Data Lake Storage Gen2-Quelle und umgekehrt neu konfiguriert werden. In solchen Szenarien wird empfohlen, eine neue Verbindung zu konfigurieren.
