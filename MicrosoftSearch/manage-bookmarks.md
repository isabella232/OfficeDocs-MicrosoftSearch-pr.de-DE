---
title: Verwalten von Lesezeichen
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Erstellen und Aktualisieren von Lesezeichen und Möglichkeiten zum Massenbearbeitung von Lesezeichenergebnissen für Microsoft Search
ms.openlocfilehash: a08bef9ccc56d395fe6570bacc856653ff3a1563
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973674"
---
# <a name="manage-bookmarks"></a>Verwalten von Lesezeichen

Lesezeichen helfen Benutzern bei der schnellen Suche nach wichtigen Websites und Tools. Jedes Lesezeichen enthält einen Titel, eine URL, eine Reihe benutzerfreundlicher Schlüsselwörter zum Auslösen des Lesezeichens und eine Kategorie.

## <a name="what-makes-a-great-bookmark"></a>Was macht ein hervorragendes Lesezeichen aus?

Ein hervorragendes Lesezeichen hat vier Schlüsselelemente:

1. Ein starker, informativer **Titel.** Verwenden Sie maximal acht Wörter oder maximal 60 Zeichen. Sie möchten, dass Ihre Benutzer auf den Titel klicken und den Inhalt anzeigen, aber vermeiden Sie offensichtliche Clickbait:
    - Gut: Probieren Sie die Favoriten dieser Woche aus dem Menü "Menu" aus. Der Titel ist klar, präzise und interessant, könnte aber überpromisierend sein.
    - Besser: Das Menü "The week's menu". Überpromise nicht oder klingt wie eine Anzeige.
    - Vermeiden Sie Folgendes: Sie werden nicht glauben, was in dieser Woche im Menü "Menu" angezeigt wird. Verwendet Clickbait-Clichés, die wie eine Anzeige klingen.
2. Eine prägnante **Beschreibung** von ca. 300 Zeichen, die den Zweck oder die Funktionalität der verknüpften Ressource zusammenfasst.
3. Eine Sammlung von **Schlüsselwörtern,** mit denen Benutzer das Lesezeichen bei der Suche finden können. Wir empfehlen mindestens fünf Schlüsselwörter. Schließen Sie auch Variationen ein, die Personen in Ihrer Organisation verwenden können, z. B. Menüs für Diess, Menüs und Menüs im Menü "Restaurant".
4. Eine hilfreiche Gruppe von **Kategorien,** die das Sortieren und Filtern von Lesezeichen im Admin Center vereinfachen. Den Benutzern werden die zugewiesenen Kategorien nie angezeigt.

## <a name="create-bookmark-answers"></a>Erstellen von Antworten auf Lesezeichen

Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/)zu ["Lesezeichen",](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) und wählen Sie aus, wie Sie neue Lesezeichen erstellen möchten:

- Hinzufügen von Lesezeichen
- Importieren SharePoint Ergebnisse
- Hinzufügen von Standardlesezeichen und vorgeschlagenen Textmarken
- Importieren von Lesezeichen
- Veröffentlichen oder Überprüfen empfohlener Lesezeichen

### <a name="add-bookmarks"></a>Hinzufügen von Lesezeichen

Suchadministratoren und -editoren können Lesezeichen im Microsoft 365 Admin Center hinzufügen und diese entweder veröffentlichen oder im Entwurf speichern. Durch die Veröffentlichung eines Lesezeichens wird der Suchindex sofort aktualisiert, sodass er für Benutzer sofort erkennbar ist. Sie können ein Lesezeichen auch planen, indem Sie das Datum und die Uhrzeit für die Veröffentlichung angeben.

- **Veröffentlicht:** Lesezeichen stehen den Benutzern der Organisation über Microsoft Search zur Verfügung.
- **Entwurf:** Als Entwürfe gespeicherte Lesezeichen stehen Ihren Benutzern nicht zur Verfügung. Verwenden Sie diesen Status, wenn Sie oder andere Projektbeteiligten Lesezeichen vor der Veröffentlichung überprüfen oder aktualisieren möchten.
- **Geplant:** Lesezeichen, die am angegebenen Datum und zur angegebenen Uhrzeit veröffentlicht werden.

Sie können die Browsererweiterung Microsoft Search Inhaltsersteller verwenden, um auf einfache Weise Lesezeichen hinzuzufügen. Wechseln Sie einfach zu der Website, die Sie als Lesezeichen hinzufügen möchten, und klicken Sie in der Erweiterung auf "Hinzufügen". Um die Erweiterung für Microsoft Edge oder Google Chrome zu installieren, wechseln Sie zum [Chrome-Webspeicher,](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) und fügen Sie sie Ihrem Browser hinzu.

### <a name="import-sharepoint-results"></a>Importieren SharePoint Ergebnisse

Wenn Ihre Organisation höhergestufte Ergebnisse in SharePoint eingerichtet hat, können Sie die Titel, URLs und Beschreibungen aus den höhergestuften Ergebnissen für Ihren Mandanten in Microsoft Search importieren und die importierten Inhalte für Ihre Benutzer verfügbar machen. In den meisten Fällen dauert das Importieren SharePoint Ergebnisse nur wenige Minuten. Wenn Sie eine große Anzahl von Ergebnissen importieren, kann es bis zu 48 Stunden dauern. Dies ist eine einfache Möglichkeit, Suchergebnisse schnell aufzufüllen und für Ihre Benutzer effektiver zu gestalten. Es wird empfohlen, höhergestufte Ergebnisse aus SharePoint als Referenz zu verwenden, um zu verstehen, wie relevante Suchergebnisse bezeichnet und erstellt werden.

### <a name="add-default-and-suggested-bookmarks"></a>Hinzufügen von Standardlesezeichen und vorgeschlagenen Lesezeichen

Wir haben einige standardmäßig vorgeschlagene Lesezeichen hinzugefügt, die Ihre Benutzer möglicherweise hilfreich finden, einschließlich Lesezeichen für Personalwesen, Vorteile, IT-Support, Kennwortverwaltung und vieles mehr. Überprüfen, aktualisieren und veröffentlichen Sie diese vorgeschlagenen Lesezeichen, um Ihren Benutzern sofort qualitativ hochwertige Ergebnisse zu liefern.

Ihre Benutzer können auch Lesezeichen vorschlagen, die mithilfe von Feedbacklinks in Microsoft Search hinzugefügt werden sollen. Ihre Empfehlungen werden als vorgeschlagene Lesezeichen angezeigt.

### <a name="import-bookmarks"></a>Importieren von Lesezeichen

Verwenden Sie die Importfunktion, um das Hinzufügen oder Bearbeiten einer großen Anzahl von Lesezeichen zu beschleunigen und zu vereinfachen. Verwenden Sie es für Folgendes:

- Massenhinzufügen von Lesezeichen: Fügen Sie Details in der Textmarkenvorlagendatei hinzu, und importieren Sie sie.
- Massenbearbeitung von Lesezeichen: Exportieren Sie Lesezeichen in eine .csv Datei, bearbeiten Sie die Textmarkendetails in der exportierten Datei, und importieren Sie dann die bearbeitete Datei.

Einige wichtige Punkte zur Vorlagendatei:

- Daten in diesen Feldern niemals bearbeiten: *ID,* *zuletzt geändert* und zuletzt *geändert von*
- Wenn Sie die *ID* einer vorhandenen Textmarke einschließen, wird sie durch die Informationen in der Importdatei ersetzt.
- Bei vorhandenen Textmarken mit demselben Titel oder derselben URL wird die Textmarke mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und die erforderlichen Felder variieren je nach dem Lesezeichenstatus.
- Basierend auf dem *Feld "Status"* werden Lesezeichen als Entwurf gespeichert, vorgeschlagen, geplant, ausgeschlossen oder automatisch veröffentlicht.
- Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Lesezeichen aus einer Organisation exportieren und in eine andere importieren. Sie müssen jedoch die Daten in der *ID-Spalte* entfernen, bevor Sie importieren.

### <a name="prevent-import-errors"></a>Vermeiden von Importfehlern

Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind, und eine Protokolldatei mit weiteren Informationen über die zu korrigierenden Zeilen und Spalten wird erstellt. Nehmen Sie die notwendigen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren. Lesezeichen können erst importiert oder gespeichert werden, wenn alle Fehler behoben sind.

Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und:

- die Kopfzeile und alle Spalten enthält, die in der Importvorlage vorhanden waren
- die Spaltenreihenfolge die gleiche ist wie in der Importvorlage
- Alle Spalten haben Werte, mit Ausnahme der drei, die leer sein können: *ID,* *Last Modified* und Last *Modified By*
- Die *Spalte "Status"* ist nicht leer, es sind erforderliche Informationen erforderlich.
- Beim Importieren von Lesezeichen "Veröffentlicht", "Vorgeschlagen", "Geplant" oder "Entwurf" sind die Spalten *"Titel",* *"URL"* und *"Schlüsselwörter"* erforderlich.
- Beim Importieren von ausgeschlossenen Lesezeichen ist die *URL-Spalte* erforderlich.

So verhindern Sie Duplizierungsfehler zwischen Lesezeichen:

- Verwenden Sie keine doppelten URLs für verschiedene Lesezeichen. Wenn eine URL einer anderen Textmarke zugewiesen ist und Sie versuchen, sie erneut aus einer Importdatei hinzuzufügen, erhalten Sie einen Fehler. Dies gilt auch für doppelte URLs für andere Arten von Antworten.
- Verwenden Sie beim Aktualisieren vorhandener Textmarken die *Spalte "Lesezeichen-ID".* Sie können jede andere Eigenschaft einer vorhandenen Textmarke aktualisieren, z. B. ein Schlüsselwort oder eine Beschreibung. Sie sollten jedoch sicherstellen, dass sich die *Textmarken-ID* in der entsprechenden Spalte der Importdatei befindet. Wenn die *Lesezeichen-ID* vorhanden ist, wird sie nicht als Neuzufügung behandelt und nicht als Fehler verarbeitet.

### <a name="publish-or-review-recommended-bookmarks"></a>Veröffentlichen oder Überprüfen empfohlener Lesezeichen

Um den manuellen Aufwand für das Hinzufügen von Lesezeichen zu reduzieren, können Microsoft Search die SharePoint Links Ihrer Organisation auswerten und Lesezeichen empfehlen. Sie können sie vor der Veröffentlichung überprüfen oder festlegen, dass sie automatisch veröffentlicht werden. Es ist kein Setup für empfohlene Lesezeichen erforderlich, sie sind aktiviert und standardmäßig auf die automatische Veröffentlichung festgelegt. Um diese Einstellungen jederzeit zu ändern, wählen Sie **Lesezeichen verwalten aus,** um den Bereich "Lesezeicheneinstellungen" zu öffnen.

![Screenshot der Empfohlenen Lesezeicheneinstellungen im Microsoft 365-Verwaltungsportal.](media/bookmarks-recommendedsettings.png)

Wenn empfohlene Lesezeichen aktiviert sind, wertet das Empfehlungsmodul SharePoint Websites in Ihrer Organisation aus, um Links mit hohem Datenverkehr zu identifizieren. Nach einem anfänglichen Evaluierungszeitraum werden die empfohlenen Lesezeichen entweder automatisch veröffentlicht oder der Liste der vorgeschlagenen Lesezeichen hinzugefügt. Der nächste Zyklus – ein Auswertungszeitraum von 30 Tagen gefolgt von der automatischen Veröffentlichung oder dem Hinzufügen vorgeschlagener Lesezeichen – beginnt dann.

Wir empfehlen Suchadministratoren oder -editoren, diese automatisch veröffentlichten oder vorgeschlagenen Lesezeichen regelmäßig zu überprüfen. Außerdem enthalten empfohlene Lesezeichen niemals URLs, die in vorhandenen veröffentlichten, vorgeschlagenen, geplanten oder ausgeschlossenen Lesezeichen vorhanden sind.

Um sicherzustellen, dass nur Benutzer mit Zugriff ein empfohlenes Lesezeichen in den Arbeitsergebnissen sehen, ist eine Zugriffsüberprüfungsfunktion für alle empfohlenen Lesezeichen enthalten. Benutzern wird nie ein empfohlenes Lesezeichen für eine SharePoint Website angezeigt, auf die sie nicht zugreifen können. Diese Zugriffsüberprüfung wird durch die Option **"Nur Personen mit Zugriff auf diesen Link"** in der Einstellung "Gruppen" für jedes empfohlene Lesezeichen gesteuert.

Die Zugriffsüberprüfung wird beendet, wenn die URL in der empfohlenen Textmarke oder die Einstellung "Gruppen" geändert wird.

Um zu verhindern, dass das Empfehlungsmodul ein Lesezeichen auf einer bestimmten Website veröffentlicht oder vorschlägt, können Sie die URL zu einer ausgeschlossenen Liste hinzufügen. Das Empfehlungsmodul veröffentlicht oder schlägt niemals ein Lesezeichen für eine ausgeschlossene Website oder eine Seite innerhalb einer ausgeschlossenen Website vor.

## <a name="about-keywords-and-reserved-keywords"></a>Informationen zu Schlüsselwörtern und reservierten Schlüsselwörtern

Ein Lesezeichen kann mehrere Schlüsselwörter haben und dasselbe Schlüsselwort freigeben, aber reserviertes Schlüsselwort kann nicht freigegeben werden. Ein reserviertes Schlüsselwort ist ein eindeutiger Begriff oder Ausdruck, der eine bestimmte Textmarke auslöst. Ein reserviertes Schlüsselwort kann nur einer Antwort zugeordnet werden. Verwenden Sie reservierte Schlüsselwörter sparsam.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F: Wie lange dauert es, bis ein Lesezeichen in Microsoft Search nach der Veröffentlichung angezeigt wird?**

**A:**  Ein Lesezeichen ist in Microsoft Search unmittelbar nach der Veröffentlichung verfügbar.

**F: Wie lange dauert es, bis ein empfohlenes Lesezeichen angezeigt wird?**

**A:**  Empfohlene Lesezeichen werden nur in Microsoft Search angezeigt, wenn sowohl empfohlene Lesezeichen als auch die automatische Veröffentlichung aktiviert sind. Während des anfänglichen Evaluierungszeitraums wertet das Empfehlungsmodul SharePoint Datenverkehr aus, um geeignete Lesezeichen zu identifizieren und diese dann automatisch zu veröffentlichen. Nach der Veröffentlichung werden sie sofort in Microsoft Search verfügbar.

**F: Wie lange dauert es, bis ein gelöschtes Lesezeichen aus Microsoft Search Ergebnissen entfernt wird?**

**A:** Gelöschte Textmarken werden sofort aus den Arbeitsergebnissen entfernt.

**F: Wird Microsoft Search Lesezeichen von Websites in allen Sprachen empfehlen?**

**A:** Ja, Microsoft Search können Lesezeichen von jeder internen SharePoint Website empfehlen, unabhängig von der Sprache.

**F: Kann ich die Anzeige empfohlener Lesezeichen in Suchergebnissen beenden?**

**A:** Um die Anzeige empfohlener Lesezeichen zu beenden, deaktivieren Sie die Einstellung für die automatische Veröffentlichung in Ihrem Admin Center. Empfohlene Lesezeichen werden der Liste der vorgeschlagenen Lesezeichen hinzugefügt.

**F: Wie kann ich ein empfohlenes Lesezeichen in Suchergebnissen oder im Admin Center identifizieren?**

**A:** In Suchergebnissen enthalten empfohlene Lesezeichen den Ausdruck "Für Sie vorgeschlagen" vor der URL. Im Admin Center weisen empfohlene Lesezeichen den Besitzerwert "SYSTEM" auf.

**F: Wie wird der Zugriff auf ein empfohlenes Lesezeichen verwaltet?**

**A:** Ein von Microsoft entwickeltes Zugriffsmodul bestimmt, ob die Url des Lesezeichens für einen bestimmten Benutzer zugänglich ist, und zeigt nur die empfohlene Textmarke für die richtige Zielgruppe an. Wenn die URL jedoch bearbeitet wird oder die Gruppeneinstellung geändert wird, wird das Modul für den entwickelten Zugriff deaktiviert.

**F: Was geschieht, wenn keine Aktion für empfohlene Lesezeichen ausgeführt wird, die der Liste "Vorgeschlagen" hinzugefügt werden?**

**A:** Um eine hohe Anzahl von Lesezeichen in der vorgeschlagenen Liste zu vermeiden, wird ein empfohlenes Lesezeichen (Besitzer = SYSTEM) nach 180 Tagen gelöscht.

**F: Wo finde ich die App-ID für eine Power App?**

**A:** Wechseln Sie zur Power Apps Website, und zeigen Sie den Detailbereich für die App an. Weitere Informationen [zum Abrufen einer App-ID.](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id)