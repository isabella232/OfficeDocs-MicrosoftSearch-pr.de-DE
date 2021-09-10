---
title: Verwalten von Grundrissenplänen
ms.author: rasrivas
author: rasrivas
manager: tonytha
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Das Grundriss-Feature in Microsoft Search hilft Benutzern, Personen, Büros und andere Einrichtungen in einem Gebäude zu finden.
ms.openlocfilehash: beeef26cc7413da654cc3ab01d92aa6cdc74e5cb
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973667"
---
# <a name="manage-floor-plans"></a>Verwalten von Grundrissenplänen

Grundrisse in **Microsoft Search** Benutzern helfen, Personen und Besprechungsräume in einem Gebäude zu finden. Grundrisse beantworten die folgenden Fragen:

- Wo befindet sich allan Deyoungs Büro?
- Gebäude 2 Stockwerk 3
- 02.02.11173 finden

## <a name="add-floor-plans"></a>Hinzufügen von Grundrissen

Führen Sie die folgenden Schritte aus, um die Antworten auf Grundrisse in **Microsoft Search** einzurichten.

### <a name="step-1-determine-your-building-codes"></a>Schritt 1: Ermitteln der Gebäudecodes

Gebäudecodes werden als Teil des Bürostandorts eines Benutzers verwendet. Sie verwenden diese Codes beim Aktualisieren von Benutzerprofilen. Nehmen wir an, Ihre Organisation hat ein Gebäude an diesem Ort: *Gebäude 2, 350 5th Avenue, New York City, NY 10016*

Hier sind einige gute Beispiele für den Code dieses Gebäudes: 2, B2, Building2, Building 2 oder NYCB2. Jedes Gebäude muss einen eindeutigen Code aufweisen.

### <a name="step-2-review-your-floor-plans"></a>Schritt 2: Überprüfen Ihrer Grundrisse

Grundrissedateien müssen im DWG-Format vorliegen; DWG-Dateien können Textbeschriftungen enthalten. Wenn eine Textbeschriftung einen Raum kennzeichnet, wird sie als Raumbeschriftung bezeichnet. Die DWG-Datei muss **mindestens 10 Räume** aufweisen, die mit Beschriftungen gekennzeichnet sind. Hier sind einige Beispiele für DWG-Dateien mit unterschiedlichen Bezeichnungstypen:

|**Textbeschriftungen einschließlich Raumbeschriftungen**|**Textbeschriftungen, aber keine Raumbeschriftungen**|**Keine Textbeschriftungen**|
|:-----:|:-----:|:-----:|
|![floorplans-textandroomlabels.png.](media/floorplans-textandroomlabels.png)|![floorplans-textnoroomlabels.png](media/floorplans-textnoroomlabels.png)|![floorplans-nolabels.png](media/floorplans-nolabels.png)|

Informationen zum Anzeigen und Aktualisieren von DWG-Dateien finden Sie im Abschnitt ["Häufig gestellte Fragen".](#frequently-asked-questions)

### <a name="step-3-update-office-locations-on-user-profiles"></a>Schritt 3: Aktualisieren von Office-Speicherorten in Benutzerprofilen

Der Bürostandort eines Benutzers ist eine Kombination aus einem Gebäudecode und einer Raumbezeichnung. Wenn die Gebäudecode beispielsweise *2* und die Raumbeschriftung *1173* ist, würde der Bürostandort *2/1173* sein.

Hinzufügen oder Aktualisieren von Office-Speicherorten für jeden Benutzer in Ihrer Organisation. Sie können den Bürostandort im Benutzerprofil im [Microsoft 365 Admin Center](https://admin.microsoft.com) ändern oder in Ihrem lokalen Active Directory so ändern, dass es mit Azure Active Directory synchronisiert wird. *PhysicalDeliveryOfficeName* ist das Feld, das für den Bürostandort verwendet wird. Wenn Ihre Raumbeschriftungen keine Bodennummern enthalten, finden Sie in den häufig gestellten Fragen Tipps.

In diesem Beispiel befindet sich das Büro von Allan im Raum 1173 im Stock 1 von Gebäude 2.
![floorplans-userlestview.png.](media/floorplans-userlistview.png)

> [!NOTE]
> Um aktualisierte Bürostandorte bei der Suche nach Grundrissen anzuzeigen, müssen Sie die Bürostandorte für **mindestens 10 Personen** pro Stockwerk aktualisieren.

### <a name="step-4-verify-office-location"></a>Schritt 4: Überprüfen des Bürostandorts

Verwenden Sie **Microsoft Search,** um einen Benutzer zu finden und zu überprüfen, ob sein Büroort korrekt angezeigt wird. Wenn Sie gerade Speicherorte aktualisiert haben, müssen Sie möglicherweise bis zu **72 Stunden** warten, bis die Updates in den Suchergebnissen angezeigt werden.

![floorplans-peoplecard.png.](media/floorplans-peoplecard.png)

### <a name="step-5-add-building-locations"></a>Schritt 5: Hinzufügen von Gebäudestandorten

Grundrisse verwenden [Standorte,](manage-locations.md) um Ihre Gebäude zu definieren. Wechseln [Sie im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Speicherorten,**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/locations)und wählen Sie dann **Hinzufügen** aus. Geben Sie den Namen, die Adresse und die Schlüsselwörter für das Gebäude ein. Fügen Sie beliebig viele Gebäude hinzu.

![floorplans-locations.png.](media/floorplans-locations.png)

Weitere Informationen zu Speicherorten finden Sie unter [Verwalten von Standorten](manage-locations.md)

### <a name="step-6-gather-and-organize-office-locations"></a>Schritt 6: Sammeln und Organisieren von Bürostandorten

Bevor Sie Grundrisse verwenden können, müssen Bürostandorte indiziert werden. Dies ist ein einmaliger Vorgang, der bis zu 48 Stunden dauern kann. Die Gesamtzeit hängt von der Größe Ihrer Organisation ab.

Wechseln Sie [im Admin Center](https://admin.microsoft.com)zu [**Grundrissenplänen,**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/floorplans)und wählen Sie dann **"Erste Schritte" aus.** Wenn dieser Hinweis nicht angezeigt wird, wurde dieser Schritt bereits für Ihre Organisation abgeschlossen.

![floorplans_hydrationstep.png.](media/floorplans_hydrationstep.png)

### <a name="step-7-upload-floor-plans"></a>Schritt 7: Hochladen Grundrisse

1. Wechseln [Sie](https://admin.microsoft.com)im Admin Center zu [**"Grundrisse".**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/floorplans)
2. Wählen Sie in der Dropdownliste ein Gebäude aus, und wählen Sie **"Weiter"** aus. Wenn das Gebäude nicht aufgeführt ist, wechseln Sie zurück, und [fügen Sie Gebäudestandorte hinzu.](#step-5-add-building-locations)
3. Wählen Sie **Hochladen Dateien** aus, und wählen Sie dann den Grundplan aus, den Sie hochladen.
4. Wenn der Upload abgeschlossen ist, müssen Sie die Floor-Nummer eingeben, die in der Grundrissdatei dargestellt ist. Wählen Sie dann **Weiter** aus.
5. (Optional) Wenn Ihr Stockwerk Über- oder Zonen verfügt, geben Sie dieses Detail ein.
6. Es wird ein Prüfbildschirm mit der Anzahl der Bürostandorte angezeigt, die den Grundrissen zugeordnet wurden. Wählen Sie **Details** aus, um sicherzustellen, dass die Zuordnung korrekt ist.
    - Wenn keine Benutzer zugeordnet sind oder Sie mit der Zuordnung nicht zufrieden sind, wählen Sie **"Zuordnung fortsetzen"** aus. Wählen Sie zum Veröffentlichen **"Überspringen" und "Veröffentlichen"** aus.
7. Geben Sie den Gebäudecode für diesen Grundriss ein. Der Gebäudecode befindet sich in der Office Location-Eigenschaft des Benutzers. Wenn beispielsweise der Bürostandort eines Benutzers **2/1173** ist, ist der Gebäudecode **2**.
8. Wiederholen Sie auf dem Prüfbildschirm Schritt 6, um sicherzustellen, dass die Zuordnung korrekt ist.
9. (Optional) Überprüfen und identifizieren Sie die Standortmuster für alle hochgeladenen Grundrisse, und wählen Sie dann **"Weiter"** aus.
10. Wiederholen Sie auf dem Prüfbildschirm Schritt 6, um sicherzustellen, dass die Zuordnung korrekt ist.
11. Wenn Sie bereit sind, wählen Sie **Veröffentlichen** aus, um den Grundplan in **Microsoft Search** verfügbar zu machen.

> [!NOTE]
> **Es dauert 48 Stunden, bis die Grundrisse veröffentlicht wurden.** Danach sehen Ihre Benutzer ein Stockwerksplanergebnis ähnlich dem unten stehenden, wenn sie nach einem Büro eines Kollegen suchen.

![floorplans-officelocation.png.](media/floorplans-officelocation.png)

### <a name="step-8-optional-specify-location-patterns"></a>Schritt 8: (Optional) Angeben von Standortmustern

Nach dem Hochladen eines Grundrisses werden die Textbeschriftungen mit den Bürostandorten in den Profilen Ihrer Benutzer verglichen. Wenn weniger als 10 Übereinstimmungen vorhanden sind, wird der Bildschirm **"Positionsmuster angeben"** angezeigt. Standortmuster werden verwendet, um Boden-, Wing- und Rauminformationen aus Bürostandorten zu extrahieren.

![floorplans-locationpattern.png.](media/floorplans-locationpattern.png)

Es ist nur Platz erforderlich, Boden und Wing sind optional, und Sie können standorte nach Bedarf überspringen.

## <a name="edit-floor-plans"></a>Bearbeiten von Grundrissenplänen

Um einen vorhandenen Grundriss zu aktualisieren, wählen Sie den Grundplan aus, den Sie ändern möchten, und wählen Sie dann **Bearbeiten** aus. Nehmen Sie Ihre Änderungen vor, und speichern Sie sie.

## <a name="troubleshooting"></a>Problembehandlung

|**Schritt**|**Fehlermeldung**|**Typ**|**Aktion**|
|:-----|:-----|:-----|:-----|
|Hochladen Grundrisse|CC_1.dwg kann nicht gelesen werden. Laden Sie den Grundplan erneut hoch oder löschen Sie ihn.|Fehler|Versuchen Sie erneut, die Datei hochzuladen. Wenn dies nicht funktioniert, löschen Sie die Datei, und versuchen Sie es erneut.|
|Hochladen Grundrisse|Es gibt zwei Dateien mit dem Namen CC_1.dwg. Löschen Sie einen dieser Elemente, oder laden Sie ihn mit einem anderen Namen erneut hoch.|Fehler|Wenn der Dateiname falsch ist, machen Sie den Dateinamen eindeutig, indem Sie Boden- oder Wing-Informationen hinzufügen und die Datei dann erneut hochladen. Wenn Sie versehentlich die gleiche Datei zweimal hinzugefügt haben, löschen Sie sie einfach.|
|Hochladen Grundrisse|Es wurden keine Daten gefunden.|Fehler|Überprüfen Sie Ihre Datei, um sicherzustellen, dass sie die richtige ist, und laden Sie sie dann erneut hoch, oder löschen Sie sie.|
|Hochladen Grundrisse|Externe Verweise fehlen in dieser Datei. Laden Sie entweder CC_1_furniture.dwg hoch, oder löschen Sie diese Datei.|Warnung|Hochladen externen Referenzdateien oder löschen.|
|Hochladen Grundrisse|Raumnummern oder Tags in der DWG-Datei konnten nicht gelesen werden. Löschen Sie diese Datei.|Warnung|Überprüfen Sie Ihre DWG-Datei, um sicherzustellen, dass die Daten enthalten sind, löschen Sie die Datei, und versuchen Sie es erneut.|
|Verknüpfen von Bürostandorten|In Azure Active Directory wurden keine Bürostandorte gefunden. Fügen Sie Standortdaten zu Azure Active Directory hinzu, bevor Sie Grundrisse einrichten.|Fehler|[Aktualisieren von Office-Speicherorten in Benutzerprofilen](#step-3-update-office-locations-on-user-profiles) |

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F:** Wie kann ich DWG-Dateien anzeigen und bearbeiten?

**A:** Verwenden Sie eine der folgenden Optionen, um DWG-Dateien anzuzeigen:

- Hochladen die Datei, um sie zu SharePoint und zu öffnen.
- Öffnen Sie die Datei in [Microsoft Visio](https://support.office.com/article/Open-insert-convert-and-save-DWG-and-DXF-AutoCAD-drawings-60cab691-0f4c-4fc9-b775-583273c8dac5) oder [Einem DWG TrueView](https://www.autodesk.com/products/dwg).
- Hochladen Sie die Datei an [den Online Viewer weiter.](https://viewer.autodesk.com/)

**F:** Wie füge ich Textbeschriftungen zu nicht gekennzeichneten Räumen hinzu?

**A:** Öffnen Sie die DWG-Datei in einem Editor, und [fügen Sie Raumbeschriftungen hinzu.](https://knowledge.autodesk.com/support/autocad-map-3d/learn-explore/caas/CloudHelp/cloudhelp/2019/ENU/MAP3D-Learn/files/GUID-4854F184-6279-4E0C-9487-34A4759017F6-htm.html)

**F:** Wie erstelle oder bearbeite ich DWG-Dateien zu Testzwecken?

**A:** Erstellen Sie eine DWG-Datei in Microsoft Visio, AutoCAD oder einem anderen DWG-Editor. Stellen Sie sicher, dass in der Datei 10 oder mehr Räume mit Bezeichnungen versehen sind.

**F:** Was ist das beste Format für Textbeschriftungen in DWG-Dateien?

**A:** Um die besten Ergebnisse zu erzielen, sollten Textbeschriftungen Bodennummern und Raumnummern enthalten. In den folgenden Beispielen wird 2 oder SC für den Gebäudecode verwendet.
<!-- markdownlint-disable no-inline-html -->
|Raumbeschriftungstypen|Untergrenze|Raum|Beispieltextbeschriftung|Office Speicherort (Gebäudecode/Textbeschriftung)|
|:-----|:-----|:-----|:-----|:-----|
|Hat Stockwerk und Raumnummer|1|173|1173|2/1173|
|| 21|45|21045|2/21045|
||23|100 KB|23-100 KB|23.02.100 KB|
||1|G06-07|1G06-07|2/1G06-07|
||2|1024A|02.1024A|02.02.1024A|
||2|1024A|02.1024A|02.02.1024A|
||2|105.01|2105.01|2/2105.01|
|Verfügt über Gebäudecode, Stockwerk und Raumnummer|0|X-11-M-12|2-0-X-11-M-12|2/2-0-X-11-M-12<br/>2-0-X-11-M-12|
||2|128A|22128A|2/22128A<br/>22128A|
||1|B2-11|21-B2-11|21.02.2012-B2-11<br/>21-B2-11|
||2|45|SC2045|SC/SC2045<br/>SC2045|

**F:** Kann ich eine DWG-Datei verwenden, die keine Bodennummern enthält?

**A:** Ja, sie können dies. Wenn Sie Bürostandorte im Azure Active Directory Profil des Benutzers aktualisieren, fügen Sie die Stockzahl als Teil der Raumnummer ein, auch wenn sie in der DWG-Datei fehlt. Nachdem Sie die Datei hochgeladen haben, wird der Bildschirm "Speicherortmuster angeben" angezeigt, und Sie können beide Werte angeben.

Eine DWG-Datei, die Raumnummern, aber keine Bodennummern enthält, sieht z. B. wie folgt aus:

![floorplans-nofloors.png.](media/floorplans-nofloors.png)

Der Bürostandort im Profil des Benutzers sollte 2/1175 sein, wobei "2" der Gebäudecode, "1" die Stockwerksnummer und "175" die Raumnummer ist.
