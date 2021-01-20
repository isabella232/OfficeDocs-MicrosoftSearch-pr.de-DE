---
title: Verwalten von Microsoft Graph Connectors für Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Verwalten von Microsoft Graph Connectors für Microsoft Search.
ms.openlocfilehash: 5258f26a5c97be4ee9f90c7a8b2b9bb8fec447bc
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905930"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>Überwachen Der Verbindungen

Um auf Ihre Connectors zugreifen und diese verwalten zu können, müssen Sie als Suchadministrator für Ihren Mandanten festgelegt werden. Wenden Sie sich an Ihren Mandantenadministrator, um Ihnen die Rolle des Suchadministrators zur Bereitstellung zu bereitstellen.

## <a name="connection-operations"></a>Verbindungsvorgänge

Navigieren Sie [im](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) [Microsoft 365 Admin Center](https://admin.microsoft.com)zur Registerkarte "Connectors".

Für jeden Connectortyp unterstützt [das Microsoft 365 Admin Center](https://admin.microsoft.com) die in der folgenden Tabelle aufgeführten Vorgänge:

Vorgang | Von Microsoft erstellter Connector | Partner oder benutzerdefinierter Connector
--- | --- | ---
Hinzufügen einer Verbindung | :heavy_check_mark: (Siehe [Konfigurieren des von Microsoft erstellten Connectors)](configure-connector.md) | :x: (Verweisen Sie auf die Administrator-UX Ihres Partners oder ihres benutzerdefinierten Connectors)
Löschen einer Verbindung | :heavy_check_mark: | :heavy_check_mark:
Bearbeiten einer veröffentlichten Verbindung | :heavy_check_mark: Name<br></br> :heavy_check_mark: Beschreibung<br></br> :heavy_check_mark: Authentifizierungsanmeldeinformationen für Die externe Datenquelle<br></br> :heavy_check_mark: Gatewayanmeldeinformationen für Ihre lokale Datenquelle<br></br> :heavy_check_mark: Aktualisierungszeitplan<br></br> | :heavy_check_mark: Name<br></br> :heavy_check_mark: Beschreibung
Bearbeiten einer Entwurfsverbindung | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a>Überwachen des Verbindungsstatus

Nachdem Sie eine Verbindung erstellt haben, wird die Anzahl der verarbeiteten Elemente auf der Registerkarte **"Connectors"** auf der **Microsoft Search-Seite** angezeigt. Nachdem die erste vollständige Durchforstung erfolgreich abgeschlossen wurde, wird der Fortschritt für regelmäßige inkrementelle Durchforstungen angezeigt. Diese Seite enthält Informationen zu den täglichen Vorgängen des Connectors sowie eine Übersicht über die Protokolle und den Fehlerverlauf.

Vier Zustände werden in der **Spalte "Status"** für jede Verbindung angezeigt:

* **Synchronisierung**. Der Connector durchforstet die Daten aus der Quelle, um die vorhandenen Elemente zu indizieren und Aktualisierungen zu machen.

* **Aktiviert:** Die Verbindung ist aktiviert, und es wird keine aktive Durchforstung ausgeführt. **Die letzte Synchronisierungszeit** gibt an, wann die letzte erfolgreiche Durchforstung passiert ist. Die Verbindung ist so neu wie die letzte Synchronisierungszeit.

* **Angehalten**. Die Durchforstungen werden von den Administratoren über die Option zum Anhalten angehalten. Die nächste Durchforstung wird nur ausgeführt, wenn sie manuell fortgesetzt wird. Die Daten aus dieser Verbindung sind jedoch weiterhin durchsuchbar.

* **Fehler**. Bei der Verbindung ist ein kritischer Fehler aufting. Dieser Fehler erfordert einen manuellen Eingriff. Der Administrator muss basierend auf der angezeigten Fehlermeldung entsprechende Maßnahmen ergreifen. Daten, die indiziert wurden, bis der Fehler aufgetreten ist, sind durchsuchbar.

## <a name="monitor-your-index-quota-utilization"></a>Überwachen der Auslastung Ihres Indexkontingents

Das verfügbare Indexkontingent und der verfügbare Verbrauch werden auf der Angebotsseite für Connectors angezeigt.

![Auslastungsbalken für Indexkontingente](media/quota_utilization.png)

>[!NOTE]
>Während des Vorschauzeitraums wurde jeder Organisation, die Graph Connectors ausprobieren, ein kostenloses festes Kontingent von bis zu 2 Millionen Elementen über alle Verbindungen bereitgestellt. Da Graph Connectors allgemein verfügbar sind, läuft das kostenlose Kontingent am 1. Februar 2021 für organisationen ab, die Graph Connectors in der Vorschau verwendet haben.
>Von Microsoft erstellten Graph-Connectors, die als ["Vorschau"](connectors-preview.md) gekennzeichnet sind, werden nicht in das aufgeladene Indexkontingent für Ihre Organisation einbezogen. Es wird jedoch auf die maximale Anzahl von 10 Verbindungen angezählt, die Sie für Ihre Organisation konfigurieren können, und auf die maximale Anzahl von 7 Millionen Elementen, die Ihre Organisation über Verbindungen indizieren kann. Jede Verbindung ist auf 700.000 Elemente beschränkt. 

Die Kontingentauslastungsleiste gibt verschiedene Zustände basierend auf dem Verbrauch des Kontingents durch Ihre Organisation an:

Status | Kontingentverbrauch
--- | ---
Normal | 1-69%
Hoch | 70-89%
Kritisch | 90%-99%
Vollständig | 100 %

Die Anzahl der indizierten Elemente wird auch bei jeder Verbindung angezeigt. Die Anzahl der von jeder Verbindung indizierten Elemente trägt zum Gesamtkontingent bei, das für Ihre Organisation verfügbar ist.

Wenn das Indexkontingent für Ihre Organisation überschritten wird, sind alle aktiven Verbindungen betroffen, und diese Verbindungen werden im **Grenzwertüberschreitungsstatus** betrieben. In diesem Zustand werden ihre aktiven Verbindungen  

* Neue Elemente können nicht hinzugefügt werden.

* Kann vorhandene Elemente aktualisieren oder löschen.

Um dieses Problem zu beheben, können Sie eine der folgenden Schritte tun:

* Erfahren Sie, wie Sie ein Indexkontingent für Ihre Organisation zu [Lizenzierungsanforderungen und -preisen erwerben.](licensing.md)

* Identifizieren Sie Verbindungen, die zu viele Inhalte enthalten, und aktualisieren Sie sie so, dass weniger Elemente indiziert werden, um Platz für Kontingente zu erhalten. Um die Verbindung zu aktualisieren, müssen Sie eine neue Verbindung mit einem neuen Erfassungsfilter löschen und erstellen, der weniger Elemente einf?nst.

* Endgültiges Löschen einer oder mehrere Verbindungen