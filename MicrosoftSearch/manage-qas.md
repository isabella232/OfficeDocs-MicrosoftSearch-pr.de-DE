---
title: F & As verwalten
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Suchen und aktualisieren Sie Antworten einzeln oder verwenden Sie verfügbare Microsoft Search Tools, um Q&As all auf einmal zu bearbeiten.
ms.openlocfilehash: 2ee42e3feaf5c14b2af820360f753ecc2e116f9b
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2021
ms.locfileid: "59334526"
---
# <a name="manage-qas"></a>F & As verwalten

Die Erstellung von Fragen und Antworten ist vergleichbar mit der Erstellung von Lesezeichen. F&So können Sie die Fragen des Benutzers beantworten, anstatt nur einen Link zu einer Webseite bereitzustellen. Sie können die Antwort auch in Rich-Text formatieren. Wenn ein Lesezeichen und ein Q-&A dasselbe Schlüsselwort verwenden, wird zuerst das Lesezeichenergebnis angezeigt. Wie Lesezeichen wird der Q&A-Index unmittelbar nach dem Hinzufügen oder Ändern eines Q-&A aktualisiert.

## <a name="add-or-edit-a-single-qa"></a>Hinzufügen oder Bearbeiten einer einzelnen Frage und Antwort

1. Wechseln [Sie](https://admin.microsoft.com)im Microsoft 365 Admin Center zu [**F&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. Um eine F&A hinzuzufügen, wählen Sie **Hinzufügen** aus.
Wählen Sie zum Bearbeiten einer Frage und Antwort die Frage und Antwort in der entsprechenden F&A-Liste aus. Während Sie die Informationen hinzufügen oder bearbeiten, wird die Vorschau automatisch aktualisiert.
1. Speichern Sie Ihre Änderungen.

### <a name="supported-html-tags"></a>Unterstützte HTML-Tags

Sie können vorhandene HTML-Inhalte verwenden oder ihrer Antwort (Beschreibung) HTML-Tags hinzufügen. Nicht unterstützte Tags werden ignoriert.

Die folgenden HTML-Tags werden unterstützt:

- blockquote
- div
- em
- h1, h2, h3 und h4
- ol, ul und li
- p
- pre
- span
- strong
- table, thead, tbody, tr, th und td
- u
- a
- code
- br
- hr
- img

## <a name="add-or-edit-qas-using-browser-extensions"></a>Hinzufügen oder Bearbeiten von Q-&Wie bei Verwendung von Browsererweiterungen

Suchadministratoren können Suchinhalte mühelos mithilfe von Browsererweiterungen erstellen. Installieren Sie die Browsererweiterung, und wechseln Sie dann zu der Website, von der Sie eine Q-&A generieren möchten. Anschließend können Sie die Q-&A erstellen und einen Link zur Quellwebsite einfügen.

Derzeit sind Browsererweiterungen für Microsoft Edge und Chrome verfügbar.

- Um Erweiterungen für Edge (Legacy) herunterzuladen, wechseln Sie zu [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Um Erweiterungen Chrome oder Edge (Chromium) herunterzuladen, wechseln Sie zum [Chrome Web Store.](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)

## <a name="bulk-add-or-edit-qas"></a>Massenhinzufügen oder -bearbeiten von F & As

Administratoren können die Import- und Exportfeatures verwenden, um Q-&As massenweise zu erstellen oder zu bearbeiten.

Verwenden Sie das Import/Export-Feature für Folgendes:

- Massenhinzufügen von Q&As – Fügen Sie Details in der Vorlagendatei "F&A" hinzu, und importieren Sie sie.
- Massenbearbeitung von Q&As – Export Q&As to a .csv file, edit the Q&A details in the exported file, and then import the file.
- Sichern von Q&As – Exportieren von Q&As in eine .csv Datei.

So importieren oder exportieren Sie Q&As:

1. Wählen Sie in der oberen rechten Ecke der Registerkarte „F&A“ **Importieren** aus.
Wählen Sie **"Exportieren"** aus, um alle vorhandenen Q-&wie in einer .csv-Datei herunterzuladen.
1. Wählen Sie im rechten Bereich die Option zum Importieren mithilfe einer .csv-Datei aus. Laden Sie die Vorlagendatei herunter, um eine Liste der erforderlichen Felder und Details abzurufen.
1. Fügen Sie F&A-Details in der Vorlagendatei hinzu, oder bearbeiten Sie sie, und speichern Sie sie auf Ihrem Computer.
1. Wählen Sie im Bereich **"Import F&A"** die Option **"Durchsuchen"** aus, und wählen Sie dann die .csv Datei aus, die Sie importieren möchten.
1. Wählen Sie **Importieren** aus.

Wichtige Vorlagendateitipps:

- Bearbeiten Sie niemals Daten in diesen Feldern: **ID**, **Zuletzt geändert** und **Zuletzt geändert von**.
- Wenn Sie die **ID** eines vorhandenen Lesezeichens angeben, wird sie durch die Informationen in der Importdatei ersetzt.
- Wenn eine Textmarke mit demselben Titel oder derselben URL vorhanden ist, wird die Textmarke mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und die erforderlichen Felder variieren je nach Lesezeichenstatus.
- Basierend auf dem **Feld "Status"** werden Lesezeichen als *Entwurf* gespeichert, *vorgeschlagen* oder *geplant,* oder sie werden automatisch veröffentlicht.
- Für Partner, die mehrere Organisationen verwalten: Sie können Ihre Lesezeichen aus einer Organisation exportieren und in eine andere importieren. Sie müssen jedoch die Daten in der Spalte **ID** vor dem Import entfernen.

> [!NOTE]
> Sie können Q-&nicht importieren, als ob fehler in der Vorlagendatei vorhanden wären. Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist, und fügen Sie alle erforderlichen Informationen ein.

Weitere Informationen zum Vermeiden von Fehlern finden Sie unter ["Verhindern von Importfehlern".](manage-bookmarks.md#prevent-import-errors)
