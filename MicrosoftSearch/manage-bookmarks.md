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
ms.openlocfilehash: 2c0b42e4be1307aa45e4cab3f5c923a7808375e4
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422874"
---
# <a name="manage-bookmarks"></a>Verwalten von Lesezeichen

Sie können ein Lesezeichen in wenigen Schritten erstellen. Jedes Lesezeichen enthält einen Titel, eine URL und eine Gruppe von Schlüsselwörtern, die es auslösen. Sie können auch Kategorien zu einer Textmarke hinzufügen, die zum Sortieren und Filtern im Administratorportal verwendet werden kann. Ein Lesezeichen kann mehrere Schlüsselwörter haben, und mehrere Lesezeichen können ein gemeinsames Schlüsselwort nutzen, aber ein reserviertes Schlüsselwort kann nicht gemeinsam genutzt werden. Wenn ein Lesezeichen erstellt oder geändert wird, wird der Suchindex sofort aktualisiert, und das Lesezeichen steht Benutzern sofort zur Verfügung.

Wenn Ihre Organisation die Ergebnisse in SharePoint höher gestuft hat, können Sie die heraufgestuften Ergebnisse in **Microsoft Search** importieren und die importierten Inhalte ihren Benutzern zur Verfügung stellen. Dies ist eine einfache Möglichkeit, Suchergebnisse schnell aufzufüllen, sobald Sie **Microsoft Search** einrichten, und es für Ihre Benutzer effektiver zu gestalten. Wir empfehlen Ihnen, höhergestufte Ergebnisse aus SharePoint als Referenz zu verwenden, um zu verstehen, wie man relevante Suchergebnisse benennt und erstellt.

## <a name="add-or-edit-a-single-bookmark"></a>Hinzufügen oder Bearbeiten eines einzelnen Lesezeichens

1. Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Lesezeichen**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Zum Hinzufügen einer Textmarke wählen Sie **Hinzufügen**aus.
Wählen Sie zum Bearbeiten eines Lesezeichens das Lesezeichen in der entsprechenden Lesezeichenliste aus.
1. Während Sie die Informationen hinzufügen oder bearbeiten, wird die Vorschau automatisch aktualisiert.
1. Speichern Sie Ihre Änderungen.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Hinzufügen oder Bearbeiten von Lesezeichen mithilfe von Browsererweiterungen

Suchadministratoren können Suchinhalte mühelos mithilfe von Browsererweiterungen erstellen. Installieren Sie die Browsererweiterung, und gehen Sie dann zu der Website, die Sie als Lesezeichen hinzufügen möchten, und fügen die Website als Lesezeichen hinzu.

Derzeit sind Browsererweiterungen für Microsoft Edge und Chrome verfügbar.

- Um Edge-Erweiterungen herunterzuladen, wechseln Sie zu [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) , und laden Sie die APP herunter.
- Um Chrome Extensions herunterzuladen, wechseln Sie zum [Chrome-Webstore](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) , und laden Sie die APP herunter.

## <a name="bulk-add-or-edit-bookmarks"></a>Massenhinzufügen oder -bearbeiten von Lesezeichen

Der Suchadministrator kann die Import- oder Exportfunktion verwenden, um Lesezeichen per Massenvorgang zu erstellen oder zu bearbeiten. Dies ist eine sehr nützliche Funktion, wenn ein Administrator eine große Anzahl von Lesezeichen hinzufügen oder bearbeiten möchte.

Verwenden Sie die Import-/Exportfunktion zum:

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

Hier sind einige wichtige Punkte, die in Bezug auf die Vorlagendatei zu beachten sind:

- Bearbeiten Sie niemals Daten in diesen Feldern: *ID*, *Zuletzt geändert* und *Zuletzt geändert von*.
- Wenn Sie die *ID* eines vorhandenen Lesezeichens angeben, wird sie durch die Informationen in der Importdatei ersetzt.
- Wenn ein Lesezeichen mit dem gleichen Titel oder der gleichen URL vorhanden ist, wird das Lesezeichen mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und die erforderlichen Felder variieren je nach dem Lesezeichenstatus.
- Auf der Grundlage des Felds *Status* werden Lesezeichen als „Entwurf“, „vorgeschlagen“ oder „geplant“ gespeichert, oder sie werden automatisch veröffentlicht.
- Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Lesezeichen aus einer org exportieren und in eine andere importieren. Sie müssen jedoch die Daten in der Spalte *ID* vor dem Import entfernen.

### <a name="prevent-import-errors"></a>Vermeiden von Importfehlern

Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind, und eine Protokolldatei mit weiteren Informationen über die zu korrigierenden Zeilen und Spalten wird erstellt. Nehmen Sie die notwendigen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren. Sie können keine Lesezeichen importieren oder speichern, bis alle Fehler behoben sind.

Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und:

- die Kopfzeile und alle Spalten enthält, die in der Importvorlage vorhanden waren
- die Spaltenreihenfolge die gleiche ist wie in der Importvorlage
- alle Spalten Werte haben, mit Ausnahme der drei, die leer sein dürfen: *ID*, *Zuletzt geändert* und *Zuletzt geändert von*
- die Spalte *Status* nicht leer ist, da diese Information erforderlich ist

Führen Sie die folgenden bewährten Methoden aus, um zu verhindern, dass Lesezeichen-zu-Bookmark-Fehler auftreten:

- Verwenden Sie keine doppelten URLs für unterschiedliche Lesezeichen. Wenn eine URL bereits einer anderen Textmarke zugewiesen ist und Sie Sie erneut aus einer Importdatei hinzufügen, wird eine Fehlermeldung angezeigt. Dies gilt auch für doppelte URLs für andere Arten von Antworten.
- Verwenden Sie die Spalte *Bookmark ID* beim Aktualisieren vorhandener Textmarken. Sie können jede andere Eigenschaft einer vorhandenen Textmarke wie Stichwort oder Beschreibung aktualisieren, aber Sie sollten sicherstellen, dass sich die *Lesezeichen-ID* in der entsprechenden Spalte der Importdatei befindet. Wenn die *Lesezeichen-ID* vorhanden ist, wird Sie vom Dienst nicht als neue Hinzufügung betrachtet, und Sie wird nicht als Fehler verarbeitet.

## <a name="power-apps"></a>Power-Apps

Helfen Sie Ihren Benutzern beim Ausführen von Aufgaben, z. B. der Eingabe von Urlaubszeiten oder dem Erstellen von Spesenabrechnungen, indem Sie bestehende PowerApps zu Ihren Lesezeichen hinzufügen.

### <a name="power-apps-explained"></a>Power apps Explained

Power Apps ist ein Dienst, mit dem Sie Geschäftsanwendungen erstellen können, die in einem Browser oder auf einem Telefon oder Tablet ausgeführt werden, ohne dass eine Programmiererfahrung erforderlich ist. PowerApps funktionieren in jedem beliebigen Browser und auf jedem beliebigen Gerät und können in weniger als einer Minute hinzugefügt werden. Weitere Informationen zu PowerApps finden Sie unter:

- [Interaktives Lernen](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [Dokumentation](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Power Apps-Startseite](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-power-app-to-a-bookmark"></a>Hinzufügen einer Power-APP zu einer Textmarke

1. Suchen Sie die [App-ID für die Power-App](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) , die Sie hinzufügen möchten.
1. Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Lesezeichen**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Fügen Sie ein Lesezeichen hinzu oder suchen Sie ein vorhandenes Lesezeichen, dem Sie eine **PowerApp** hinzufügen möchten.
1. Wählen Sie in den **Lesezeicheneinstellungen** **PowerApp** und dann **PowerApp hinzufügen** aus.
1. Geben oder fügen Sie die **App-ID** ein.
    Die Höhe und Breite werden automatisch angepasst. Lesezeichen können Hoch- und Querformat unterstützen, die Größe kann derzeit aber nicht geändert werden. Die Lesezeichenvorschau zeigt eine voll funktionsfähige PowerApp, um das Testen einfach zu machen.
1. Wählen Sie **Veröffentlichen** oder **Als Entwurf speichern** aus.
