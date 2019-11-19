---
title: Bewährte Methoden für Microsoft Search-Grundrisse
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Bewährte Methoden für Microsoft Search-Grundrisse
ms.openlocfilehash: ddad671592ab3cf05400faa1261ee7258f3868bb
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699852"
---
# <a name="best-practices-for-microsoft-search-floor-plans"></a>Bewährte Methoden für Microsoft Search-Grundrisse

Um die Microsoft Search-Grundrisse erfolgreich zu implementieren, müssen Sie drei Datenteile koordinieren:

- **Erstellen von Standortdaten**: welches Format und wie kann hinzugefügt werden?
- **Grundriss Karte im DWG-Format**: Wie kann ich anzeigen und welche Daten für einen maximalen Erfolg enthalten?
- **Mitarbeiter Bürostandort in [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/)**: welches Format soll verwendet werden und wie hinzugefügt werden? <br>

Die bewährten Methoden zum Bereitstellen von Microsoft Search-Grundrissen werden in den folgenden Abschnitten ebenfalls beschrieben.

## <a name="building-location-data"></a>Erstellen von Standortdaten
Bevor Sie Grundrisse hinzufügen, müssen Sie Ihre Gebäude zu Microsoft-Such Standorten hinzufügen. Geben Sie die folgenden erforderlichen Gebäudedaten an:

|Erforderliche Gebäudedaten  |Beispiel  |
|---------|---------|
|Name     |    Gebäude 1, New York City     |
|Adresse     |     123 any Avenue, New York, NY 10118  |
|Längengrad (optional)   |    40,760539,-73,975341      |
|Schlüsselwörter     |    Büro in New York, Gebäude 1, Hauptniederlassung, Hauptsitz     |

Sie können mehrere Gebäude gleichzeitig hinzufügen, indem Sie das **Import** -Feature auf der Registerkarte **Speicherorte** verwenden, anstatt jeweils einen Ort hinzuzufügen. Mit dem **Import** -Feature können Sie den Breitengrad angeben. Weitere Informationen finden Sie unter [Verwalten von Speicherorten](manage-locations.md).

## <a name="floor-plan-map-in-dwg-format"></a>Grundriss Karte im DWG-Format
Um Maps in Microsoft Search zu erstellen, müssen Sie Grundrisse im DWG-Format mit spezifischen Informationen hochladen. Informationen zum Erstellen und Anzeigen von DWG-formatierten Dateien finden Sie unter [DWG Viewer](https://www.autodesk.in/products/dwg). 

Grundriss Karten zeigen vier Elemente an:

1. **Raumnummern**: im folgenden Beispiel werden Raumnummern als **B1 1001** und **B1 1002**definiert. **B1** ist der GEBÄUDECODE, und **1001** enthält die stockwerksnummer **1** und die Office-Nummer **001**.
1. **Raumlayouts.**: zur Klärung von Details, wenn mehrere Benutzer ein Büro teilen, können Sie Layouts wie Stühle und Schreibtisch definieren.
1. **Raumtypen**: einige Beispiele sind Büro, Korridor, offener Bereich und Toilette.
1. **Objektinformationen**: Wenn sich Benutzer in einem offenen Bereich befinden, können Sie angeben, an welchem Schreibtisch Sie sitzen. In diesem Beispiel werden die Schreibtische von **TB1** und **TB2**bezeichnet.

![Einfache Office-Karte mit der Bezeichnung von Raumnummern, Objekten und Raumtypen](media/Floorplans-LayoutwithCallouts.png)

In diesem Diagramm sind die Raumnummern das wichtigste Element. Sie werden dem Bürostandort einer Person in Ihrem Benutzerkonto zugeordnet, wie in der folgenden Abbildung dargestellt.

![Registerkarte "Übersicht" der Personen Suchergebnis Karte mit den Details des Benutzers, einschließlich des Office-Standorts](media/floorplans-peoplecard.png)

Diese Informationen werden in [Azure AD](https://azure.microsoft.com/services/active-directory/) in der **PhysicalDeliveryOfficeName** -Eigenschaft gespeichert. Im Microsoft 365 [Admin Center](https://admin.microsoft.com)wird es als **Office** -Eigenschaft bezeichnet und kann in **aktive Benutzer**hinzugefügt werden.

### <a name="dwg-files"></a>DWG-Dateien
Microsoft Search erfordert Grund Plandateien in DWG, einem [AutoCAD](https://www.autodesk.com/autocad) -Zeichnungsformat. Die Dateien müssen **Layout** -und **Bezeichnungs** Daten enthalten. **Raumnummern** sind die wichtigsten Beschriftungen für Grundrisse.

Es wird empfohlen, dass Sie Ihr Büronummern System mit der in der folgenden Tabelle dargestellten Exact-Match-Methode erstellen. Sie sind jedoch nicht auf diese Bezeichnung limitiert. Wenn beispielsweise der Bürostandort des Benutzers in [Azure AD](https://azure.microsoft.com/services/active-directory/) **B1 1001**ist, können Sie die Raumnummer in der DWG-Datei mit einer der folgenden Optionen bezeichnen.

|Vergleich  |Layout  |
|---------|---------|
|Exakte Übereinstimmung mit dem Office-Standort (empfohlen) <br> **B1 1001** <br> GEBÄUDECODE: B1<br>Floor: 1 <br>Zimmer Nummer: 001    |    ![Einzelner Büro Grundriss mit der Büronummer "B1 1001"](media/floorplans-layoutexactmatch.png)     |
|Übereinstimmung Zwischengeschoss Decke und Raumnummer <br> **1001**<br>Floor: 1 <br>Zimmer Nummer: 001    |   ![Einzelner Office-Grundriss mit der Office-Nummer "1001"](media/floorplans-layoutfloorroom.png)   |
|Nur Raumnummer abgleichen <br> **1**<br>Zimmer Nummer: 1        |    ![Einzelne Office Floor-Karte mit der Office-Nummer "1"](media/floorplans-layoutroomonly.png)     |

## <a name="user-account-office-location"></a>Benutzerkonto-Office-Standort
Um den Standort eines Mitarbeiters zuzuordnen, werden die Raumnummern in DWG-Dateien den Office-Speicherorten im Konto des Benutzers in [Azure AD](https://azure.microsoft.com/services/active-directory/)zugeordnet. Die **Office-Standort** Eigenschaft muss mit den Office-Standortinformationen in der DWG-Datei übereinstimmen.

In der folgenden Tabelle werden die bewährten Methoden für die Zuordnung von Standortdaten erläutert:

|Bewährte Methode  |Erklärung |
|---------|---------|
|Fügen Sie GEBÄUDECODE, Geschossdecke und Raumnummer ein.     |   Mit diesen Daten erhalten Sie die beste Möglichkeit, exakte Übereinstimmungen zu erstellen.     |
|Fügen Sie nach dem Erstellen von Codes und geschossen ein Trennzeichen ein.     |  Trennen Sie die Bausteine von Boden-und Raumnummern mit einem Trennzeichen oder einem Leerzeichen, wie in den folgenden Beispielen dargestellt:<br> B1 1001<br> B1/1001 <br> B1-1001.   |
|Raumnummer folgt immer GEBÄUDECODE-, Flügel-und Bodeninformationen.     |  Wenn die Raumnummer **1001**ist, legen Sie den Office-Standort auf **B1 1001**, **B1/1001**oder **B1-1001**fest. <br> Wenn die Raumnummer **F1-001**ist, legen Sie den Office-Standort auf **B1 F1-001** oder **B1/F1-001**fest. <br> Wenn die Raumnummer **1**ist, legen Sie die [Azure AD](https://azure.microsoft.com/services/active-directory/) Position auf **B1 1001**, **B1/1001**oder **B1-F1-001**fest.       |
|

## <a name="next-steps"></a>Nächste Schritte
[Verwalten von Speicherorten](manage-locations.md)<br>
[Verwalten von Grundrissen](manage-floorplans.md)