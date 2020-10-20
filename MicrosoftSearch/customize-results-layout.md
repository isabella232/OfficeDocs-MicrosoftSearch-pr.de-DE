---
title: Anpassen des Suchergebnis Layouts
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
description: Erstellen eines Layouts zum Anzeigen Ihrer benutzerdefinierten Suchergebnisse mithilfe adaptiver Karten
ms.openlocfilehash: 0856adfd85a921cf026cd59a8ca2c5beea2ffcf2
ms.sourcegitcommit: 7ceefb7a96ae6886145b929791c7448c139366b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2020
ms.locfileid: "48595273"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a>Erstellen eines Layouts zum Anpassen von Suchergebnissen

Sie können das Ergebnis Layout für eine benutzerdefinierte vertikale mithilfe des Such Layout-Designers entwerfen. Sie können mit dem Entwurf des Layouts beginnen, indem Sie Vorlagen auswählen, die im Layout-Designer angeboten werden, und diese verwenden, wenn Sie Ihren Anforderungen entsprechen. Sie können diese Vorlagen auch auf verschiedene Arten bearbeiten, um Ihren Anforderungen zu entsprechen. Beispiel: Hinzufügen/Entfernen von Bildern, Hinzufügen/Entfernen von Text und Ändern von Text. Wenn keine der Vorlagen Ihren Anforderungen entspricht, können Sie mit dem Entwerfen Ihres Layouts mit einer leeren Vorlage beginnen.  

Nachdem das Layout bereit ist, verwenden Sie die [Vorlage Sprache für Adaptive Karten](https://docs.microsoft.com/adaptive-cards/templating/language) , um ein Ergebnis Layout-JSON zu erstellen, die zum Definieren eines Ergebnistyps verwendet wird. Sie ordnen die Ergebniseigenschaften dem Layout mithilfe des Zuordnungs Schritts im Layout-Designer zu.  

## <a name="create-a-layout-on-your-own"></a>Erstellen eines Layouts auf eigene Faust

Das Erstellen eines Layouts auf eigene Faust erfordert Kenntnisse über [Adaptive Karten](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) und deren [Schema](https://adaptivecards.io/explorer/). Das Suchergebnislayout verwendet eine Teilmenge der Elemente, die von adaptiven Karten angeboten werden, und Sie können den Layout-Designer verwenden, um mehr über den unterstützten Satz von Elementen zu erfahren.  

Erstellen Sie beim Erstellen Ihres eigenen Layouts das Layout für die Adaptive Karte mithilfe von Daten aus dem Connector, und schließen Sie dann das Layout ab.
Es gibt zwei Hauptschritte beim Erstellen Ihres eigenen Layouts:

- Entwerfen Sie das Layout.
- Trennen Sie die Daten von der Vorlage.

### <a name="design-the-layout"></a>Entwerfen des Layouts

In diesem Beispiel wird ein Layout mit einer Kopfzeile, einem Link und einem beschreibenden Text angezeigt.

![Beispiel für ein Layout mit Kopfzeile, Link und Beschreibung.](media/Verts-ExampleLayout.png)

Und hier ist die zugehörige JSON-Datei des Layouts:

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

Hier ist das Layout JSON nach dem Binden der Daten:

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

Beispieldaten: Geben Sie Beispieldaten im **Beispieldaten Editor** an, um die datengebundene Karte im **Vorschaumodus**anzuzeigen.

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a>Zuordnen des Layouts zu den Ergebniseigenschaften

Sie müssen jedes Feld des Layouts einer Result-Eigenschaft oder einer Connector-Eigenschaft zuordnen, um das Ergebnis Layout JSON zu generieren.

![Bildschirmaufnahme eines Beispiel Layouts auf der Seite des Such Layout-Designers, wobei ein Feld ausgewählt und der Eigenschaftenbereich geöffnet ist.](media/Verts-SearchLayoutDesigner.png)

Wählen Sie ein Feld im Layout aus, um die Variablen hervorzuheben, die zugeordnet werden müssen. Sie können mehrere Variablen für ein einzelnes Feld verwenden, und alle Felder müssen den Ergebniseigenschaften zugeordnet werden.

### <a name="show-snippet-on-search-result"></a>Ausschnitt im Suchergebnis anzeigen  

Dynamische Codeausschnitte, die für die **Content** -Eigenschaft des Connector-Ergebnisses generiert wurden, können im Suchergebnis angezeigt werden. **ResultSnippet** ist die Systemeigenschaft, die als Platzhalter Eigenschaft für die für jedes Verbindungs Ergebnis generierten Codeausschnitte fungiert. Um die Codeausschnitte im Ergebnis Layout anzuzeigen, muss die **ResultSnippet** -Systemeigenschaft einem entsprechenden Feld (beispielsweise Description) im Suchergebnislayout zugeordnet werden. Ausschnitte, die für jedes Ergebnis generiert werden, heben auch die Übereinstimmungen im Codeausschnitt mit dem vom Benutzer eingegebenen Abfrageausdruck hervor. 

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte

Bevor Sie beginnen, sollten Sie einige Dinge tun, die Sie vermeiden sollten, um sicherzustellen, dass Ihre Layouts erfolgreich sein werden.

### <a name="do"></a>Dos

- Bearbeiten Sie eine Vorlage, um den Link "Logo" im Layout bereitzustellen, wenn Sie statische Links für Logos verwenden und keine Ergebniseigenschaften sind.
- Überprüfen Sie das Ergebnis Layout für Szenarien, in denen keine Daten für eine Result-Eigenschaft zurückgegeben werden, die in der Ergebnis-JSON verwendet wird. Verwenden Sie die `$when` Bedingung, um ein Element auszublenden, wenn die Eigenschaft keine Daten enthält.  
- Stellen Sie sicher, dass die Datentypen der `$when` Bedingung und der Result-Eigenschaft übereinstimmen. Vergleichen Sie beispielsweise nicht `Number` mit `Text` in der `$when` Bedingung.  
- Denken Sie an Designanforderungen beim Entwerfen eines Ergebnis Layouts.  
- Stellen Sie sicher, dass das `Textblock`   Element dynamischen Inhalt verarbeiten kann. `wrap`Für diesen Zweck können Sie die Eigenschaften und des- `maxLines` Elements verwenden.
- Formatieren Sie das Datum ordnungsgemäß, wenn Sie `{DATE()}` in Abschlag verwenden.  

### <a name="dont"></a>Don’ts

- Definieren Sie beim Binden von Werten keine ungültigen Datentypen. Weitere Informationen zu Datentypen finden Sie unter [Verwalten des Suchschemas](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).
- Vermeiden Sie das Zuschneiden des Ergebnisses auf der Ergebnisseite, indem Sie der maximalen Höhe des Ergebnis Layouts JSON folgen. Wenn Sie die maximale Höhe des Ergebnis Layouts überschreiten, wird das Ergebnis auf der Ergebnisseite abgeschnitten.
- Verwenden Sie keine `px` Werte in Elementeigenschaften.
- Verwenden Sie keinen Abschlag, wenn Sie mit der **ResultSnippet** -Eigenschaft im Ergebnis Layout die Abfrage Übereinstimmung im Suchergebnis hervorheben möchten. 

## <a name="resources"></a>Ressourcen

[Anpassen der Suchergebnisseite](customize-search-page.md)

[Adaptive Karten](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[Vorlagensprache für Adaptive Karten](https://docs.microsoft.com/adaptive-cards/templating/language)

[Adaptives Karten Schema](https://adaptivecards.io/explorer/)