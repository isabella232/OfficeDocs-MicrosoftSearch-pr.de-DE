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
ms.openlocfilehash: 605610264e2068deb6215c3157efc24cf0b0a2fd
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626828"
---
# <a name="make-content-easy-to-find"></a>Inhalte leicht auffindbar machen

Microsoft Search hilft Benutzern, relevante Inhalte zu finden. Es ist eine sichere Möglichkeit zum Durchsuchen von Intranet-und Webinhalten. Diese Art der Integration über das Internet und Organisationen ist nur von Microsoft verfügbar. Mit der Microsoft-Suche können Administratoren ihr Wissen über eine Organisation nutzen, um Benutzern die Suche nach relevanten Inhalten zu erleichtern. 

## <a name="components-that-find-content"></a>Komponenten, die Inhalte finden
In der Microsoft-Suche erstellen Administratoren [Lesezeichen](manage-bookmarks.md), [PowerApps](integrate-powerapps.md), [Q&A](manage-qas.md)und [Speicherorte](manage-locations.md) , die die Suche nach Inhalten erleichtern. Jede dieser Suchkomponenten enthält einen Titel, eine URL und eine Gruppe von Schlüsselwörtern, die sie auslösen.

## <a name="bookmarks"></a>Lesezeichen
Sie können [Bookmarks](manage-bookmarks.md) in wenigen Schritten erstellen. Jedes Lesezeichen enthält einen Titel, eine URL und eine Gruppe von Schlüsselwörtern, die es auslösen. Eine Textmarke kann mehrere Schlüsselwörter aufweisen, und mehrere Lesezeichen können dasselbe Stichwort verwenden. Aber reservierte Schlüsselwörter können nicht freigegeben werden. Beim Erstellen oder Ändern einer Textmarke wird der Suchindex aktualisiert, und die Textmarke steht den Benutzern sofort zur Verfügung.

Wenn Ihre Organisation die Ergebnisse in [SharePoint](http://sharepoint.com/) **höher gestuft** hat, können Sie diese Ergebnisse in Microsoft Search importieren. Mit höher gestuften Ergebnissen können Sie Schnellsuch Ergebnisse auffüllen, die Inhalte für Benutzer zur Verfügung stellen und die Microsoft-Suche effektiver gestalten, sobald Sie Sie eingerichtet haben. Wir empfehlen Ihnen, höhergestufte Ergebnisse aus SharePoint als Referenz zu verwenden, um zu verstehen, wie man relevante Suchergebnisse benennt und erstellt. 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>Hinzufügen oder Bearbeiten von Lesezeichen mithilfe von Browsererweiterungen
Suchadministratoren können Suchinhalte mühelos mithilfe von Browsererweiterungen erstellen. Um die Website als Lesezeichen hinzuzufügen, installieren Sie die Browser Erweiterung. Wechseln Sie dann zur Website, und fügen Sie Sie als Textmarke hinzu. Weitere Informationen finden Sie unter [Manage Bookmarks](manage-bookmarks.md).

Derzeit stehen Browsererweiterungen für [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) und [Google Chrome](https://www.google.com)zur Verfügung: 
- Um die Edge-Erweiterung herunterzuladen, wechseln Sie zum [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Um die Chrome-Erweiterung herunterzuladen, wechseln Sie zum [Chrome-Webstore](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="powerapps"></a>PowerApps

Durch das Hinzufügen vorhandener [PowerApps](integrate-powerapps.md) zu Ihren [Lesezeichen](manage-bookmarks.md)können Benutzer Aufgaben wie das Eingeben von Urlaubszeiten oder Berichtsausgaben erledigen. 

Mit [PowerApps](integrate-powerapps.md)können Sie Geschäfts-Apps erstellen, die in einem Browser oder auf einem Telefon oder Tablet ausgeführt werden. Es ist keine Programmiererfahrung erforderlich. PowerApps funktioniert in jedem Browser und auf jedem Gerät. Das Hinzufügen dauert weniger als eine Minute. Weitere Informationen zu PowerApps finden Sie in den folgenden Artikeln:
- [Gesteuertes Lernen](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [PowerApps-Dokumentation](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [PowerApps-Startseite](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Hinzufügen einer PowerApp zu einem Lesezeichen

1. Suchen Sie die [App-ID](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) für das PowerApp, das Sie hinzufügen möchten.
1. Wechseln Sie im Microsoft 365 [Admin Center](https://admin.microsoft.com)zu **Einstellungen** > **Microsoft Search**. 
1. Fügen Sie ein Lesezeichen hinzu oder suchen Sie ein vorhandenes Lesezeichen, dem Sie eine PowerApp hinzufügen möchten.
1. Wählen Sie in **Lesezeichen Einstellungen**die Option **Power App**aus. Wählen Sie dann **Add a Power App**aus.
1. Geben Sie die **App-ID**ein. Die Höhe und Breite werden automatisch angepasst. [Lesezeichen](manage-bookmarks.md) können sowohl Hochformat-als auch Querformat Orientierungen unterstützen, derzeit kann die Größe jedoch nicht geändert werden. Um den Test zu vereinfachen, zeigt die Lesezeichen Vorschau eine voll funktionsfähige PowerApp.
1. Wählen Sie **Veröffentlichen** oder **Als Entwurf speichern** aus.

## <a name="qa"></a>F&A

Das Erstellen eines [Q&a ähnelt dem](manage-qas.md) Erstellen von [Lesezeichen](manage-bookmarks.md). Mit Q&A können Sie Antworten auf Benutzer Fragen anstelle von nur einem Link zur Webseite bereitstellen. Sie können Antworten in Rich-Text mithilfe der verfügbaren Tools formatieren. Wenn ein Lesezeichen und ein Q&a dasselbe Stichwort freigeben, wird zuerst das Ergebnis der Textmarke angezeigt. Wie bei Lesezeichen wird das q&einen Index unmittelbar nach dem Hinzufügen oder Ändern eines q&a aktualisiert. 

### <a name="supported-html-tags"></a>Unterstützte HTML-Tags

Sie können HTML-Inhalte verwenden oder HTML-Tags zu ihrer Antwort oder Beschreibung hinzufügen. Wir unterstützen diese HTML-Tags:
 
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
> Sie können Q&A-Elemente nicht importieren, wenn Fehler in der Vorlagendatei vorliegen. Um Fehler zu vermeiden, stellen Sie sicher, dass Ihre Importdatei ordnungsgemäß formatiert ist und alle erforderlichen Informationen enthält. Weitere Informationen zum [verhindern von Importfehlern](#prevent-import-errors)finden Sie unter.

## <a name="locations"></a>Standorte

Mit [Standorten](manage-locations.md)können Ihre Benutzeradressen finden und die Gebäude Ihrer Organisation lokalisieren. Das Feature **Orte** bietet einen genauen Standort für Büros, Standorte und Gebäude sowie Richtungen und Navigation. Um optimale Ergebnisse zu erzielen, müssen Administratoren alle wichtigen Standorte Ihrer Organisationen zu Microsoft Search hinzufügen. Im Gegensatz zu [Lesezeichen](manage-bookmarks.md) und [Q&A](manage-qas.md)wird der Speicherort Index nicht sofort aktualisiert. Es kann mehrere Stunden dauern, bis neue oder geänderte Speicherorte in den Suchergebnissen angezeigt werden.

## <a name="get-started"></a>Erste Schritte
Wenn Sie herausfinden möchten, was Ihre Benutzer benötigen und diese Informationen leicht erkennen lassen, probieren Sie einige der folgenden Methoden aus:

- Ermitteln Sie die Websites und Seiten mit dem meisten Datenverkehr anhand von Intranetsuchprotokollen.
- Ermitteln Sie Apps, Websites und Tools, die täglich oder wöchentlich verwendet werden.
- Suchen Sie direkte Links für Mitarbeitervergütungen.
- Suchen Sie Richtlinien und Prozesse, die Benutzer kennen müssen.
- Entscheiden Sie, welche Benutzer sich für den Support wenden und wie Sie dies tun.
- Abrufen von Informationen, die regelmäßig, entweder saisonal oder basierend auf Geschäftszyklen, benötigt werden. Ein Beispiel sind Personen, die nach Tools suchen, um Auszeiten oder Vierteljährliche Finanz Aktualisierungen zu buchen.
- Sammeln Sie Richtlinien für regionale oder mobile Benutzer. Beispiele sind Vorteile, die je nach Standort variieren.
- Ermitteln interner Websites und Informationen für allgemeine Suchvorgänge im Internet. Beispiele sind Datenverkehr, Informationen zum öffentlichen Nahverkehr, lokales Wetter, von Unternehmenspartnern verfügbare Rabatte sowie Gesundheits-und Fitnessprogramme.
- Suchen Sie Informationen zu vom Unternehmen geförderten Veranstaltungen, Konferenzen oder Erholungsangeboten.
- Recherchieren Sie allgemeine Probleme bei IT, Personalwesen und Support sowie häufig gestellte Fragen (FAQs) und die Antworten darauf.

## <a name="involve-smes-and-users"></a>Einbeziehen von KMU und Benutzern
In einer Organisation suchen Benutzer nach einer Reihe einfacher bis komplexer Themen. Einfache Beispiele sind Office-Adressen und Mitarbeiter Vorteile. Komplexe Beispiele sind neue Arbeitsprozesse, technische Informationen und Vorgehensweisen. Um eine solche Vielzahl von Inhalten zu erstellen oder zu finden, benötigen Sie Fachwissen in verschiedenen Bereichen, Themen und Technologien. 

Die meisten Suchadministratoren verfügen nicht über spezifisches Wissen zu jedem Thema. Wenn Sie die Menge der verfügbaren Inhalte ohne Hilfe von externen Ressourcen skalieren möchten, suchen Sie nach Expertenwissen und Wissen anderer Personen in Ihrer Organisation.

### <a name="get-content-from-smes"></a>Abrufen von Inhalten von KMU
Nutzen Sie die Experten der Fachbereiche (SMEs) in Ihrer Organisation, einschließlich Experten aus HR, Support, Vertrieb, Technologie und anderen wichtigen Bereichen. KMU können Inhalte direkt mitwirken, wenn Sie Sie als Microsoft-Such-Editoren hinzufügen. 

### <a name="involve-your-users"></a>Einbeziehen Ihrer Benutzer
Bitten Sie Benutzer, Ressourcen als Lesezeichen vorzuschlagen. Fordern Sie die Benutzer außerdem auf, Fehler wie beschädigte oder ungültige Links zu melden.

## <a name="set-up-components"></a>Einrichten von Komponenten
Führen Sie die Schritte in den folgenden Abschnitten aus, um einzelne oder Massen [Lesezeichen](manage-bookmarks.md), [Q&A](manage-qas.md)und [Speicherorte](manage-locations.md)hinzuzufügen oder zu bearbeiten. 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>Hinzufügen oder Bearbeiten einer einzelnen Textmarke, Q&einer oder einer Standortkomponente
1. Wechseln Sie im Microsoft 365 [Admin Center](https://admin.microsoft.com)zu **Einstellungen** > **Microsoft Search**. Wählen Sie die benannte Registerkarte der Komponente aus. Die Registerkarte **Lesezeichen** ist standardmäßig aktiviert.
1. Zum Hinzufügen einer Komponente wählen Sie **Neu hinzufügen**aus. 
1. Um eine Komponente zu bearbeiten, wählen Sie die Textmarke in der entsprechenden Komponentenliste aus. 
1. Während Sie die Informationen hinzufügen oder bearbeiten, wird die Vorschau automatisch aktualisiert.

### <a name="bulk-add-or-edit-components"></a>Massen hinzufügen oder Bearbeiten von Komponenten
Mit den **Import** -und **Export** Funktionen können Suchadministratoren Massen erstellen oder Bearbeiten von [Lesezeichen](manage-bookmarks.md), [Q&A](manage-qas.md)und [Speicherorten](manage-locations.md). Dieses Feature ist hilfreich, wenn ein Administrator viele Komponenten hinzufügen oder bearbeiten möchte. 

Die Funktionen Import und Export bieten folgende Funktionen:
- **Massen hinzufügen**. Fügen Sie Details in die Vorlagendatei der Komponente ein, und importieren Sie Sie.
- **Massenbearbeitung**. Exportieren Sie Komponenten in eine CSV-Datei, bearbeiten Sie die Lesezeichen Details in der exportierten CSV, und importieren Sie dann die aktualisierte CSV.
- **Importieren Sie heraufgestufte Websites aus [SharePoint](http://sharepoint.com/)**. Dieses Feature gilt nur für [Lesezeichen](manage-bookmarks.md).
- **Sicherung**. Exportieren von Komponenten in eine CSV-Datei.

Führen Sie die folgenden Schritte aus, um Komponenten zu importieren oder zu exportieren:
1. Wählen Sie in der oberen rechten Ecke der benannten Registerkarte der Komponente **Import**aus. 
1. Wenn Sie alle vorhandenen Komponenten in einer CSV-Datei herunterladen möchten, wählen Sie **exportieren**aus.
1. Wählen Sie im rechten Bereich die Option zum Importieren mithilfe einer CSV-Datei oder von [SharePoint](http://sharepoint.com/)aus.
1. Wenn Sie eine Liste der erforderlichen Felder und Details erhalten möchten, laden Sie die Vorlagendatei der Komponente herunter. 
1. Hinzufügen oder Bearbeiten von Komponentendetails in der Vorlagendatei. Speichern Sie Sie dann auf Ihrem Computer. 
1. Wählen Sie im **Import** Bereich der Komponente die Option **Durchsuchen**aus. Wählen Sie dann die gewünschte CSV-Datei aus, und wählen Sie **importieren**aus.

### <a name="template-guidelines"></a>Vorlagen Richtlinien
Beachten Sie die folgenden Richtlinien und Einschränkungen bei der Arbeit mit Vorlagendateien:
- Bearbeiten Sie niemals Daten in diesen Feldern: *ID*, *zuletzt geändert*und *zuletzt geändert von*.
- Wenn Sie die *ID* einer vorhandenen Textmarke einschließen, wird Sie durch die Informationen in der Importdatei ersetzt.
- Wenn eine Textmarke mit dem gleichen Titel oder der gleichen URL in der vorhandenen Datei vorhanden ist, wird die Textmarke mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und die erforderlichen Felder sind je nach Lesezeichen Status unterschiedlich.
- Basierend auf dem Feld *Status* werden Lesezeichen als **Entwurf**, **vorgeschlagen**oder **geplant**gespeichert. Andernfalls werden Sie automatisch veröffentlicht.
- Wenn Sie mehrere Organisationen verwalten, können Sie Ihre Lesezeichen aus einer org exportieren und in eine andere importieren. Sie müssen jedoch die Daten in der Spalte *ID* vor dem Import entfernen.

> [!Note]
> Sie können keine Komponentenelemente importieren, wenn es Fehler in der Vorlagendatei gibt. Um Fehler zu vermeiden, stellen Sie sicher, dass Ihre Importdatei ordnungsgemäß formatiert ist und alle erforderlichen Informationen enthält.

### <a name="prevent-import-errors"></a>Vermeiden von Importfehlern

Sie erhalten eine Fehlermeldung, wenn alle erforderlichen Daten fehlen oder ungültig sind. Eine Protokolldatei generiert mit weiteren Informationen zu den zu korrigierenden Zeilen und Spalten. Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie erneut, die Datei zu importieren. Sie können keine Lesezeichen importieren oder speichern, bis alle Fehler behoben sind.

Um Fehler zu vermeiden, stellen Sie sicher, dass Ihre Importdatei ordnungsgemäß formatiert ist und diese Anforderungen erfüllt:
- Die Überschriftenzeile und alle Spalten in der Importvorlage sind enthalten.
- Die Reihenfolge der Spalten ist identisch mit der Importvorlage.
- Alle Spalten haben Werte, mit Ausnahme der drei, die leer sein können: *ID*, *zuletzt geändert*und *zuletzt geändert von*. 
- Die *Status* Spalte ist nicht leer.

### <a name="titles-and-descriptions"></a>Titel und Beschreibungen
Verbundene Titel und Beschreibungen helfen Benutzern zu ermitteln, ob Ergebnisse Ihre Suchabfrage beantworten. Gute Titel und Beschreibungen entsprechen dem Hauptzweck des Ergebnisses. Ein Beispiel ist der Titel **Childcare Benefits** with the description *erfahren Sie mehr über die Vorteile bei der kostenpflichtigen Kinderbetreuung*. Mit diesen verbundenen Daten können Benutzer, die nach **Kinderbetreuung** suchen, monetäre Unterstützungsleistungen finden und einen Link erhalten, um weitere Informationen zu erhalten.

### <a name="keywords"></a>Schlüsselwörter
Mit Stichwörtern können Benutzer in Ihrer Organisation relevante Inhalte durchsuchen und finden. Sie müssen Keyword-Begriffe ihren Verwandten Suchergebnissen zuordnen. Microsoft Search schlägt Stichwörter auf der Grundlage des Titels und der URL Ihrer Inhalte vor. Um weitere Stichwörter zu identifizieren, erhalten Sie Antworten auf diese Fragen:

1. **Welche Suchbegriffe können die von Ihnen identifizierten Informationen finden?** Beziehen Sie sich auf alle vorhandenen Terminologie in Ihrer Organisation, sowie auf verwandte Variationen, Akronyme, Themen und Themen.
1. **Welche Variationen oder Wörter verwenden die Benutzer, um über diese Informationen zu sprechen?** Bitten Sie Ihr Support Team, diese Schlüsselwörter bereitzustellen.

Wenn Sie beispielsweise ein Ergebnis erstellen, das mit einem Tool zum Übermitteln von Urlaubs Anforderungen verknüpft ist, sind die Suchbegriffe **Urlaubs** -und **Submit-Urlaubsanfrage** gute Optionen. Benutzer in Ihrer Organisation können auch nach Urlaubs bezogenen Informationen mit **Feiertag** oder **Freizeit**suchen. Um Benutzern das Auffinden relevanter Inhalte zu erleichtern, fügen Sie diese Stichwörter und andere Informationen wie **Urlaubsanfrage** und **Anforderungszeit**ein.

### <a name="reserved-keywords"></a>Reservierte Schlüsselwörter
 Ein reserviertes Schlüsselwort ist ein eindeutiger Begriff oder Ausdruck, der ein Ergebnis auslöst. Im Gegensatz zu anderen Schlüsselwörtern sind reservierte Schlüsselwörter nur einem Ergebnis zugeordnet. Verwenden Sie reservierte Schlüsselwörter nur sparsam, damit Microsoft Search auf der Grundlage ihrer Nutzung lernen kann.

Ein Beispiel ist eine Textmarke für eine Website zum Übermitteln Ihrer Stunden. Wenn die **Protokollzeit** ein reserviertes Schlüsselwort ist, sehen Benutzer in Ihrer Organisation, die nach **Protokollzeit** suchen, diese Website als die einzige Textmarke im Microsoft-Suchfeld. 

### <a name="group-related-content-with-keywords"></a>Gruppieren von verwandten Inhalten mit Stichwörtern
Wenn Sie möchten, dass Benutzer zusammengehörige Inhalte finden, wenn Sie nach einem bestimmten Begriff suchen, weisen Sie dasselbe Stichwort allen verwandten Inhalten zu. Ein Beispiel ist eine Suche nach Prozessen und Tools rund um Lebensstatus Änderungen. Wenn Sie Antworten zusammen mit aktualisierten Vorteilen, Steuerinformationen sowie Namen-und Alias Änderungen gruppieren möchten, schließen Sie ein Stichwort wie **Marriage**ein.

### <a name="search-settings"></a>Sucheinstellungen
Mit den Sucheinstellungen können Sie Ihre Inhalte anpassen und auf bestimmte Benutzergruppen ausrichten. Diese Microsoft-Sucheinstellungen steuern, wann ein Suchergebnis angezeigt wird und wer es sehen kann:

- **Datum**. Um zu steuern, wann Inhalt verfügbar oder nicht verfügbar ist, legen Sie ein Startdatum und ein Enddatum fest. Beispielsweise wird das zeitkritische Material in den Suchergebnissen angezeigt, wenn es relevant ist.
- **Land oder Region**. Sie können Länder oder Regionen auswählen, sodass nur Benutzer an diesen Orten bestimmte Inhalte sehen. Beispielsweise werden länderspezifische Informationen in den Suchergebnissen nur in diesen Ländern angezeigt.
- **Gruppen** Einstellungen stellen Ergebnisse nur für Mitglieder ausgewählter Gruppen zur Verfügung. Wenn Sie beispielsweise Websites erstellen, die sich nur auf Mitarbeiter in der Personalabteilung beziehen, ordnen Sie diese Einstellung der entsprechenden Personal Sicherheitsgruppe zu.
- **Gerät oder Betriebssystem**. Wählen Sie Gerätetypen oder Betriebssysteme aus, sodass nur Benutzer, die auf diesen Geräten suchen oder diese Systeme verwenden, diese Textmarke sehen.
- **Gezielte Variationen**. Diese Einstellung variiert den Inhalt einer Textmarke basierend auf dem Gerät und Speicherort eines Benutzers.

## <a name="test-your-content"></a>Testen der Inhalte
Nachdem Sie [Lesezeichen](manage-bookmarks.md) und [Q&A](manage-qas.md)erstellt haben, überprüfen Sie die folgenden Ergebnisse:
- Die richtige Textmarke oder Q&A wird angezeigt.
- Alle zusammen mit Stichwörtern gruppierten Inhalte werden wie geplant zusammen angezeigt.
- In den Suchantworten wird nichts Unerwartetes angezeigt.
- Die Textmarke oder Q&A verfügt über genügend Informationen.

Benutzer und KMU, die zur Erstellung von Inhalten beitragen, können Suchergebnisse unterstützen und prüfen.

## <a name="review-and-update-periodically"></a>Überprüfen und Aktualisieren in regelmäßigen Abständen
Autorisierende Informationen wie [Lesezeichen](manage-bookmarks.md) und [Q&](manage-qas.md) müssen frisch bleiben. Führen Sie die folgenden Schritte regelmäßig aus:
- Korrigieren oder entfernen Sie fehlerhafte und ungültige URLs.
- Entfernen Sie Bookmarks oder Q&A, die nicht mehr relevant sind.
- Überprüfen Sie auf Änderungen des Tools, Websitenamens oder Teamnamens.
- Prüfen Sie, ob die Textmarke oder Q&a autorisierend genug ist oder eine deutlichere Beschreibung benötigt.

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>Erhalten Sie Einblicke in Bookmarks, Q&A und Standorte

Die Microsoft-Suche zeigt Ihnen, wie viele [Lesezeichen](manage-bookmarks.md), [Q&A](manage-qas.md)und [Orte](manage-locations.md) veröffentlicht, geplant oder vorgeschlagen werden. Das [Dashboard "Insights](get-insights.md) " zeigt das Lesezeichen, Q&A und die Gesamtposition der Standorte nach Status:

- **Veröffentlicht**: die Anzahl der veröffentlichten Ergebnissen, die für Benutzer zur Verfügung stehen
- **Geplant:** die Anzahl der geplanten Ergebnissen in der Veröffentlichungspipeline
- **Vorgeschlagen:** die Anzahl der Vorschläge von Benutzern

Vorgeschlagene [Lesezeichen](manage-bookmarks.md), [Q&a](manage-qas.md)und [Speicherorte](manage-locations.md) sind ein guter Indikator für Lücken in ihren Inhalten. Sie helfen Ihnen zu verstehen, was Ihre Benutzer suchen, finden aber nicht. Diese Daten deuten möglicherweise darauf hin, dass Sie weitere Lesezeichen, Q&A oder Speicherorte erstellen müssen. Oder Sie müssen Ihre vorhandenen Inhalte möglicherweise mithilfe von besseren Stichwörtern, reservierten Schlüsselwörtern und Suchzeichenfolgen aktualisieren, damit Ihre Inhalte besser auffindbar sind.

### <a name="review-top-search-queries"></a>Überprüfen der wichtigsten Suchabfragen

Um herauszufinden, welche Suchvorgänge die meisten Impressionen in den letzten 90 Tagen generiert haben, überprüfen Sie Ihre häufigsten Suchabfragen. *Impression* bedeutet, wie oft eine Seite in den Suchergebnissen angezeigt wurde. Die **oberste Abfrage** Karte im [Insights-Dashboard](get-insights.md) zeigt die Top 25-Benutzersuche für jeden Ergebnistyp, die Gesamtzahl der Suchvorgänge und die Klickrate (Click-through Rate, CTR). Mit diesem Bericht können Sie Suchabfrage Volumen identifizieren und Abfragen mit hoher und niedriger Suchaktivität ermitteln.

Niedrige Such Anzahl deutet möglicherweise auf Benutzer Unzufriedenheit hin. Beide Benutzer suchen nicht nach diesen Inhalten, oder Sie verwenden unterschiedliche Stichwörter, um Sie zu finden. Die CTR zeigt an, wie oft Benutzer die höhergestuften Ergebnisse auswählen und wie nützlich Ihre Abfrageregeln und -ergebnisse für Benutzer sind. Eine niedrige Klickrate gibt an, dass Benutzer den Inhalt finden, er erfüllt jedoch nicht deren Anforderungen. Überprüfen Sie in diesen Fällen den Inhalt. Um Inhalte an Suchabfragen auszurichten, stellen Sie sicher, dass Sie den Such-und Update Titeln, Beschreibungen und Stichwörtern von Benutzern entspricht. 

### <a name="analyze-impressions-by-result-type"></a>Analysieren von Aufrufen nach Ergebnistyp

Einfach zu lesende Grafiken auf der **Impression-Verteiler** Karte im [Insights-Dashboard](get-insights.md) zeigen Impressionen in verschiedenen Zeitfenstern an. Die Zeitachse zeigt die tägliche Anzahl von Aufrufen für einen Ergebnistyp. Mit diesen Diagrammen können Sie bestimmen, welcher Ergebnistyp am häufigsten oder selten verwendet wird. Die seltene Verwendung eines bestimmten Ergebnistyps bedeutet nicht zwangsläufig, dass der Ergebnistyp nicht gut ist. Sie zeigt nur, wie Benutzer das Suchergebnis verwenden.

 Wenn ein bestimmter Ergebnistyp von Benutzern bevorzugt wird, können Sie weitere Suchergebnisse desselben Typs erstellen. Um sicherzustellen, dass Stichwörter geeignet sind, überprüfen Sie die Stichwörter der Ergebnistypen mit geringer Auslastung. Mit diesem Bericht können Sie auch Änderungen im Benutzerverhalten im Laufe der Zeit anzeigen.
