---
title: Verwalten von Grundrissen
ms.author: rasrivas
author: rasrivas
manager: tonytha
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Das Feature "Grundrisse" in der Microsoft-Suche hilft Benutzern, Personen, Büros und andere Annehmlichkeiten in einem Gebäude zu finden.
ms.openlocfilehash: 9871cda3790f210dc0c406d1d29abe2c571c1085
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626792"
---
# <a name="manage-floor-plans"></a>Verwalten von Grundrissen

Die Microsoft-Such Bodenpläne helfen Benutzern, Personen und Besprechungsräume in einem Gebäude zu finden. Grundrisse Beantwortung dieser Fragen:
- Wo ist Allan deyoungs Büro?
- Wo befindet sich der Besprechungsraum C1?

![Grundriss Karte, die den Bürostandort des Benutzers innerhalb des Gebäudes identifiziert.](media/floorplans-officelocation.png)

Damit Sie einfach Antworten auf Fragen wie diese finden, müssen Informationen zu den Gebäuden, Büros und Einrichtungen einer Organisation verfügbar sein und durchsuchbar gemacht werden. Größere Organisationen verfügen in der Regel über Einrichtungen oder Raum Verwaltungsteams, die diese Informationen möglicherweise bereits verfügbar haben. In einer kleineren Organisation muss der Suchadministrator möglicherweise erstellen und hinzufügen.

## <a name="48-hours-before-you-begin"></a>48 Stunden, bevor Sie beginnen
Bevor Sie mit dem Hochladen von Grundrissen beginnen, müssen Sie die Office-Standorte der Benutzer indizieren. Je nach Größe Ihrer Organisation kann es bis zu 48 Stunden dauern. Wenn Sie diesen Schritt ignorieren, erhalten Sie Fehler beim Ausführen des Verfahrens.

![Seite "Bildschirmaufzeichnung der Grundrisse" mit "Microsoft muss Office-Standorte sammeln und organisieren, bevor Sie die Grundrisse hochladen können" Hinweis.](media/floorplans_hydrationstep.png)

Wechseln Sie im Microsoft [365 Admin Center](https://admin.microsoft.com)zu **Einstellungen** > **Microsoft-Such** > **Bodenpläne**, und wählen Sie dann **Erste Schritte**aus.

Wenn dieser Hinweis nicht angezeigt wird, haben Sie oder eine Person in Ihrer Organisation diesen Schritt bereits eingeleitet.

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte
Um Benutzern zu helfen, Informationen zu Büros und Gebäude Einrichtungen zu finden, müssen Sie Folgendes hinzufügen:

|Berücksichtigt     |Warum ist dies so wichtig?  |
|---------|---------|
|Gebäude Standort    |    Sie müssen jedes Gebäude an Microsoft-Suchspeicherorten hinzufügen. Sie sollten ein Standard Benennungsformat für jedes Gebäude erstellen. Sie können das Gebäude mithilfe einer Straßenadresse oder Kartenkoordinaten hinzufügen.     |
|**Office** -Eigenschaft für alle Benutzerkonten     |    Jedes Benutzerkonto muss über die **Office** -Eigenschaft mit Ihrem Office-Standort verfügen. Und Office-Standorte sollten einem Standardformat entsprechen und Informationen zu Gebäude, Boden und Raum enthalten.   <br> In Azure AD wird diese Eigenschaft als **PhysicalDeliveryOfficeName**bezeichnet.    |
|Grundriss Datei im DWG-Format     |   Sie benötigen einen separaten Grundriss für jede Etage oder einen Flügel Ihres Gebäudes und fügen die Office-Informationen in das gleiche Format ein, das Sie in der Office-Eigenschaft des Benutzers verwendet haben. Die Datei muss sich im DWG-Format von AutoCAD Drawing befinden. |

Weitere Informationen finden Sie unter [Best Practices for Microsoft Search Floor Plans](floorplans-bestpractices.md).

## <a name="building-location"></a>Gebäude Standort

Identifizieren der Gebäude, die als Standorte hinzugefügt werden müssen. Die Standortadresse und die Kartenkoordinaten eines Gebäudes sind der erste Identifikationspunkt. Wenn das Gebäude noch nicht als Standort hinzugefügt wird, muss der Administrator es hinzufügen. Weitere Informationen finden Sie unter [Verwalten von Speicherorten](manage-locations.md) .

## <a name="floor-plans-files"></a>Grund Riss Dateien

Nachdem ein Gebäude identifiziert wurde, können Sie seine Grundrisse hinzufügen. Alle Grundriss Dateien müssen im DWG-Format vorliegen. Wenn Ihre Organisation diese nicht bereits hat, müssen Sie die Grundrisse in einer DWG-kompatiblen app erstellen. Grundrisse müssen alle Räume, einschließlich Konferenz-oder Besprechungsräume, Toiletten, Küchen, e-Mail-Räume und andere Einrichtungen auf jeder Etage des Gebäudes ordnungsgemäß zuordnen, um die Suche zu ermöglichen.

### <a name="office-locations"></a>Office-Standorte

Um grundrissplänen zugeordnet zu werden, müssen alle Office-Standorte und Mitarbeiter-Office-Daten im Konto des Benutzers liegen. Im Grundriss müssen die Office-Standorte eindeutig sein und dürfen nicht wiederholt werden. Wenn beispielsweise zwei Personen Office 2/1173 teilen, kann **2/1173** nur eine eindeutige Instanz in ihren Grundrissen haben, die Benutzerkonten in Azure AD jedoch beide denselben Bürostandort haben.

![Floorplans-peoplecard. png](media/floorplans-peoplecard.png)

 > [!Note] 
 > Wenn ein Benutzer nach einem Raum oder Büro Speicherort eines Kollegen sucht, werden die Raumnummern in Grundrissen mit Office-Standorten in Azure AD abgeglichen. Wenn eine Übereinstimmung gefunden wird, wird die Zuordnung angezeigt.

## <a name="add-floor-plan"></a>Grund Riss hinzufügen

 Wenn Sie zum ersten Mal zu Grundrissen wechseln, wird möglicherweise oben auf der Seite eine Notiz angezeigt, die besagt, dass *Microsoft Office-Standorte sammeln und organisieren muss, bevor Sie Grundrisse hochladen können*. Wählen Sie erste **Schritte** aus, um Ihre Azure AD Office-Standorte zu indizieren. 

1. Wechseln Sie im [Admin Center](https://admin.microsoft.com)zu **Einstellungen** > **Microsoft-Such** >**Bodenpläne**, und wählen Sie dann **Grundrisse hinzufügen**aus.
4. Wählen Sie das Gebäude in der Dropdownliste aus, und wählen Sie **weiter**aus. Wenn das Gebäude nicht aufgeführt ist, müssen Sie es an Standorten hinzufügen. Weitere Informationen finden Sie unter [Verwalten von Speicherorten](manage-locations.md) .
6. Wählen Sie **Dateien hochladen**aus, und wählen Sie dann den Grundriss aus, den Sie hochladen möchten. 
1. Nachdem die Datei erfolgreich hoch lädt, müssen Sie ermitteln, wie die Boden Nummer oder der Flügel dargestellt wird. 
7. Geben Sie den Code zum Identifizieren des Gebäudes ein. Der GEBÄUDECODE befindet sich im Konto des Benutzers in der Office- **Standort** Eigenschaft. Wenn beispielsweise der Office-Standort des Benutzers **2/1173**lautet, ist Building Code **2**. 
9. Überprüfen und identifizieren Sie die Standort Muster für alle hochgeladenen Grundrisse, und wählen Sie dann **weiter**aus.
10. Wenn Sie bereit sind, wählen Sie **veröffentlichen** aus, um den Grundriss durchsuchbar zu machen.

> [!Note] 
> Wenn sich ein Grundriss in einem Entwurfszustand befindet, ist er unvollständig. Mit einem Entwurf können sich die Beteiligten beim Hochladen und Erstellen von Grundrissen koordinieren. Außerdem können Sie Grundrisse stufenweise bereitstellen.

## <a name="edit-floor-plans"></a>Bearbeiten von Grundrissen

1. Wechseln Sie im [Admin Center](https://admin.microsoft.com)zu **Einstellungen** > **Microsoft-Such** > **Grundrisse**. 
1. Wählen Sie **veröffentlicht** oder **Entwurf**aus, wählen Sie den Grundriss aus, den Sie ändern möchten, und wählen Sie dann **Bearbeiten**aus.
5. Nehmen Sie die gewünschten Änderungen vor, und wählen Sie dann **Speichern**aus.

## <a name="troubleshoot-errors"></a>Beheben von Fehlern

Sie können den nächsten Schritt zur Definition von Boden-, Flügel-und Rauminformationen erst dann durchführen, wenn alle Fehler behoben sind. In der folgenden Tabelle werden Fehlermeldungen zu Dateiuploads und Aktionen zum Beheben der Probleme aufgeführt.

| Fehlermeldung   | Typ    | Aktion       |
|:----------------| :--------- | :-------------- |
| CC_1. DWG kann nicht gelesen werden. Laden Sie den Grundriss erneut hoch oder löschen Sie ihn. | Fehler |  Versuchen Sie erneut, die Datei hochzuladen. Wenn dies nicht funktioniert, löschen Sie die Datei, und versuchen Sie es dann erneut. |
| Es gibt zwei Dateien mit dem Namen CC_1. dwg. Löschen Sie eine dieser oder laden Sie Sie mit einem anderen Namen erneut hoch.| Fehler | Wenn der Dateiname falsch ist, machen Sie den Dateinamen durch Hinzufügen von Floor-oder Wing-Informationen eindeutig, und laden Sie die Datei erneut hoch. <br><br>Wenn Sie die gleiche Datei versehentlich zweimal hinzugefügt haben, löschen Sie Sie einfach. |
| Keine Daten gefunden. | Fehler | Überprüfen Sie Ihre Datei, um sicherzustellen, dass Sie richtig ist, und laden Sie Sie dann erneut hoch, oder löschen Sie Sie. |
| In dieser Datei fehlen externe Verweise. Laden Sie entweder "CC_1_furniture. DWG" hoch, oder löschen Sie diese Datei. | Warnung | Externe Referenzdateien hochladen oder löschen.|
| In der DWG-Datei konnten keine Raumnummern oder Tags gelesen werden. Löschen Sie diese Datei. | Warnung | Überprüfen Sie Ihre DWG-Datei, um sicherzustellen, dass die Daten enthalten sind, und löschen Sie die Datei, und versuchen Sie es erneut. |
