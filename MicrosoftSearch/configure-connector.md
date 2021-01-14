---
title: Konfigurieren des von Microsoft erstellten Connectors für Microsoft Search
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Konfigurieren des von Microsoft erstellten Connectors für Microsoft Search
ms.openlocfilehash: 61a7d444ddc4c290b5098c327faa8e70f0ef1049
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847546"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Setupübersicht für Graph Connectors von Microsoft 

In diesem Artikel wird der grundlegende Prozess zusammengefasst, der für die Verwendung des [Microsoft 365 Admin Centers](https://admin.microsoft.com) zum Einrichten von Graph Connectors durch Microsoft erforderlich ist. Der grundlegende Prozess umfasst die folgenden Schritte:  
<!---Add links to each section in the doc--->

1. Fügen Sie einen Graph Connector im Microsoft 365 Admin Center hinzu.
2. Benennen Sie die Verbindung.
3. Konfigurieren Sie die Verbindungseinstellungen.
4. Verwalten von Suchberechtigungen.
5. Zuweisen von Eigenschaftenbeschriftungen.
6. Verwalten des Schemas.
7. Wählen Sie Aktualisierungseinstellungen aus.
8. Überprüfen Sie die Verbindung.

Es ist wichtig zu beachten, dass der Einrichtungsprozess für alle Graph Connectors von Microsoft sehr ähnlich ist, aber nicht genau gleich ist. **Lesen Sie nicht nur diesen Artikel, sondern lesen Sie auch die connectorspezifischen Informationen für Ihre Datenquelle.**  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center

Führen Sie die folgenden Schritte aus, um einen der von Microsoft erstellten Connectors zu konfigurieren.

1. Melden Sie sich bei Ihrem Administratorkonto im [Microsoft 365 Admin Center an.](https://admin.microsoft.com)
2. Wählen Sie im Navigationsbereich **"Einstellungen"** und dann "Suche **& Intelligence" aus.** Wählen Sie die [Registerkarte "Connectors" aus.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)
3. Wählen **Sie +Hinzufügen** aus, und wählen Sie dann die Datenquelle Ihrer Wahl aus dem Menü der verfügbaren Optionen aus.

![Verfügbare Datenquellen sind: ADLS Gen2, Enterprise-Websites, Microsoft SQL-Server, Azure SQL, Oracle SQL-Datenbank, ServiceNow, Dateifreigabe, Azure DevOps und MediaWiki.](media/add-connector.png)

>[! Hinweis:] Sie können maximal zehn Graph-Verbindungen zu jedem Mandanten hinzufügen.

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung
Sie müssen die folgenden Attribute angeben: 

* Name  
* Verbindungs-ID 
* Beschreibung (optional) 

Die Verbindungs-ID erstellt implizite Eigenschaften für den Connector. Er darf nur alphanumerische Zeichen enthalten und darf maximal 32 Zeichen lang sein. 

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Der Prozess zum Konfigurieren der Verbindungseinstellungen variiert je nach Datenquellentyp. Informationen zum Typ der Datenquelle, die Sie Ihrem Mandanten hinzufügen möchten, um diesen Schritt im Setupprozess abzuschließen, finden Sie in den connectorspezifischen Informationen.  

Weitere Informationen zum Herstellen einer Verbindung mit einer lokalen Datenquelle finden Sie unter ["Installieren eines lokalen Datengateways".](https://aka.ms/configuregateway)

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen

Zugriffssteuerungslisten (Access Control Lists, ACLs) bestimmen, welche Benutzer in Ihrer Organisation auf jedes Datenelement zugreifen können.  

Einige Connectors wie [Microsoft SQL](MSSQL-connector.md) und Azure Data Lake [Storage Gen2](azure-data-lake-connector.md) unterstützen [nativ Azure Active Directory (Azure AD)-ACLs.](https://docs.microsoft.com/azure/active-directory/)

Andere Connectors wie [ServiceNow,](servicenow-connector.md) [Azure DevOps](azure-devops-connector.md)und [Salesforce](salesforce-connector.md) unterstützen die Synchronisierung von Nicht-Azure AD-Benutzern und -Gruppen.  

## <a name="step-5-assign-property-labels"></a>Schritt 5: Zuweisen von Eigenschaftsbezeichnungen
Sie können Ihren Quelleigenschaften auf der Seite "Eigenschaftenbezeichnungen zuweisen" semantische Bezeichnungen zuweisen. Bezeichnungen sind von Microsoft bereitgestellte bekannte Tags, die semantische Bedeutung bieten. Sie ermöglichen Es Microsoft, Ihre Connectordaten in Microsoft 365-Erfahrungen wie erweiterte Suche, Personenkarten, intelligente Ermittlung und vieles mehr zu integrieren.  

In der folgenden Tabelle sind die derzeit unterstützten Bezeichnungen und deren Beschreibungen aufgeführt.  

Label | Beschreibung
--- | ---  
**title** | Der Titel für das Element, das in der Suche und anderen Erfahrungen angezeigt werden soll 
**url** | Die Ziel-URL des Elements im Quellsystem 
**createdBy** | Name der Person, die das Element erstellt hat 
**lastModifiedBy** | Name der Person, die das Element zuletzt bearbeitet hat 
**authors** | Name der Personen, die an dem Element teilgenommen bzw. an dem Element zusammengearbeitet haben 
**createdDateTime** | Wann wurde das Element erstellt? 
**lastModifiedDateTime** | Wann wurde das Element zuletzt bearbeitet? 
**fileName** | Name des Dateielements 
**fileExtension** | Dateielementtyp, z. B. PDF oder WORD 

Die Eigenschaften auf dieser Seite werden basierend auf Ihrer Datenquelle vorab ausgewählt. Sie können diese Auswahl jedoch ändern, wenn eine andere Eigenschaft für eine bestimmte Bezeichnung besser geeignet ist.  

Der **Bezeichnungstitel** ist die wichtigste Bezeichnung. Es wird **dringend empfohlen,** dass Sie dieser Bezeichnung eine Eigenschaft zugewiesen haben, damit Ihre Verbindung an der Ergebnisclustererfahrung [teilnehmen kann.](result-cluster.md)

Falsche Zuordnungsbezeichnungen führen zu einer verschlechterten Sucherfahrung. Es ist in Ordnung, dass einigen Bezeichnungen keine Eigenschaft zugewiesen ist.  

## <a name="step-6-manage-schema"></a>Schritt 6: Verwalten des Schemas

### <a name="content-property"></a>Inhaltseigenschaft

Es wird dringend empfohlen, eine **Content-Eigenschaft" aus dem Dropdownmenü der Optionen auszuwählen oder die Standardeinstellung zu behalten, wenn eine vorhanden ist. Diese Eigenschaft wird für die Volltextindizierung von Inhalten, die Generierung von Codeausschnitten für [Suchergebnisse,](result-cluster.md) die Teilnahme am Ergebniscluster, spracherkennung, HTML/Text-Unterstützung, Rangfolge und Relevanz sowie Abfrageformulierung verwendet.

Wenn Sie eine Inhaltseigenschaft auswählen, können Sie beim Erstellen des Ergebnistyps die vom System generierte Eigenschaft **"ResultSnippet"** [verwenden.](customize-results-layout.md) Diese Eigenschaft dient als Platzhalter für die dynamischen Codeausschnitte, die zur Abfragezeit aus der Inhaltseigenschaft generiert werden. Wenn Sie diese Eigenschaft in Ihrem Ergebnistyp verwenden, werden Codeausschnitte in ihren Suchergebnissen generiert.

### <a name="creating-aliases-for-source-properties"></a>Erstellen von Aliasen für Quelleigenschaften

Sie können Ihren Eigenschaften unter der Spalte "Alias" auf der Seite "Schema verwalten" Aliase hinzufügen. Aliase sind Anzeigenamen für Ihre Eigenschaften. Sie werden in Abfragen und beim Erstellen von Filtern verwendet. Sie werden auch verwendet, um Quelleigenschaften aus mehreren Verbindungen so zu normalisieren, dass sie denselben Namen haben. Auf diese Weise können Sie einen einzelnen Filter für eine Vertikale mit mehreren Verbindungen erstellen. Weitere [Informationen finden Sie auf der Seite "Suchergebnisse anpassen".](customize-search-page.md)  

### <a name="search-schema-attributes"></a>Suchschemaattribute

Sie können die Suchschemaattribute festlegen, um die Suchfunktionalität jeder Quelleigenschaft zu steuern. Ein Suchschema hilft zu bestimmen, welche Ergebnisse auf der Suchergebnissetseite angezeigt werden und welche Informationen Endbenutzer anzeigen und darauf zugreifen können.

Zu den **Suchschemaattributen gehören durchsuchbare,** **abfragbare,** **abrufbare** und **einsetzbare Suchschemaattribute.** In der folgenden Tabelle sind die einzelnen Attribute aufgeführt, die von Microsoft Graph Connectors unterstützt werden, und ihre Funktionen werden erläutert.

Suchschemaattribut | Funktion | Beispiel
--- | --- | ---
DURCHSuchbar | Macht den Textinhalt einer Eigenschaft durchsuchbar. Eigenschafteninhalte sind im Volltextindex enthalten. | Wenn es sich bei der Eigenschaft um **einen** Titel handelt, gibt eine Abfrage für **Enterprise** Antworten zurück, die das Wort **"Enterprise"** in einem beliebigen Text oder Titel enthalten.
ABSABFRAGEBAR | Sucht nach der Abfrage nach einer Übereinstimmung für eine bestimmte Eigenschaft. Der Eigenschaftenname kann dann entweder programmgesteuert oder ausführlich in der Abfrage angegeben werden. |  Wenn die **Eigenschaft "Title"** absingbar ist, wird die Abfrage **"Title: Enterprise"** unterstützt. 
ABRUFBAR | Im Ergebnistyp können nur abrufbare Eigenschaften verwendet und im Suchergebnis angezeigt werden. |
EINFEINBAR | Einsetzbare Eigenschaften können wie auf der Microsoft Search-Ergebnisse-Seite verwendet werden. | Benutzer in Ihrer Organisation können [auf](custom-filters.md) der Suchergebnissetseite nach **"lastModifiedDateTime"** filtern, wenn die Eigenschaft während des Verbindungsaufbaus als einfeinbar gekennzeichnet ist.

Für alle Connectors mit Ausnahme des Dateifreigabeconnectors müssen benutzerdefinierte Typen manuell festgelegt werden. Zum Aktivieren der Suchfunktionen für jedes Feld benötigen Sie ein Suchschema, das einer Liste von Eigenschaften zugeordnet ist. Der Verbindungsassistent wählt automatisch ein Suchschema basierend auf dem ausgewählten Quelleigenschaftensatz aus. Sie können dieses Schema ändern, indem Sie die Kontrollkästchen für jede Eigenschaft und jedes Attribut auf der Suchschemaseite aktivieren.

![Das Schema für einen Connector kann durch Hinzufügen oder Entfernen von Abfrage-, Such- und Abruffunktionen angepasst werden.](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Einschränkungen und Empfehlungen für Suchschemaeinstellungen

* Die **Inhaltseigenschaft** ist nur durchsuchbar. Nachdem diese Eigenschaft in der Dropdownliste ausgewählt wurde, kann sie nicht als abrufbar **oder** **abfragbar markiert werden.**

* Erhebliche Leistungsprobleme treten auf, wenn Suchergebnisse mit der **Inhaltseigenschaft gerendert** werden. Ein Beispiel ist das **Textfeld "Text"** für einen Knowledge Base-Artikel von [ServiceNow.](https://www.servicenow.com)

* Nur Eigenschaften, die in den Suchergebnissen als abrufbar gekennzeichnet sind, können zum Erstellen moderner Ergebnistypen (MRTs) verwendet werden.

* Nur Zeichenfolgeneigenschaften können als durchsuchbar markiert werden.

> [!NOTE]
> Nachdem Sie eine Verbindung erstellt haben, **können Sie das** Schema nicht mehr ändern. Dazu müssen Sie Ihre Verbindung löschen und eine neue erstellen.

## <a name="step-7-refresh-settings"></a>Schritt 7: Aktualisieren von Einstellungen

Das Aktualisierungsintervall bestimmt, wie oft Ihre Daten zwischen der Datenquelle und Microsoft Search synchronisiert werden. Jeder Datenquellentyp verfügt über einen anderen Satz optimaler Aktualisierungszeitpläne, basierend auf der Anzahl der geänderten Daten und der Art der Änderungen.

Es gibt zwei Arten von Aktualisierungsintervallen, die **vollständige** Aktualisierung und inkrementelle Aktualisierung **sind,** aber inkrementelle Aktualisierungen sind für einige Datenquellen nicht verfügbar.

Bei einer vollständigen Aktualisierung verarbeitet und indiziert die Suchmaschine jedes Element in der Inhaltsquelle, unabhängig von vorherigen Durchforstungen. Eine vollständige Aktualisierung funktioniert am besten für die folgenden Situationen:

* Erkennen von Löschungen von Daten.
* Bei der inkrementellen Aktualisierung konnte der Inhalt aufgrund von Fehlern nicht aktualisiert werden.
* AcLs wurden geändert.
* Durchforstungsregeln wurden geändert.
* Wann das Schema für die Verbindung aktualisiert wurde (Schemaupdates werden noch nicht unterstützt)

Mit einer **inkrementellen Aktualisierung** kann das Suchmodul nur die Elemente verarbeiten und indizieren, die seit der letzten erfolgreichen Durchforstung erstellt oder geändert wurden. Daher werden nicht alle Daten in der Inhaltsquelle neu indiziert. Inkrementelle Aktualisierungen funktionieren am besten, um Inhalte, Metadaten, Berechtigungen und andere Updates zu erkennen.

Inkrementelle Aktualisierungen sind wesentlich schneller als vollständige Aktualisierungen, da unveränderte Elemente nicht verarbeitet werden. Wenn Sie jedoch inkrementelle Aktualisierungen ausführen, müssen Sie dennoch regelmäßig vollständige Aktualisierungen ausführen, um eine genaue Datensynchronisierung zwischen der Inhaltsquelle und dem Suchindex zu erhalten.

![Einstellungen für inkrementelle Durchforstungen und vollständige Durchforstungsintervalle mit inkrementeller Anzeige bei 15 Minuten und vollständige Durchforstung bei 1 Woche.](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Sie können die gesamte Konfiguration überprüfen und die Einstellungen nach Bedarf bearbeiten, bevor Sie die Verbindung herstellen. **Lesen Sie unbedingt die connectorspezifischen Informationen für Ihre Datenquelle, wenn Sie dies noch nicht getan haben.** Wählen **Sie "Aktualisierung fertig** stellen" aus, wenn Sie zum Abschließen der Verbindung bereit sind.

## <a name="how-do-i-know-the-connection-setup-worked"></a>Wo finde ich, dass die Verbindungseinrichtung funktioniert hat?

Wechseln Sie zur Liste Ihrer veröffentlichten Verbindungen unter der Registerkarte **"Connectors"** im [Admin Center.](https://admin.microsoft.com) Informationen zum Aktualisieren und Löschen finden Sie unter ["Verwalten des Connectors".](manage-connector.md)
