---
title: Verwalten von Layouts für Suchergebnisse
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Erstellen Sie mithilfe adaptiver Karten ein Layout zum Anzeigen ihrer angepassten Suchergebnisse.
ms.openlocfilehash: d29b1a45f11079f4b71f71a387cf43cbf2f48e7d
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031737"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a>Erstellen eines Layouts zum Anpassen von Suchergebnissen

Sie können das Ergebnislayout für eine benutzerdefinierte Vertikale mithilfe des Suchlayout-Designers entwerfen. Sie können mit dem Entwerfen des Layouts beginnen, indem Sie vorlagen auswählen, die im Layout-Designer angeboten werden, und diese verwenden, wenn sie Ihren Anforderungen entsprechen. Sie können diese Vorlagen auch auf unterschiedliche Weise bearbeiten, um Ihren Anforderungen gerecht zu werden. Beispiel: Hinzufügen/Entfernen von Bildern, Hinzufügen/Entfernen von Text und Ändern von Text. Wenn keine der Vorlagen Ihren Anforderungen entspricht, können Sie das Layout mithilfe einer leeren Vorlage entwerfen.  

Nachdem das Layout bereit ist, verwenden Sie die Vorlage für [adaptive](/adaptive-cards/templating/language) Karten, um ein Ergebnislayout-JSON zu erstellen, das zum Definieren eines Ergebnistyps verwendet wird. Sie ordnen die Ergebniseigenschaften dem Layout mithilfe des Zuordnungsschritts im Layout-Designer zu.  

## <a name="create-a-layout-on-your-own"></a>Eigenes Layout erstellen

Das Erstellen eines Layouts allein erfordert Kenntnisse der [adaptiven Karten und](/adaptive-cards/authoring-cards/getting-started) deren [Schema.](https://adaptivecards.io/explorer/) Das Suchergebnislayout verwendet eine Teilmenge der Elemente, die von adaptiven Karten angeboten werden, und Sie können den Layoutdesigner verwenden, um mehr über den unterstützten Satz von Elementen zu erfahren.  

Erstellen Sie beim Erstellen Ihres eigenen Layouts das layout für adaptive Karten mithilfe von Daten aus Ihrem Connector, und finalisieren Sie das Layout.
Es gibt zwei Hauptschritte beim Erstellen eines eigenen Layouts:

- Entwerfen Sie das Layout.
- Trennen Sie die Daten von der Vorlage.

### <a name="design-the-layout"></a>Entwerfen des Layouts

In diesem Beispiel wird ein Layout mit einer Kopfzeile, einem Link und einem beschreibenden Text angezeigt.

![Beispiel für ein Layout mit einer Kopfzeile, einem Link und einer Beschreibung.](media/Verts-ExampleLayout.png)

Und hier ist die zugeordnete JSON-Datei des Layouts:

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
     "body": [
{

            "type": "ColumnSet",
             "columns": [
                 {
                     "type": "Column",
                     "width": 8,
                     "items": [
                         {
                             "type": "TextBlock",
                             "text": "Contoso Marketing Analysis - Q3 FY18",
                             "color": "Accent",
                             "size": "Medium",
                             "spacing": "None",
                             "$when": "{title != \"\"}",
                             "weight": "Bolder"
                        },
                        {
                        "type": "TextBlock",  
                        "text": "https://contoso.com/hr/link",
                        "spacing": "None",  
                        "color": "Dark",
                        "weight": "Bolder"

                        },

                        {  
                        "type": "TextBlock",
                        "text": "Marketing team at Contoso.., and looking at the Contoso Marketing documents on the team site. This contains the data from FY20 and will taken over to FY21...Marketing Planning is ongoing for FY20..",  
                        "wrap": true,
                        "maxLines": 2,
                        "spacing": "Medium"
                        }
                        ],

                    "horizontalAlignment": "Center",
                    "spacing": "None"

                }

            ]

        }
        ],

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json"
}
```

### <a name="separate-the-data-from-the-layout"></a>Trennen der Daten vom Layout

Sie können die Daten vom Layout trennen und die Daten binden.

Hier ist Layout JSON nach dem Binden der Daten:

```json
{

    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
    {
    "type": "ColumnSet",
"columns": [

                {
                "type": "Column",
                "width": 8,
                "items": [
                {
                "type": "TextBlock",
                "text": "[{title}]({titleUrl})",
                "color": "Accent",
                "size": "Medium",
                "spacing": "None",
                "weight": "Bolder"

                 },
                 {
                 "type": "TextBlock",
                 "text": "{link}",
                 "spacing": "None",
                 "color": "Dark",
                 "weight": "Bolder"
                 },
                 {
                 "type": "TextBlock",
                 "text": "{description}",
                 "wrap": true,
                 "maxLines": 2,
                 "spacing": "Medium"
                 }
                 ],
                 "horizontalAlignment": "Center",
                 "spacing": "None"
                 }
                 ]

        }

    ],

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json"
}
```

Beispieldaten: Geben Sie Beispieldaten im **Beispieldaten-Editor an,** um die datengebundene Karte im **Vorschaumodus anzuzeigen.**

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a>Ordnen Sie das Layout den Ergebniseigenschaften zu.

Sie müssen jedes Feld des Layouts einer Ergebniseigenschaft oder einer Connectoreigenschaft zuordnungen, um das Ergebnislayout JSON zu generieren.

![Bildschirmaufnahme eines Beispiellayouts auf der Seite Suchlayout-Designer, bei dem ein Feld ausgewählt und der Eigenschaftenbereich geöffnet ist.](media/Verts-SearchLayoutDesigner.png)

Wählen Sie ein Feld im Layout aus, um die Variablen zu markieren, die zugeordnet werden müssen. Sie können mehrere Variablen für ein einzelnes Feld verwenden, und alle Felder müssen den Ergebniseigenschaften zugeordnet werden.

### <a name="show-snippet-on-search-result"></a>Codeausschnitt im Suchergebnis anzeigen  

Dynamische Codeausschnitte, die in der **Inhaltseigenschaft** des Connectorergebniss generiert werden, können im Suchergebnis angezeigt werden. **ResultSnippet** ist die Systemeigenschaft, die als Platzhaltereigenschaft für die Codeausschnitte dient, die für jedes Connector-Ergebnis generiert werden. Zum Anzeigen der Codeausschnitte im Ergebnislayout muss die **ResultSnippet-Systemeigenschaft** einem entsprechenden Feld zugeordnet werden, z. B. Beschreibung, im Suchergebnislayout. Codeausschnitte, die für jedes Ergebnis generiert werden, markieren auch die Übereinstimmungen im Codeausschnitt mit dem vom Benutzer eingegebenen Abfragebegriff.

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte

Bevor Sie beginnen, sollten Sie einige Dinge tun und einige Dinge vermeiden, die Sie vermeiden sollten, um sicherzustellen, dass Ihre Layouts erfolgreich sind.

### <a name="do"></a>Dos

- Bearbeiten Sie eine Vorlage, um den Logolink im Layout zur Verfügung zu stellen, wenn Sie statische Links für Logos und keine Ergebniseigenschaften verwenden.
- Überprüfen Sie das Ergebnislayout für Szenarien, in denen keine Daten für eine ergebniseigenschaft zurückgegeben werden, die im Ergebnis-JSON verwendet wird. Verwenden Sie `$when` die Bedingung, um ein Element auszublenden, wenn die Eigenschaft keine Daten enthält.  
- Stellen Sie sicher, dass die Datentypen der `$when` Bedingung und der result-Eigenschaft übereinstimmen. Vergleichen Sie z. B. nicht `Number` mit `Text` in der `$when` Bedingung.  
- Denken Sie an Designanforderungen beim Entwerfen eines Ergebnislayouts.  
- Stellen Sie sicher, dass `Textblock`   das Element dynamische Inhalte verarbeiten kann. Zu diesem Zweck können Sie `wrap` die Eigenschaften and element `maxLines` verwenden.
- Formatieren Sie das Datum bei Verwendung `{DATE()}` in Markdown ordnungsgemäß.  

### <a name="dont"></a>Don’ts

- Definieren Sie beim Binden von Werten keine ungültigen Datentypen. Weitere Informationen zu Datentypen finden Sie unter [Manage the Search schema](/sharepoint/search/manage-the-search-schema).
- Vermeiden Sie das Zuschneiden des Ergebnisses auf der Ergebnisseite, indem Sie der maximalen Höhe des Ergebnislayouts JSON folgen. Wenn Sie die maximale Höhe des Ergebnislayouts überschreiten, wird das Ergebnis auf der Ergebnisseite zugeschnitten.
- Verwenden Sie keine `px` Werte in Elementeigenschaften.
- Verwenden Sie markdown nicht mit der **ResultSnippet-Eigenschaft** im Ergebnislayout, um die Abfrage übereinstimmung im Suchergebnis zu markieren.

## <a name="resources"></a>Ressourcen

[Anpassen der Suchergebnisseite](customize-search-page.md)

[Adaptive Karten](/adaptive-cards/authoring-cards/getting-started)

[Vorlage für adaptive Karten](/adaptive-cards/templating/language)

[Adaptives Kartenschema](https://adaptivecards.io/explorer/)