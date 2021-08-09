---
title: Inhalte mit Microsoft Search leicht auffindbar machen
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Erstellen Sie Lesezeichen, Standorte und F&A-Artikel, um die Inhalte Ihrer Organisation leicht auffindbar zu machen.
ms.openlocfilehash: 0cf3152e7fb47f0cb1b1fa3fe0df43645a2536e171fd8211050a1773ec86a490
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532939"
---
# <a name="make-content-easy-to-find"></a>Inhalte leicht auffindbar machen

Microsoft Search hilft Benutzern, relevante Inhalte zu finden. Ist eine sichere Möglichkeit, sowohl Ihre Intranet- als auch Ihre Webinhalte zu durchsuchen. Diese Art der web- und organisationsübergreifenden Integration gibt es nur bei Microsoft. Mit Microsoft Search können Administratoren ihr Wissen über eine Organisation nutzen, um die relevanten Inhalte für Benutzer leicht auffindbar zu machen. 

## <a name="components-that-find-content"></a>Komponenten, die Inhalte finden
In Microsoft Search erstellen Administratoren [Lesezeichen,](manage-bookmarks.md) [PowerApps,](integrate-powerapps.md) [F&A](manage-qas.md)und [Speicherorte,](manage-locations.md) die die Suche von Inhalten vereinfachen. Jede dieser Suchkomponenten enthält einen Titel, eine URL und eine Gruppe von Schlüsselwörtern, die sie auslösen.

## <a name="bookmarks"></a>Lesezeichen
Sie können [Lesezeichen](manage-bookmarks.md) in nur wenigen Schritten erstellen. Jedes Lesezeichen enthält einen Titel, eine URL und eine Gruppe von Schlüsselwörtern, die es auslösen. Ein Lesezeichen kann mehrere Schlüsselwörter haben, und mehrere Lesezeichen können dasselbe Schlüsselwort verwenden. Reservierte Schlüsselwörter können jedoch nicht freigegeben werden. Wenn Sie ein Lesezeichen erstellen oder ändern, wird der Suchindex aktualisiert, und das Lesezeichen steht benutzern sofort zur Verfügung.

Wenn Ihre Organisation in [SharePoint](http://sharepoint.com/) **höhergestufte Ergebnisse** eingerichtet hat, können Sie diese Ergebnisse in Microsoft Search importieren. Mit höhergestuften Ergebnissen können Sie Suchergebnisse schnell auffüllen, die Inhalte für Benutzer verfügbar machen und Microsoft Search effektiver machen, sobald Sie sie einrichten. Wir empfehlen Ihnen, höhergestufte Ergebnisse aus SharePoint als Referenz zu verwenden, um zu verstehen, wie man relevante Suchergebnisse benennt und erstellt. 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>Hinzufügen oder Bearbeiten von Lesezeichen mithilfe von Browsererweiterungen
Suchadministratoren können Suchinhalte mühelos mithilfe von Browsererweiterungen erstellen. Um die Website als Lesezeichen hinzuzufügen, installieren Sie die Browsererweiterung. Wechseln Sie dann zur Website, und fügen Sie sie als Lesezeichen hinzu. Weitere Informationen finden Sie unter [Verwalten von Lesezeichen.](manage-bookmarks.md)

Derzeit sind Browsererweiterungen für [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) und [Google Chrome](https://www.google.com)verfügbar: 
- Um die Edge-Erweiterung herunterzuladen, wechseln Sie zum [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Um die Chrome-Erweiterung herunterzuladen, wechseln Sie zum [Chrome Web Store.](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)

## <a name="powerapps"></a>PowerApps

Durch Hinzufügen vorhandener [PowerApps](integrate-powerapps.md) zu Ihren [Lesezeichen](manage-bookmarks.md)können Benutzer Aufgaben wie das Eingeben von Urlaubszeiten oder das Melden von Ausgaben erledigen. 

Mit [PowerApps](integrate-powerapps.md)können Sie Geschäfts-Apps erstellen, die in einem Browser oder auf einem Smartphone oder Tablet ausgeführt werden. Es ist keine Codierung erforderlich. PowerApps funktionieren in jedem Browser und auf jedem Gerät. Das Hinzufügen dauert weniger als eine Minute. Weitere Informationen zu PowerApps finden Sie in den folgenden Artikeln:
- [Geführtes Lernen](/learn/browse/?products=powerapps)
- [PowerApps-Dokumentation](/powerapps/maker/canvas-apps/get-sessionid)
- [PowerApps home](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Hinzufügen einer PowerApp zu einem Lesezeichen

1. Suchen Sie die [App-ID](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) für die PowerApp, die Sie hinzufügen möchten.
1. Wechseln Sie im Microsoft 365 [Admin Center](https://admin.microsoft.com)zu **Einstellungen**  >  **Microsoft Search**. 
1. Fügen Sie ein Lesezeichen hinzu oder suchen Sie ein vorhandenes Lesezeichen, dem Sie eine PowerApp hinzufügen möchten.
1. Wählen Sie in **den Lesezeicheneinstellungen** **Power App** aus. Wählen Sie dann **"Power App hinzufügen"** aus.
1. Geben Sie die **App-ID** ein. Die Höhe und Breite werden automatisch angepasst. [Lesezeichen](manage-bookmarks.md) können sowohl Hoch- als auch Querformat unterstützen, die Größe kann jedoch derzeit nicht geändert werden. Um das Testen zu vereinfachen, zeigt die Lesezeichenvorschau eine voll funktionsfähige PowerApp an.
1. Wählen Sie **Veröffentlichen** oder **Als Entwurf speichern** aus.

## <a name="qa"></a>F&A

Das Erstellen einer [F-&A](manage-qas.md) entspricht dem Erstellen von [Lesezeichen.](manage-bookmarks.md) Mit F&A können Sie Antworten auf Benutzerfragen anstelle eines Links zur Webseite bereitstellen. Sie können Antworten in Rich-Text mithilfe der verfügbaren Tools formatieren. Wenn ein Lesezeichen und ein Q-&A dasselbe Schlüsselwort verwenden, wird zuerst das Lesezeichenergebnis angezeigt. Wie Lesezeichen wird der Q&A-Index unmittelbar nach dem Hinzufügen oder Ändern eines Q-&A aktualisiert. 

### <a name="supported-html-tags"></a>Unterstützte HTML-Tags

Sie können HTML-Inhalte verwenden oder Ihrer Antwort oder Beschreibung HTML-Tags hinzufügen. Wir unterstützen diese HTML-Tags:
 
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

Nicht unterstützte Tags werden entweder ignoriert oder als Text angezeigt. Sie sollten vorab eine Vorschau Ihrer Karten anzeigen.

> [!Note]
> Sie können Q-&A-Elemente nicht importieren, wenn fehler in der Vorlagendatei vorhanden sind. Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und alle erforderlichen Informationen enthält. Weitere Informationen zum Verhindern von [Importfehlern.](#prevent-import-errors)

## <a name="locations"></a>Speicherorte

Mit ["Standorte"](manage-locations.md)können Ihre Benutzer Adressen finden und Gebäude Ihrer Organisation finden. Die **Standortfunktion** bietet einen genauen Ort für Büros, Campus und Gebäude sowie Wegbeschreibungen und Navigation. Um optimale Ergebnisse zu erzielen, müssen Administratoren alle wichtigen Standorte ihrer Organisation zu Microsoft Search hinzufügen. Im Gegensatz zu [Lesezeichen](manage-bookmarks.md) und [F&A](manage-qas.md)wird der Speicherortindex nicht sofort aktualisiert. Es kann mehrere Stunden dauern, bis neue oder geänderte Speicherorte in suchergebnissen angezeigt werden.

## <a name="get-started"></a>Erste Schritte
Um herauszufinden, was Ihre Benutzer benötigen, und um diese Informationen leicht zu finden, probieren Sie einige der folgenden Methoden aus:

- Ermitteln Sie die Websites und Seiten mit dem meisten Datenverkehr anhand von Intranetsuchprotokollen.
- Ermitteln Sie Apps, Websites und Tools, die täglich oder wöchentlich verwendet werden.
- Suchen Sie direkte Links für Mitarbeitervergütungen.
- Suchen Sie Richtlinien und Prozesse, die Benutzer kennen müssen.
- Entscheiden Sie, an welchen Benutzer sich der Support wenden soll und wie dies funktioniert.
- Abrufen von Informationen, die in regelmäßigen Abständen erforderlich sind, entweder in der Branche oder basierend auf Geschäftszyklen. Ein Beispiel sind Personen, die nach Tools suchen, um Arbeitsfreie Zeit oder vierteljährliche Finanzupdates zu reservieren.
- Sammeln von Richtlinien für regionale oder mobile Benutzer. Beispiele sind Vorteile, die je nach Standort variieren.
- Ermitteln sie interne Websites und Informationen für allgemeine Websuchen. Beispiele sind Datenverkehr, Informationen zum öffentlichen Transit, lokales Wetter, Rabatte, die von Unternehmenspartnern zur Verfügung stehen, sowie Gesundheits- und Fitnessprogramme.
- Suchen Sie Informationen zu vom Unternehmen geförderten Veranstaltungen, Konferenzen oder Erholungsangeboten.
- Recherchieren Sie allgemeine Probleme bei IT, Personalwesen und Support sowie häufig gestellte Fragen (FAQs) und die Antworten darauf.

## <a name="involve-smes-and-users"></a>Einbeziehen von SMEs und Benutzern
In einer Organisation suchen Benutzer nach einer Reihe einfacher bis komplexer Themen. Einfache Beispiele sind Office-Adressen und Mitarbeitervorteile. Komplexe Beispiele sind neue Arbeitsprozesse, technische Informationen und Vorgehensweisen. Um eine so große Vielfalt an Inhalten zu erstellen oder zu finden, benötigen Sie Fachwissen in verschiedenen Bereichen, Themen und Technologien. 

Die meisten Suchadministratoren verfügen nicht über spezifische Kenntnisse zu jedem Thema. Um die Menge der verfügbaren Inhalte ohne Hilfe von externen Ressourcen zu skalieren, suchen Sie Fachwissen und Wissen von anderen Personen in Ihrer Organisation.

### <a name="get-content-from-smes"></a>Abrufen von Inhalten von SMEs
Nutzen Sie die Fachexperten (Subject Matter Experts, SMEs) in Ihrer Organisation, einschließlich Experten aus Personalwesen, Support, Vertrieb, Technologie und anderen wichtigen Bereichen. SMEs können Inhalte direkt beitragen, wenn Sie sie als Microsoft Search-Editoren hinzufügen. 

### <a name="involve-your-users"></a>Einbeziehen Ihrer Benutzer
Bitten Sie Benutzer, Ressourcen als Lesezeichen vorzuschlagen. Bitten Sie Benutzer außerdem, Fehler wie fehlerhafte oder ungültige Links zu melden.

## <a name="set-up-components"></a>Einrichten von Komponenten
Um einzelne Oder [Massenlesezeichen](manage-bookmarks.md), [Q&A](manage-qas.md)und [Speicherorte](manage-locations.md)hinzuzufügen oder zu bearbeiten, führen Sie die Schritte in den folgenden Abschnitten aus. 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>Hinzufügen oder Bearbeiten einer einzelnen Lesezeichen-, Q-&A- oder Standortkomponente
1. Wechseln Sie im Microsoft 365 [Admin Center](https://admin.microsoft.com)zu **Einstellungen**  >  **Microsoft Search**. Wählen Sie die benannte Registerkarte der Komponente aus. Die Registerkarte **"Lesezeichen"** ist standardmäßig ausgewählt.
1. Wählen Sie zum Hinzufügen einer Komponente die Option **"Neu hinzufügen"** aus. 
1. Um eine Komponente zu bearbeiten, wählen Sie die Textmarke in der entsprechenden Komponentenliste aus. 
1. Während Sie die Informationen hinzufügen oder bearbeiten, wird die Vorschau automatisch aktualisiert.

### <a name="bulk-add-or-edit-components"></a>Massenzufügen oder Bearbeiten von Komponenten
Mit den **Import-** und **Exportfunktionen** können Suchadministratoren [Lesezeichen,](manage-bookmarks.md) [F&A](manage-qas.md)und [Speicherorte](manage-locations.md)massenweise erstellen oder bearbeiten. Dieses Feature ist hilfreich, wenn ein Administrator viele Komponenten hinzufügen oder bearbeiten möchte. 

Die Import- und Exportfeatures bieten folgende Funktionen:
- **Massenzufügen von**. Fügen Sie Details in die Vorlagendatei der Komponente ein, und importieren Sie sie.
- **Massenbearbeitung**. Exportieren Sie Komponenten in eine CSV-Datei, bearbeiten Sie dann die Textmarkendetails in der exportierten CSV-Datei, und importieren Sie dann die aktualisierte CSV-Datei.
- **Importieren höhergestufter Websites aus [SharePoint](http://sharepoint.com/)**. Dieses Feature gilt nur für [Lesezeichen](manage-bookmarks.md).
- **Sicherung**. Exportieren sie Komponenten in eine CSV-Datei.

Gehen Sie folgendermaßen vor, um Komponenten zu importieren oder zu exportieren:
1. Wählen Sie in der oberen rechten Ecke der benannten Registerkarte der Komponente die Option **"Importieren"** aus. 
1. Um alle vorhandenen Komponenten in einer CSV-Datei herunterzuladen, wählen Sie **Exportieren** aus.
1. Wählen Sie im rechten Bereich die Option zum Importieren mithilfe einer CSV-Datei oder aus [SharePoint](http://sharepoint.com/)aus.
1. Laden Sie die Vorlagendatei der Komponente herunter, um eine Liste der erforderlichen Felder und Details abzurufen. 
1. Hinzufügen oder Bearbeiten von Komponentendetails in der Vorlagendatei. Speichern Sie es dann auf Ihrem Computer. 
1. Wählen Sie im **Importbereich** der Komponente **"Durchsuchen" aus.** Wählen Sie dann die gewünschte CSV-Datei aus, und wählen Sie **"Importieren"** aus.

### <a name="template-guidelines"></a>Vorlagenrichtlinien
Beachten Sie diese Richtlinien und Einschränkungen beim Arbeiten mit Vorlagendateien:
- Daten in diesen Feldern nie bearbeiten: *ID,* *Zuletzt geändert* und zuletzt *geändert von*.
- Wenn Sie die *ID* einer vorhandenen Textmarke einschließen, wird sie durch die Informationen in der Importdatei ersetzt.
- Wenn in der vorhandenen Datei eine Textmarke mit demselben Titel oder derselben URL vorhanden ist, wird die Textmarke mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und erforderliche Felder variieren je nach Lesezeichenstatus.
- Basierend auf dem *Feld "Status"* werden Lesezeichen als **Entwurf,** **vorgeschlagen** oder **geplant** gespeichert. Andernfalls werden sie automatisch veröffentlicht.
- Wenn Sie mehrere Organisationen verwalten, können Sie Ihre Lesezeichen aus einer Organisation exportieren und in eine andere importieren. Sie müssen jedoch die Daten in der Spalte *ID* vor dem Import entfernen.

> [!Note]
> Sie können Komponentenelemente nicht importieren, wenn fehler in der Vorlagendatei vorhanden sind. Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und alle erforderlichen Informationen enthält.

### <a name="prevent-import-errors"></a>Vermeiden von Importfehlern

Wenn erforderliche Daten fehlen oder ungültig sind, wird eine Fehlermeldung angezeigt. Eine Protokolldatei generiert weitere Informationen zu den Zeilen und Spalten, die korrigiert werden sollen. Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie erneut, die Datei zu importieren. Lesezeichen können erst importiert oder gespeichert werden, wenn alle Fehler behoben sind.

Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und die folgenden Anforderungen erfüllt:
- Die Kopfzeile und alle Spalten in der Importvorlage sind enthalten.
- Die Spaltenreihenfolge ist identisch mit der Importvorlage.
- Alle Spalten haben Werte, mit Ausnahme der drei, die leer sein können: *ID*, *Last Modified* und Last *Modified By*. 
- Die Spalte *"Status"* ist nicht leer.

### <a name="titles-and-descriptions"></a>Titel und Beschreibungen
Verbundene Titel und Beschreibungen helfen Benutzern zu bestimmen, ob die Ergebnisse ihre Suchabfrage beantworten. Gute Titel und Beschreibungen spiegeln den Hauptzweck des Ergebnisses wider. Ein Beispiel ist der Titel "Leistungen für **Die Pflege"** mit der Beschreibung *"Informationen zu Den Vorteilen, die ihnen helfen, die Kosten für* die Pflege zu bezahlen". Mit diesen verbundenen Daten können Benutzer, die nach **Einerdingen** suchen, finanzielle Unterstützungsvorteile finden und einen Link erhalten, um mehr zu erfahren.

### <a name="keywords"></a>Schlüsselwörter
Mit Schlüsselwörtern können Benutzer in Ihrer Organisation relevante Inhalte suchen und suchen. Sie müssen Schlüsselwörter den zugehörigen Suchergebnissen zuordnen. Microsoft Search schlägt Schlüsselwörter basierend auf dem Titel und der URL Ihrer Inhalte vor. Um weitere Schlüsselwörter zu identifizieren, erhalten Sie Antworten auf diese Fragen:

1. **Welche Suchbegriffe können die von Ihnen identifizierten Informationen finden?** Verweisen Sie auf alle vorhandenen Terminologie in Ihrer Organisation sowie auf verwandte Variationen, Akronyme, Themen und Themen.
1. **Welche Variationen oder Wörter werden verwendet, um über diese Informationen zu sprechen?** Bitten Sie Ihr Supportteam, diese Schlüsselwörter bereitzustellen.

Wenn Sie z. B. ein Ergebnis erstellen, das auf ein Tool zum Übermitteln von Urlaubsanfragen verweist, sind die Schlüsselwörter **"Urlaub"** und **"Urlaubsanfrage übermitteln"** gute Optionen. Benutzer in Ihrer Organisation suchen möglicherweise auch nach urlaubsbezogenen Informationen mit **Feiertagen** oder **arbeitsfreien Zeiten.** Um benutzern das Auffinden relevanter Inhalte zu erleichtern, fügen Sie diese Schlüsselwörter und andere Wie z. B. die Übermittlung von **Feiertagsanfragen** und **die Anforderung einer Arbeitsfreie Zeit** hinzu.

### <a name="reserved-keywords"></a>Reservierte Schlüsselwörter
 Ein reserviertes Schlüsselwort ist ein eindeutiger Begriff oder Ausdruck, der ein Ergebnis auslöst. Im Gegensatz zu anderen Schlüsselwörtern sind reservierte Schlüsselwörter nur einem Ergebnis zugeordnet. Verwenden Sie reservierte Schlüsselwörter nur sparsam, damit Microsoft Search auf der Grundlage ihrer Nutzung lernen kann.

Ein Beispiel ist ein Lesezeichen für eine Website zum Übermitteln Ihrer Stunden. Wenn **die Protokollzeit** ein reserviertes Schlüsselwort ist, sehen Benutzer in Ihrer Organisation, die nach **Protokollzeit** suchen, diese Website als einziges Lesezeichen im Feld Microsoft Search. 

### <a name="group-related-content-with-keywords"></a>Gruppieren verwandter Inhalte mit Schlüsselwörtern
Wenn Benutzer nach Sätzen verwandter Inhalte suchen sollen, wenn sie nach einem bestimmten Begriff suchen, weisen Sie allen verwandten Inhalten dasselbe Schlüsselwort zu. Ein Beispiel ist die Suche nach Prozessen und Tools im Umgang mit Änderungen des Lebenszyklus. Um Antworten zum Aktualisieren von Vorteilen, Steuerinformationen sowie Namens- und Aliasänderungen zu gruppieren, schließen Sie ein Schlüsselwort wie **"Stichwörter"** ein.

### <a name="search-settings"></a>Sucheinstellungen
Mithilfe von Sucheinstellungen können Sie Ihre Inhalte anpassen und bestimmte Benutzergruppen ansprechen. Diese Microsoft Search Einstellungen steuern, wann ein Suchergebnis angezeigt wird und wer es sehen kann:

- **Datum**. Um zu steuern, wann Inhalte verfügbar oder nicht verfügbar sind, legen Sie ein Startdatum und ein Enddatum fest. Beispielsweise wird zeitsensibles Material in Suchergebnissen angezeigt, wenn es relevant ist.
- **Land oder Region**. Sie können Länder oder Regionen auswählen, sodass nur Benutzern an diesen Speicherorten bestimmte Inhalte angezeigt werden. Länderspezifische Informationen werden beispielsweise nur in diesen Ländern in den Suchergebnissen angezeigt.
- **Gruppeneinstellungen** machen Ergebnisse nur für Mitglieder ausgewählter Gruppen verfügbar. Wenn Sie beispielsweise Websites erstellen, die sich nur auf Mitarbeiter in der Personalabteilung beziehen, ordnen Sie diese Einstellung der entsprechenden Personalsicherheitsgruppe zu.
- **Gerät oder Betriebssystem**. Wählen Sie Gerätetypen oder Betriebssysteme aus, sodass nur Benutzer, die auf diesen Geräten suchen oder diese Systeme verwenden, dieses Lesezeichen sehen.
- **Gezielte Variationen**. Diese Einstellung variiert den Inhalt eines Lesezeichens je nach Gerät und Standort des Benutzers.

## <a name="test-your-content"></a>Testen Ihrer Inhalte
Überprüfen Sie nach dem Erstellen von [Lesezeichen](manage-bookmarks.md) und [F&A](manage-qas.md)die folgenden Ergebnisse:
- Das richtige Lesezeichen oder die richtige Q-&A wird angezeigt.
- Alle Inhalte, die mit Schlüsselwörtern gruppiert sind, werden wie geplant zusammen angezeigt.
- In den Suchantworten wird nichts Unerwartetes angezeigt.
- Das Lesezeichen oder die Q-&A enthält genügend Informationen.

Benutzer und SMEs, die an der Inhaltserstellung mitwirken, können beim Testen und Überprüfen von Suchergebnissen helfen.

## <a name="review-and-update-periodically"></a>Überprüfen und Aktualisieren in regelmäßigen Abständen
Autorisierende Informationen wie [Lesezeichen](manage-bookmarks.md) und [F&A](manage-qas.md) müssen aktuell bleiben. Führen Sie diese Schritte regelmäßig aus:
- Korrigieren oder entfernen Sie fehlerhafte und ungültige URLs.
- Entfernen Sie Lesezeichen oder Q&A, die nicht mehr relevant sind.
- Überprüfen Sie auf Änderungen des Tools, Websitenamens oder Teamnamens.
- Überlegen Sie, ob das Lesezeichen oder die Q-&A autoritativ genug ist oder eine klarere Beschreibung benötigt.

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>Erhalten Sie Einblicke zu Lesezeichen, Q&A und Speicherorten

Microsoft Search zeigt, wie viele [Lesezeichen](manage-bookmarks.md), [F&A](manage-qas.md)und [Speicherorte](manage-locations.md) veröffentlicht, geplant oder vorgeschlagen werden. Im [Insights-Dashboard](./usage-reports.md) werden Lesezeichen, F&A und Standortsummen nach Status angezeigt:

- **Veröffentlicht**: die Anzahl der veröffentlichten Ergebnissen, die für Benutzer zur Verfügung stehen
- **Geplant:** die Anzahl der geplanten Ergebnissen in der Veröffentlichungspipeline
- **Vorgeschlagen:** die Anzahl der Vorschläge von Benutzern

Vorgeschlagene [Lesezeichen,](manage-bookmarks.md) [F&A](manage-qas.md)und [Speicherorte](manage-locations.md) sind ein guter Indikator für Lücken in Ihren Inhalten. Sie helfen Ihnen zu verstehen, wonach Ihre Benutzer suchen, aber nicht finden. Diese Daten deuten möglicherweise darauf hin, dass Sie weitere Lesezeichen, F&A oder Speicherorte erstellen müssen. Oder Sie müssen Ihre vorhandenen Inhalte mithilfe besserer Schlüsselwörter, reservierter Schlüsselwörter und Suchzeichenfolgen aktualisieren, um Ihre Inhalte leichter auffindbar zu machen.

### <a name="review-top-search-queries"></a>Überprüfen der wichtigsten Suchabfragen

Um herauszufinden, welche Suchvorgänge die meisten Aufrufe in den letzten 90 Tagen generiert haben, überprüfen Sie Ihre wichtigsten Suchabfragen. *"Eindruck"* bedeutet, wie oft eine Seite in Suchergebnissen angezeigt wurde. Auf der Karte **"Häufigste Abfragen"** im [dashboard Insights](./usage-reports.md) werden die 25 häufigsten Benutzersuchen für jeden Ergebnistyp, die Gesamtanzahl der Suchvorgänge und die Klickrate (CTR) angezeigt. Mit diesem Bericht können Sie das Suchabfragevolumen identifizieren und Abfragen mit hoher und niedriger Suchaktivität ermitteln.

Niedrige Suchanzahl kann auf Unzufriedenheit des Benutzers hindeuten. Entweder suchen Benutzer nicht nach diesen Inhalten, oder sie verwenden unterschiedliche Schlüsselwörter, um sie zu finden. Die CTR zeigt an, wie oft Benutzer die höhergestuften Ergebnisse auswählen und wie nützlich Ihre Abfrageregeln und -ergebnisse für Benutzer sind. Ein niedriger CTR-Wert gibt an, dass Benutzer den Inhalt finden, aber nicht ihren Anforderungen entsprechen. Überprüfen Sie in solchen Fällen den Inhalt. Um Inhalte an Suchabfragen auszurichten, stellen Sie sicher, dass sie den Such- und Aktualisierungstiteln, Beschreibungen und Schlüsselwörtern der Benutzer entsprechen. 

### <a name="analyze-impressions-by-result-type"></a>Analysieren von Aufrufen nach Ergebnistyp

Einfach zu lesende Diagramme in der **Impression-Verteilerkarte** im [Insights-Dashboard](./usage-reports.md) zeigen Aufrufe über verschiedene Zeitrahmen an. Die Zeitachse zeigt die tägliche Anzahl von Aufrufen für einen Ergebnistyp. Mit diesen Diagrammen können Sie ermitteln, welcher Ergebnistyp am häufigsten oder selten verwendet wird. Die seltenen Verwendung eines bestimmten Ergebnistyps bedeutet nicht notwendigerweise, dass der Ergebnistyp nicht gut ist. Sie zeigt nur, wie Benutzer das Suchergebnis verwenden.

 Wenn ein bestimmter Ergebnistyp von Benutzern bevorzugt wird, können Sie weitere Suchergebnisse desselben Typs erstellen. Um sicherzustellen, dass Schlüsselwörter angemessen sind, überprüfen Sie die Schlüsselwörter von Ergebnistypen mit geringer Nutzung. Mit diesem Bericht können Sie auch Änderungen am Benutzerverhalten im Laufe der Zeit sehen.