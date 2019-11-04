---
title: Azure Data Lake-Connector für Microsoft-Suche
ms.author: v-pamcn
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
ms.openlocfilehash: bedd7307ca2add52408bb9a5e3b3b21fd75df258
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949776"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Azure Data Lake-Speicher Gen2-Connector

Mit dem [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) -Connector können Benutzer in Ihrer Organisation nach Dateien und deren Inhalten suchen. Dieser Connector greift auf Daten zu, die in Azure-BLOB-Containern und Hierarchie fähigen Ordnern in einem Azure Data Lake-Speicher für Generation 2 gespeichert sind.

Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen Azure Data Lake-Gen2-Connector konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle

### <a name="primary-storage-connection-string"></a>Primäre Speicher Verbindungszeichenfolge 
Geben Sie auf dem Bildschirm **Authentifizierung und Konfiguration** die primäre Speicher Verbindungszeichenfolge an. Diese Zeichenfolge ist erforderlich, um den Zugriff auf Ihr Speicherkonto zuzulassen. Um Ihre Verbindungszeichenfolge zu finden, wechseln Sie zum [Azure-Portal](https://ms.portal.azure.com/#home) , und navigieren Sie zum Abschnitt **Keys** des Azure Data Lake-Speicher Gen2-Kontos. Kopieren Sie die Verbindungszeichenfolge, und fügen Sie Sie in das entsprechende Feld auf dem Bildschirm ein.

Wenn Sie den **AccountKey** (einen Parameter in der primären Speicher Verbindungszeichenfolge) nicht bereitstellen möchten, müssen Sie unserem Graph Connectors-Dienst Lesezugriff gewähren. Befolgen Sie auf der Registerkarte **Zugriffssteuerung** Ihres Azure Data Lake-Speicher Gen2 die Anweisungen auf dieser Seite, um Zugriff auf die folgende APP zu gewähren:
* **Erste Partei-APP-ID:** 56c1da01-2129-48f7-9355-af6d59d42766
* **Name der ersten Partei-App:** Graph Connector-Dienst

### <a name="storage-account-and-queue-notifications-optional"></a>Speicherkonto-und Warteschlangen Benachrichtigungen (optional)
Unterstützung für das Verarbeiten von Änderungen in Echtzeit im Graph Connectors-Dienst kann in Zukunft hinzugefügt werden. In diesem Fall werden die in einer Warteschlange gespeicherten Gen2-Änderungsbenachrichtigungen für Azure Data Lake überwacht. Sie müssen eine Warteschlange im gleichen Konto wie Ihr Azure Data Lake-Speicher Gen2 oder ein anderes Speicherkonto erstellen.

Nachdem Sie eine Warteschlange erstellt haben, wechseln Sie zur Registerkarte **Ereignisse** auf der Seite Warteschlange, um das Ereignisabonnement zu konfigurieren. Wählen Sie alle BLOB-Ereignisse aus, die von der Warteschlange empfangen werden, und verbinden Sie die Warteschlange mit dem Gen2-Konto des Azure Data Lake-Speichers.

## <a name="manage-the-search-schema"></a>Verwalten des Suchschemas
Auf dem Bildschirm " **Schema verwalten** " können Sie die Schema Attribute (**abgefragt**, **durchsuchbar**und **abrufbar**) ändern, die den verwalteten Eigenschaften zugeordnet sind. Diese Attribute verwalteter Eigenschaften sind Daten, die aus Ihrem Azure Data Lake-Speicher Gen2-Konto indiziert werden.

## <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen
Auf dem Bildschirm **Suchberechtigungen verwalten** können Sie die Zugriffssteuerungslisten (Access Control Lists, ACLs) aus Ihrem Speicherkonto aufnehmen. Wenn diese Suchberechtigungen festgelegt sind, wird der Such Inhalt basierend auf den Berechtigungen gekürzt, die dem angemeldeten Azure AD Benutzer zugewiesen sind, der den Inhalt durchsucht. Alternativ können Sie festlegen, dass alle von Ihrem Speicherkonto indizierten Inhalte für alle Benutzer in Ihrer Organisation sichtbar gemacht werden sollen. In diesem Fall können alle Benutzer in Ihrer Organisation auf alle Daten in Ihrem Speicherkonto zugreifen.
 
## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans
Auf dem Bildschirm **Einstellungen aktualisieren** können Sie das Intervall für inkrementelle Durchforstung und das vollständige Durchforstungs Intervall festlegen. Die Standardintervalle für den Azure Data Lake-Speicher Gen2-Connector liegen bei einer inkrementellen Durchforstung und einer Woche für eine vollständige Durchforstung bei 15 Minuten.
 
## <a name="limitations"></a>Einschränkungen
Derzeit ist Azure Data Lake Storage Gen2 Multi-Protocol-Zugriff nur in den zentralen USA, West-Zentralamerika, Kanada Zentral, Ost-und Ostasien, Nordeuropa, Ost-US2, Südostasien, Westeuropa, Westamerika, Australien Ost, Japan Ost, West US2 und Brasilien verfügbar. Süden.

Updates und weitere Informationen finden Sie unter [Multi-Protocol Access on Azure Data Lake Storage (Preview)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-multi-protocol-access).


