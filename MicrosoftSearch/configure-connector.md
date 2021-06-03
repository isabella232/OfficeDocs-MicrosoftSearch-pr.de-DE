---
title: Konfigurieren Des von Microsoft Graph Connector für Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Setupübersicht für Graph Connectors von Microsoft
ms.openlocfilehash: ef94d530af63d8b8b33dfae3c4b411164ef31feb
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720943"
---
<!-- Previous ms.author: monaray -->

<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Setupübersicht für Graph Connectors von Microsoft 

Dieser Artikel zeigt den grundlegenden Prozess, der zum Einrichten der Graph Connectors von **Microsoft** im [Microsoft 365 Admin Center erforderlich ist.](https://admin.microsoft.com) Der einfache Prozess umfasst die folgenden Schritte:  
<!---Add links to each section in the doc--->

1. [Hinzufügen eines Graph im Microsoft 365 Admin Center](#step-1-add-a-graph-connector-in-the-microsoft-365-admin-center)
2. [Benennen der Verbindung](#step-2-name-the-connection)
3. [Konfigurieren der Verbindungseinstellungen](#step-3-configure-the-connection-settings)
4. [Verwalten von Suchberechtigungen](#step-4-manage-search-permissions)
5. [Zuweisen von Eigenschaftsbezeichnungen](#step-5-assign-property-labels)
6. [Schema verwalten](#step-6-manage-schema)
7. [Aktualisieren von Einstellungen](#step-7-refresh-settings)
8. [Überprüfen der Verbindung](#step-8-review-connection)

Dieser Artikel enthält außerdem Informationen zur Problembehandlung, Einschränkungen und den nächsten Schritten:

* [Problembehandlung](#troubleshooting)
* [Einschränkungen](#limitations)
* [Nächste Schritte](#next-steps)

> [!NOTE]
> Der Einrichtungsprozess ist für alle Graph von Microsoft ähnlich, ist aber nicht identisch. **Lesen Sie nicht nur diesen Artikel, sondern lesen Sie auch die connectorspezifischen Informationen für Ihre Datenquelle.**  

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph im Microsoft 365 Admin Center

Führen Sie die folgenden Schritte aus, um einen der von Microsoft erstellten Graph zu konfigurieren:

1. Melden Sie sich bei Ihrem Administratorkonto im [Microsoft 365 Admin Center an.](https://admin.microsoft.com)

2. Wählen Sie im Navigationsbereich **Einstellungen** aus, und wählen Sie dann **Suchen & Aus.** Wählen Sie die [Registerkarte Connectors aus.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)

3. Wählen **Sie +Hinzufügen** aus, und wählen Sie dann im Menü der verfügbaren Optionen die Datenquelle Ihrer Wahl aus.

   > [!div class="mx-imgBorder"]
   > ![Verfügbare Datenquellen sind: ADLS Gen2, Enterprise-Websites, Microsoft SQL-Server, Azure SQL, Oracle SQL-Datenbank, ServiceNow, Dateifreigabe, Azure DevOps und MediaWiki.](media/add-connector.png)

> [!NOTE]
> Sie können maximal zehn Graph Mandanten hinzufügen.

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung

Geben Sie die folgenden Attribute an:

* Name (erforderlich)
* Verbindungs-ID (erforderlich)
* Beschreibung (optional)

Die Verbindungs-ID erstellt implizite Eigenschaften für Den Connector. Sie darf nur alphanumerische Zeichen enthalten und darf maximal 32 Zeichen umfassen.

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Der Vorgang zum Konfigurieren der Verbindungseinstellungen variiert je nach Datenquellentyp. Informationen zum Typ der Datenquelle, die Sie Ihrem Mandanten hinzufügen möchten, finden Sie in den connectorspezifischen Informationen, um diesen Schritt im Setupvorgang abzuschließen.  

Weitere Informationen zum Herstellen einer Verbindung mit einer lokalen Datenquelle finden Sie unter [Install an on-premises data gateway](/data-integration/gateway/service-gateway-install).

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen

Zugriffssteuerungslisten (Access Control Lists, ACLs) bestimmen, welche Benutzer in Ihrer Organisation auf jedes Datenelement zugreifen können.  

Einige Connectors wie [Microsoft SQL](MSSQL-connector.md) und Azure Data Lake [Storage Gen2](azure-data-lake-connector.md) unterstützen systemeigene [Azure Active Directory (Azure AD)-ACLs.](/azure/active-directory/)

Andere Connectors wie [ServiceNow,](servicenow-connector.md) [Azure DevOps](azure-devops-connector.md)und [Salesforce](salesforce-connector.md) unterstützen die Synchronisierung von Nicht-Azure AD-Benutzern und -Gruppen.  

## <a name="step-5-assign-property-labels"></a>Schritt 5: Zuweisen von Eigenschaftsbezeichnungen

Sie können Ihren Quelleigenschaften auf der Seite "Eigenschaftsbezeichnungen zuweisen" semantische Bezeichnungen zuweisen. Bezeichnungen sind bekannte Von Microsoft bereitgestellte Tags, die semantische Bedeutung bieten. Sie ermöglichen Es Microsoft, Ihre Connectordaten in Microsoft 365 wie erweiterte Suche, Personenkarten, intelligente Erkennung und vieles mehr zu integrieren.  

In der folgenden Tabelle sind die derzeit unterstützten Bezeichnungen und deren Beschreibungen aufgeführt.  

Bezeichnung | Beschreibung
--- | ---  
**title** | Der Titel für das Element, das in der Suche und anderen Erfahrungen angezeigt werden soll
**url** | Die Ziel-URL des Elements im Quellsystem
**createdBy** | Name der Person, die das Element erstellt hat
**lastModifiedBy** | Name der Person, die das Element zuletzt bearbeitet hat
**authors** | Name der Personen, die an dem Element teilgenommen/mitgearbeitet haben
**createdDateTime** | Wann wurde das Element erstellt?
**lastModifiedDateTime** | Wann wurde das Element zuletzt bearbeitet?
**fileName** | Name des Dateielements
**fileExtension** | Dateielementtyp, z. B. .pdf oder .word

Die Eigenschaften auf dieser Seite sind basierend auf Ihrer Datenquelle vorab ausgewählt. Sie können diese Auswahl jedoch ändern, wenn eine andere Eigenschaft verfügbar ist, die für eine bestimmte Bezeichnung besser geeignet ist.  

Der **Bezeichnungstitel** ist die wichtigste Bezeichnung. Es wird dringend **empfohlen,** dieser Bezeichnung eine Eigenschaft zugewiesen zu haben, damit Ihre Verbindung an der [Ergebnisclustererfahrung teilnehmen kann.](result-cluster.md)

Falsch zugeordnete Bezeichnungen führen zu einer schlechteren Suchfunktion. Es ist in Ordnung, dass einigen Bezeichnungen keine Eigenschaft zugewiesen ist.  

## <a name="step-6-manage-schema"></a>Schritt 6: Verwalten des Schemas

### <a name="content-property"></a>Content-Eigenschaft

Es wird empfohlen, eine **Content-Eigenschaft** aus dem Dropdownmenü der Optionen auszuwählen oder die Standardeinstellung zu behalten, wenn eine vorhanden ist. Diese Eigenschaft wird für die Volltextindizierung von Inhalten, die Generierung von Suchergebnissen für Seitenausschnitte, [](result-cluster.md) die Teilnahme am Ergebniscluster, die Spracherkennung, html/text-Unterstützung, Rangfolge und Relevanz und Abfrageformulierung verwendet.

Wenn Sie eine Inhaltseigenschaft auswählen, haben Sie die Möglichkeit, die vom System generierte Eigenschaft **ResultSnippet** zu verwenden, wenn Sie den [Ergebnistyp erstellen.](customize-results-layout.md) Diese Eigenschaft dient als Platzhalter für die dynamischen Codeausschnitte, die zur Abfragezeit von der Inhaltseigenschaft generiert werden. Wenn Sie diese Eigenschaft in Ihrem Ergebnistyp verwenden, werden Codeausschnitte in den Suchergebnissen generiert.

### <a name="creating-aliases-for-source-properties"></a>Erstellen von Aliasen für Quelleigenschaften

Sie können Ihren Eigenschaften unter der Spalte "Alias" auf der Seite "Schema verwalten" Aliase hinzufügen. Aliase sind Anzeigenamen für Ihre Eigenschaften und werden auch in Abfragen und beim Erstellen von Filtern verwendet. Sie werden auch verwendet, um Quelleigenschaften aus mehreren Verbindungen so zu normalisieren, dass sie denselben Namen haben. Auf diese Weise können Sie einen einzelnen Filter für eine Vertikale mit mehreren Verbindungen erstellen. Weitere Informationen finden Sie unter [Customize the search results page](customize-search-page.md).  

### <a name="search-schema-attributes"></a>Suchschemaattribute

Sie können die Suchschemaattribute festlegen, um die Suchfunktionalität jeder Quelleigenschaft zu steuern. Ein Suchschema hilft zu bestimmen, welche Ergebnisse auf der Suchergebnissetseite angezeigt werden und welche Informationen Endbenutzer anzeigen und darauf zugreifen können.

Suchschemaattribute umfassen Optionen für **Query,** **Search,** **Retrieve** und **Refine**. In der folgenden Tabelle sind die attribute aufgeführt, die von Microsoft Graph unterstützt werden, und ihre Funktionen werden erläutert.

Suchschemaattribut | Funktion | Beispiel
--- | --- | ---
SEARCH | Macht den Textinhalt einer Eigenschaft durchsuchbar. Eigenschafteninhalte sind im Volltextindex enthalten. | Wenn die Eigenschaft **title** ist, gibt eine Abfrage für **Enterprise** Antworten zurück, die das Wort **Enterprise** Text oder Titel enthalten.
QUERY | Sucht nach Abfrage nach einer Übereinstimmung für eine bestimmte Eigenschaft. Der Eigenschaftsname kann dann entweder programmgesteuert oder ausführlich in der Abfrage angegeben werden. |  Wenn die **Title-Eigenschaft** abgefragt werden kann, wird die Abfrage **Title: Enterprise** unterstützt.
ABRUFEN | Nur abgerufene Eigenschaften können im Ergebnistyp verwendet und im Suchergebnis angezeigt werden. |
EINSCHRÄNKUNG | Die Einschränkungsoption kann wie auf der Microsoft Search-Ergebnisseite verwendet werden. | Benutzer in Ihrer Organisation können [auf](custom-filters.md) der Suchergebnissetseite nach **URL** filtern, wenn die Einschränkungseigenschaft während der Verbindungseinrichtung markiert ist

Für alle Connectors mit Ausnahme des Dateifreigabeconnectors müssen benutzerdefinierte Typen manuell festgelegt werden. Zum Aktivieren der Suchfunktionen für jedes Feld benötigen Sie ein Suchschema, das einer Liste von Eigenschaften zugeordnet ist. Der Verbindungs-Assistent wählt automatisch ein Suchschema basierend auf den ausgewählten Quelleigenschaften aus. Sie können dieses Schema ändern, indem Sie die Kontrollkästchen für jede Eigenschaft und jedes Attribut auf der Suchschemaseite aktivieren.

> [!div class="mx-imgBorder"]
> ![Schema für einen Connector kann durch Hinzufügen oder Entfernen von Abfrage-, Such- und Retrieve-Funktionen angepasst werden.](media/manageschema.png)

### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Einschränkungen und Empfehlungen für Suchschemaeinstellungen

* Die **Content-Eigenschaft** ist nur durchsuchbar. Sobald diese Eigenschaft im Dropdown ausgewählt wurde, kann sie nicht mit den Optionen **abrufen oder** **abfragen verwendet werden.**

* Erhebliche Leistungsprobleme treten auf, wenn Suchergebnisse mit der **Inhaltseigenschaft gerendert** werden. Ein Beispiel ist das **Feld Textinhalt** für einen ServiceNow-Knowledge-Base-Artikel. [](https://www.servicenow.com)

* Nur Eigenschaften, die in den Suchergebnissen als abrufbares Rendern markiert sind, können zum Erstellen moderner Ergebnistypen (MRTs) verwendet werden.

* Nur Zeichenfolgeneigenschaften können als durchsuchbar markiert werden.

> [!NOTE]
> Nachdem Sie eine Verbindung erstellt haben, **können Sie das Schema** nicht mehr ändern. Dazu müssen Sie Ihre Verbindung löschen und eine neue erstellen.

## <a name="step-7-refresh-settings"></a>Schritt 7: Aktualisieren von Einstellungen

Das Aktualisierungsintervall bestimmt, wie oft Ihre Daten zwischen der Datenquelle und Microsoft Search synchronisiert werden. Jede Art von Datenquelle verfügt über einen anderen Satz optimaler Aktualisierungszeitpläne, die auf der Anzahl der Änderungen und der Art der Änderungen basieren.

Es gibt zwei Arten von  Aktualisierungsintervallen, die vollständige Aktualisierung und inkrementelle Aktualisierung **sind,** aber inkrementelle Aktualisierungen sind für einige Datenquellen nicht verfügbar.

Bei einer vollständigen Aktualisierung verarbeitet und indiziert die Suchmaschine die Elemente, die sich in der Inhaltsquelle geändert haben, unabhängig von vorherigen Durchforstungen. Eine vollständige Aktualisierung funktioniert am besten für die folgenden Situationen:

* Erkennen von Löschvorgängen von Daten.
* Bei der inkrementellen Aktualisierung wurden Fehler gefunden, und es ist ein Fehler aufgetreten.
* AcLs wurden geändert.
* Durchforstungsregeln wurden geändert.
* Das Schema für die Verbindung wurde aktualisiert (Schemaupdates werden noch nicht unterstützt).

Mit einer **inkrementellen Aktualisierung** kann die Suchmaschine nur die Elemente verarbeiten und indizieren, die seit der letzten erfolgreichen Durchforstung erstellt oder geändert wurden. Aus diesem Grund werden nicht alle Daten in der Inhaltsquelle neu indiziert. Inkrementelle Aktualisierungen funktionieren am besten, um Inhalte, Metadaten, Berechtigungen und andere Updates zu erkennen.

Inkrementelle Aktualisierungen sind viel schneller als vollständige Aktualisierungen, da unveränderte Elemente nicht verarbeitet werden. Wenn Sie jedoch inkrementelle Aktualisierungen ausführen möchten, müssen Sie weiterhin regelmäßig vollständige Aktualisierungen ausführen, um die ordnungsgemäße Datensynchronisierung zwischen der Inhaltsquelle und dem Suchindex aufrecht zu erhalten.

> [!div class="mx-imgBorder"]
> ![Einstellungen für inkrementelle Durchforstung und vollständiges Durchforstungsintervall mit inkrementellem Crawl bei 15 Minuten und Vollständige Durchforstung bei 1 Woche.](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Sie können die gesamte Konfiguration überprüfen und die Einstellungen nach Bedarf bearbeiten, bevor Sie die Verbindung abschließen. **Achten Sie darauf, die connectorspezifischen Informationen für Ihre Datenquelle zu lesen, wenn Sie dies noch nicht getan haben.** Wählen **Sie Aktualisieren fertig** stellen aus, wenn Sie zum Abschließen der Verbindung bereit sind.

### <a name="confirm-if-the-connection-setup-worked"></a>Bestätigen, ob die Verbindungseinrichtung funktioniert hat

Wechseln Sie zur Liste der veröffentlichten Verbindungen unter der Registerkarte **Connectors** im [Admin Center](https://admin.microsoft.com). Informationen zum Erstellen von Aktualisierungen und Löschungen finden Sie unter [Manage your connector](manage-connector.md).

## <a name="troubleshooting"></a>Problembehandlung
<!---Insert troubleshooting recommendations for this data source-->
Lesen Sie die connectorspezifischen Informationen für Ihre Datenquelle. 

> [!NOTE]
> Nicht alle connectorspezifischen Artikel enthalten derzeit Empfehlungen zur Problembehandlung.

## <a name="limitations"></a>Einschränkungen
<!---Insert limitations for this data source-->
Informationen zu Einschränkungen, die für alle Datenquellen gelten, finden Sie im [Artikel Übersicht über Microsoft Graph Connectors.](connectors-overview.md)

Sehen Sie sich die connectorspezifischen Informationen für Ihre Datenquelle an, um herauszufinden, ob andere Einschränkungen für diesen bestimmten Graph gelten.

## <a name="next-steps"></a>Nächste Schritte

Nach der Veröffentlichung der Verbindung müssen Sie die Suchergebnissetseite anpassen. Weitere Informationen zum Anpassen von Suchergebnissen finden Sie unter [Customize the search results page](customize-search-page.md).