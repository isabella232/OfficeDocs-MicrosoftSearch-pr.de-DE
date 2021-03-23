---
title: Details und Fehler von Connectors
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
description: Details und Fehler von Connectors
ms.openlocfilehash: 6b1368818668c94a92f575609e953effe6cf21c1
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031305"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="view-connection-details-and-errors"></a>Verbindungsdetails und -Fehler anzeigen

Um auf Ihre Connectors zugreifen und diese verwalten zu können, müssen Sie als Suchadministrator für Ihren Mandanten festgelegt werden. Wenden Sie sich an Den Mandantenadministrator, um Sie für die Rolle des Suchadministrators zu verwenden.

Navigieren Sie zur [Registerkarte Connectors](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) im [Microsoft 365 Admin Center](https://admin.microsoft.com).

Sie können Verbindungsdetails und Fehler anzeigen, wenn Sie auf der Registerkarte Connectors auf die [Verbindung klicken.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)  

## <a name="view-your-last-crawl-info"></a>Anzeigen der letzten Durchforstungsinformationen

Nachdem die erste inkrementelle oder vollständige Durchforstung erfolgreich abgeschlossen wurde, werden die letzten Durchforstungsdatenwerte unter dem letzten Durchforstungsheader im Detailbereich angezeigt. Wenn es keine letzte durchforstete Durchforstung gab, werden keine Informationen unter dem letzten Durchforstungsheader angezeigt. Diese Informationen zur letzten Durchforstung helfen Ihnen, Einblicke in die Funktionsweise der Durchforstung zu erhalten und erforderlichenfalls die erforderlichen Schritte zu ergreifen.

Die folgenden letzten Durchforstungswerte stehen für jede Verbindung zur Verfügung:

Wert | Beschreibung
--- | ---
**Abgeschlossen unter** | Datum und Uhrzeit der letzten Durchforstung abgeschlossen
**Typ** | Inkrementelle oder vollständige Durchforstung
**Duration** | Zeit bis zum Abschluss der letzten Durchforstung
**Erfolge** | Anzahl der Elemente, die bei der letzten Durchforstung erfolgreich aufgenommen wurden
**Fehler** | Anzahl der Elemente, die bei der letzten Durchforstung fehlert

## <a name="monitor-errors"></a>Überwachen von Fehlern

Für jeden **aktiven Connector auf** der Registerkarte **Connectors** werden alle vorhandenen Durchforstungsfehler unter der Registerkarte **Fehler** angezeigt. Auf der Registerkarte werden Fehlercodes, die Anzahl der einzelnen Optionen und Fehlerprotokolldownloadoptionen aufgeführt. Sehen Sie sich das Beispiel in der folgenden Abbildung an. Wählen Sie einen **Fehlercode aus,** um die Fehlerdetails anzuzeigen.

![Connectors-Liste mit ausgewähltem Connector und Detailbereich mit 3 Fehlern für diesen Connector.](media/errormonitoring1.png)

Wählen Sie den Fehlercode aus, um die spezifischen Details eines Fehlers anzuzeigen. Ein Bildschirm mit Fehlerdetails und einem Link wird angezeigt. Die neuesten Fehler werden oben angezeigt. Sehen Sie sich das Beispiel in der folgenden Tabelle an.

![Connectorliste mit ausgewähltem Connector und Detailbereich mit der Liste der Fehler für den Connector.](media/errormonitoring2.png)

Unten sehen Sie die Liste der verschiedenen Fehler, die für jede Verbindung angezeigt werden können.

Fehlercode | Fehlermeldung | Lösung
--- | --- | ---
1000 | Die Datenquelle ist nicht verfügbar. Überprüfen Sie Ihre Internetverbindung, oder stellen Sie sicher, dass der Zugriff auf die Datenquelle weiterhin über den Connector möglich ist. | Dieser Fehler tritt auf, wenn die Datenquelle aufgrund eines Netzwerkproblems nicht erreichbar ist oder wenn die Datenquelle selbst gelöscht, verschoben oder umbenannt wird. Überprüfen Sie, ob die bereitgestellten Datenquellendetails noch gültig sind.
1001 | Die Daten können nicht aktualisiert werden, da die Datenquelle den Connector drosselt. | Überprüfen Sie, ob die Skalierungsgrenzwerte erhöht werden können, oder warten Sie, bis eine weniger datenverkehrslastige Zeit des Tages auf die Datenquelle beschränkt ist.
1002 | Kann nicht bei der Datenquelle authentifiziert werden. Stellen Sie sicher, dass die dieser Datenquelle zugeordneten Anmeldeinformationen korrekt sind. | Klicken **Sie auf Bearbeiten,** um die Authentifizierungsanmeldeinformationen zu aktualisieren.
1003 | Das dem Connector zugeordnete Konto verfügt nicht über die Berechtigung für den Zugriff auf das Element. |  Stellen Sie sicher, dass das richtige Konto Zugriff auf das Element hat, das indiziert werden soll.
1004 | Das lokale Datengateway kann nicht erreicht werden. Stellen Sie sicher, dass der Gatewaydienst ausgeführt wird und die Gatewaydetails in der Verbindungskonfiguration aktualisiert werden. | Überprüfen Sie den Computer mit dem Gateway, öffnen Sie die Power BI-Gatewayanwendung, und stellen Sie sicher, dass das Gateway ausgeführt wird. Stellen Sie sicher, dass das Gateway dasselbe Administratorkonto wie Microsoft Search verwendet, und stellen Sie dann sicher, dass alle Gatewaydetails in der Verbindungskonfiguration aktualisiert werden.
1005 | Die dieser Datenquelle zugeordneten Anmeldeinformationen sind abgelaufen. Verlängern Sie die Anmeldeinformationen, und aktualisieren Sie die Verbindung. | Klicken **Sie auf Bearbeiten,** um die Authentifizierungsanmeldeinformationen zu aktualisieren.
1006 | Ihre Gatewayversion ist veraltet und unterstützt diesen Connector nicht mehr. Sie müssen das Gateway aktualisieren. | Besuchen Sie [Installieren eines lokalen Datengateways,](/data-integration/gateway/service-gateway-install) um die neueste Version des Power BI-Gateways auf dem Computer herunterzuladen und zu installieren, der das Gateway enthält.
1007 | Keine gültige Power BI-Lizenz erkannt. Sie benötigen eine gültige Power BI-Lizenz, um diese Durchforstung durchführen zu können. | Sie benötigen eine gültige Power BI-Lizenz, um diese Durchforstung durchführen zu können. Überprüfen Sie, ob Ihre Organisation über eine gültige Lizenz verfügt. Versuchen Sie es dann erneut. Falls nicht, rufen Sie eine Lizenz ab, und versuchen Sie es dann erneut.
1008 | Die Gesamtkontingentauslastung Ihres Mandanten hat seinen Grenzwert erreicht. | Versuchen Sie, eine Verbindung zu löschen, um einen Teil Ihres Kontingents frei zu geben, oder passen Sie Ihre Aufnahmefilter an, um weniger Daten einsenden zu können. Wenn diese das Problem nicht lösen, wenden Sie sich an den Microsoft-Support.
1009 | Die Gesamtkontingentauslastung für Ihre Verbindung hat ihren Grenzwert erreicht. | Versuchen Sie, ihre Aufnahmefilter anzupassen, um weniger Daten einsenden zu können. Wenn das Problem dadurch nicht behoben wird, wenden Sie sich an den Microsoft-Support.
1010 | Die Gesamtkontingentauslastung für die Indizierung von Nicht-Azure AD-Gruppen hat ihren Grenzwert von 100K erreicht. | Versuchen Sie, eine Verbindung zu löschen, um einen Teil Ihres Kontingents frei zu geben, oder passen Sie Ihre Aufnahmefilter an, um weniger Daten einsenden zu können. Wenn diese das Problem nicht lösen, wenden Sie sich an den Microsoft-Support.
1011 | Der [Graph-Connector-Agent](on-prem-agent.md) ist nicht erreichbar oder offline. | 
1012 | Fehler bei der Authentifizierung ihrer Verbindung aufgrund eines nicht unterstützten Authentifizierungsmodus. | Bearbeiten Sie die Verbindung, um die Authentifizierungseinstellungen für Ihre Verbindung zu aktualisieren.
2001 | Die Indizierung wird aufgrund einer großen Anzahl von Updates in der Warteschlange gedrosselt. Je nach Warteschlange kann es einige Zeit dauern, bis die Updates abgeschlossen sind. | Warten Sie, bis die Warteschlange gelöscht wird.
2002 | Fehler bei der Indizierung aufgrund der nicht unterstützten Elementformatierung. | Weitere Informationen finden Sie in der connectorspezifischen Dokumentation.
2003 | Fehler bei der Indizierung aufgrund nicht unterstützter Elementinhalte. | Weitere Informationen finden Sie in der connectorspezifischen Dokumentation.
2004 | Fehler bei der Indizierung aufgrund der nicht unterstützten Element- oder Dateigröße. | Weitere Informationen finden Sie in der connectorspezifischen Dokumentation.
2005 | Fehler bei der Indizierung, da der URI zu lang ist. | Weitere Informationen finden Sie in der connectorspezifischen Dokumentation.
2006 | Fehler bei der Benutzerzuordnung aufgrund einer ungültigen Zuordnungsformel oder eines Azure AD-Benutzers mit dieser Eigenschaft. | Versuchen Sie, die Verbindung mit einer anderen Zuordnungsformel zu löschen und neu zu erstellen. 
2007 | Dieses Element wird in Microsoft Search nicht angezeigt, da einige Benutzer oder Gruppen ohne Berechtigung zum Anzeigen dieses Elements nicht indiziert werden konnten. | 
2008 | Verbindungen dürfen keine Azure AD-Gruppen mit mehr als 50.000 Mitgliedern haben. | Versuchen Sie, Benutzer aus einer Gruppe zu entfernen, oder versuchen Sie, Elemente, die mit dieser Gruppe verbunden sind, aus der Aufnahme zu entfernen, und erstellen Sie die Verbindung neu.
2009 | Die Indizierung von Nicht-Azure AD-Gruppen wird aufgrund einer großen Anzahl von Anforderungen vorübergehend angehalten. Die Indizierung wird fortgesetzt, wenn das System die Verarbeitung dieser Anforderungen abgeschlossen hat. Überprüfen Sie dies später. | 
2010 | Diese Verbindung ist aufgrund eines von Microsoft vorgenommenen Updates nicht mehr gültig. Löschen Sie die Verbindung, und erstellen Sie eine neue Verbindung. | Löschen Sie die Verbindung, und erstellen Sie eine neue Verbindung.
5000 | Es ist etwas schief gelaufen. Wenn dies fortgesetzt wird, wenden Sie sich an den Support. |