---
title: Verwalten von Microsoft Graph Connectors für Microsoft Search
ms.author: mecampos
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Verwalten von Microsoft Graph Connectors für Microsoft Search.
ms.openlocfilehash: dd82114ff6aa651b57ce1941685840906ecf7318
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2021
ms.locfileid: "59334533"
---
# <a name="monitor-your-connections"></a>Ihre Verbindungen überwachen

Um auf Ihre Connectors zugreifen und diese verwalten zu können, müssen Sie als Suchadministrator für Ihren Mandanten festgelegt werden. Wenden Sie sich an Ihren Mandantenadministrator, um Sie für die Rolle des Suchadministrators bereitzustellen.

## <a name="connection-operations"></a>Verbindungsvorgänge

Navigieren Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zur [Registerkarte "Connectors".](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)

Für jeden Verbindertyp unterstützt das [Microsoft 365 Admin Center](https://admin.microsoft.com) die in der folgenden Tabelle gezeigten Vorgänge:

Vorgang | Microsoft Graph-Connectors | Partner- oder Graph Connectors
--- | --- | ---
Hinzufügen einer Verbindung | :heavy_check_mark: (Siehe [Setupübersicht](configure-connector.md)) | :x: (Wenden Sie sich an Ihren Partner oder die benutzerdefinierte Connector-Administrator-UX)
Löschen einer Verbindung | :heavy_check_mark: | :heavy_check_mark:
Bearbeiten einer veröffentlichten Verbindung | :heavy_check_mark: Name und Beschreibung<br></br> :heavy_check_mark: Verbindungseinstellungen<br></br> :heavy_check_mark: Eigenschaftenbeschriftungen<br></br> :heavy_check_mark: Schema<br></br> :heavy_check_mark: Aktualisierungszeitplan<br></br> | :heavy_check_mark: Name<br></br> :heavy_check_mark: Beschreibung
Bearbeiten eines Verbindungsentwurfs | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a>Überwachen des Verbindungsstatus

Nachdem Sie eine Verbindung hergestellt haben, wird die Anzahl der verarbeiteten Elemente auf der Registerkarte **Connectors** auf der **Microsoft Search** Seite angezeigt. Nachdem die anfängliche vollständige Durchforstung erfolgreich abgeschlossen wurde, wird der Fortschritt für regelmäßige inkrementelle Durchforstungen angezeigt. Diese Seite enthält Informationen zu den täglichen Vorgängen des Connectors und eine Übersicht über die Protokolle und den Fehlerverlauf.

Fünf Zustände werden in der Spalte **"Status"** für jede Verbindung angezeigt:

* **Synchronisieren .** Der Connector durchforstet die Daten aus der Quelle, um die vorhandenen Elemente zu indizieren und Aktualisierungen vorzunehmen.

* **Bereit:** Die Verbindung ist bereit, und es wird keine aktive Durchforstung ausgeführt. **Die letzte Synchronisierungszeit** gibt an, wann die letzte erfolgreiche Durchforstung stattgefunden hat. Die Verbindung ist so aktuell wie die letzte Synchronisierungszeit.

* **Angehalten.** Die Durchforstungen werden von den Administratoren über die Unterbrechungsoption angehalten. Die nächste Durchforstung wird nur ausgeführt, wenn sie manuell fortgesetzt wird. Die Daten aus dieser Verbindung sind jedoch weiterhin durchsuchbar.

* **Fehler**. Bei der Verbindung ist ein schwerwiegender Fehler aufgetreten. Dieser Fehler erfordert einen manuellen Eingriff. Der Administrator muss basierend auf der angezeigten Fehlermeldung entsprechende Maßnahmen ergreifen. Daten, die indiziert wurden, bis der Fehler aufgetreten ist, können durchsucht werden.

* **Delete Failed**. Fehler beim Löschen der Verbindung. Je nach Fehlergrund sind die Daten möglicherweise noch indiziert, das Elementkontingent kann weiterhin genutzt werden und Durchforstungen für die Verbindung werden möglicherweise noch ausgeführt. Es wird empfohlen, die Verbindung in diesem Zustand erneut zu löschen.

## <a name="monitor-your-index-quota-utilization"></a>Überwachen der Indexkontingentauslastung

Das verfügbare Indexkontingent und die verfügbare Nutzung werden auf der Connectors-Zielseite angezeigt.

:::image type="content" alt-text="Indexkontingent-Auslastungsbalken." source="media/quota_utilization.png" lightbox="media/quota_utilization.png":::

Die Kontingentauslastungsleiste gibt verschiedene Zustände basierend auf der Kontingentnutzung durch Ihre Organisation an:

Status | Kontingentauslastungsstufen
--- | --- 
Standard | 0-79%
High | 80-89%
Kritisch | 90%-99%
Vollständig | 100 %

Die Anzahl der indizierten Elemente wird auch bei jeder Verbindung angezeigt. Die Anzahl der von jeder Verbindung indizierten Elemente trägt zum gesamt für Ihre Organisation verfügbaren Kontingent bei.

Wenn das Indexkontingent für Ihre Organisation überschritten wird, sind alle aktiven Verbindungen betroffen, und diese Verbindungen werden im **Zustand "Grenzwert überschritten"** ausgeführt. In diesem Zustand ihre aktiven Verbindungen  

* Neue Elemente können nicht hinzugefügt werden.

* Kann vorhandene Elemente aktualisieren oder löschen.

Um dies zu beheben, können Sie eine der folgenden Aktionen ausführen:

* Erfahren Sie, wie Sie das Indexkontingent für Ihre Organisation unter [Lizenzierungsanforderungen und Preisen](licensing.md)erwerben.

* Identifizieren Sie Verbindungen, bei denen zu viel Inhalt aufgenommen wird, und aktualisieren Sie sie so, dass weniger Elemente indiziert werden, um Platz für Kontingente zu schaffen. Um die Verbindung zu aktualisieren, müssen Sie eine neue Verbindung mit einem neuen Aufnahmefilter löschen und erstellen, der weniger Elemente enthält.

* Löschen Sie eine oder mehrere Verbindungen dauerhaft.
