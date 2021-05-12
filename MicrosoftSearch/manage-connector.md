---
title: Verwalten von Microsoft Graph Connectors für Microsoft Search
ms.author: mecampos
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Verwalten von Microsoft Graph Connectors für Microsoft Search.
ms.openlocfilehash: 685b501f3afe25d75c13a1fe6cc2c1b5db8a3511
ms.sourcegitcommit: e5d695c40b68c2f1fa082fa9de20b9aa6d5b8050
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52325168"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>Ihre Verbindungen überwachen

Um auf Ihre Connectors zugreifen und diese verwalten zu können, müssen Sie als Suchadministrator für Ihren Mandanten festgelegt werden. Wenden Sie sich an Den Mandantenadministrator, um Sie für die Rolle des Suchadministrators zu verwenden.

## <a name="connection-operations"></a>Verbindungsvorgänge

Navigieren Sie zur [Registerkarte Connectors](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) im Microsoft 365 [Admin Center](https://admin.microsoft.com).

Für jeden Connectortyp unterstützt [Microsoft 365 Admin Center](https://admin.microsoft.com) die in der folgenden Tabelle gezeigten Vorgänge:

Vorgang | Microsoft Graph-Connectors | Partner- oder Graph Connectors
--- | --- | ---
Hinzufügen einer Verbindung | :heavy_check_mark: (Siehe [Setupübersicht](configure-connector.md)) | :x: (Verweisen Sie auf Ihre Partner- oder benutzerdefinierte Connectoradministrator-UX)
Löschen einer Verbindung | :heavy_check_mark: | :heavy_check_mark:
Bearbeiten einer veröffentlichten Verbindung | :heavy_check_mark: Name und Beschreibung<br></br> :heavy_check_mark: Verbindungseinstellungen<br></br> :heavy_check_mark: Eigenschaftenbezeichnungen<br></br> :heavy_check_mark: Schema<br></br> :heavy_check_mark: Aktualisierungszeitplan<br></br> | :heavy_check_mark: Name<br></br> :heavy_check_mark: Beschreibung
Bearbeiten einer Entwurfsverbindung | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a>Überwachen des Verbindungsstatus

Nachdem Sie eine Verbindung erstellt haben, wird die Anzahl der verarbeiteten Elemente auf der Registerkarte **Connectors** auf der **Seite Microsoft Search** angezeigt. Nachdem die anfängliche vollständige Durchforstung erfolgreich abgeschlossen wurde, wird der Fortschritt für regelmäßige inkrementelle Durchforstungen angezeigt. Diese Seite enthält Informationen zu den täglichen Vorgängen des Connectors sowie eine Übersicht über die Protokolle und den Fehlerverlauf.

Fünf Zustände werden in der **Spalte Status** für jede Verbindung angezeigt:

* **Synchronisieren**. Der Connector durchforstet die Daten aus der Quelle, um die vorhandenen Elemente zu indizieren und Aktualisierungen zu erstellen.

* **Ready**: Die Verbindung ist bereit, und es wird keine aktive Durchforstung ausgeführt. **Die letzte Synchronisierungszeit** gibt an, wann die letzte erfolgreiche Durchforstung passiert ist. Die Verbindung ist so neu wie die letzte Synchronisierungszeit.

* **Angehalten**. Die Durchforstungen werden von den Administratoren über die Pause-Option angehalten. Die nächste Durchforstung wird nur ausgeführt, wenn sie manuell fortgesetzt wird. Die Daten aus dieser Verbindung sind jedoch weiterhin durchsuchbar.

* **Fehler**. Die Verbindung hatte einen kritischen Fehler. Dieser Fehler erfordert manuellen Eingriff. Der Administrator muss basierend auf der angezeigten Fehlermeldung entsprechende Maßnahmen ergreifen. Daten, die bis zum Fehler indiziert wurden, sind durchsuchbar.

* **Fehler löschen.** Fehler beim Löschen der Verbindung. Je nach Fehlergrund sind die Daten möglicherweise noch indiziert, das Elementkontingent wird möglicherweise noch verwendet, und Crawls werden möglicherweise weiterhin für die Verbindung ausgeführt. Es wird empfohlen, die Verbindung in diesem Zustand erneut zu löschen.

## <a name="monitor-your-index-quota-utilization"></a>Überwachen der Indexkontingentauslastung

Das verfügbare Indexkontingent und der verfügbare Verbrauch werden auf der Angebotsseite der Connectors angezeigt.

![Indexkontingentauslastungsleiste](media/quota_utilization.png)
 
>[!NOTE]
>Während des Vorschauzeitraums wurde für jede Organisation, die Graph Connectors ausprobieren, ein kostenloses festes Kontingent von bis zu 2 Millionen Elementen für alle Verbindungen bereitgestellt. Da Graph connectors allgemein verfügbar sind, läuft das kostenlose Kontingent am 1. April 2021 für organisationen ab, die Graph Connectors in der Vorschau verwendet haben.
>Von Microsoft Graph Connectors, die als ["Vorschau"](./connectors-overview.md) gekennzeichnet sind, werden nicht in das insgesamt berechnete Indexkontingent für Ihre Organisation einbezogen. Es wird jedoch auf die maximale Anzahl von 10 Verbindungen angezählt, die Sie für Ihre Organisation konfigurieren können, und die maximale Anzahl von 7 Millionen Elementen, die Ihre Organisation über Verbindungen indizieren kann. Jede Verbindung ist auf 700.000 Elemente beschränkt. 

Die Kontingentauslastungsleiste gibt verschiedene Zustände basierend auf dem Verbrauch von Kontingenten durch Ihre Organisation an:

Status | Kontingentauslastungsstufen
--- | --- 
Standard | 0-79%
Hoch | 80-89%
Kritisch | 90%-99%
Vollständig | 100 %

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

Die Anzahl der indizierten Elemente wird auch bei jeder Verbindung angezeigt. Die Anzahl der von jeder Verbindung indizierten Elemente trägt zum Gesamtkontingent bei, das für Ihre Organisation verfügbar ist.

Wenn das Indexkontingent für Ihre Organisation überschritten wird, werden alle aktiven Verbindungen betroffen sein, und diese Verbindungen werden im **Grenzwertüberschreitungsstatus** betrieben. In diesem Zustand werden Ihre aktiven Verbindungen  

* Neue Elemente können nicht hinzugefügt werden.

* Vorhandene Elemente können aktualisiert oder gelöscht werden.

Um dies zu beheben, können Sie eine der folgenden Schritte tun:

* Informationen zum Kauf von Indexkontingenten für Ihre Organisation finden Sie unter [Lizenzierungsanforderungen und Preise](licensing.md).

* Identifizieren Sie Verbindungen, bei denen zu viel Inhalt aufgenommen wird, und aktualisieren Sie sie, um weniger Elemente zu indizieren, um Platz für Kontingente zu machen. Um die Verbindung zu aktualisieren, müssen Sie eine neue Verbindung mit einem neuen Aufnahmefilter löschen und erstellen, der weniger Elemente einf?

* Dauerhaftes Löschen einer oder mehreren Verbindungen