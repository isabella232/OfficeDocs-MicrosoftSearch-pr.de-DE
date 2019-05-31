---
title: F & As verwalten
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
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Suchen und aktualisieren Sie Antworten einzeln oder verwenden Sie die verfügbaren Microsoft Search-Tools, um alle gleichzeitig zu bearbeiten
ms.openlocfilehash: 8620842e64a40eb32467c42a289bdec3b67d303b
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591521"
---
# <a name="manage-qas"></a>F & As verwalten

Die Erstellung von Fragen und Antworten ist vergleichbar mit der Erstellung von Lesezeichen. Fragen und Antworten ermöglichen es Ihnen, die Frage des Benutzers zu beantworten, statt nur einen Link zur Webseite bereitzustellen. Sie können die Antwort mit den verfügbaren Tools als Rich-Text formatieren. Wenn ein Lesezeichen sowie Fragen und Antworten ein gemeinsames Schlüsselwort nutzen, wird zuerst das Lesezeichenergebnis angezeigt. Wie Lesezeichen wird der F&A-Index sofort nach dem Hinzufügen oder Ändern einer Frage und Antwort aktualisiert. 

## <a name="add-or-edit-a-single-qa"></a>Hinzufügen oder Bearbeiten einer einzelnen Frage und Antwort
1. Gehen Sie zum **Microsoft 365 Admin Center**.
1. Wechseln Sie im Navigationsbereich zu **Einstellungen**, und wählen Sie **Microsoft Search** aus.
1. Wählen Sie die Registerkarte **F&A** aus. Standardmäßig ist die erste Registerkarte (**Lesezeichen**) ausgewählt.
1. Wählen Sie zum Hinzufügen einer Frage und Antwort **Neu hinzufügen** aus.
Wählen Sie zum Bearbeiten einer Frage und Antwort die Frage und Antwort in der entsprechenden F&A-Liste aus.
1. Während Sie die Informationen hinzufügen oder bearbeiten, wird die Vorschau automatisch aktualisiert.
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

## <a name="bulk-add-or-edit-qas"></a>Massenhinzufügen oder -bearbeiten von F & As
Administratoren können die Import- und Exportfunktion verwenden, um Fragen und Antworten per Massenvorgang zu erstellen oder zu bearbeiten. Dies ist eine nützliche Funktion, wenn Administratoren eine große Anzahl von Fragen und Antworten hinzufügen oder bearbeiten müssen. 

Verwenden Sie die Import-/Exportfunktion zum:
1. Massenhinzufügen von Fragen und Antworten – Fügen Sie Details in der Vorlagendatei für Fragen und Antworten hinzu, und importieren Sie sie dann.
1. Massenbearbeiten von Fragen und Antworten – Exportieren Sie Fragen und Antworten in eine CSV-Datei, bearbeiten Sie dann die F&A-Details in der exportierten CSV-Datei, und importieren Sie die aktualisierte CSV-Datei.
1. Sichern von Fragen und Antworten – Exportieren Sie Fragen und Antworten in eine CSV-Datei.

So importieren oder exportieren Sie Fragen und Antworten:
1. Wählen Sie in der oberen rechten Ecke der Registerkarte „F&A“ **Importieren** aus. Wählen Sie **Exportieren** aus, um alle vorhandenen Fragen und Antworten in eine CSV-Datei herunterzuladen.
1. Wählen Sie im rechten Bereich die Option zum Importieren mithilfe einer CSV-Datei.
Laden Sie die Vorlagendatei herunter, um eine Liste der erforderlichen Felder und Details zu erhalten. 
1. Fügen Sie F&A-Details in der Vorlagendatei hinzu oder bearbeiten Sie sie, und speichern Sie sie auf Ihrem Computer. 
1. Klicken Sie im Bereich **Fragen und Antworten importieren** auf **Durchsuchen**, und wählen Sie dann die CSV-Datei aus, die Sie importieren möchten.
1. Wählen Sie **Importieren** aus.

Hier sind einige wichtige Punkte in Bezug auf die Vorlagendatei:
- Bearbeiten Sie niemals Daten in diesen Feldern: *ID*, *Zuletzt geändert* und *Zuletzt geändert von*.
- Wenn Sie die *ID* eines vorhandenen Lesezeichens angeben, wird sie durch die Informationen in der Importdatei ersetzt.
- Wenn ein Lesezeichen mit dem gleichen Titel oder der gleichen URL vorhanden ist, wird das Lesezeichen mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und die erforderlichen Felder variieren je nach dem Lesezeichenstatus.
- Auf der Grundlage des Felds „Status“ werden Lesezeichen als „Entwurf“, „vorgeschlagen“ oder „geplant“ gespeichert, oder sie werden automatisch veröffentlicht.
- Bei Organisationen mit mehreren Mandanten können Sie Ihre Lesezeichen von einem Mandanten exportieren und zu einem anderen importieren. Sie müssen jedoch die Daten in der Spalte *ID* vor dem Import entfernen.

**Hinweis:** Sie können Fragen und Antworten nicht importieren, wenn Fehler in der Vorlagendatei vorhanden sind. Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist, und geben Sie alle erforderlichen Informationen an. 

Weitere Informationen zum Vermeiden von Fehlern finden Sie unter [Vermeiden von Importfehlern](manage-bookmarks.md#prevent-import-errors).