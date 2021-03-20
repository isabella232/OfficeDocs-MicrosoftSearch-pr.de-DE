---
title: Verwalten von Lesezeichen
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Erstellen und Aktualisieren von Lesezeichen und Möglichkeiten zum Massenbearbeitung von Lesezeichenergebnissen für Microsoft Search
ms.openlocfilehash: b801e75f772a585c2ddfedd09aff3b74c1d909b5
ms.sourcegitcommit: 2f770de12b27546b18b2e86517d2c25522eb9022
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929607"
---
# <a name="manage-bookmarks"></a>Verwalten von Lesezeichen

Lesezeichen helfen Personen bei der schnellen Suche nach wichtigen Websites und Tools. Jede Textmarke enthält einen Titel, eine URL, eine Reihe benutzerfreundlicher Schlüsselwörter zum Auslösen des Lesezeichens und eine Kategorie.

## <a name="what-makes-a-great-bookmark"></a>Was ein großartiges Lesezeichen macht

Ein großartiges Lesezeichen verfügt über vier Schlüsselelemente:

1. Ein starker, informativer **Titel**. Zielen Sie auf maximal acht Wörter oder maximal 60 Zeichen. Sie möchten, dass Ihre Benutzer auf den Titel klicken und den Inhalt anzeigen, aber vermeiden Sie offensichtliches Clickbait:
    - Gut: Probieren Sie die beliebten Favoriten dieser Woche aus dem Menü der Cafeteria aus. Der Titel ist klar, prägnant und interessant, könnte aber überpromierend sein.
    - Besser: Das Menü der Mensa in dieser Woche. Überpromise oder klingt nicht wie eine Anzeige.
    - Vermeiden: Sie werden nicht glauben, was in dieser Woche in das Menü der Mensa kommt. Verwendet Clickbait-Klischees, die wie eine Anzeige klingen.
2. Eine prägnierte Beschreibung , ca. 300 Zeichen, die den Zweck oder die Funktionalität der verknüpften Ressource zusammenfasst.
3. Eine Sammlung von **Schlüsselwörtern,** die Personen beim Suchen helfen, das Lesezeichen zu finden. Wir empfehlen mindestens fünf Schlüsselwörter. Schließen Sie auch Variationen ein, die von Personen in Ihrer Organisation verwendet werden können, z. B. Menümenüs, Mittagsmenüs und Cafémenüs, die alle Variationen für das Menü "Cafeteria" sein können.
4. Eine hilfreiche Reihe von **Kategorien,** die das Sortieren und Filtern von Lesezeichen im Admin Center vereinfachen. Den Benutzern werden die zugewiesenen Kategorien nie angezeigt.

## <a name="create-bookmark-answers"></a>Erstellen von Textmarkenantworten

Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com/)zu Lesezeichen, und wählen Sie aus, wie Sie neue Lesezeichen erstellen möchten: [](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks)

- Hinzufügen von Lesezeichen
- Importieren von SharePoint-Ergebnissen
- Hinzufügen von Standardmarken und vorgeschlagenen Lesezeichen
- Importieren von Lesezeichen
- Veröffentlichen oder Überprüfen empfohlener Lesezeichen

### <a name="add-bookmarks"></a>Hinzufügen von Lesezeichen

Suchadministratoren und -editoren können Lesezeichen im Microsoft 365 Admin Center hinzufügen und sie entweder veröffentlichen oder im Entwurf speichern. Durch das Veröffentlichen einer Textmarke wird der Suchindex sofort aktualisiert, damit er sofort für Benutzer gefunden werden kann. Sie können auch ein Lesezeichen planen, indem Sie Datum und Uhrzeit der Veröffentlichung angeben.

- **Veröffentlicht**: Lesezeichen stehen den Benutzern der Organisation über Microsoft Search zur Verfügung.
- **Entwurf**: Als Entwürfe gespeicherte Lesezeichen stehen Ihren Benutzern nicht zur Verfügung. Verwenden Sie diesen Status, wenn Sie oder andere Beteiligte Lesezeichen überprüfen oder aktualisieren möchten, bevor Sie sie veröffentlichen.
- **Scheduled**: Bookmarks that will be published on the specified date and time.

Sie können die Microsoft Search Content Creator-Browsererweiterung verwenden, um lesezeichen einfach hinzuzufügen. Um die Browsererweiterung zu installieren, wechseln Sie zu der Website, die Sie als Lesezeichen hinzufügen möchten, und klicken Sie in der Erweiterung auf Hinzufügen.
Installieren Sie die Erweiterung für Edge und Chrome:

- Für Chromium Edge oder Chrome: Wechseln Sie zum [Chrome Web Store,](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) und fügen Sie die Erweiterung hinzu.
- Legacy-Edge: Wechseln Sie zum [Microsoft Store,](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) und fügen Sie die Erweiterung hinzu.

### <a name="import-sharepoint-results"></a>Importieren von SharePoint-Ergebnissen

Wenn Ihre Organisation in SharePoint heraufgestufte Ergebnisse eingerichtet hat, können Sie die Titel, URLs und Beschreibungen aus den heraufgestuften Ergebnissen für Ihren Mandanten in Microsoft Search importieren und die importierten Inhalte Ihren Benutzern zur Verfügung stellen. In den meisten Fällen dauert das Importieren von SharePoint-Ergebnissen nur wenige Minuten. Wenn Sie eine große Anzahl von Ergebnissen importieren, kann es bis zu 48 Stunden dauern. Dies ist eine einfache Möglichkeit, suchergebnisse schnell auffüllen und effektiver für Ihre Benutzer zu machen. Es wird empfohlen, heraufgestufte Ergebnisse aus SharePoint als Referenz zu verwenden, um zu verstehen, wie relevante Suchergebnisse bezeichnet und erstellt werden.

### <a name="add-default-and-suggested-bookmarks"></a>Hinzufügen von Standard- und vorgeschlagenen Lesezeichen

Wir haben einige vorgeschlagene Standardmarken für Benutzer hinzugefügt, z. B. Lesezeichen für Personalwesen, Vorteile, IT-Unterstützung, Kennwortverwaltung und vieles mehr. Überprüfen, aktualisieren und veröffentlichen Sie diese vorgeschlagenen Lesezeichen, um Ihren Benutzern sofort qualitativ hochwertige Ergebnisse zu bieten.

Ihre Benutzer können auch Lesezeichen vorschlagen, die mithilfe von Feedbacklinks in Microsoft Search hinzugefügt werden möchten. Ihre Empfehlungen werden als vorgeschlagene Lesezeichen angezeigt.

### <a name="import-bookmarks"></a>Importieren von Lesezeichen

Verwenden Sie das Import-Feature, um das Hinzufügen oder Bearbeiten einer großen Anzahl von Textmarken schneller und einfacher zu gestalten. Verwenden Sie es für:

- Massen hinzufügen von Lesezeichen: Fügen Sie Details in die Lesezeichenvorlagendatei hinzu, und importieren Sie sie dann.
- Massenbearbeitung von Lesezeichen: Exportieren Sie Lesezeichen in eine CSV-Datei, bearbeiten Sie die Lesezeichendetails in der exportierten Datei, und importieren Sie dann die bearbeitete Datei.

Einige wichtige Punkte zur Vorlagendatei:

- Daten in diesen Feldern nie *bearbeiten: ID*, *Last Modified* und Last *Modified By*
- Wenn Sie die *ID* einer vorhandenen Textmarke hinzufügen, wird sie durch die Informationen in der Importdatei ersetzt.
- Bei vorhandenen Lesezeichen mit demselben Titel oder derselben URL wird die Textmarke mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und die erforderlichen Felder variieren je nach dem Lesezeichenstatus.
- Basierend auf dem *Feld Status* werden Lesezeichen als Entwurf, Vorgeschlagen, Geplant, Ausgeschlossen oder automatisch veröffentlicht.
- Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Lesezeichen aus einer Organisation exportieren und in eine andere importieren. Sie müssen jedoch die Daten in der Spalte *ID entfernen,* bevor Sie importieren.

### <a name="prevent-import-errors"></a>Vermeiden von Importfehlern

Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind, und eine Protokolldatei mit weiteren Informationen über die zu korrigierenden Zeilen und Spalten wird erstellt. Nehmen Sie die notwendigen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren. Sie können lesezeichen erst importieren oder speichern, wenn alle Fehler behoben sind.

Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und:

- die Kopfzeile und alle Spalten enthält, die in der Importvorlage vorhanden waren
- die Spaltenreihenfolge die gleiche ist wie in der Importvorlage
- Alle Spalten haben Werte, mit Ausnahme der drei Werte, die leer sein *können:* *ID*, *Last Modified* und Last Modified By
- Die *Spalte* Status ist nicht leer, es sind erforderliche Informationen
- Beim Importieren von Veröffentlichten, Vorgeschlagenen, Geplanten oder Entwurfsmarken sind die Spalten *Titel,* *URL* und *Schlüsselwörter* erforderlich.
- Beim Importieren ausgeschlossener Lesezeichen ist die *SPALTE URL* erforderlich.

So verhindern Sie Duplizierungsfehler zwischen Textmarken:

- Verwenden Sie keine doppelten URLS für unterschiedliche Lesezeichen. Wenn einer anderen Textmarke eine URL zugewiesen ist und Sie versuchen, sie erneut aus einer Importdatei hinzuzufügen, wird eine Fehlermeldung angezeigt. Dies gilt auch für doppelte URLs für andere Arten von Antworten.
- Verwenden Sie beim Aktualisieren vorhandener Lesezeichen die *Spalte Lesezeichen-ID.* Sie können jede andere Eigenschaft eines vorhandenen Lesezeichens aktualisieren, z. B. Stichwort oder Beschreibung, sie sollten jedoch sicherstellen, dass sich die *Lesezeichen-ID* in der entsprechenden Spalte der Importdatei befindet. Wenn die *Lesezeichen-ID* vorhanden ist, wird sie nicht als neues Hinzufügen behandelt und nicht als Fehler verarbeitet.

### <a name="publish-or-review-recommended-bookmarks"></a>Veröffentlichen oder Überprüfen empfohlener Lesezeichen

Um den manuellen Aufwand zum Hinzufügen von Lesezeichen zu reduzieren, kann Microsoft Search die SharePoint-Links Ihrer Organisation auswerten und Lesezeichen empfehlen. Sie können sie vor der Veröffentlichung überprüfen oder so festlegen, dass sie automatisch veröffentlicht werden. Für empfohlene Lesezeichen ist kein Setup erforderlich, sie sind aktiviert und standardmäßig auf automatische Veröffentlichung festgelegt. Wenn Sie diese Einstellungen jederzeit ändern möchten, wählen Sie **Lesezeichen verwalten** aus, um den Bereich Lesezeicheneinstellungen zu öffnen.

![Screenshot der empfohlenen Lesezeicheneinstellungen im Microsoft 365 Admin Portal](media/bookmarks-recommendedsettings.png)

Wenn empfohlene Lesezeichen aktiviert sind, wertet das Empfehlungsmodul SharePoint-Websites in Ihrer Organisation aus, um Links mit hohem Datenverkehr zu identifizieren. Nach einem ersten Auswertungszeitraum werden die empfohlenen Lesezeichen entweder automatisch veröffentlicht oder der Liste der vorgeschlagenen Lesezeichen hinzugefügt. Der nächste Zyklus – ein 30-tägiger Evaluierungszeitraum gefolgt von der automatischen Veröffentlichung oder dem Hinzufügen vorgeschlagener Lesezeichen – beginnt dann.

Es wird empfohlen, dass Suchadministratoren oder -editoren diese automatisch veröffentlichten oder vorgeschlagenen Lesezeichen regelmäßig überprüfen. Außerdem enthalten empfohlene Lesezeichen nie URLs, die in vorhandenen Veröffentlichten, Vorgeschlagenen, Geplanten oder Ausgeschlossenen Lesezeichen gefunden wurden.

Um sicherzustellen, dass nur Benutzern mit Zugriff ein empfohlenes Lesezeichen in den Arbeitsergebnissen angezeigt wird, ist für alle empfohlenen Lesezeichen ein Zugriffsüberprüfungsfeature enthalten. Benutzern wird nie ein empfohlenes Lesezeichen für eine SharePoint-Website, auf die sie nicht zugreifen können, gesehen. Diese Zugriffsüberprüfung wird durch die Option **Nur** Personen mit Zugriff auf diesen Link in der Gruppeneinstellung für jedes empfohlene Lesezeichen gesteuert.

Die Zugriffsüberprüfung wird beendet, wenn die URL in der empfohlenen Textmarke oder die Gruppeneinstellung geändert wird.

Um zu verhindern, dass das Empfehlungsmodul einer bestimmten Website ein Lesezeichen veröffentlicht oder vor schlägt, können Sie die URL einer ausgeschlossenen Liste hinzufügen. Das Empfehlungsmodul veröffentlicht oder schlägt niemals ein Lesezeichen für eine ausgeschlossene Website oder Seite innerhalb einer ausgeschlossenen Website vor.

## <a name="about-keywords-and-reserved-keywords"></a>Informationen zu Schlüsselwörtern und reservierten Schlüsselwörtern

Ein Lesezeichen kann mehrere Schlüsselwörter enthalten und dasselbe Schlüsselwort freigeben, reservierte Schlüsselwörter können jedoch nicht freigegeben werden. Ein reserviertes Schlüsselwort ist ein eindeutiger Ausdruck oder Ausdruck, der eine bestimmte Textmarke auslöst. Ein reserviertes Schlüsselwort kann nur einer Antwort zugeordnet werden. Verwenden Sie reservierte Schlüsselwörter sparsam.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F: Wie lange dauert es, bis ein Lesezeichen in Microsoft Search nach der Veröffentlichung sichtbar ist?**

**A:**  Eine Textmarke steht in Microsoft Search unmittelbar nach der Veröffentlichung zur Verfügung.

**F: Wie lange dauert es, bis ein empfohlenes Lesezeichen angezeigt wird?**

**A:**  Empfohlene Lesezeichen werden nur in Microsoft Search angezeigt, wenn sowohl empfohlene Lesezeichen als auch automatische Veröffentlichung aktiviert sind. Während des anfänglichen Evaluierungszeitraums wertet das Empfehlungsmodul den SharePoint-Datenverkehr aus, um geeignete Lesezeichen zu identifizieren und diese automatisch zu veröffentlichen. Nach der Veröffentlichung werden sie sofort in Microsoft Search verfügbar.

**F: Wie lange dauert es, bis ein gelöschtes Lesezeichen aus den Microsoft-Suchergebnissen entfernt wird?**

**A:** Gelöschte Lesezeichen werden sofort aus den Arbeitsergebnissen entfernt.

**F: Wird Microsoft Search Lesezeichen von Websites in allen Sprachen empfehlen?**

**A:** Ja, Microsoft Search kann Lesezeichen von einer beliebigen internen SharePoint-Website empfehlen, unabhängig von der Sprache.

**F: Kann ich die Anzeige empfohlener Lesezeichen in Suchergebnissen beenden?**

**A:** Um die Anzeige empfohlener Lesezeichen zu beenden, deaktivieren Sie die Automatische Veröffentlichung in Ihrem Admin Center. Empfohlene Lesezeichen werden der Liste der vorgeschlagenen Lesezeichen hinzugefügt.

**F: Wie kann ich ein empfohlenes Lesezeichen in Suchergebnissen oder im Admin Center identifizieren?**

**A:** In den Suchergebnissen enthalten empfohlene Lesezeichen den Ausdruck "Vorgeschlagen für Sie" vor der URL. Im Admin Center haben empfohlene Lesezeichen den Besitzerwert "SYSTEM".

**F: Wie wird der Zugriff auf eine empfohlene Textmarke verwaltet?**

**A:** Ein microsoft-technisches Zugriffsmodul bestimmt, ob auf die Lesezeichen-URL für einen bestimmten Benutzer zugegriffen werden kann und zeigt die empfohlene Textmarke nur der richtigen Zielgruppe an. Wenn die URL jedoch bearbeitet oder die Gruppeneinstellung geändert wird, wird das Modul für den technischen Zugriff deaktiviert.

**F: Was geschieht, wenn für empfohlene Lesezeichen, die der Vorgeschlagenen Liste hinzugefügt wurden, keine Aktion ergriffen wird?**

**A**: Um eine hohe Anzahl von Lesezeichen in der vorgeschlagenen Liste zu vermeiden, wird ein empfohlenes Lesezeichen (Besitzer = SYSTEM) nach 180 Tagen gelöscht.

**F: Wo finde ich die App-ID für eine Power App?**

**A:** Wechseln Sie zur Power Apps-Website, und zeigen Sie den Detailbereich für die App an. Erfahren Sie mehr über [das Abrufen einer App-ID](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id).
