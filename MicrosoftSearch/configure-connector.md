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
ms.openlocfilehash: ce2515b3eaa859a8fbb00d83c4727865ab55e174
ms.sourcegitcommit: 6aea7102c94855e9f80711c0f3d7bf5833ce8fb5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464476"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="set-up-your-microsoft-built-connector-for-microsoft-search"></a>Einrichten Ihres von Microsoft erstellten Connectors für Microsoft Search

Dieser Artikel führt Sie durch die Schritte zum Konfigurieren eines von Microsoft erstellten Connectors. In diesem Artikel wird der Fluss der Einrichtung einer Verbindung im Microsoft 365 [Admin Center](https://admin.microsoft.com)erläutert. Weitere Informationen zum Einrichten spezieller von Microsoft erstellte Connectors finden Sie in den folgenden Artikeln:

* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [Azure SQL](MSSQL-connector.md)
* [Unternehmenswebsites](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [ServiceNow](servicenow-connector.md)

## <a name="set-up"></a>Einrichten

Führen Sie die folgenden Schritte aus, um einen der von Microsoft erstellten Connectors zu konfigurieren.

1. Wechseln Sie zur [Registerkarte Connectors](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) im [Microsoft 365 Admin Center](https://admin.microsoft.com).
2. Melden Sie sich mit den Anmeldeinformationen für Ihren [Microsoft 365](https://www.microsoft.com/microsoft-365) -Mandanten bei Ihrem Konto an.
3. Wählen Sie **Add a Connector**aus.
4. Wählen Sie in der Liste der verfügbaren Connectors den Connector Ihrer Wahl aus.

![Zu den verfügbaren Datenquellen gehören: Azure DevOps Connector, ServiceNow, ADLS Gen2, Enterprise-Websites, MediaWiki, Microsoft SQL Server und Azure SQL.](media/add_connector.png)

### <a name="name-the-connector"></a>Nennen Sie den Connector

Um eine Verbindung zu erstellen, geben Sie zunächst die folgenden Attribute an:

1. Name der Verbindung
2. Verbindungs-ID
3. Description (optional)

Die Verbindungs-ID erstellt implizite Eigenschaften für den Connector. Er darf nur alphanumerische Zeichen enthalten und darf maximal 32 Zeichen lang sein.

### <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle

Der Daten Verbindungsprozess variiert je nach Typ des Connectors. Weitere Informationen zum Herstellen einer Verbindung mit Ihrer lokalen Datenquelle finden Sie unter [Install an on-premises Data Gateway](https://aka.ms/configuregateway).

### <a name="select-source-properties"></a>Quelleigenschaften auswählen

Die Datenfelder, die von der Drittanbieter-Datenquelle als Quelleigenschaften festgelegt wurden, werden in Microsoft Search indiziert. Um diese Eigenschaften zu ändern, wählen Sie in der Seitenleiste rechts auf der Seite **Verbinder** die Option **Eigenschaften bearbeiten** aus. Sie können **bis zu 64 Quelleigenschaften**auswählen.

### <a name="manage-the-search-schema"></a>Verwalten des Suchschemas

#### <a name="content-property"></a>Content-Eigenschaft

Sie können auswählen, welche Source-Eigenschaft die **Content** -Eigenschaft (Volltextindex des Elements) ist, indem Sie eine beliebige Zeichenfolgeneigenschaft aus der Dropdownliste der **Inhalts** Eigenschaft auswählen. Alternativ können Sie die standardmäßig ausgewählte Eigenschaft beibehalten, wenn eine vorhanden ist.

Es ist besonders wichtig, dass die richtige Eigenschaft ausgewählt ist, da diese Eigenschaft für die Volltextindizierung von Inhalten, die Generierung von Codeausschnitt der Suchergebnisseite, die Spracherkennung, die Unterstützung von HTML/Text, die Rangfolge und Relevanz sowie die Abfrage Formulierung verwendet wird.

Wenn Sie eine Eigenschaft für **Inhalt**auswählen, haben Sie die Möglichkeit, beim [Erstellen des Ergebnistyps](customize-results-layout.md)die vom System generierte Eigenschaft **ResultSnippet** zu verwenden. Diese Eigenschaft dient als Platzhalter für die dynamischen Ausschnitte, die zur Abfragezeit aus der **Content** -Eigenschaft generiert werden. Wenn Sie diese Eigenschaft in Ihrem Ergebnistyp verwenden, werden Ausschnitte in ihren Suchergebnissen generiert.

#### <a name="search-schema-attributes"></a>Attribute für das Suchschema

Sie können die Suchschema Attribute so festlegen, dass die Suchfunktionen der einzelnen Quelleigenschaften gesteuert werden. Mithilfe eines Suchschemas können Sie bestimmen, welche Ergebnisse auf der Suchergebnisseite angezeigt werden und welche Informationen Endbenutzer anzeigen und darauf zugreifen können.

Suchschema Attribute umfassen **durchsuchbar**, **abgefragt**und **abrufbar**. In der folgenden Tabelle sind die Attribute aufgeführt, die von Microsoft Graph-Connectors unterstützt werden, und deren Funktionen erläutert.

Suchschema Attribut | Funktion | Beispiel
--- | --- | ---
Durchsuchbare | Legt den Textinhalt einer Eigenschaft durchsuchbar. Eigenschaften Inhalte sind im Volltextindex enthalten. | Wenn die Eigenschaft **Title**lautet, gibt eine Abfrage für **Enterprise** Antworten zurück, die das Wort **Enterprise** in einem beliebigen Text oder Titel enthalten.
QUERYABLE | Sucht nach einer Suchabfrage nach einer Übereinstimmung für eine bestimmte Eigenschaft. Der Eigenschaften Name kann dann entweder programmgesteuert oder wörtlich in der Abfrage angegeben werden. |  Wenn die **Title** -Eigenschaft abgefragt wird, wird der Abfrage **Titel: Enterprise** unterstützt.
Abrufbar | Nur Abruf bare Eigenschaften können im Ergebnistyp verwendet werden und im Suchergebnis angezeigt werden. |

Für alle Connectors müssen benutzerdefinierte Typen manuell festgelegt werden. Zum Aktivieren der Suchfunktionen für jedes Feld benötigen Sie ein Suchschema, das einer Liste von Eigenschaften zugeordnet ist. Der Verbindungs-Assistent wählt automatisch ein Suchschema basierend auf den von Ihnen ausgewählten Quelleigenschaften aus. Sie können dieses Schema ändern, indem Sie die Kontrollkästchen für jede Eigenschaft und jedes Attribut auf der Seite Suchschema aktivieren.

![Das Schema für einen Connector kann durch Hinzufügen oder Entfernen von Abfrage-, Such-und Abruffunktionen angepasst werden.](media/manageschema.png)

#### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Einschränkungen und Empfehlungen für Suchschema Einstellungen

* Die **Content** -Eigenschaft ist nur durchsuchbar. Wenn diese Eigenschaft im Dropdownmenü ausgewählt ist, kann Sie nicht als **abrufbar** oder **abgefragt**markiert werden. Es treten erhebliche Leistungsprobleme auf, wenn Suchergebnisse mit der **Content** -Eigenschaft gerendert werden. Ein Beispiel ist das **Text** Inhaltsfeld für einen [ServiceNow](https://www.servicenow.com) Knowledge Base-Artikel.

* Nur Eigenschaften, die als abrufbares Rendering in den Suchergebnissen markiert sind, können zum Erstellen moderner Ergebnistypen (MRT) verwendet werden.

* Nur Zeichenfolgeneigenschaften können durchsuchbar gekennzeichnet werden.


> [!Note]
> Nachdem Sie eine Verbindung erstellt haben, **können** Sie das Schema nicht ändern. Hierzu müssen Sie die Verbindung löschen und eine neue erstellen.

### <a name="manage-search-permissions"></a>Verwalten von Suchberechtigungen

Zugriffssteuerungslisten (Access Control Lists, ACLs) bestimmen, welche Benutzer in Ihrer Organisation auf die einzelnen Datenelemente zugreifen können. Alle Connectors unterstützen Suchberechtigungen, die für alle Benutzer sichtbar sind.

### <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans

Der Aktualisierungszeitplan legt fest, wie oft Ihre Daten mit dem Index in Microsoft Graph und Microsoft Search synchronisiert werden. Sie können die Aktualisierung auf zwei Arten planen: vollständige Durchforstung oder inkrementelle Durchforstung.

Bei einer **vollständigen Durchforstung**verarbeitet und indiziert die Suchmaschine jedes Element in der Inhaltsquelle, unabhängig von vorherigen Crawls. Die vollständige Durchforstung funktioniert am besten in diesen Situationen:

* Erkennen von Löschungen von Daten.
* Fehler beim Crawlen von Inhalten durch den inkrementellen Crawl.
* ACLs wurden geändert.
* Durchforstungsregeln wurden geändert.
* Ein Software Update für Microsoft Search ist erforderlich. Updates ändern das Suchschema.

Bei einer **inkrementellen Durchforstung**kann die Suchmaschine nur die Elemente verarbeiten und indizieren, die seit der letzten erfolgreichen Durchforstung erstellt oder geändert wurden. Daher werden nicht alle Daten in der Inhaltsquelle erneut indiziert. Inkrementelle Crawls funktionieren am besten, um Inhalte, Metadaten, Berechtigungen und andere Updates zu erkennen.

Inkrementelle Crawls sind wesentlich schneller als vollständige Durchforstungen, da unveränderte Elemente nicht verarbeitet werden. Um eine exakte Datensynchronisierung zwischen der Inhaltsquelle und dem Suchindex zu gewährleisten, müssen Sie beide Crawls regelmäßig durchführen.

Jeder Connector verfügt über einen anderen optimalen Satz von Aktualisierungs Zeitplänen, basierend auf der Häufigkeit, mit der Daten geändert werden, und den Typ der Änderungen.

![Inkrementelle Crawl-und vollständige Durchforstungs Intervalleinstellungen, die bei einer Dauer von 15 Minuten und einer vollständigen Durchforstung von 1 Woche angezeigt](media/refreshschedule.png)

### <a name="review-connector-settings"></a>Überprüfen der Verbindungseinstellungen

Nachdem Sie den Connector konfiguriert haben, führt Sie das [Admin Center](https://admin.microsoft.com) zu einer Seite, auf der Sie die Einstellungen überprüfen können. Sie können den Konfigurationsprozess wiederholen, um eine beliebige Einstellung zu bearbeiten, bevor Sie die Verbindung bestätigen. Weitere Informationen finden Sie unter [Manage Your Connector](manage-connector.md).

## <a name="next-steps-customize-the-search-results-page"></a>Nächste Schritte: Anpassen der Suchergebnisseite

Mit der Microsoft Search-Benutzeroberfläche können Ihre Endbenutzer Inhalte aus Ihren [Microsoft 365](https://www.microsoft.com/microsoft-365) -Produktivitäts-apps und dem breiteren Microsoft-Ökosystem durchsuchen. Die vertikale Suche bezieht sich auf die Registerkarten, die angezeigt werden, wenn ein Benutzer in [Bing](https://Bing.com)die Suchergebnisse in [SharePoint](https://sharepoint.com/), [Microsoft Office](https://Office.com)und Microsoft-Suche anzeigt. Sie können die Such vertikalen so anpassen, dass die Ergebnisse eingegrenzt werden, sodass nur ein bestimmter Typ von Suchergebnissen angezeigt wird. Diese vertikalen Werte werden als Registerkarte oben auf der Suchergebnisseite angezeigt. Ein moderner Ergebnistyp (MRT) ist die Benutzeroberfläche, die festlegt, wie Ergebnisse dargestellt werden.

Erstellen Sie Ihre eigenen vertikalen und Ergebnistypen, sodass Endbenutzer Suchergebnisse aus neuen Verbindungen anzeigen können. Ohne diesen Schritt werden Daten aus ihrer Verbindung nicht auf der Suchergebnisseite angezeigt.

Weitere Informationen zum Erstellen von vertikalen und MRT finden Sie unter [Anpassen der Suchergebnisseite](customize-search-page.md).

## <a name="how-do-i-know-the-connection-setup-worked"></a>Woher weiß ich, dass das Verbindungssetup funktioniert hat?

Wechseln Sie zur Liste der veröffentlichten Verbindungen auf der Registerkarte **Connectors** im [Admin Center](https://admin.microsoft.com). Informationen zum Erstellen von Updates und Löschungen finden Sie unter [Manage Your Connector](manage-connector.md).
