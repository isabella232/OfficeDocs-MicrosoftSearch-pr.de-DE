---
title: Verwalten von Microsoft Graph-Connectors für Microsoft Search
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Verwalten von Microsoft Graph-Connectors für Microsoft Search.
ms.openlocfilehash: 962ceb488fa308eb31a98a8fad33d628f3590e89
ms.sourcegitcommit: 1255c2612aec290ae117bdc24c3b4dabd1e5ca11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "39205867"
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
Löschen einer Verbindung | : heavy_check_mark: | : heavy_check_mark:
Bearbeiten einer veröffentlichten Verbindung | : heavy_check_mark: Name<br></br> : heavy_check_mark: Beschreibung<br></br> : heavy_check_mark: Authentifizierungsanmeldeinformationen für Ihre externe Datenquelle<br></br> : heavy_check_mark: Gateway-Anmeldeinformationen für Ihre lokale Datenquelle<br></br> : heavy_check_mark: Aktualisierungszeitplan<br></br> | : heavy_check_mark: Name<br></br> : heavy_check_mark: Beschreibung
Bearbeiten einer Entwurfs Verbindung | : heavy_check_mark: | x

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

Unten sehen Sie eine Liste mit verschiedenen Fehlern, die für jede Verbindung angezeigt werden können. Wenn diese Lösungen nicht funktionieren, wenden Sie sich an den Support oder senden Sie uns (Feedback) [Connectors-Feedback.MD]. 

**Fehlercode** | **Fehlermeldung** | **Lösung**
--- | --- | ---
1000 | Die Datenquelle ist nicht verfügbar. Überprüfen Sie Ihre Internetverbindung, oder stellen Sie sicher, dass der Connector weiterhin auf die Datenquelle zugreifen kann. | Dieser Fehler tritt auf, wenn die Datenquelle aufgrund eines Netzwerkproblems nicht erreichbar ist oder wenn die Datenquelle selbst gelöscht, verschoben oder umbenannt wird. Überprüfen, ob die bereitgestellten Datenquellendetails noch gültig sind.
1001 | Die Daten können nicht aktualisiert werden, da die Datenquelle die Verbindung drosselt. | Um die Drosselung der Datenquelle zu überprüfen, ob die Skalierungs Grenzwerte erhöht werden können, oder warten Sie, bis eine geringere Datenverkehrs intensive Tageszeit vorliegt.
1002 | Authentifizierung bei der Datenquelle nicht möglich. Stellen Sie sicher, dass die dieser Datenquelle zugeordneten Anmeldeinformationen richtig sind. | Klicken Sie auf **Bearbeiten** , um die Authentifizierungsanmeldeinformationen zu aktualisieren.
1003 | Das dem Connector zugeordnete Konto verfügt nicht über die Berechtigung, auf das Element zuzugreifen. |  Stellen Sie sicher, dass das richtige Konto Zugriff auf das Element hat, das Sie indizieren möchten.
1004 | Das lokale Daten Gateway kann nicht erreicht werden. Stellen Sie sicher, dass der Gatewaydienst aktiv ist. | Wechseln Sie zu dem Computer, der über das Gateway verfügt, und überprüfen Sie, ob das Power BI-Gateway ausgeführt wird, indem Sie die Power BI-Gateway-Anwendung öffnen. Stellen Sie sicher, dass das Gateway mit dem für Microsoft Search verwendeten Administratorkonto angemeldet ist. 
1005 | Anmeldeinformationen, die dieser Datenquelle zugeordnet sind, sind abgelaufen. Erneuern Sie die Anmeldeinformationen, und aktualisieren Sie die Verbindung. | Klicken Sie auf **Bearbeiten** , um die Authentifizierungsanmeldeinformationen zu aktualisieren. 
1006 | Ihre Gateway-Version ist veraltet und unterstützt diesen Connector nicht mehr. Das Gateway muss aktualisiert werden. | Weitere Informationen finden Sie unter (install a on-premiseshttps://docs.microsoft.com/en-us/data-integration/gateway/service-gateway-installData Gateway) [], um die neueste Version des Power BI-Gateways auf dem Computer mit dem Gateway herunterzuladen und zu installieren.
2001 | Die Indizierung wird aufgrund einer großen Anzahl von Updates in der Warteschlange eingeschränkt. Je nach Warteschlange kann es einige Zeit dauern, bis die Aktualisierungen abgeschlossen sind. | Warten Sie, bis die Warteschlange gelöscht wird.
2002 | Die Indizierung ist aufgrund einer nicht unterstützten Element Formatierung fehlgeschlagen. | Weitere Informationen finden Sie in der Connector-spezifischen Dokumentation.
2003 | Die Indizierung ist aufgrund eines nicht unterstützten Elementinhalts fehlgeschlagen. | Weitere Informationen finden Sie in der Connector-spezifischen Dokumentation. 
2004 | Die [Dateigröße](https://docs.microsoft.com/en-us/microsoftsearch/file-share-connector#content-requirements) ist zu groß, um indiziert zu werden. Sie muss vor der Verarbeitung 100 MB oder weniger betragen und darf nach der Verarbeitung nicht größer als 4 MB sein. Die Datei wird in diesem Fall teilweise indiziert. Einige in der Datei vorhandene Ausdrücke geben möglicherweise kein Suchergebnis zurück. |  
5000 | Etwas ist schief gelaufen. Wenn dieser Vorgang fortgesetzt wird, wenden Sie sich an den Support. | 

## <a name="preview-limitations"></a>Vorschau Einschränkungen
* Wenn Sie einen von Microsoft erstellten Connector **veröffentlichen** , kann es einige Minuten dauern, bis die Verbindung erstellt wurde. Während dieser Zeit zeigt die Verbindung den Status als ausstehend an. Außerdem gibt es keine automatische Aktualisierung, Sie müssen also manuell aktualisieren.
* Das [Microsoft 365 Admin Center](https://admin.microsoft.com) unterstützt das Anzeigen und Bearbeiten des **Suchschemas** nach dem Veröffentlichen einer Verbindung nicht. Um das Suchschema zu bearbeiten, löschen Sie die Verbindung, und erstellen Sie dann eine neue.
* Wenn Sie den **Aktualisierungszeitplan**ihrer Verbindung verwalten, wird die Anzahl der Elemente angezeigt, die während jeder Sitzung synchronisiert werden. Der Synchronisierungsverlauf ist jedoch nicht verfügbar.
