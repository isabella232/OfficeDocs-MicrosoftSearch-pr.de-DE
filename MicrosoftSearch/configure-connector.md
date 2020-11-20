---
title: Konfigurieren Ihres von Microsoft erstellten Connectors für Microsoft Search
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
description: Konfigurieren Ihres von Microsoft erstellten Connectors für Microsoft Search
ms.openlocfilehash: 86ddf0387e3d00a005f25207a322c8470799b76b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367608"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Setup-Übersicht für Graph-Konnektoren von Microsoft 

In diesem Artikel wird der grundlegende Prozess zusammengefasst, der erforderlich ist, um die Graph-Konnektoren von Microsoft mit dem [Microsoft 365 Admin Center](https://admin.microsoft.com) einzurichten. Der grundlegende Prozess umfasst die folgenden Schritte:  
<!---Add links to each section in the doc--->

1. Fügen Sie einen Graph-Konnektor im Microsoft 365 Admin Center hinzu.
2. Nennen Sie die Verbindung.
3. Konfigurieren Sie die Verbindungseinstellungen.
4. Verwalten von Suchberechtigungen.
5. Zuweisen von Eigenschaften Bezeichnungen.
6. Verwalten des Schemas.
7. Wählen Sie Aktualisierungseinstellungen aus.
8. Überprüfen Sie die Verbindung.

Beachten Sie, dass der Installationsvorgang für alle Graph-Konnektoren von Microsoft sehr ähnlich ist, jedoch nicht exakt identisch ist. **Lesen Sie zusätzlich zum Lesen dieses Artikels unbedingt den Connector-Specific für Ihre Datenquelle.**  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Schritt 1: Hinzufügen eines Graph-Konnektors im Microsoft 365 Admin Center

Führen Sie die folgenden Schritte aus, um einen der von Microsoft erstellten Connectors zu konfigurieren.

1. Melden Sie sich bei Ihrem Administratorkonto im [Microsoft 365 Admin Center](https://admin.microsoft.com) an.
2. Wählen Sie im Navigationsbereich die Option **Einstellungen** aus, und wählen Sie dann **Such & Intelligence** aus. Wählen Sie die [Registerkarte Connectors](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)aus.
3.  Wählen Sie **+ Hinzufügen** aus, und wählen Sie dann im Menü der verfügbaren Optionen die gewünschte Datenquelle aus.

![Zu den verfügbaren Datenquellen gehören: ADLS Gen2, Enterprise-Websites, Microsoft SQL Server, Azure SQL, Oracle SQL Database, ServiceNow, Dateifreigabe, Azure DevOps und MediaWiki.](media/add-connector.png)

>[! Hinweis:] Sie können jedem Mandanten maximal zehn Graph-Verbindungen hinzufügen.

## <a name="step-2-name-the-connection"></a>Schritt 2: Benennen der Verbindung
Diese Attribute müssen angegeben werden: 

* Name  
* Verbindungs-ID 
* Description (optional) 

Die Verbindungs-ID erstellt implizite Eigenschaften für den Connector. Er darf nur alphanumerische Zeichen enthalten und darf maximal 32 Zeichen lang sein. 

## <a name="step-3-configure-the-connection-settings"></a>Schritt 3: Konfigurieren der Verbindungseinstellungen

Der Prozess zum Konfigurieren der Verbindungseinstellungen variiert je nach Typ der Datenquelle. Lesen Sie die Connector-spezifischen Informationen für den Typ der Datenquelle, den Sie Ihrem Mandanten hinzufügen möchten, um diesen Schritt im Setupvorgang abzuschließen.  

Weitere Informationen zum Herstellen einer Verbindung mit einer lokalen Datenquelle finden Sie unter [Install an on-premises Data Gateway](https://aka.ms/configuregateway).

## <a name="step-4-manage-search-permissions"></a>Schritt 4: Verwalten von Suchberechtigungen

Zugriffssteuerungslisten (Access Control Lists, ACLs) bestimmen, welche Benutzer in Ihrer Organisation auf die einzelnen Datenelemente zugreifen können.  

Einige Connectors wie [Microsoft SQL](MSSQL-connector.md) -und [Azure Data Lake-Speicher Gen2](azure-data-lake-connector.md) unterstützen systemeigene [Azure Active Directory (Azure AD)-](https://docs.microsoft.com/azure/active-directory/) ACLs.

Andere Connectors wie [ServiceNow](servicenow-connector.md), [Azure DevOps](azure-devops-connector.md)und [Salesforce](salesforce-connector.md) unterstützen das synchronisieren nicht Azure Ader Benutzer und Gruppen.  

## <a name="step-5-assign-property-labels"></a>Schritt 5: Zuweisen von Eigenschaften Bezeichnungen
Sie können semantische Bezeichnungen ihren Quelleigenschaften auf der Seite "Eigenschaften Bezeichnungen zuweisen" zuweisen. Bezeichnungen sind bekannte von Microsoft bereitgestellte Tags, die eine semantische Bedeutung bieten. Sie ermöglichen es Microsoft, ihre connectordaten in Microsoft 365-Benutzeroberflächen zu integrieren, beispielsweise Erweiterte Suche, Personen Karten, intelligente Erkennung und vieles mehr.  

In der folgenden Tabelle sind die aktuell unterstützten Bezeichnungen und deren Beschreibungen aufgeführt.  

Bezeichnung | Beschreibung
--- | ---  
**title** | Der Titel für das Element, das in Such-und anderen Erfahrungen angezeigt werden soll 
**url** | Die Ziel-URL des Elements im Quellsystem 
**createdBy** | Name der Person, die das Element erstellt hat 
**lastModifiedBy** | Name der Person, die das Element zuletzt bearbeitet hat 
**authors** | Name der Personen, die an dem Element teilgenommen/zusammengearbeitet haben 
**createdDateTime** | Wann wurde das Element erstellt? 
**lastModifiedDateTime** | Wann wurde das Element zuletzt bearbeitet 
**fileName** | Name des Dateielements 
**fileExtension** | Typ des Dateielements wie. PDF oder. Word 

Die Eigenschaften auf dieser Seite sind basierend auf Ihrer Datenquelle vorab ausgewählt, aber Sie können diese Auswahl ändern, wenn es eine andere Eigenschaft gibt, die für eine bestimmte Bezeichnung besser geeignet ist.  

Der Beschriftungs **Titel** ist die wichtigste Bezeichnung. Es wird **dringend empfohlen** , dass Sie über eine Eigenschaft verfügen, die dieser Bezeichnung zugewiesen ist, damit Ihre Verbindung an der [Ergebnis Cluster Erfahrung](result-cluster.md)teilnehmen kann.

Falsch Zuordnungs Bezeichnungen führen zu einer Verschlechterung der Suchumgebung. Für einige Bezeichnungen ist es in Ordnung, dass keine Eigenschaft zugewiesen ist.  

## <a name="step-6-manage-schema"></a>Schritt 6: Verwalten des Schemas

### <a name="content-property"></a>Content-Eigenschaft

Es wird dringend empfohlen, dass Sie im Dropdownmenü von Optionen eine * *-Inhaltseigenschaft auswählen oder den Standardwert beibehalten, wenn einer vorhanden ist. Diese Eigenschaft wird für die Volltextindizierung von Inhalten, die Generierung von Seitenausschnitt des Suchergebnisses, die Teilnahme an [Ergebnis Clustern](result-cluster.md) , die Spracherkennung, die Unterstützung von HTML/Text, die Rangfolge und Relevanz sowie die Abfrage Formulierung verwendet.

Wenn Sie eine Inhaltseigenschaft auswählen, haben Sie die Möglichkeit, beim [Erstellen des Ergebnistyps](customize-results-layout.md)die vom System generierte Eigenschaft **ResultSnippet** zu verwenden. Diese Eigenschaft dient als Platzhalter für die dynamischen Ausschnitte, die zur Abfragezeit aus der Content-Eigenschaft generiert werden. Wenn Sie diese Eigenschaft in Ihrem Ergebnistyp verwenden, werden Ausschnitte in ihren Suchergebnissen generiert.

### <a name="creating-aliases-for-source-properties"></a>Erstellen von Aliasen für Quelleigenschaften

Sie können Aliase zu ihren Eigenschaften in der Spalte "Alias" auf der Seite "Schema verwalten" hinzufügen. Aliase sind benutzerfreundliche Namen für ihre Eigenschaften. Sie werden in Abfragen und beim Erstellen von Filtern verwendet. Sie werden auch verwendet, um Quelleigenschaften von mehreren Verbindungen so zu normalisieren, dass Sie denselben Namen haben. Auf diese Weise können Sie einen einzelnen Filter für eine vertikale mit mehreren Verbindungen erstellen. Weitere Informationen finden Sie unter [Anpassen der Suchergebnisseite](customize-search-page.md) .  

### <a name="search-schema-attributes"></a>Attribute für das Suchschema

Sie können die Suchschema Attribute so festlegen, dass die Suchfunktionen der einzelnen Quelleigenschaften gesteuert werden. Mithilfe eines Suchschemas können Sie bestimmen, welche Ergebnisse auf der Suchergebnisseite angezeigt werden und welche Informationen Endbenutzer anzeigen und darauf zugreifen können.

Suchschema Attribute sind **durchsuchbar** **, abfragbar,** **abrufbar** und **verfeinernd**. In der folgenden Tabelle sind die Attribute aufgeführt, die von Microsoft Graph-Connectors unterstützt werden, und deren Funktionen erläutert.

Suchschema Attribut | Funktion | Beispiel
--- | --- | ---
Durchsuchbare | Legt den Textinhalt einer Eigenschaft durchsuchbar. Eigenschaften Inhalte sind im Volltextindex enthalten. | Wenn die Eigenschaft **Title** lautet, gibt eine Abfrage für **Enterprise** Antworten zurück, die das Wort **Enterprise** in einem beliebigen Text oder Titel enthalten.
QUERYABLE | Sucht nach einer Suchabfrage nach einer Übereinstimmung für eine bestimmte Eigenschaft. Der Eigenschaften Name kann dann entweder programmgesteuert oder wörtlich in der Abfrage angegeben werden. |  Wenn die **Title** -Eigenschaft abgefragt wird, wird der Abfrage **Titel: Enterprise** unterstützt. 
Abrufbar | Nur Abruf bare Eigenschaften können im Ergebnistyp verwendet werden und im Suchergebnis angezeigt werden. |
Einschränkbaren | Raffinations Eigenschaften können wie auf der Seite Microsoft-Suchergebnisse verwendet werden. | Benutzer in Ihrer Organisation können auf der Suchergebnisseite nach **lastModifiedDateTime** [Filtern](custom-filters.md) , wenn die Eigenschaft beim Einrichten der Verbindung als "verfeinern" gekennzeichnet ist.

Für alle Connectors mit Ausnahme des Dateifreigabe-Konnektors müssen benutzerdefinierte Typen manuell festgelegt werden. Zum Aktivieren der Suchfunktionen für jedes Feld benötigen Sie ein Suchschema, das einer Liste von Eigenschaften zugeordnet ist. Der Verbindungs-Assistent wählt automatisch ein Suchschema basierend auf den von Ihnen ausgewählten Quelleigenschaften aus. Sie können dieses Schema ändern, indem Sie die Kontrollkästchen für jede Eigenschaft und jedes Attribut auf der Seite Suchschema aktivieren.

![Das Schema für einen Connector kann durch Hinzufügen oder Entfernen von Abfrage-, Such-und Abruffunktionen angepasst werden.](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Einschränkungen und Empfehlungen für Suchschema Einstellungen

* Die **Content** -Eigenschaft ist nur durchsuchbar. Wenn diese Eigenschaft im Dropdownmenü ausgewählt ist, kann Sie nicht als **abrufbar** oder **abgefragt** markiert werden.

* Es treten erhebliche Leistungsprobleme auf, wenn Suchergebnisse mit der **Content** -Eigenschaft gerendert werden. Ein Beispiel ist das **Text** Inhaltsfeld für einen [ServiceNow](https://www.servicenow.com) Knowledge Base-Artikel.

* Nur Eigenschaften, die als abrufbares Rendering in den Suchergebnissen markiert sind, können zum Erstellen moderner Ergebnistypen (MRT) verwendet werden.

* Nur Zeichenfolgeneigenschaften können durchsuchbar gekennzeichnet werden.

> [!NOTE]
> Nachdem Sie eine Verbindung erstellt haben, **können** Sie das Schema nicht ändern. Hierzu müssen Sie die Verbindung löschen und eine neue erstellen.

## <a name="step-7-refresh-settings"></a>Schritt 7: Aktualisieren von Einstellungen

Das Aktualisierungsintervall legt fest, wie oft Ihre Daten zwischen der Datenquelle und der Microsoft-Suche synchronisiert werden. Jeder Datenquellentyp hat einen anderen Satz optimaler Aktualisierungs Zeitpläne, basierend auf der Häufigkeit, mit der Daten geändert werden, und den Typ der Änderungen.

Es gibt zwei Arten von Aktualisierungsintervallen, die **vollständig aktualisiert** und **inkrementell aktualisiert** werden, aber inkrementelle Aktualisierungen sind für einige Datenquellen nicht verfügbar.

Bei einer vollständigen Aktualisierung verarbeitet und indiziert die Suchmaschine jedes Element in der Inhaltsquelle, unabhängig von vorherigen Crawls. Eine vollständige Aktualisierung eignet sich am besten für diese Situationen:

* Erkennen von Löschungen von Daten.
* Die inkrementelle Aktualisierung konnte den Inhalt aufgrund von Fehlern nicht aktualisieren.
* ACLs wurden geändert.
* Durchforstungsregeln wurden geändert.
* Wenn das Schema für die Verbindung aktualisiert wurde (Schema Updates werden noch nicht unterstützt)

Bei einer **inkrementellen Aktualisierung** kann die Suchmaschine nur die Elemente verarbeiten und indizieren, die seit der letzten erfolgreichen Durchforstung erstellt oder geändert wurden. Daher werden nicht alle Daten in der Inhaltsquelle erneut indiziert. Inkrementelle Aktualisierungen funktionieren am besten, um Inhalte, Metadaten, Berechtigungen und andere Updates zu erkennen.

Inkrementelle Aktualisierungen sind wesentlich schneller als vollständige Aktualisierungen, da unveränderte Elemente nicht verarbeitet werden. Wenn Sie jedoch inkrementelle Aktualisierungen ausführen möchten, müssen Sie dennoch regelmäßig vollständige Aktualisierungen ausführen, um eine exakte Datensynchronisierung zwischen der Inhaltsquelle und dem Suchindex beizubehalten.

![Inkrementelle Crawl-und vollständige Durchforstungs Intervalleinstellungen, die bei einer Dauer von 15 Minuten und einer vollständigen Durchforstung von 1 Woche angezeigt](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>Schritt 8: Überprüfen der Verbindung

Sie können die gesamten Konfigurations-und Bearbeitungseinstellungen nach Bedarf überprüfen, bevor Sie die Verbindung abschließen. **Lesen Sie unbedingt die Connector-spezifischen Informationen für Ihre Datenquelle, falls dies noch nicht geschehen ist.** Wählen Sie **Aktualisierung fertig stellen** aus, wenn Sie zum Abschließen der Verbindung fertig sind.

## <a name="how-do-i-know-the-connection-setup-worked"></a>Woher weiß ich, dass das Verbindungssetup funktioniert hat?

Wechseln Sie zur Liste der veröffentlichten Verbindungen auf der Registerkarte **Connectors** im [Admin Center](https://admin.microsoft.com). Informationen zum Erstellen von Updates und Löschungen finden Sie unter [Manage Your Connector](manage-connector.md).
