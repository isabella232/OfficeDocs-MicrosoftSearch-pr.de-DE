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
ms.openlocfilehash: 6a678464ec23c2d4c90190b6a02c0a73839b50ee
ms.sourcegitcommit: 41d28060238091455c7b8b011c67ae60c8a41f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619576"
---
# <a name="manage-bookmarks"></a>Verwalten von Lesezeichen

Mithilfe von Lesezeichen können Benutzer schnell wichtige Websites und Tools mit nur einer Suche finden. Jede Textmarke enthält einen Titel, eine URL, eine Reihe von benutzerfreundlichen Stichwörtern zum Auslösen der Textmarke sowie eine Kategorie.

## <a name="what-makes-a-great-bookmark"></a>Was ist ein großartiges Lesezeichen?

Ein großes Lesezeichen besteht aus vier Hauptelementen:

1. Ein starker, informativer **Titel**. Ziel für maximal 8 Wörter oder maximal 60 Zeichen. Sie möchten, dass Ihre Benutzer auf den Titel klicken und den Inhalt anzeigen, vermeiden jedoch offensichtliche clickbait:
    - Gut: Probieren Sie die schmackhaften Favoriten dieser Woche im Menü "Cafeteria" aus. Der Titel ist klar, prägnant und interessant, kann aber viel versprechend sein.
    - Besser: das Cafeteria-Menü dieser Woche. Nicht über zuzusagen oder klingt wie eine Anzeige.
    - Vermeiden Sie: Sie werden nicht glauben, was in dieser Woche zum Menü "Cafeteria" kommt. Verwendet clickbait-Klischees, die wie eine Anzeige klingen.
2. Eine prägnante **Beschreibung** von ungefähr 300 Zeichen, die den Zweck oder die Funktionalität der verknüpften Ressource zusammenfasst.
3. Eine Sammlung von **Schlüsselwörtern** , die Benutzern beim Suchen der Textmarke helfen soll. Mindestens fünf Stichwörter werden empfohlen. Schließen Sie auch Variationen ein, die Personen in Ihrer Organisation verwenden können, beispielsweise Speisekarte, Mittagsmenüs und Café-Menü.
4. Eine hilfreiche Gruppe von **Kategorien** , die das Sortieren und Filtern von Lesezeichen im Admin Center erleichtern. Ihren Benutzern werden die zugewiesenen Kategorien nie angezeigt.

## <a name="create-bookmark-answers"></a>Erstellen von Lesezeichen Antworten

Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/)zu [Lesezeichen](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) , und wählen Sie aus, wie Sie neue Lesezeichen erstellen möchten:

- Hinzufügen von Lesezeichen
- Importieren von SharePoint-Ergebnissen
- Standard-Lesezeichen und vorgeschlagene Lesezeichen hinzufügen
- Importieren von Lesezeichen
- Veröffentlichen oder überprüfen empfohlener Lesezeichen

### <a name="add-bookmarks"></a>Hinzufügen von Lesezeichen

Suchadministratoren und-Redakteure können Lesezeichen im Microsoft 365 Admin Center hinzufügen. Lesezeichen können in Entwurf veröffentlicht oder gespeichert werden. Durch das Veröffentlichen einer Textmarke wird der Suchindex sofort aktualisiert, damit Benutzer sofort mit der Erkennung beginnen und diese verwenden können. Sie können auch eine Textmarke planen, indem Sie das Datum und die Uhrzeit angeben, zu der Sie veröffentlicht werden.

- **Veröffentlicht**: Lesezeichen stehen den Benutzern der Organisation über die Microsoft-Suche zur Verfügung.
- **Draft**: Lesezeichen, die als Entwürfe gespeichert sind, stehen ihren Benutzern nicht zur Verfügung. Verwenden Sie diesen Status, wenn Sie oder andere Beteiligte Lesezeichen lesen oder aktualisieren möchten, bevor Sie Sie veröffentlichen.
- **Geplant**: Lesezeichen, die zum angegebenen Datum und zur angegebenen Uhrzeit veröffentlicht werden.

Sie können die Microsoft Search Content Creator-Browser Erweiterung verwenden, um einfach Lesezeichen hinzuzufügen. Um die Browser Erweiterung zu installieren, wechseln Sie zu der Website, die Sie als Textmarke hinzufügen möchten, und klicken Sie auf in der Erweiterung hinzufügen.
Installieren Sie die Erweiterung für Edge und Chrome:

- Für Chrom Edge oder Chrome: Wechseln Sie zum [Chrome-Webstore](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) , und fügen Sie die Erweiterung hinzu.
- Für Legacy Edge: Wechseln Sie zum [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) , und fügen Sie die Erweiterung hinzu.

### <a name="import-sharepoint-results"></a>Importieren von SharePoint-Ergebnissen

Wenn Ihre Organisation heraufgestufte Ergebnisse in SharePoint eingerichtet hat, können Sie die Titel, URLs und Beschreibungen aus den höher gestuften Ergebnissen für Ihren Mandanten in die Microsoft-Suche importieren und die importierten Inhalte ihren Benutzern zur Verfügung stellen. In den meisten Fällen dauert das Importieren von SharePoint-Ergebnissen nur wenige Minuten. Wenn Sie eine große Anzahl von Ergebnissen importieren, kann es bis zu 48 Stunden dauern. Dies ist eine einfache Möglichkeit, Suchergebnisse schnell aufzufüllen und effektiver für Ihre Benutzer zu machen. Es wird empfohlen, höher gestufte Ergebnisse aus SharePoint als Referenz zu verwenden, um zu verstehen, wie relevante Suchergebnisse benannt und erstellt werden.

### <a name="add-default-and-suggested-bookmarks"></a>Hinzufügen von Standard-und empfohlenen Lesezeichen

Wir haben einige standardmäßige Lesezeichen vorgeschlagen, die Ihre Benutzer hilfreich finden können, einschließlich Lesezeichen für HR, Vorteile, IT-Support, Kennwortverwaltung und vieles mehr. Überprüfen, aktualisieren und veröffentlichen Sie diese vorgeschlagenen Lesezeichen, damit Ihre Benutzer sofort qualitativ hochwertige Ergebnisse erhalten.

Ihre Benutzer können auch Lesezeichen vorschlagen, die in Microsoft Search mithilfe von Feedback Links hinzugefügt werden sollen. Ihre Empfehlungen werden als vorgeschlagene Lesezeichen angezeigt.

### <a name="import-bookmarks"></a>Importieren von Lesezeichen

Verwenden Sie das Feature zum Importieren, um das Hinzufügen oder Bearbeiten einer großen Anzahl von Textmarken schneller und einfacher zu machen. Verwenden Sie es für Folgendes:

- Massen Hinzufügen von Lesezeichen: Fügen Sie der Textmarke-Vorlagendatei Details hinzu, und importieren Sie Sie.
- Massen Bearbeitungs Lesezeichen: Exportieren Sie Lesezeichen in eine CSV-Datei, bearbeiten Sie die Lesezeichen Details in der exportierten Datei, und importieren Sie dann die bearbeitete Datei.

Einige wichtige Punkte zur Vorlagendatei:

- Daten in diesen Feldern nie bearbeiten: *ID*, *zuletzt geändert* und *zuletzt geändert von*
- Wenn Sie die *ID* einer vorhandenen Textmarke einschließen, wird Sie durch die Informationen in der Importdatei ersetzt.
- Bei vorhandenen Textmarken mit dem gleichen Titel oder der gleichen URL wird das Lesezeichen mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und die erforderlichen Felder variieren je nach dem Lesezeichenstatus.
- Basierend auf dem Feld " *Status* " werden Lesezeichen als Entwurf gespeichert, vorgeschlagen, geplant, ausgeschlossen oder werden automatisch veröffentlicht.
- Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Lesezeichen aus einer org exportieren und in eine andere importieren. Sie müssen die Daten jedoch vor dem Importieren in der *ID-* Spalte entfernen.

### <a name="prevent-import-errors"></a>Vermeiden von Importfehlern

Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind, und eine Protokolldatei mit weiteren Informationen über die zu korrigierenden Zeilen und Spalten wird erstellt. Nehmen Sie die notwendigen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren. Sie können keine Lesezeichen importieren oder speichern, bis alle Fehler behoben sind.

Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und:

- die Kopfzeile und alle Spalten enthält, die in der Importvorlage vorhanden waren
- die Spaltenreihenfolge die gleiche ist wie in der Importvorlage
- Alle Spalten haben Werte, mit Ausnahme der drei, die leer sein können: *ID*, *zuletzt geändert* und *zuletzt geändert von*
- Die *Status* Spalte ist nicht leer, es sind die erforderlichen Informationen.
- Beim Importieren veröffentlichter, vorgeschlagener, geplanter oder Draft-Lesezeichen sind die Spalten *Title*, *URL* und *Keywords* erforderlich.
- Wenn ausgeschlossene Lesezeichen importiert werden, ist die *URL* -Spalte erforderlich.

So verhindern Sie Fehler beim Duplizieren von Lesezeichen zu Lesezeichen:

- Verwenden Sie keine doppelten URLs für unterschiedliche Lesezeichen. Wenn eine URL einer anderen Textmarke zugewiesen ist und Sie versuchen, Sie erneut aus einer Importdatei hinzuzufügen, erhalten Sie eine Fehlermeldung. Dies gilt auch für doppelte URLs für andere Arten von Antworten.
- Verwenden Sie beim Aktualisieren vorhandener Lesezeichen die Spalte *Bookmark ID* . Sie können jede andere Eigenschaft einer vorhandenen Textmarke wie Stichwort oder Beschreibung aktualisieren, aber Sie sollten sicherstellen, dass sich die *Lesezeichen-ID* in der entsprechenden Spalte der Importdatei befindet. Wenn die *Lesezeichen-ID* vorhanden ist, wird Sie nicht als neue Addition behandelt und nicht als Fehler verarbeitet.

### <a name="publish-or-review-recommended-bookmarks"></a>Veröffentlichen oder überprüfen empfohlener Lesezeichen

Um den manuellen Aufwand für das Hinzufügen von Lesezeichen zu reduzieren, kann Microsoft Search SharePoint-Links in Ihrer Organisation auswerten und Lesezeichen empfehlen, und Sie können Sie vor der Veröffentlichung überprüfen oder festlegen, dass Sie automatisch veröffentlicht werden. Für empfohlene Lesezeichen ist kein Setup erforderlich, Sie sind jedoch standardmäßig für die automatische Veröffentlichung aktiviert und festgelegt. Wenn Sie diese Einstellungen jederzeit ändern möchten, wählen Sie **Lesezeichen verwalten** aus, um den Bereich Lesezeichen Einstellungen zu öffnen.

![Screenshot der empfohlenen Lesezeichen Einstellungen im Microsoft 365-Verwaltungsportal](media/bookmarks-recommendedsettings.png)

Wenn Empfohlene Lesezeichen aktiviert sind, evaluiert das Empfehlungs Modul SharePoint-Websites in Ihrer Organisation, um Verbindungen mit hohem Datenverkehr zu identifizieren. Nach einem anfänglichen Evaluierungszeitraum werden die empfohlenen Lesezeichen entweder automatisch veröffentlicht oder der Liste der vorgeschlagenen Lesezeichen hinzugefügt. Der nächste Zyklus beginnt dann mit einem 30-tägigen Evaluierungszeitraum, dem die automatische Veröffentlichung oder das Hinzufügen vorgeschlagener Lesezeichen gefolgt ist.

Wir schlagen vor, dass Administratoren oder Redakteure regelmäßig über diese automatisch veröffentlichten oder vorgeschlagenen Lesezeichensuchen. Außerdem werden empfohlene Lesezeichen niemals URLs enthalten, die in vorhandenen veröffentlichten, vorgeschlagenen, geplanten oder ausgeschlossenen Lesezeichen gefunden wurden.

Um sicherzustellen, dass nur Benutzer mit Access eine empfohlene Textmarke in ihren Arbeitsergebnissen sehen, ist für alle empfohlenen Lesezeichen eine Zugriffs Prüfungsfunktion enthalten. Benutzer, die nicht über Berechtigungen für den Zugriff auf eine SharePoint-Website verfügen, werden nie die empfohlene Textmarke für diese Website sehen. Diese Zugriffsüberprüfung wird von der Option **nur Personen mit Zugriff auf diesen Link** in der Gruppeneinstellung für jede empfohlene Textmarke gesteuert.

Die Zugriffsüberprüfung wird angehalten, wenn die URL in der empfohlenen Textmarke oder in der Einstellung Gruppen geändert wird.

Um zu verhindern, dass das Empfehlungs Modul eine Textmarke für eine bestimmte Website veröffentlicht oder vorschlägt, können Sie die URL zu einer ausgeschlossenen Liste hinzufügen. Das Empfehlungs Modul veröffentlicht oder schlägt keine Textmarke für eine ausgeschlossene Website oder eine Seite innerhalb einer ausgeschlossenen Website vor.

## <a name="about-keywords-and-reserved-keywords"></a>Informationen zu Schlüsselwörtern und reservierten Schlüsselwörtern

Eine Textmarke kann mehrere Schlüsselwörter enthalten, und Lesezeichen können dasselbe Schlüsselwort verwenden, aber reserviertes Schlüsselwort kann nicht freigegeben werden. Ein reserviertes Schlüsselwort ist ein eindeutiger Ausdruck oder Ausdruck, der eine bestimmte Textmarke auslöst. Ein reserviertes Schlüsselwort kann nur einer Antwort zugeordnet werden. Verwenden Sie reservierte Schlüsselwörter sparsam.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F.: wie lange dauert es, bis eine Textmarke in Microsoft Search angezeigt wird, nachdem Sie veröffentlicht wurde?**

**A:**  Eine Textmarke steht in der Microsoft-Suche unmittelbar nach der Veröffentlichung zur Verfügung.

**F.: wie lange dauert es, bis eine empfohlene Textmarke angezeigt wird?**

**A:**  Empfohlene Lesezeichen werden nur in Microsoft Search angezeigt, wenn sowohl empfohlene Lesezeichen als auch automatische Veröffentlichung aktiviert sind. Während des anfänglichen Evaluierungszeitraums evaluiert das Empfehlungs Modul SharePoint-Datenverkehr, um geeignete Lesezeichen zu identifizieren und Sie dann automatisch zu veröffentlichen. Nach der Veröffentlichung werden Sie sofort in der Microsoft-Suche zur Verfügung gestellt.

**F.: werden von der Microsoft-Suche Lesezeichen von Websites in allen Sprachen empfohlen?**

**A**.: Ja, Microsoft Search kann Lesezeichen von jeder internen SharePoint-Website unabhängig von der Sprache empfehlen.

**F.: kann ich das Anzeigen empfohlener Lesezeichen in Suchergebnissen beenden?**

**A:** Um die Anzeige empfohlener Lesezeichen zu beenden, deaktivieren Sie die Einstellung für die automatische Veröffentlichung in Ihrem Admin Center. Empfohlene Lesezeichen werden der Liste der vorgeschlagenen Lesezeichen hinzugefügt.

**F.: Wie kann ich eine empfohlene Textmarke in Suchergebnissen oder im Admin Center identifizieren?**

**A:** In den Suchergebnissen enthalten die empfohlenen Lesezeichen den Ausdruck "vorgeschlagen für Sie" vor der URL. Im Admin Center haben verminte Lesezeichen den Besitzer Wert "System".

**F.: wie wird der Zugriff auf ein empfohlenes Lesezeichen verwaltet?**

**A**: ein von Microsoft entwickeltes Zugriffsmodul ermittelt, ob die Lesezeichen-URL für einen bestimmten Benutzer zugänglich ist, und zeigt nur die empfohlene Textmarke für die richtige Zielgruppe an. Wenn die URL jedoch bearbeitet oder die Gruppeneinstellung geändert wird, wird das Modul für den entwickelten Zugriff deaktiviert.

**F.: Was geschieht, wenn für empfohlene Lesezeichen, die der vorgeschlagenen Liste hinzugefügt wurden, keine Aktion ausgeführt wird?**

**A**: um eine große Anzahl von Lesezeichen in der vorgeschlagenen Liste zu vermeiden, wird eine empfohlene Textmarke (owner = System) nach 180 Tagen gelöscht.

**F: Wo finde ich die APP-ID für eine Power-App?**

**A**: Wechseln Sie zur Power apps-Website, und zeigen Sie den Detailbereich für die APP an. Erfahren Sie mehr über [das erhalten einer APP-ID](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id).
