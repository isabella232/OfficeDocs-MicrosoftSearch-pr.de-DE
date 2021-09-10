---
title: Azure Data Lake Graph Connector für Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Azure Data Lake Storage Gen2-Graph-Connectors für Microsoft Search
ms.openlocfilehash: f60de4252e514f84bc92daf4ea65c535cf40a13d
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973471"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Azure Data Lake Storage Gen2 Graph Connector

Der Azure Data Lake Storage Gen2 Graph Connector ermöglicht Es Benutzern in Ihrer Organisation, nach Dateien zu suchen, die in [Azure Blob Storage-](/azure/storage/blobs/storage-blobs-introduction) und [Azure Data Lake Gen 2 Storage-Konten](/azure/storage/blobs/data-lake-storage-introduction) gespeichert sind.

> [!NOTE]
> Lesen Sie den Artikel [**"Setup your Graph connector",**](configure-connector.md) um die allgemeinen Anweisungen zum Einrichten Graph Connectors zu verstehen.

Dieser Artikel richtet sich an alle Personen, die einen Azure Data Lake Storage Gen2-Connector konfigurieren, ausführen und überwachen. Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Azure Data Lake Storage Gen2-Connector gelten. Dieser Artikel enthält auch Informationen zu [Einschränkungen.](#limitations)

In diesem Artikel verwenden wir *Azure Storage* als generischen Begriff für [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction) und Azure Data Lake Gen [2 Storage.](/azure/storage/blobs/data-lake-storage-introduction)

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph Connectors im Microsoft 365 Admin Center

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Geben Sie die Zeichenfolge für die primäre Speicherverbindung ein. Diese Zeichenfolge ist erforderlich, um den Zugriff auf Ihr Speicherkonto zu ermöglichen. Um Ihre Verbindungszeichenfolge zu finden, wechseln Sie zum [Azure-Portal,](https://ms.portal.azure.com/#home) und navigieren Sie **zum** Schlüsselabschnitt Ihres relevanten Azure Storage Kontos.

Wenn Sie den **AccountKey** (einen Parameter in der primären Speicherverbindungszeichenfolge) nicht bereitstellen möchten, gewähren Sie Zugriff auf unseren Graph Connectors-Dienst für die folgenden Rollen:

* Storage Blob Data Reader
* Storage Mitwirkender für Warteschlangendaten
* Storage Blob-Delegator

Navigieren Sie zur Registerkarte **"Zugriffssteuerung"** Ihres Azure Storage Kontos, und folgen Sie den Anweisungen dort, um Zugriff auf die folgende App zu gewähren:

* **First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766
* **First Party App Name:** Graph Connector Service

### <a name="storage-account-and-queue-notifications-optional"></a>Storage Konto- und Warteschlangenbenachrichtigungen (optional)

Unterstützung für die Verarbeitung von Änderungen in Echtzeit im Graph Connectors-Dienst kann in Zukunft hinzugefügt werden. In diesem Fall überwachen wir Azure Storage in einer Warteschlange gespeicherten Änderungsbenachrichtigungen. Sie müssen eine Warteschlange in demselben Konto wie Ihr Azure Storage Konto erstellen.

Nachdem Sie eine Warteschlange erstellt haben, wechseln Sie zur Registerkarte **"Ereignisse"** auf der Warteschlangenseite, um das **Ereignisabonnement** zu konfigurieren. Wählen Sie alle Blob-Ereignisse aus, die die Warteschlange empfängt, und verbinden Sie die Warteschlange mit dem Azure Storage Konto.

## <a name="step-4-assign-property-labels"></a>Schritt 4: Zuweisen von Eigenschaftenbeschriftungen

Sie können jeder Bezeichnung eine Quelleigenschaft zuweisen, indem Sie aus einem Menü mit Optionen auswählen. Obwohl dieser Schritt nicht obligatorisch ist, verbessert die Verwendung einiger Eigenschaftenbezeichnungen die Suchrelevanz und stellt bessere Suchergebnisse für Endbenutzer sicher.

## <a name="step-5-manage-schema"></a>Schritt 5: Verwalten des Schemas

Auf dem Bildschirm **"Schema verwalten"** können Sie die den Eigenschaften zugeordneten Schemaattribute ändern. Die Optionen sind **Abfrage,** **Suche,** **Abrufen** und **Verfeinern.** Sie können auch optionale Aliase hinzufügen und die **Inhaltseigenschaft** auswählen.

## <a name="step-6-manage-search-permissions"></a>Schritt 6: Verwalten von Suchberechtigungen

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Sie können die Zugriffssteuerungslisten (Access Control Lists, ACLs) aus Ihrem [Azure Data Lake Gen 2 Storage-Konto](/azure/storage/blobs/data-lake-storage-introduction) aufnehmen. Wenn diese Suchberechtigungen festgelegt sind, wird der Suchinhalt basierend auf den Berechtigungen des benutzers gekürzt, der [Azure Active Directory](/azure/active-directory/)angemeldet ist. Alternativ können Sie festlegen, dass alle in Ihrem Speicherkonto indizierten Inhalte für alle Benutzer in Ihrer Organisation sichtbar sind. In diesem Fall hat jeder in Ihrer Organisation Zugriff auf alle Daten in Ihrem Speicherkonto.

Der Azure Data Lake Storage Gen2 Graph Connector unterstützt Suchberechtigungen, die **für "Jeder"** oder **nur für Personen mit Zugriff auf diese Datenquelle** sichtbar sind. Indizierte Daten, die in den Suchergebnissen angezeigt werden, können für Benutzer in der Organisation sichtbar sein, die Zugriff auf jedes Element haben.

### <a name="azure-blob-storage"></a>Azure Blob Storage

Für eine Verbindung mit [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction)ist der gesamte Inhalt, der aus der konfigurierten Quelle indiziert ist, für jeden in Ihrer Organisation sichtbar. Zugriffssteuerungslisten werden auf Blobebene in Azure Blob Storage nicht unterstützt.

## <a name="step-7-set-the-refresh-schedule"></a>Schritt 7: Festlegen des Aktualisierungszeitplans

Auf dem Bildschirm **"Aktualisieren Einstellungen"** können Sie das inkrementelle Durchforstungsintervall und das vollständige Durchforstungsintervall festlegen. Die Standardintervalle für den Azure Data Lake Storage Gen2-Connector sind 15 Minuten für eine inkrementelle Durchforstung und eine Woche für eine vollständige Durchforstung.

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Einschränkungen

Eine veröffentlichte Verbindung für Azure Blob Storage kann nicht für die Azure Data Lake Storage Gen2-Quelle neu konfiguriert werden und umgekehrt. In solchen Szenarien wird empfohlen, eine neue Verbindung zu konfigurieren.

Außerdem muss die Größe der Dateien 4 MB oder weniger betragen, damit sie durchforstet werden können. Derzeit unterstützte Dateitypen sind:

* Word (docx, .docm, .dotx, .dotm)
* PowerPoint (.pptm, .pptx, POTM, POTX, PPAM, PPSM, PPSX)
* Excel (.xlsx, XLSM)
* Legacy-Office formate (.doc, PUNKT usw.)
* Text (.txt)
* HTML
* PDF

Binärdateien wie Bilder (.jpg, .bmp usw.) werden nicht unterstützt. Wenn eine .docx Datei beispielsweise nur Bilder enthält, wird sie möglicherweise übersprungen, da keine Inhalte zurückgegeben wurden.