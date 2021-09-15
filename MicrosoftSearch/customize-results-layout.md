---
title: Verwalten von Layouts für Suchergebnisse
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
description: Erstellen Sie mithilfe adaptiver Karten ein Layout, um Ihre benutzerdefinierten Suchergebnisse anzuzeigen.
ms.openlocfilehash: 44808d1dba8d765ba67fcd0c3dcf6f186a0b774c
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375946"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a>Erstellen eines Layouts zum Anpassen von Suchergebnissen

Sie können das Ergebnislayout für eine benutzerdefinierte Vertikale mithilfe des Suchlayout-Designers entwerfen. Sie können mit dem Entwerfen des Layouts beginnen, indem Sie im Layout-Designer angebotene Vorlagen auswählen und diese verwenden, wenn sie Ihren Anforderungen entsprechen. Sie können diese Vorlagen auch auf verschiedene Weise bearbeiten, um Ihre Anforderungen zu erfüllen. Beispiel: Hinzufügen/Entfernen von Bildern, Hinzufügen/Entfernen von Text und Ändern von Text. Wenn keine der Vorlagen Ihren Anforderungen entspricht, können Sie mit dem Entwerfen ihres Layouts mithilfe einer leeren Vorlage beginnen.  

Nachdem das Layout fertig ist, verwenden Sie die Sprache der Vorlage für [adaptive Karten,](/adaptive-cards/templating/language) um eine Ergebnislayout-JSON zu erstellen, die zum Definieren eines Ergebnistyps verwendet wird. Sie ordnen die Ergebniseigenschaften dem Layout mithilfe des Zuordnungsschritts im Layout-Designer zu.  

## <a name="create-a-layout-on-your-own"></a>Erstellen eines eigenen Layouts

Das Erstellen eines Layouts allein erfordert Kenntnisse [adaptiver Karten](/adaptive-cards/authoring-cards/getting-started) und deren [Schema.](https://adaptivecards.io/explorer/) Das Suchergebnislayout verwendet eine Teilmenge der Elemente, die von adaptiven Karten angeboten werden, und Sie können den Layout-Designer verwenden, um mehr über den unterstützten Satz von Elementen zu erfahren.  

Erstellen Sie beim Erstellen Ihres eigenen Layouts das Layout für adaptive Karten mithilfe von Daten aus Ihrem Connector, und fertig stellen Sie das Layout dann fertig.
Es gibt zwei Hauptschritte beim Erstellen Ihres eigenen Layouts:

- Entwerfen Sie das Layout.
- Trennen Sie die Daten von der Vorlage.

### <a name="design-the-layout"></a>Entwerfen des Layouts

In diesem Beispiel wird ein Layout mit einer Kopfzeile, einem Link und einem beschreibenden Text angezeigt.

![Beispiel für ein Layout mit einer Kopfzeile, einem Link und einer Beschreibung.](media/Verts-ExampleLayout.png)

Und hier ist die zugeordnete JSON-Datei des Layouts:

```json
{
    "type": "AdaptiveCard",
    "version": "1.3",
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
    "version": "1.3",
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
                            "text": "[${title}](${titleUrl})",
                            "color": "Accent",
                            "size": "Medium",
                            "spacing": "None",
                            "weight": "Bolder"
                        },
                        {
                            "type": "TextBlock",
                            "text": "${link}",
                            "spacing": "None",
                            "color": "Dark",
                            "weight": "Bolder"
                        },
                        {
                            "type": "TextBlock",
                            "text": "${description}",
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

Beispieldaten: Geben Sie Beispieldaten im **Beispieldaten-Editor** an, um die datengebundene Karte im **Vorschaumodus** anzuzeigen.

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a>Zuordnen des Layouts zu den Ergebniseigenschaften

Sie müssen jedes Feld des Layouts einer Ergebniseigenschaft oder einer Connectoreigenschaft zuordnen, um das Ergebnislayout JSON zu generieren.

![Bildschirmaufnahme eines Beispiellayouts auf der Seite "Suchlayout-Designer", auf dem ein Feld ausgewählt und der Eigenschaftenbereich geöffnet ist.](media/Verts-SearchLayoutDesigner.png)

Wählen Sie ein Feld im Layout aus, um die Variablen hervorzuheben, die zugeordnet werden müssen. Sie können mehrere Variablen für ein einzelnes Feld verwenden, und alle Felder müssen den Ergebniseigenschaften zugeordnet werden.

### <a name="show-snippet-on-search-result"></a>Codeausschnitt im Suchergebnis anzeigen  

Dynamische Codeausschnitte, die für die **Inhaltseigenschaft** des Connectorergebnisses generiert werden, können im Suchergebnis angezeigt werden. **ResultSnippet** ist die Systemeigenschaft, die als Platzhaltereigenschaft für die Codeausschnitte fungiert, die für jedes Connector-Ergebnis generiert werden. Um die Codeausschnitte im Ergebnislayout anzuzeigen, muss die **ResultSnippet-Systemeigenschaft** einem entsprechenden Feld zugeordnet werden, z. B. Beschreibung im Suchergebnislayout. Codeausschnitte, die für jedes Ergebnis generiert werden, markieren auch die Übereinstimmungen im Codeausschnitt mit dem vom Benutzer eingegebenen Abfragebegriff.

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte

Bevor Sie beginnen, sollten Sie ein paar Dinge tun, und einige Dinge, die Sie vermeiden sollten, um sicherzustellen, dass Ihre Layouts erfolgreich sind.

### <a name="do"></a>Dos

- Bearbeiten Sie eine Vorlage, um den Logolink im Layout bereitzustellen, wenn Sie statische Links für Logos und keine Ergebniseigenschaften verwenden.
- Überprüfen Sie das Ergebnislayout für Szenarien, in denen keine Daten für eine Ergebniseigenschaft zurückgegeben werden, die im Ergebnis-JSON-Code verwendet wird. Verwenden Sie die `$when` Bedingung, um ein Element auszublenden, wenn die Eigenschaft keine Daten enthält.  
- Stellen Sie sicher, dass Datentypen der `$when` Bedingung und die Ergebniseigenschaft übereinstimmen. Vergleichen Sie z. B. nicht `Number` mit `Text` der `$when` Bedingung.  
- Denken Sie beim Entwerfen eines Ergebnislayouts an die Designanforderungen.  
- Stellen Sie sicher, dass das `Textblock`   Element dynamischen Inhalt verarbeiten kann. Sie können die `wrap` Eigenschaften und `maxLines` Elementeigenschaften für diesen Zweck verwenden.
- Richtig formatieren Sie das Datum bei Verwendung `{DATE()}` in Markdown.  

### <a name="dont"></a>Don’ts

- Definieren Sie beim Binden von Werten keine ungültigen Datentypen. Weitere Informationen zu Datentypen finden Sie unter [Verwalten des Suchschemas.](/sharepoint/search/manage-the-search-schema)
- Vermeiden Sie das Zuschneiden des Ergebnisses auf der Ergebnisseite, indem Sie der maximalen Höhe des Ergebnislayout-JSON folgen. Wenn Sie die maximale Höhe des Ergebnislayouts überschreiten, wird das Ergebnis auf der Ergebnisseite zugeschnitten.
- Verwenden Sie keine `px` Werte in Elementeigenschaften.
- Verwenden Sie markdown nicht mit der **ResultSnippet-Eigenschaft** im Ergebnislayout, um die Abfrageüberstimmung im Suchergebnis hervorzuheben.

## <a name="resources"></a>Ressourcen

[Anpassen der Suchergebnisseite](customize-search-page.md)

[Adaptive Karten](/adaptive-cards/authoring-cards/getting-started)

[Sprache der Vorlage für adaptive Karten](/adaptive-cards/templating/language)

[Schema adaptiver Karten](https://adaptivecards.io/explorer/)
