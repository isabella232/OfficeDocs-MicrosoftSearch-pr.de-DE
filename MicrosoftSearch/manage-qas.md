---
title: F & As verwalten
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
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Suchen und aktualisieren Sie die Antworten einzeln, oder verwenden Sie die verfügbaren Microsoft-Such Tools, um Q&als alle gleichzeitig zu bearbeiten.
ms.openlocfilehash: 78a6ee0ff14f3347b0b2e2a65cc1ee0f68500981
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996085"
---
# <a name="manage-qas"></a>F & As verwalten

Die Erstellung von Fragen und Antworten ist vergleichbar mit der Erstellung von Lesezeichen. Q&, damit Sie die Fragen des Benutzers beantworten können, anstatt lediglich einen Link zu einer Webseite bereitzustellen. Sie können die Antwort auch in Rich-Text formatieren. Wenn ein Lesezeichen und ein Q&a dasselbe Stichwort verwenden, wird zuerst das Ergebnis der Textmarke angezeigt. Wie bei Lesezeichen wird das q&ein Index unmittelbar nach dem Hinzufügen oder Ändern eines q&a aktualisiert.

## <a name="add-or-edit-a-single-qa"></a>Hinzufügen oder Bearbeiten einer einzelnen Frage und Antwort

1. Gehen Sie zum **Microsoft 365 Admin Center**.
1. Wechseln Sie im Navigationsbereich zu **Einstellungen**  >  **Microsoft Search**  >  **Answers**  >  [**Q&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. Wählen Sie zum Hinzufügen einer Frage und Antwort **Neu hinzufügen** aus.
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

## <a name="add-or-edit-qas-using-browser-extensions"></a>Hinzufügen oder Bearbeiten von Q&als Verwendung von Browsererweiterungen

Suchadministratoren können Suchinhalte mühelos mithilfe von Browsererweiterungen erstellen. Installieren Sie die Browser Erweiterung, und wechseln Sie dann zu der Website, von der Sie ein Q&a generieren möchten. Anschließend können Sie Q&a erstellen und einen Link zur Quellwebsite hinzufügen.

Derzeit stehen Browsererweiterungen für Microsoft Edge und Chrome zur Verfügung.

- Um Erweiterungen für Edge (Legacy) herunterzuladen, wechseln Sie zu [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Um Extensions Chrome oder Edge (Chromium) herunterzuladen, wechseln Sie zum [Chrome-Webstore](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="bulk-add-or-edit-qas"></a>Massenhinzufügen oder -bearbeiten von F & As

Administratoren können die Funktionen zum Importieren und Exportieren zum Massen erstellen oder Bearbeiten von Q&as verwenden.

Verwenden Sie die Funktion zum Importieren/Exportieren für:

- Massen Hinzufügen von q&as – fügen Sie Details im q-&einer Vorlagendatei hinzu, und importieren Sie Sie.
- Massenbearbeitung q&as-Export q&als CSV-Datei, bearbeiten Sie die q #d2 Details in der exportierten Datei, und importieren Sie die Datei.
- Sichern Sie q&as-Export q&als CSV-Datei.

So importieren oder exportieren Sie Q&wie:

1. Wählen Sie in der oberen rechten Ecke der Registerkarte „F&A“ **Importieren** aus.
Wählen Sie **exportieren** aus, um alle vorhandenen Q-&wie in einer CSV-Datei herunterzuladen.
1. Wählen Sie im rechten Bereich die Option zum Importieren mithilfe einer CSV-Datei aus. Laden Sie die Vorlagendatei herunter, um eine Liste der erforderlichen Felder und Details zu erhalten.
1. Fügen oder bearbeiten Sie Q&Details in der Vorlagendatei, und speichern Sie Sie auf Ihrem Computer.
1. Wählen Sie im Bereich **Q importieren&einen** **Durchsuchen**aus, und wählen Sie dann die CSV-Datei aus, die Sie importieren möchten.
1. Wählen Sie **Importieren** aus.

Wichtige Vorlagendatei Tipps:

- Bearbeiten Sie niemals Daten in diesen Feldern: **ID**, **Zuletzt geändert** und **Zuletzt geändert von**.
- Wenn Sie die **ID** eines vorhandenen Lesezeichens angeben, wird sie durch die Informationen in der Importdatei ersetzt.
- Wenn ein Lesezeichen mit dem gleichen Titel oder der gleichen URL vorhanden ist, wird das Lesezeichen mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und die erforderlichen Felder sind je nach Lesezeichen Status unterschiedlich.
- Basierend auf dem Feld **Status** werden Lesezeichen als *Entwurf*, *vorgeschlagen*oder *geplant*gespeichert, oder Sie werden automatisch veröffentlicht.
- Für Partner, die mehrere Organisationen verwalten: Sie können Ihre Lesezeichen aus einer org exportieren und in eine andere importieren. Sie müssen jedoch die Daten in der Spalte **ID** vor dem Import entfernen.

> [!NOTE]
> Sie können Q&nicht als Fehler in der Vorlagendatei importieren. Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und alle erforderlichen Informationen enthält.

Weitere Informationen zum Vermeiden von Fehlern finden Sie unter [Prevent Import Errors](manage-bookmarks.md#prevent-import-errors).
