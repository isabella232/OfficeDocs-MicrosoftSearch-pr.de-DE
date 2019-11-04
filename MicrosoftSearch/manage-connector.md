---
title: Verwalten von Microsoft Graph-Connectors für Microsoft Search
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Verwalten von Microsoft Graph-Connectors für Microsoft Search.
ms.openlocfilehash: 5aab310a05d073221918a8aaa80ea1e06c818e51
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949823"
---
# <a name="manage-your-connector-for-microsoft-search"></a>Verwalten des Connectors für Microsoft Search

Für den Zugriff auf und die Verwaltung Ihrer Connectors müssen Sie als Suchadministrator für Ihren Mandanten festgelegt sein. Wenden Sie sich an Ihren mandantenadministrator, um Sie für die Suchadministrator Rolle zu informieren.

## <a name="get-started"></a>Erste Schritte

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com)an.
2. Wechseln Sie zu **Einstellungen** > **Microsoft-Such** > -**Konnektoren**.

Für jeden Connectortyp unterstützt das [Microsoft 365 Admin Center](https://admin.microsoft.com) die in der folgenden Tabelle aufgeführten Vorgänge:

**Vorgang** | **Von Microsoft erstellter Connector** | **Partner oder benutzerdefinierter Connector**
--- | --- | ---
Hinzufügen einer Verbindung | : heavy_check_mark: (siehe [Konfigurieren Ihres von Microsoft erstellten Connectors](configure-connector.md)) | : x: (Bezug auf Ihren Partner oder den benutzerdefinierten Connector-Administrator UX)
Löschen einer Verbindung | :heavy_check_mark: | :heavy_check_mark:
Bearbeiten einer veröffentlichten Verbindung | : heavy_check_mark: Name<br></br> : heavy_check_mark: Description<br></br> : heavy_check_mark: Authentifizierungsanmeldeinformationen für Ihre externe Datenquelle<br></br> : heavy_check_mark: Gateway-Anmeldeinformationen für Ihre lokale Datenquelle<br></br> : heavy_check_mark: Aktualisierungszeitplan<br></br> | : heavy_check_mark: Name<br></br> : heavy_check_mark: Description
Bearbeiten einer Entwurfs Verbindung | :heavy_check_mark: | x

## <a name="monitor-your-connection-status"></a>Überwachen des Verbindungsstatus
Nachdem Sie eine Verbindung erstellt haben, wird die Anzahl der verarbeiteten Elemente auf der Registerkarte **Connectors** auf der Seite **Microsoft-Suche** angezeigt. Nachdem die anfängliche vollständige Durchforstung erfolgreich abgeschlossen wurde, wird der Fortschritt für periodische inkrementelle Crawls angezeigt. Diese Seite enthält Informationen zu den täglichen Vorgängen des Connectors sowie eine Übersicht über die Protokolle und den Fehler Verlauf.

Vier Zustände werden in der Spalte **Status** für jede Verbindung angezeigt:
* **Synchronisierung**. Der Connector durchforstet die Daten aus der Quelle, um die vorhandenen Elemente zu indizieren und Aktualisierungen vorzunehmen.
* **Aktiviert**: die Verbindung ist aktiviert, und es wird keine aktive Durchforstung ausgeführt. **Letzte Synchronisierungszeit** gibt an, wann die letzte erfolgreiche Durchforstung aufgetreten ist. Die Verbindung ist so aktuell wie die letzte Synchronisierungszeit.
* **Angehalten**. Die durch forstungen werden von den Administratoren durch die Option Pause angehalten. Die nächste Durchforstung wird nur ausgeführt, wenn Sie manuell fortgesetzt wird. Die Daten aus dieser Verbindung sind jedoch weiterhin durchsuchbar.
* **Fehlerhaft**. Die Verbindung hatte einen kritischen Fehler. Für diesen Fehler ist ein manueller Eingriff erforderlich. Der Administrator muss die entsprechende Aktion basierend auf der angezeigten Fehlermeldung durchführen. Daten, die bis zum Auftreten des Fehlers indiziert wurden, sind durchsuchbar.

### <a name="monitor-errors"></a>Überwachen von Fehlern
Für jeden **aktiven Connector** auf der Registerkarte **Connectors** werden alle vorhandenen Durchforstungs Fehler unter der Registerkarte **Fehler** angezeigt. Auf der Registerkarte werden Fehlercodes, die Anzahl der einzelnen und Downloadoptionen für das Fehlerprotokoll aufgelistet. Sehen Sie sich das Beispiel in der folgenden Abbildung an. Wählen Sie einen **Fehlercode** aus, um die Details des Fehlers anzuzeigen.

![Liste der Connectors mit ausgewähltem Konnektor und Detailbereich mit 3 Fehlern für diesen Connector.](media/errormonitoring1.png)

Um die spezifischen Details eines Fehlers anzuzeigen, wählen Sie den entsprechenden Fehlercode aus. Ein Bildschirm mit Fehlerdetails und einem Link wird angezeigt. Die neuesten Fehler werden oben angezeigt. Siehe das Beispiel in der folgenden Tabelle.

![Connectorliste mit ausgewähltem Konnektor und Detailbereich, der die Liste der Fehler für den Connector anzeigt. ](media/errormonitoring2.png)

## <a name="preview-limitations"></a>Vorschau Einschränkungen
* Wenn Sie einen von Microsoft erstellten Connector **veröffentlichen** , kann es einige Minuten dauern, bis die Verbindung erstellt wurde. Während dieser Zeit zeigt die Verbindung den Status als ausstehend an. Außerdem gibt es keine automatische Aktualisierung, Sie müssen also manuell aktualisieren.
* Das [Microsoft 365 Admin Center](https://admin.microsoft.com) unterstützt das Anzeigen und Bearbeiten des **Suchschemas** nach dem Veröffentlichen einer Verbindung nicht. Um das Suchschema zu bearbeiten, löschen Sie die Verbindung, und erstellen Sie dann eine neue.
* Wenn Sie den **Aktualisierungszeitplan**ihrer Verbindung verwalten, wird die Anzahl der Elemente angezeigt, die während jeder Sitzung synchronisiert werden. Der Synchronisierungsverlauf ist jedoch nicht verfügbar.
