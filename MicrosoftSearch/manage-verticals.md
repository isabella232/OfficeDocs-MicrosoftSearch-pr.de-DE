---
title: Verwalten von Such-Vertikalen
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Verwalten der Such-Vertikalen auf der Ergebnisseite
ms.openlocfilehash: 0396c1f67b22a77a39f78aa1f058ee4b2019a39c
ms.sourcegitcommit: 02d4f91210d992da080fd39d5b60f8cf30d8f0b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2021
ms.locfileid: "60238403"
---
# <a name="manage-search-verticals"></a>Verwalten von Such-Vertikalen

Such verticals are tabs on the search result page that show results of a specific type or from select sources. Die Vertikale Dateien zeigt beispielsweise Ergebnisse an, die als Dateien klassifiziert sind, und erleichtert Benutzern, die Dokumente suchen. Sie können Vertikalen in Microsoft Search an die Anforderungen Ihrer Organisation oder einzelner Abteilungen anpassen.

Sie können Vertikale auf zwei Ebenen verwalten:

- **Organisationsebene** – Eine Vertikale auf Organisationsebene wird auf der Suchergebnisseite angezeigt, wenn Benutzer über ihre [SharePoint](https://sharepoint.com/) Startseite, [Microsoft Office](https://office.com)und Microsoft Search in [Bing](https://bing.com)
- **Websiteebene** – Eine Vertikale auf Websiteebene wird auf der Suchergebnisseite angezeigt, wenn Benutzer auf einer SharePoint Website suchen. Beispielsweise können Sie Ihren Kundendienstmitarbeitern ermöglichen, direkt von der SharePoint Website ihrer Abteilung aus nach Vorfällen des Schweregrads 1 zu suchen.

## <a name="understanding-search-verticals"></a>Grundlegendes zu Such-Vertikalen

Microsoft Search verfügt über zwei Arten von Vertikalen, sofort einsatzbereite und benutzerdefinierte Vertikale. Sofort einsatzbereite Vertikale wie "Alle", "Dateien" und "Personen" erstellen einfachen Zugriff auf die am häufigsten verwendeten Suchergebnisse.

Zusätzliche Konfigurationsoptionen werden in benutzerdefinierten Vertikalen angeboten und können verwendet werden, um die beste Benutzererfahrung zu erzielen.

Sie können Such-Vertikalen hinzufügen, die für Ihre Organisation relevant sind. Sie können beispielsweise eine Vertikale für marketingbezogene Inhalte und eine weitere für den Vertrieb erstellen, basierend auf der Art der Informationen, die jede Abteilung benötigt. Vertikalen können hinzugefügt werden, um Ergebnisse aus Inhalten anzuzeigen, die von [Graph Connectors](connectors-overview.md)indiziert wurden. Sie können jedoch keine vertikale Für Inhalte erstellen, die sich in SharePoint befinden.

## <a name="create-search-verticals"></a>Erstellen von Such-Vertikalen

Die vertikale Verwaltungsumgebung wird vom Assistenten gesteuert. Sie werden durch die Schritte zum Definieren des Vertikalnamens, der Inhaltsquelle und des Bereichs der zu durchsuchenden Inhalte geführt. Sie können einen begrenzten Satz von [KQL (Keyword Query Language)](#keyword-query-language-kql) verwenden, um den Umfang der vertikalen Suche nach einer bestimmten Inhaltsquelle zu definieren.

Im Folgenden werden die Schritte zum Erstellen der benutzerdefinierten Vertikalen auf Microsoft Search in [SharePoint Zuhause,](https://sharepoint.com/) [Office](https://office.com/)oder [Bing beschrieben.](https://bing.com/)  

### <a name="manage-organization-level-verticals"></a>Verwalten von Vertikalen auf Organisationsebene

1. Wechseln [Sie](https://admin.microsoft.com)im Microsoft 365 Admin Center zur Seite [**"Vertikalen"**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) im Abschnitt **"Anpassung".**
1. Klicken Sie auf **"Hinzufügen",** um eine neue Vertikale zu erstellen.
1. Nachdem Sie die Konfigurationsschritte durchlaufen haben, können Sie die Vertikale überprüfen und speichern.  

### <a name="manage-site-level-verticals"></a>Verwalten von Vertikalen auf Websiteebene

1. Öffnen Sie auf der SharePoint Website, auf der Sie die Vertikalen verwalten möchten, den Einstellungsbereich, indem Sie auf den Zahnrad klicken.
1. Wählen Sie **"Websiteinformationen"** und dann **"Alle Websiteeinstellungen anzeigen"** aus.  
1. Suchen Sie nach dem Abschnitt Microsoft Search, und wählen Sie dann **"Sucheinstellungen konfigurieren"** aus.
1. Wechseln Sie im Navigationsbereich zu "Benutzerdefinierte Oberfläche", und wählen Sie dann **"Vertikal" aus.**
1. Klicken Sie auf **"Hinzufügen",** um eine neue Vertikale zu erstellen.
1. Nachdem Sie Ihre Konfiguration festgelegt haben, können Sie die Vertikale überprüfen und speichern.  

## <a name="view-the-vertical-in-search-results"></a>Anzeigen der Vertikalen in Suchergebnissen

Ein [Suchergebnislayout](manage-result-types.md) ist erforderlich, damit Graph Connectorergebnisse auf der vertikalen Suchseite gerendert werden können. Wenn Sie sicherstellen möchten, dass ein geeignetes Ergebnislayout vorhanden ist, können Sie die Such-Vertikale aktivieren. Nachdem Sie eine Vertikale aktiviert haben, gibt es eine Verzögerung von einigen Stunden, bevor Sie sie anzeigen können. Sie können cacheClear=true an die URL in SharePoint anfügen und Office, um die Vertikale sofort anzuzeigen. Fügen Sie in Bing &features=uncachedVerticals an die vertikale URL der Arbeit an, um die Vertikale sofort anzuzeigen.

> [!NOTE]
> Hinzugefügte Vertikale sind in [SharePoint](https://sharepoint.com/) und [Office](https://office.com) nicht sichtbar, wenn sie von mobilen Webbrowsern angezeigt werden.

## <a name="advanced-configuration-options"></a>Erweiterte Konfigurationsoptionen

### <a name="multiple-connections-in-a-vertical"></a>Mehrere Verbindungen in einer vertikalen

Eine Such-Vertikale kann Ergebnisse aus mehreren Verbindungsquellen anzeigen. Diese Option bietet Flexibilität beim Entwerfen der Suchergebnisseite. Mit dem vertikalen Einrichtungsprozess können Administratoren im Schritt "Inhaltsquelle" mehrere Verbindungen auswählen.

Wenn Sie so viele *Semantikbezeichnungen* wie möglich genau benennen, wird diese Erfahrung verbessert. Sie fügen semantische Bezeichnungen am Punkt der Schemadefinition und -aufnahme hinzu. [Weitere Informationen zum Erstellen und Verwalten von Semantikbezeichnungen.](configure-connector.md#step-6-assign-property-labels)
[Hier](configure-connector.md#step-6-assign-property-labels) finden Sie weitere Informationen zum Erstellen und Verwalten von Semantikbezeichnungen.

> [!NOTE]
> - Die mehreren Verbindungen in einem vertikalen Feature befinden sich derzeit in der Vorschau. Weitere Informationen finden Sie unter [Connectors Preview Features](connectors-overview.md#what-are-the-preview-features).
> - Eine Verbindung kann als Inhaltsquelle unter einer einzelnen Vertikalen hinzugefügt werden. Verbindungen unter mehreren Vertikalen können nicht verwendet werden.

Verwenden Sie allgemeine Quelleigenschaften, um eine Abfrage für eine Such-Vertikale einzurichten, in der mehrere Verbindungsquellen hinzugefügt wurden, um die Abfrage zu erstellen.

### <a name="keyword-query-language-kql"></a>Keyword Query Language (KQL)

Eine Abfrage kann einer vertikalen Abfrage hinzugefügt werden, um die Ergebnisse der Such-Vertikalen mithilfe von [KQL (Keyword Query Language)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) einzugrenzen (eingeschränkte Unterstützung). Auf dieser Seite sind die verfügbaren Eigenschaften aufgeführt. Es wird empfohlen, Freitext-Schlüsselwörter und Eigenschaftseinschränkungen für boolesche Operatoren zum Erstellen von KQL zu verwenden. Dynamische Rangfolgenoperatoren wie XRANK, Näherungsoperatoren und Wörter werden nicht unterstützt.

Hier sind einige Beispielabfragen.

|Szenario         | Abfrage   |  
| --------- | ------ |
|Ausschließen von Ergebnissen von Archivwebsites           |NICHT (path:http://contoso.sharepoint.com/archive OR path:http://contoso.sharepoint.com/CompanyArchive)|
| Ausschließen von Ergebnissen basierend auf der Dateitypeigenschaft | NOT(FileType:htm)|  

#### <a name="profile-query-variables"></a>Profilabfragevariablen

Verwenden Sie Variablen im KQL-Abfrageabschnitt einer Vertikalen, um dynamische Daten als Eingabe für die Abfrage einer Vertikalen bereitzustellen. Sie können Profilabfragevariablen verwenden, um die Suchergebnisse für den angemeldeten Benutzer kontextbezogen zu gestalten. Profilabfragevariablen rufen Werte aus dem [Profil](/graph/api/resources/profile)des angemeldeten Benutzers ab.

Um beispielsweise eine "Tickets"-Vertikale zu erstellen, damit der Benutzer Supporttickets findet, die ihm zugewiesen sind, können Sie die folgende Abfrage im Abschnitt "Abfrage" während der vertikalen Erstellung auf der Verwaltungsseite angeben:  

`AssignedTo:{Profile.accounts.userPrincipalName}`

In dieser Sprache werden die Suchergebnisse eingegrenzt, sodass nur die Elemente angezeigt werden, für die der Zugewiesene der Benutzer ist, der die Suche ausführt.

[Profilressource](/graph/api/resources/profile) macht Eigenschaften als Sammlungen verfügbar. Beispielsweise werden Informationen im Zusammenhang mit E-Mail-Adressen über die E-Mail-Sammlung, Arbeitspositionen als Positionssammlung usw. verfügbar gemacht. Alle im Benutzerprofil verfügbaren Eigenschaften, die AAD als Quelltyp aufweisen, werden als Abfragevariablen verfügbar gemacht.

Betrachten Sie einen Benutzer, der drei E-Mail-Adressen in der E-Mail-Sammlung zur Verfügung hat, wie hier gezeigt:

```json
"emails": [{ 

        "address": "Megan.Bowen@contoso.com",
        "id": "xyz", 
        "source": { 
            "CreatedBy": "xyz", 
            "CreatedOn": "2222", 
            "Type": "official" 
        },
        "type": "main" 
    }, { 
        "address": "meganb@hotmail.com",
        "id": "abc", 
        "source": { 
            "CreatedBy": "abc",
            "CreatedOn": "3333", 
            "Type": "non-official",
        },
        "type": "work"
    }, { 
        "address": "meganb@outlook.com",
        "id": "pqr", 
        "source": { 
            "CreatedBy": "pqr", 
            "CreatedOn": "4444", 
            "Type": "personal" 
        },
        "type": "personal" 
    } 
] 
```

- Die Abfrage `MyProperty: {Profile.emails.address}` wird in *"MyProperty" aufgelöst: "Megan.Bowen@contoso.com".*  

- Verwenden Sie die Mehrwerterweiterungssyntax, um alle Werte des Adressattributs aufzulösen. Die Abfrage `{|MyProperty:{Profile.emails.address}}` wird in *((MyProperty:"Megan.Bowen@contoso \. com")* oder *(MyProperty: "meganb@hotmail \. com")* oder  *(MyProperty:"meganb@outlook \. com"))* aufgelöst.

Verwenden Sie den Operator "|", um Mehrwertvariablen aufzulösen. Weitere Beispiele für die Profilerweiterung finden Sie in der folgenden Tabelle.

| #         | Syntax |  Zurückgegebener Wert  |
| --------- | ------ | --- |
| 1    | MyProperty:{Profile.emails.address}  |   "Megan \. Bowen@contoso.com"  |
| 2 | MyProperty:{Profile.emails}   |    {Profile.emails} Dies wird nicht aufgelöst, da *E-Mails* ein Objekt sind.|
| 3    | {? MyProperty:{Profile.emails}}  |  Dies wird nicht aufgelöst, da *E-Mails* ein Objekt sind. Das "?" -Operator ignoriert Abfragevariablen, die nicht aufgelöst werden. Diese Variable wird entfernt, wenn sie weiter unten im Abfragestapel übergeben wird.   |
| 4  | {&#124;MyProperty: {Profile.emails.source.Type}}    |  ((MyProperty:"official") oder (MyProperty:"non-official") oder (MyProperty:"personal"))    |

> [!NOTE]
>
> - Profilabfragevariablen werden nur für benutzerdefinierte Vertikale unterstützt, die einen [Connector](connectors-overview.md) als Inhaltsquelle verwenden.
> - Das Feature "Profilabfragevariablen" befindet sich derzeit in der Vorschau. Weitere Informationen zur Vorschau finden Sie unter [Connectors Preview Features](connectors-overview.md#what-are-the-preview-features).

## <a name="troubleshooting"></a>Problembehandlung

Hier ist eine Liste der häufig auftretenden Probleme und Aktionen zur Behebung dieser Probleme.

|Problem  |Aktion  |
|---------|---------|
| Ich sehe die Fehlermeldung "Etwas ist schief gelaufen" in der Vertikalen. | Zum Abschließen des Setups sind sowohl die vertikalen als auch die Ergebnistypen erforderlich. Stellen Sie sicher, dass beide für die Inhaltsquelle eingerichtet sind. |
| Ich sehe keine Inhaltsquellen auf der vertikalen Seite. | Stellen Sie sicher, dass Sie Connectors und indizierte Daten konfiguriert haben.   |
