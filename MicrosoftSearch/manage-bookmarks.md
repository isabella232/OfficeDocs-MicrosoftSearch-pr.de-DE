---
title: Verwalten von Lesezeichen
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Erstellen und Aktualisieren von Lesezeichen und Möglichkeiten zum Massen bearbeiten von Lesezeichen Ergebnissen für Microsoft Search
ms.openlocfilehash: eb65121b53ab110b91880a65a5146d868f3a7405
ms.sourcegitcommit: d88226f9c3a99540a591dc0a26408bb9960cf39a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2020
ms.locfileid: "48134167"
---
# <a name="manage-bookmarks"></a>Verwalten von Lesezeichen

Sie können ein Lesezeichen in wenigen Schritten erstellen. Jedes Lesezeichen enthält einen Titel, eine URL und eine Gruppe von Schlüsselwörtern, die es auslösen. Sie können auch Kategorien zu einer Textmarke hinzufügen, die zum Sortieren und Filtern im Administratorportal verwendet werden kann. Eine Textmarke kann mehrere Schlüsselwörter enthalten, und Lesezeichen können dasselbe Schlüsselwort verwenden, aber reserviertes Schlüsselwort kann nicht freigegeben werden. Wenn eine Textmarke erstellt oder geändert wird, wird der Suchindex sofort aktualisiert, und die Textmarke steht Benutzern sofort zur Verfügung.

Wenn Ihre Organisation heraufgestufte Ergebnisse in SharePoint eingerichtet hat, können Sie die heraufgestuften Ergebnisse in **Microsoft Search** importieren und die importierten Inhalte ihren Benutzern zur Verfügung stellen. Dies ist eine einfache Möglichkeit, Suchergebnisse schnell aufzufüllen, sobald Sie **Microsoft Search** einrichten, und es für Ihre Benutzer effektiver zu gestalten. Es wird empfohlen, höher gestufte Ergebnisse aus SharePoint als Referenz zu verwenden, um zu verstehen, wie relevante Suchergebnisse benannt und erstellt werden.

## <a name="add-or-edit-a-single-bookmark"></a>Hinzufügen oder Bearbeiten eines einzelnen Lesezeichens

1. Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Lesezeichen**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Zum Hinzufügen einer Textmarke wählen Sie **Hinzufügen**aus.
Wählen Sie zum Bearbeiten eines Lesezeichens das Lesezeichen in der entsprechenden Lesezeichenliste aus.
1. Während Sie die Informationen hinzufügen oder bearbeiten, wird die Vorschau automatisch aktualisiert.
1. Speichern Sie Ihre Änderungen.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Hinzufügen oder Bearbeiten von Lesezeichen mithilfe von Browsererweiterungen

Suchadministratoren können Suchinhalte mühelos mithilfe von Browsererweiterungen erstellen. Installieren Sie die Browser Erweiterung, wechseln Sie zu der Website, die Sie als Lesezeichen hinzufügen möchten, und fügen Sie die Textmarke hinzu.

Derzeit sind Browsererweiterungen für Microsoft Edge und Chrome verfügbar.

- Um Edge-Erweiterungen herunterzuladen, wechseln Sie zu [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) , und laden Sie die APP herunter.
- Um Chrome Extensions herunterzuladen, wechseln Sie zum [Chrome-Webstore](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) , und laden Sie die APP herunter.

## <a name="bulk-add-or-edit-bookmarks"></a>Massenhinzufügen oder -bearbeiten von Lesezeichen

Verwenden Sie die Funktion "Importieren oder exportieren" zum Massen erstellen oder Bearbeiten von Lesezeichen. Es macht das Hinzufügen oder Bearbeiten einer großen Anzahl von Textmarken schneller und einfacher. Verwenden Sie es für Folgendes:

- Massenhinzufügen von Lesezeichen – Fügen Sie Details in der Vorlagendatei für Lesezeichen hinzu, und importieren Sie sie dann.
- Massenbearbeiten von Lesezeichen – Exportieren Sie Lesezeichen in eine CSV-Datei, bearbeiten Sie dann die Lesezeichendetails in der exportierten CSV-Datei, und importieren Sie die aktualisierte CSV-Datei.
- Importieren höhergestufter Websites aus SharePoint
- Sichern von Lesezeichen – Exportieren Sie Lesezeichen in eine CSV-Datei.

So importieren oder exportieren Sie Lesezeichen:

1. Wählen Sie in der oberen rechten Ecke der Registerkarte **Lesezeichen** **Importieren** aus.
Wählen Sie **Exportieren** aus, um alle vorhandenen Lesezeichen in eine CSV-Datei herunterzuladen.
1. Wählen Sie im rechten Bereich die Option zum Importieren mithilfe einer CSV-Datei oder aus SharePoint.
Laden Sie die Vorlagendatei herunter, um eine Liste der erforderlichen Felder und Details zu erhalten.
1. Fügen Sie Lesezeichendetails in der Vorlagendatei hinzu oder bearbeiten Sie sie, und speichern Sie sie dann auf Ihrem Computer.
1. Klicken Sie im Bereich **Lesezeichen importieren** auf **Durchsuchen**, und wählen Sie dann die CSV-Datei aus, die Sie importieren möchten.
1. Wählen Sie **Importieren** aus.

Hier sind einige wichtige Punkte zur Vorlagendatei:

- Daten in diesen Feldern nie bearbeiten: *ID*, *zuletzt geändert*und *zuletzt geändert von*
- Wenn Sie die *ID* einer vorhandenen Textmarke einschließen, wird Sie durch die Informationen in der Importdatei ersetzt.
- Bei vorhandener Textmarke mit dem gleichen Titel oder der gleichen URL wird das Lesezeichen mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und die erforderlichen Felder variieren je nach dem Lesezeichenstatus.
- Basierend auf dem Feld " *Status* " werden Lesezeichen als Entwurf, vorgeschlagen, geplant gespeichert, oder Sie werden automatisch veröffentlicht.
- Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Lesezeichen aus einer org exportieren und in eine andere importieren. Sie müssen die Daten jedoch vor dem Importieren in der *ID-* Spalte entfernen.

### <a name="prevent-import-errors"></a>Vermeiden von Importfehlern

Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind, und eine Protokolldatei mit weiteren Informationen über die zu korrigierenden Zeilen und Spalten wird erstellt. Nehmen Sie die notwendigen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren. Sie können keine Lesezeichen importieren oder speichern, bis alle Fehler behoben sind.

Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und:

- die Kopfzeile und alle Spalten enthält, die in der Importvorlage vorhanden waren
- die Spaltenreihenfolge die gleiche ist wie in der Importvorlage
- Alle Spalten haben Werte, mit Ausnahme der drei, die leer sein können: *ID*, *zuletzt geändert*und *zuletzt geändert von*
- Die *Status* Spalte ist nicht leer, es sind die erforderlichen Informationen.

So verhindern Sie Fehler beim Duplizieren von Lesezeichen zu Lesezeichen:

- Verwenden Sie keine doppelten URLs für unterschiedliche Lesezeichen. Wenn eine URL einer anderen Textmarke zugewiesen ist und Sie versuchen, Sie erneut aus einer Importdatei hinzuzufügen, erhalten Sie eine Fehlermeldung. Dies gilt auch für doppelte URLs für andere Arten von Antworten.
- Verwenden Sie beim Aktualisieren vorhandener Lesezeichen die Spalte *Bookmark ID* . Sie können jede andere Eigenschaft einer vorhandenen Textmarke wie Stichwort oder Beschreibung aktualisieren, aber Sie sollten sicherstellen, dass sich die *Lesezeichen-ID* in der entsprechenden Spalte der Importdatei befindet. Wenn die *Lesezeichen-ID* vorhanden ist, wird Sie nicht als neue Addition behandelt und nicht als Fehler verarbeitet.

## <a name="power-apps"></a>Power-Apps

Helfen Sie Ihren Benutzern, Aufgaben wie das Eingeben von Urlaubszeiten oder Berichtsausgaben durch Hinzufügen vorhandener Power apps zu Ihren Lesezeichen abzuschließen.

### <a name="power-apps-explained"></a>Power apps Explained

Power Apps ist ein Dienst, mit dem Sie Geschäftsanwendungen erstellen können, die in einem Browser oder auf einem Telefon oder Tablet ausgeführt werden, ohne dass eine Programmiererfahrung erforderlich ist. Power-apps funktionieren in jedem Browser und auf jedem Gerät und benötigen weniger als eine Minute zum Hinzufügen. Weitere Informationen zu Power apps finden Sie unter:

- [Interaktives Lernen](https://docs.microsoft.com/learn/browse/?terms=power%20apps)
- [Dokumentation](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Power Apps-Startseite](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-power-app-to-a-bookmark"></a>Hinzufügen einer Power-APP zu einer Textmarke

1. Suchen Sie die [App-ID für die Power-App](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) , die Sie hinzufügen möchten.
1. Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Lesezeichen**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Fügen Sie eine Textmarke hinzu, oder suchen Sie nach einer vorhandenen Textmarke, der Sie eine **Power-App** hinzufügen möchten.
1. Wählen Sie in **Lesezeichen Einstellungen**die Option **Power App**aus, und geben Sie die **App-ID**ein, oder fügen Sie Sie ein.
    Die Höhe und Breite werden basierend auf der Ausrichtung, die beim Erstellen der Power-App ausgewählt wurde, automatisch angepasst. Lesezeichen unterstützen sowohl Hochformat als auch Querformat. Die Lesezeichenvorschau zeigt eine voll funktionsfähige PowerApp, um das Testen einfach zu machen.
1. Wählen Sie **Veröffentlichen** oder **Als Entwurf speichern** aus.
