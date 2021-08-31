---
title: Anpassen der Microsoft Search Seite
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Hinzufügen von Such-Vertikalen und Anpassen von Suchergebnissen
ms.openlocfilehash: 1ca436a2617e32e285715e4fffd622dc7a571ca1
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702174"
---
# <a name="customize-the-search-results-page"></a>Anpassen der Suchergebnisseite

Sie können *Such-Vertikalen* und *Ergebnistypen* erstellen, um die Suchergebnisse anzupassen, die Benutzern angezeigt werden, wenn sie in Microsoft [SharePoint,](https://sharepoint.com/) [Microsoft Office](https://office.com)und Microsoft Search in [Bing](https://bing.com)suchen. Vertikalen erleichtern benutzern das Auffinden der Informationen, für die sie über die Berechtigung zum Anzeigen verfügen.

Sie können beispielsweise eine Suchsparte für Marketinganalysedaten aus Drittanbietersoftware für Ihre Benutzer in der Marketingabteilung erstellen. Sie können auch Ergebnistypen definieren und das Layout für diese Daten anpassen.

## <a name="about-search-verticals"></a>Informationen zu Such-Vertikalen

Oben auf der Ergebnisseite Microsoft Search befindet sich eine Reihe von Registerkarten. Hierbei handelt es sich um Such-Vertikalen. Eine Such-Vertikale zeigt nur Ergebnisse eines bestimmten Typs oder eines bestimmten Inhaltssatzes an. Beispiele sind **Dateien** oder **News**. Standardmäßig zeigt Microsoft Search die Vertikalen **"Alle",** **"Personen",** **"Dateien",** **"Websites"** und **"News"** an.  

Sie können Such-Vertikalen hinzufügen, die für Ihre Organisation relevant sind. Diese werden auf der Ergebnisseite Microsoft Search in SharePoint, Office und Bing angezeigt. Sie können beispielsweise eine Vertikale für marketingbezogene Inhalte und eine weitere für den Vertrieb erstellen, basierend auf der Art der Informationen, die jede Abteilung benötigt. Sie können Vertikale hinzufügen, um nur Ergebnisse aus Inhalten anzuzeigen, die über Connectors indiziert wurden.

Sie können Vertikale und Ergebnistypen auf zwei Ebenen erstellen:

- **Organisationsebene** – Eine Vertikale, die Sie auf Organisationsebene erstellen, wird auf der Suchergebnisseite angezeigt, wenn Benutzer über ihre [SharePoint](https://sharepoint.com/) Startseite, auf [Office](https://office.com)oder auf [Bing](https://bing.com)suchen.
- **Standortebene** – Beispielsweise möchten Sie Ihren Kundendienstmitarbeitern ermöglichen, direkt von der SharePoint Website ihrer Abteilung aus nach Vorfällen des *Schweregrads 1* zu suchen.

### <a name="multiple-connections-in-a-vertical"></a>Mehrere Verbindungen in einer vertikalen

Eine Such-Vertikale kann Ergebnisse aus mehreren Verbindungsquellen anzeigen. Diese Option bietet Flexibilität beim Entwerfen der Suchergebnisseite. Mit dem vertikalen Einrichtungsprozess können Administratoren im Schritt "Inhaltsquelle" mehrere Verbindungen auswählen.

Wenn Sie so viele *Semantikbezeichnungen* wie möglich genau benennen, wird diese Erfahrung verbessert. Sie fügen semantische Bezeichnungen am Punkt der Schemadefinition und -aufnahme hinzu. [Weitere Informationen zum Erstellen und Verwalten von Semantikbezeichnungen.](configure-connector.md#step-6-assign-property-labels)
[Hier](configure-connector.md#step-6-assign-property-labels) finden Sie weitere Informationen zum Erstellen und Verwalten von Semantikbezeichnungen.

> [!NOTE]
> Die mehreren Verbindungen in einem vertikalen Feature befinden sich derzeit in der Vorschau. Weitere Informationen finden Sie unter [Connectors Preview Features](connectors-overview.md#what-are-the-preview-features).

Eine Verbindung kann als Inhaltsquelle unter einer einzelnen Vertikalen hinzugefügt werden. Verbindungen unter mehreren Vertikalen können nicht verwendet werden.

Verwenden Sie allgemeine Quelleigenschaften, um eine Abfrage für eine Such-Vertikal einzurichten, in der mehrere Verbindungsquellen hinzugefügt wurden, um die Abfrage zu erstellen.

### <a name="before-you-create-verticals-and-result-types"></a>Vor dem Erstellen von Vertikalen und Ergebnistypen

Die folgenden Faktoren sollten Sie in Ihrem Plan berücksichtigen:

- Stellen Sie sicher, dass der Connector indiziert wurde. Je nach Dateigröße kann dies bis zu 48 Stunden dauern.

- Sie können keine Vertikale für Inhalte erstellen, die sich in SharePoint befinden.

Dies sind die Schritte zum Implementieren einer vertikalen:

1. Erstellen Sie die Vertikale. In diesem Schritt definieren Sie den vertikalen Namen, die Inhaltsquelle und den Umfang des zu durchsuchenden Inhalts.
2. Definieren Sie, wie die Ergebnisse für diese Vertikale aussehen.  
3. Aktivieren Sie die vertikale (anzuzeigende) Vertikal auf der vertikalen Listenseite.

## <a name="step-1-create-the-search-vertical"></a>Schritt 1: Erstellen der Such-Vertikalen

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte zum Definieren des Vertikalnamens, der Inhaltsquelle und des Bereichs der zu durchsuchenden Inhalte geführt.

>[!Note]
>Vertikalen werden in einem deaktivierten Zustand erstellt. Sie können diese aktivieren, um sie sichtbar zu machen.

Sie können einen begrenzten Satz von [KQL (Keyword Query Language)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) verwenden, um den Bereich einzugrenzen. (Die Eigenschaften, die Sie verwenden können, werden weiter unten in diesem Artikel beschrieben.) Es wird empfohlen, Freitext-Schlüsselwörter und Eigenschaftseinschränkungen für boolesche Operatoren zu verwenden. KQL unterstützt auch [Profilabfragevariablen,](#profile-query-variables) um die Ergebnisse unter der Vertikalen zu optimieren.

### <a name="create-a-vertical-at-the-organization-level"></a>Erstellen einer Vertikalen auf Organisationsebene

Führen Sie die folgenden Schritte aus, um eine vertikale Microsoft Search in SharePoint Zuhause, Office oder Bing zu erstellen:

1. Wechseln [Sie im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**"Vertikalen".**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Wählen Sie **"Hinzufügen"** aus, um zu beginnen.  

### <a name="create-a-vertical-at-the-site-level"></a>Erstellen einer Vertikalen auf Websiteebene

1. Wechseln Sie auf der [SharePoint](https://sharepoint.com/) Website, auf der Sie die Vertikale verwenden möchten, zu **Einstellungen**.
2. Wählen Sie **"Websiteinformationen"** und dann **"Alle Websiteeinstellungen anzeigen"** aus.
3. Suchen Sie den **Abschnitt Microsoft Search,** und wählen Sie dann **Microsoft Search für diese Websitesammlung konfigurieren** aus.
4. Wechseln Sie im Navigationsbereich zu **"Benutzerdefinierte Oberfläche",** und wählen Sie dann die Registerkarte **"Vertikal" aus.**
5. Wählen Sie zum Hinzufügen einer vertikalen , **hinzufügen**. Oder um eine Vertikale zu bearbeiten, wählen Sie sie aus der Liste aus.

## <a name="step-2-create-result-types"></a>Schritt 2: Erstellen von Ergebnistypen

Mithilfe von *Ergebnistypen* können Sie definieren, wie Ergebnisse in der vertikalen Leiste angezeigt werden. Mit dem Ergebnislayout können Sie wichtige Informationen direkt in den Suchergebnissen anzeigen, sodass Benutzer nicht jedes Ergebnis auswählen müssen, um festzustellen, ob sie das gesuchte Ergebnis gefunden haben.

### <a name="default-search-result-layout"></a>Standardmäßiges Suchergebnislayout

Ein standardmäßiges Suchergebnislayout für Connectorinhalte wird angezeigt, wenn die *Bezeichnungen* und *Inhaltseigenschaften* bei der Konfiguration des Connectors den Quelleigenschaften ordnungsgemäß zugeordnet wurden. Die *Titelbezeichnung* ist die wichtigste Bezeichnung. Es *wird dringend* empfohlen, dieser Bezeichnung eine Eigenschaft zur Verwendung des standardmäßigen Suchergebnislayouts zuzuweisen.

### <a name="create-your-own-result-type"></a>Erstellen Eines eigenen Ergebnistyps

Um Ein eigenes Suchergebnislayout zu erstellen und das standardmäßige Suchergebnislayout außer Kraft zu setzen, erstellen Sie einen *Ergebnistyp.* Ein Ergebnistyp einer Suche ist eine Regel, die bewirkt, dass unterschiedliche Arten von Suchergebnissen auf verschiedene Weisen angezeigt werden. Es besteht aus:

- **Eine oder mehrere Bedingungen,** mit denen jedes Suchergebnis verglichen werden soll, z. B. die Inhaltsquelle des Suchergebnisses.  
- Ein **Ergebnislayout, das** für Suchergebnisse verwendet werden soll, die die Bedingungen erfüllen. Das resultierende Layout steuert, wie die Ergebnisse, die die Bedingungen erfüllen, auf einer Suchergebnisseite angezeigt werden und sich verhalten.

*Wenn Sie keine geeignete Zuordnung zum Anzeigen des standardmäßigen Suchergebnislayouts durchführen, müssen Sie mindestens einen Ergebnistyp erstellen, damit die Ergebnisse in der vertikalen Ansicht angezeigt werden.* 

Sie können für jede Vertikale mehrere Ergebnistypen erstellen, sodass Sie unterschiedliche Layouts für unterschiedliche Ergebnistypen verwenden können. Beispielsweise können Sie Vorfälle *des Schweregrads 1* so anpassen, dass sie auffälligere Farben und eine größere Schriftart als *Vorfälle mit Schweregrad 3* aufweisen.

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte geführt, um den Namen, die Inhaltsquelle und die Bedingungen für den Ergebnistyp zu definieren. Sie können die Priorität des Ergebnistyps in der Listenansicht definieren.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Erstellen eines Ergebnistyps auf Organisationsebene

1. Wechseln [Sie](https://admin.microsoft.com)im Microsoft 365 Admin Center zu [**Ergebnistypen.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)
2. Um einen Ergebnistyp hinzuzufügen, wählen Sie **Hinzufügen** aus. Um einen Ergebnistyp zu bearbeiten, wählen Sie den Ergebnistyp aus der entsprechenden Liste aus.

### <a name="create-a-result-type-at-the-site-level"></a>Erstellen eines Ergebnistyps auf Websiteebene

1. Wechseln Sie auf der [SharePoint](https://sharepoint.com/) Website, auf der Der Ergebnistyp angezeigt werden soll, zu **Einstellungen**.
2. Wählen Sie **"Websiteinformationen"** und dann **"Alle Websiteeinstellungen anzeigen"** aus.
3. Suchen Sie nach dem **Abschnitt Microsoft Search,** und wählen Sie dann **Microsoft Search für diese Websitesammlung** konfigurieren aus.
4. Wechseln Sie im Navigationsbereich zu **"Benutzerdefinierte Oberfläche",** und wählen Sie die Registerkarte **"Ergebnistyp" aus.**
5. Um einen Ergebnistyp hinzuzufügen, wählen Sie **Hinzufügen** aus.  Oder wählen Sie zum Bearbeiten eines Ergebnistyps den Ergebnistyp in der Liste aus.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>Schritt 3: Anzeigen der Vertikalen nach der Aktivierung

Nachdem Sie die Vertikale aktiviert haben, gibt es eine Verzögerung von einigen Stunden, bevor Sie sie anzeigen können. Sie können die URL jedoch `cacheClear=true` in SharePoint anfügen und Office, um die Vertikale sofort anzuzeigen. Fügen Sie Bing sofort an die Anfügeliste `&features=uncachedVerticals` `Work vertical URL` an, um die Vertikale anzuzeigen.

> [!NOTE]
> Hinzugefügte Vertikale sind auf SharePoint]( https://sharepoint.com/) und [Office](https://office.com) nicht sichtbar, wenn sie in mobilen Webbrowsern angezeigt werden.

## <a name="profile-query-variables"></a>Profilabfragevariablen

Verwenden Sie Variablen im KQL-Abfrageabschnitt einer Vertikalen, um dynamische Daten als Eingabe für die Abfrage einer Vertikalen bereitzustellen. Sie können Profilabfragevariablen verwenden, um die Suchergebnisse für den angemeldeten Benutzer kontextbezogen zu gestalten. Profilabfragevariablen rufen Werte aus dem [Profil](/graph/api/resources/profile)des angemeldeten Benutzers ab.

Um beispielsweise eine "Tickets"-Vertikale zu erstellen, damit der Benutzer Supporttickets findet, die ihm zugewiesen sind, können Sie die folgende Abfrage im Abschnitt "Abfrage" während der vertikalen Erstellung auf der Verwaltungsseite angeben:  

`AssignedTo:{Profile.accounts.userPrincipalName}`

In dieser Sprache werden die Suchergebnisse eingegrenzt, sodass nur die Elemente angezeigt werden, für die der Zugewiesene der Benutzer ist, der die Suche ausführt.

[Profilressource](/graph/api/resources/profile) macht Eigenschaften als Sammlungen verfügbar. Beispielsweise werden Informationen im Zusammenhang mit E-Mail-Adressen durch E-Mail-Sammlung, Arbeitspositionen als Positionssammlung usw. verfügbar gemacht. Alle im Benutzerprofil verfügbaren Eigenschaften, die AAD als Quelltyp aufweisen, werden als Abfragevariablen verfügbar gemacht.


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

- Die Abfrage `MyProperty: {Profile.emails.address}` wird in *MyProperty aufgelöst: "Megan.Bowen@contoso.com"*.  

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
> - Profilabfragevariablen werden im Abschnitt "Abfrage" des [vertikalen Einrichtungsprozesses](customize-search-page.md#step-1-create-the-search-vertical)definiert.
> - Das Feature "Profilabfragevariablen" befindet sich derzeit in der Vorschau. Weitere Informationen zur Vorschau finden Sie unter [Connectors Preview Features](connectors-overview.md#what-are-the-preview-features).

## <a name="troubleshooting"></a>Problembehandlung

Hier ist eine Liste der häufig auftretenden Probleme und Aktionen zur Behebung dieser Probleme.

|Problem  |Aktion  |
|---------|---------|
| Ich sehe die Fehlermeldung "Etwas ist schief gelaufen" in der Vertikalen. | Zum Abschließen des Setups sind sowohl der vertikale als auch der Ergebnistyp erforderlich. Stellen Sie sicher, dass Sie beide für dieselbe Inhaltsquelle erstellt haben. |
| Ich sehe mein Ergebnislayout nicht, obwohl ich eins erstellt habe. | Es kann zu einer Verzögerung von einigen Minuten kommen, da diese Einstellungen zwischengespeichert werden. Warten Sie einige Minuten, und versuchen Sie es erneut.        |
| Ich sehe keine Inhaltsquellen auf der vertikalen Seite oder auf der Ergebnistypseite. | Stellen Sie sicher, dass Sie Connectors und indizierte Daten konfiguriert haben.   |

## <a name="next-steps"></a>Nächste Schritte

[Anpassen des Ergebnislayouts](customize-results-layout.md)
