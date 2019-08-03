---
title: Lesezeichen verwalten
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Erstellen und aktualisieren Sie Lesezeichen und Methoden zur Massenbearbeitung von Lesezeichenergebnissen für Microsoft Search.
ms.openlocfilehash: 0cd37ebcd7cd3ea7bbe55064fd41a3c42b2e4725
ms.sourcegitcommit: f9760d027637cc0d2e5c3a9e47928422cb6e452a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2019
ms.locfileid: "36170320"
---
# <a name="manage-bookmarks"></a>Lesezeichen verwalten

Sie können ein Lesezeichen in wenigen Schritten erstellen. Jedes Lesezeichen enthält einen Titel, eine URL und eine Gruppe von Schlüsselwörtern, die es auslösen. Ein Lesezeichen kann mehrere Schlüsselwörter haben, und mehrere Lesezeichen können ein gemeinsames Schlüsselwort nutzen, aber ein reserviertes Schlüsselwort kann nicht gemeinsam genutzt werden. Wenn ein Lesezeichen erstellt oder geändert wird, wird der Suchindex sofort aktualisiert, und das Lesezeichen steht Benutzern sofort zur Verfügung.

Wenn Ihre Organisation höhergestufte Ergebnisse in SharePoint eingerichtet hat, können Sie die höhergestuften Ergebnisse in **Microsoft Search** importieren und den importierten Inhalt für Ihre Benutzer verfügbar machen. Dies ist eine einfache Möglichkeit, Suchergebnisse schnell aufzufüllen, sobald Sie **Microsoft Search** einrichten, und es für Ihre Benutzer effektiver zu gestalten. Wir empfehlen Ihnen, höhergestufte Ergebnisse aus SharePoint als Referenz zu verwenden, um zu verstehen, wie man relevante Suchergebnisse benennt und erstellt. 

## <a name="add-or-edit-a-single-bookmark"></a>Hinzufügen oder Bearbeiten eines einzelnen Lesezeichens
1. Gehen Sie zum **Microsoft 365 Admin Center**.
1. Wechseln Sie im Navigationsbereich zu **Einstellungen**, und wählen Sie dann **Microsoft Search** aus.
Standardmäßig ist die Registerkarte **Lesezeichen** ausgewählt.
1. Wählen Sie zum Hinzufügen eines Lesezeichens **Neu hinzufügen** aus. Wählen Sie zum Bearbeiten eines Lesezeichens das Lesezeichen in der entsprechenden Lesezeichenliste aus. 
1. Während Sie die Informationen hinzufügen oder bearbeiten, wird die Vorschau automatisch aktualisiert.
1. Speichern Sie Ihre Änderungen.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Hinzufügen oder Bearbeiten von Lesezeichen mithilfe von Browsererweiterungen
Suchadministratoren können Suchinhalte mühelos mithilfe von Browsererweiterungen erstellen. Installieren Sie die Browsererweiterung, und gehen Sie dann zu der Website, die Sie als Lesezeichen hinzufügen möchten, und fügen die Website als Lesezeichen hinzu.

Derzeit sind Browsererweiterungen für Microsoft Edge und Chrome verfügbar. 
- Gehen Sie zum Herunterladen der Microsoft Edge-Erweiterung zum [Microsoft Store](https://www.microsoft.com/en-us/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab), und laden Sie die App herunter.
- Gehen Sie zum Herunterladen der Chrome-Erweiterung zum [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm), und laden Sie die App herunter.

## <a name="bulk-add-or-edit-bookmarks"></a>Massenhinzufügen oder -bearbeiten von Lesezeichen
Der Suchadministrator kann die Import- oder Exportfunktion verwenden, um Lesezeichen per Massenvorgang zu erstellen oder zu bearbeiten. Dies ist eine sehr nützliche Funktion, wenn ein Administrator eine große Anzahl von Lesezeichen hinzufügen oder bearbeiten möchte. 

Verwenden Sie die Import-/Exportfunktion zum:
- Massenhinzufügen von Lesezeichen – Fügen Sie Details in der Vorlagendatei für Lesezeichen hinzu, und importieren Sie sie dann.
- Massenbearbeiten von Lesezeichen – Exportieren Sie Lesezeichen in eine CSV-Datei, bearbeiten Sie dann die Lesezeichendetails in der exportierten CSV-Datei, und importieren Sie die aktualisierte CSV-Datei.
- Importieren höhergestufter Websites aus SharePoint
- Sichern von Lesezeichen – Exportieren Sie Lesezeichen in eine CSV-Datei.

So importieren oder exportieren Sie Lesezeichen:
1. Wählen Sie in der oberen rechten Ecke der Registerkarte **Lesezeichen** **Importieren** aus. Wählen Sie **Exportieren** aus, um alle vorhandenen Lesezeichen in eine CSV-Datei herunterzuladen.
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
- Bei Organisationen mit mehreren Mandanten können Sie Ihre Lesezeichen von einem Mandanten exportieren und zu einem anderen importieren. Sie müssen jedoch die Daten in der Spalte *ID* vor dem Import entfernen.

### <a name="prevent-import-errors"></a>Vermeiden von Importfehlern
Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind, und eine Protokolldatei mit weiteren Informationen über die zu korrigierenden Zeilen und Spalten wird erstellt. Nehmen Sie die notwendigen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren. Sie können keine Lesezeichen importieren oder speichern, bis alle Fehler behoben sind.

Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und:
- die Kopfzeile und alle Spalten enthält, die in der Importvorlage vorhanden waren
- die Spaltenreihenfolge die gleiche ist wie in der Importvorlage
- alle Spalten Werte haben, mit Ausnahme der drei, die leer sein dürfen: *ID*, *Zuletzt geändert* und *Zuletzt geändert von* 
- die Spalte *Status* nicht leer ist, da diese Information erforderlich ist

## <a name="powerapps"></a>PowerApps
Helfen Sie Ihren Benutzern beim Ausführen von Aufgaben, z. B. der Eingabe von Urlaubszeiten oder dem Erstellen von Spesenabrechnungen, indem Sie bestehende PowerApps zu Ihren Lesezeichen hinzufügen. 

### <a name="what-are-powerapps"></a>Was sind PowerApps?
PowerApps ist ein Dienst, mit dem Sie Geschäfts-Apps erstellen können, die in einem Browser oder auf einem Smartphone oder Tablet ausgeführt werden, ohne dass eine Codierung erforderlich ist. PowerApps funktionieren in jedem beliebigen Browser und auf jedem beliebigen Gerät und können in weniger als einer Minute hinzugefügt werden. Weitere Informationen zu PowerApps finden Sie unter:
- 
  [Interaktives Lernen](https://docs.microsoft.com/de-DE/learn/browse/?products=powerapps)
- 
  [Dokumentation](https://docs.microsoft.com/de-DE/powerapps/maker/canvas-apps/get-sessionid)
- [PowerApps Home](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Hinzufügen einer PowerApp zu einem Lesezeichen
1. Suchen Sie die [App-ID für die PowerApp](https://docs.microsoft.com/de-DE/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id), die Sie hinzufügen möchten.
1. Melden Sie sich an und gehen Sie zum **Microsoft 365 Admin Center**.
1. Wechseln Sie im Navigationsbereich zu **Einstellungen**, und wählen Sie dann **Microsoft Search** aus.
1. Fügen Sie ein Lesezeichen hinzu oder suchen Sie ein vorhandenes Lesezeichen, dem Sie eine **PowerApp** hinzufügen möchten.
1. Wählen Sie in den **Lesezeicheneinstellungen** **PowerApp** und dann **PowerApp hinzufügen** aus.
1. Geben oder fügen Sie die **App-ID** ein.
    Die Höhe und Breite werden automatisch angepasst. Lesezeichen können Hoch- und Querformat unterstützen, die Größe kann derzeit aber nicht geändert werden. Die Lesezeichenvorschau zeigt eine voll funktionsfähige PowerApp, um das Testen einfach zu machen.
1. Wählen Sie **Veröffentlichen** oder **Als Entwurf speichern** aus.
