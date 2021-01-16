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
ms.openlocfilehash: cf1231f8003d166977398ef4bdcc1ad12104dd05
ms.sourcegitcommit: d22fe2a34d7efe2dd5bbb456f0d00eb5f6c7608c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880609"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="manage-your-connections-for-microsoft-search"></a>Verwalten Ihrer Verbindungen für Microsoft Search

Um auf Ihre Connectors zugreifen und diese verwalten zu können, müssen Sie als Suchadministrator für Ihren Mandanten festgelegt werden. Wenden Sie sich an Ihren Mandantenadministrator, um Ihnen die Rolle des Suchadministrators zur Bereitstellung zu bereitstellen.

## <a name="get-started"></a>Erste Schritte

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

### <a name="view-your-last-crawl-info"></a>Anzeigen der letzten Durchforstungsinformationen

Nachdem die erste inkrementelle oder vollständige Durchforstung erfolgreich abgeschlossen wurde, werden die letzten Durchforstungsdatenwerte unter dem letzten Durchforstungsheader im Detailbereich angezeigt. Wenn es keine letzte durchforstete Durchforstung gab, werden unter dem letzten Durchforstungsheader keine Informationen angezeigt. Diese Informationen zur letzten Durchforstung helfen Ihnen, Einblicke in die Art und Weise zu gewinnen, wie die Durchforstung ausgeführt wurde, und gegebenenfalls erforderliche Schritte zu unternehmen.

Die folgenden letzten Durchforstungswerte sind für jede Verbindung verfügbar:

Wert | Beschreibung
--- | ---
Abgeschlossen am | Datum und Uhrzeit der letzten Durchforstung
Typ | Inkrementelle oder vollständige Durchforstung
Dauer | Wie lange die letzte Durchforstung ge dauern hat
Erfolge | Anzahl der Elemente, die bei der letzten Durchforstung erfolgreich aufgenommen wurden
Fehler | Anzahl der Elemente, bei der letzten Durchforstung Fehler aufgetreten sind

### <a name="monitor-errors"></a>Überwachen von Fehlern

Alle **vorhandenen Durchforstungsfehler** werden für jeden aktiven Connector auf der Registerkarte **"Connectors"** unter der Registerkarte **"Fehler"** angezeigt. Auf der Registerkarte werden Fehlercodes, die Anzahl der einzelnen Sowie Downloadoptionen für Fehlerprotokolle aufgeführt. Sehen Sie sich das Beispiel in der folgenden Abbildung an. Wählen Sie einen **Fehlercode aus,** um die Fehlerdetails anzuzeigen.

![Connectorliste mit ausgewähltem Connector und Detailbereich mit drei Fehlern für diesen Connector.](media/errormonitoring1.png)

Um die spezifischen Details eines Fehlers anzuzeigen, wählen Sie dessen Fehlercode aus. Ein Bildschirm mit Fehlerdetails und einem Link wird angezeigt. Die neuesten Fehler werden oben angezeigt. Sehen Sie sich das Beispiel in der folgenden Tabelle an.

![Connectorliste mit ausgewähltem Connector und Detailbereich mit der Liste der Fehler für den Connector.](media/errormonitoring2.png)

Im Folgenden finden Sie eine Liste der verschiedenen Fehler, die für jede Verbindung auftreten können.

Fehlercode | Fehlermeldung | Lösung
--- | --- | ---
1000 | Die Datenquelle ist nicht verfügbar. Überprüfen Sie Ihre Internetverbindung, oder stellen Sie sicher, dass der Connector weiterhin auf die Datenquelle zugreifen kann. | Dieser Fehler tritt auf, wenn die Datenquelle aufgrund eines Netzwerkproblems nicht erreichbar ist oder wenn die Datenquelle selbst gelöscht, verschoben oder umbenannt wird. Überprüfen Sie, ob die bereitgestellten Datenquellendetails noch gültig sind.
1001 | Die Daten können nicht aktualisiert werden, da die Datenquelle den Connector drosselt. | Überprüfen Sie, ob die Skalierungsgrenzwerte der Datenquelle erhöht werden können, oder warten Sie, bis eine weniger datenverkehrslastige Tageszeit vor sich geht.
1002 | Die Authentifizierung bei der Datenquelle ist nicht erfolgreich. Stellen Sie sicher, dass die dieser Datenquelle zugeordneten Anmeldeinformationen korrekt sind. | Klicken **Sie auf "Bearbeiten",** um die Authentifizierungsanmeldeinformationen zu aktualisieren.
1003 | Das dem Connector zugeordnete Konto verfügt nicht über die Berechtigung für den Zugriff auf das Element. |  Stellen Sie sicher, dass das richtige Konto Zugriff auf das Element hat, das indiziert werden soll.
1004 | Das lokale Datengateway kann nicht erreicht werden. Stellen Sie sicher, dass der Gatewaydienst ausgeführt wird und die Gatewaydetails in der Verbindungskonfiguration aktualisiert werden. | Überprüfen Sie den Computer mit dem Gateway, öffnen Sie die Power BI-Gateway-Anwendung, und stellen Sie sicher, dass das Gateway ausgeführt wird. Stellen Sie sicher, dass das Gateway das gleiche Administratorkonto wie Microsoft Search verwendet, und stellen Sie dann sicher, dass alle Gatewaydetails in der Verbindungskonfiguration aktualisiert werden.
1005 | Die dieser Datenquelle zugeordneten Anmeldeinformationen sind abgelaufen. Erneuern Sie die Anmeldeinformationen, und aktualisieren Sie die Verbindung. | Klicken **Sie auf "Bearbeiten",** um die Authentifizierungsanmeldeinformationen zu aktualisieren.
1006 | Ihre Gatewayversion ist veraltet und unterstützt diesen Connector nicht mehr. Sie müssen das Gateway aktualisieren. | Besuchen Sie [die Installation eines lokalen Datengateways,](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) um die neueste Version des Power -BI-Gateways auf dem Computer herunterzuladen und zu installieren, der das Gateway enthält.
1007 | Keine gültige Power BI-Lizenz erkannt. Sie benötigen eine gültige Power BI-Lizenz, um diese Durchforstung durchzuführen. | Sie benötigen eine gültige Power BI-Lizenz, um diese Durchforstung durchzuführen. Überprüfen Sie, ob Ihre Organisation über eine gültige Lizenz verfügt. Versuchen Sie es dann erneut. Falls nicht, rufen Sie eine Lizenz ab, und versuchen Sie es dann erneut.
1008 | Die Gesamtkontingentauslastung Ihres Mandanten hat seinen Grenzwert erreicht. Versuchen Sie, eine Verbindung zu löschen, um einen Teil Ihres Kontingents frei zu geben, oder passen Sie Ihre Aufnahmefilter an, um weniger Daten einsenden zu können. | Versuchen Sie, eine Verbindung zu löschen, um einen Teil Ihres Kontingents frei zu geben, oder passen Sie Ihre Aufnahmefilter an, um weniger Daten einsenden zu können. Wenn diese das Problem nicht lösen, wenden Sie sich an den Microsoft-Support.
2001 | Die Indizierung wird aufgrund einer großen Anzahl von Updates in der Warteschlange gedrosselt. Je nach Warteschlange kann es einige Zeit dauern, bis die Updates abgeschlossen sind. | Warten Sie, bis die Warteschlange gelöscht wird.
2002 | Fehler bei der Indizierung aufgrund einer nicht unterstützten Elementformatierung. | Weitere Informationen finden Sie in der connectorspezifischen Dokumentation.
2003 | Fehler bei der Indizierung aufgrund von nicht unterstützten Elementinhalten. | Weitere Informationen finden Sie in der connectorspezifischen Dokumentation.
2010 | Diese Verbindung ist aufgrund eines von Microsoft vorgenommenen Updates nicht mehr gültig. Löschen Sie die Verbindung, und erstellen Sie eine neue Verbindung. | Löschen Sie die Verbindung, und erstellen Sie eine neue Verbindung.
5000 | Es ist ein Fehler aufgegangen. Wenn dies fortgesetzt wird, wenden Sie sich an den Support. |

## <a name="monitor-your-index-quota-utilization"></a>Überwachen der Auslastung Ihres Indexkontingents

Das verfügbare Indexkontingent und der verfügbare Verbrauch werden auf der Angebotsseite für Connectors angezeigt.

![Auslastungsbalken für Indexkontingente](media/quota_utilization.png)

>[!NOTE]
>Während des Vorschauzeitraums wurde jeder Organisation, die Graph Connectors ausprobieren, ein kostenloses festes Kontingent von bis zu 2 Millionen Elementen über alle Verbindungen bereitgestellt. Da Graph Connectors allgemein verfügbar sind, läuft das kostenlose Kontingent am 1. Februar 2021 für organisationen ab, die Graph Connectors in der Vorschau verwendet haben.
>Von Microsoft erstellten Graph-Connectors, die als ["Vorschau"](connectors-preview.md) gekennzeichnet sind, werden nicht in das aufgeladene Indexkontingent für Ihre Organisation einbezogen. Es wird jedoch auf die maximale Anzahl von 10 Verbindungen angezählt, die Sie für Ihre Organisation konfigurieren können, und auf die maximale Anzahl von 7 Millionen Elementen, die Ihre Organisation über Verbindungen indizieren kann. Jede Verbindung ist auf 700.000 Elemente beschränkt. 

Die Kontingentauslastungsleiste zeigt verschiedene Zustände basierend auf dem Verbrauch des Kontingents durch Ihre Organisation an:

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

* Endgültiges Löschen einer oder mehreren Verbindungen

## <a name="limitations"></a>Einschränkungen

* Wenn Sie **einen** von Microsoft erstellten Connector veröffentlichen, kann es einige Minuten dauern, bis die Verbindung erstellt wurde. Während dieser Zeit zeigt die Verbindung ihren Status als ausstehend an.

* Das [Microsoft 365 Admin Center](https://admin.microsoft.com) unterstützt  die Bearbeitung des Suchschemas nach der Veröffentlichung einer Verbindung nicht. Um das Suchschema zu bearbeiten, löschen Sie Ihre Verbindung, und erstellen Sie dann eine neue.

* Der Erfassungsdurchsatz wird bei etwa vier Elementen pro Sekunde gedrosselt.

* Schemaupdates werden nicht unterstützt. Nachdem Sie eine Verbindungseinrichtung erstellt haben, gibt es keine Möglichkeit, das Schema zu aktualisieren. Sie können die Verbindung nur löschen und neu erstellen.

* Es gibt ein Verbindungslimit. Jeder Mandant kann bis zu 10 Verbindungen erstellen.

* Die Bearbeitungsunterstützung für die Verbindung ist nicht verfügbar. Nachdem die Verbindung erstellt wurde, können Sie sie nicht mehr bearbeiten oder ändern. Wenn Sie Details ändern müssen, müssen Sie die Verbindung löschen und neu erstellen.
