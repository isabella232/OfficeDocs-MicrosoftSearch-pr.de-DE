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
ms.openlocfilehash: 0617108d0bdcefe417290a1a3ccf37ad50eb2415
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031593"
---
# <a name="make-content-easy-to-find"></a>Inhalte leicht auffindbar machen

Microsoft Search hilft Benutzern, relevante Inhalte zu finden. Es ist eine sichere Möglichkeit, sowohl Intranet- als auch Webinhalte zu durchsuchen. Diese Art der Integration über das Web und Organisationen ist nur von Microsoft verfügbar. Mit Microsoft Search können Administratoren ihr Wissen über eine Organisation nutzen, um benutzern die Suche nach relevanten Inhalten zu ermöglichen. 

## <a name="components-that-find-content"></a>Komponenten, die Inhalte finden
In Microsoft Search erstellen Administratoren Lesezeichen, [PowerApps,](integrate-powerapps.md) [Q&A](manage-qas.md)und [Speicherorte,](manage-locations.md) die die Suche nach Inhalten vereinfachen. [](manage-bookmarks.md) Jede dieser Suchkomponenten enthält einen Titel, eine URL und eine Gruppe von Schlüsselwörtern, die sie auslösen.

## <a name="bookmarks"></a>Lesezeichen
Sie können Lesezeichen in [nur](manage-bookmarks.md) wenigen Schritten erstellen. Jedes Lesezeichen enthält einen Titel, eine URL und eine Gruppe von Schlüsselwörtern, die es auslösen. Ein Lesezeichen kann mehrere Schlüsselwörter haben, und mehrere Lesezeichen können dasselbe Schlüsselwort gemeinsam verwenden. Reservierte Schlüsselwörter können jedoch nicht freigegeben werden. Wenn Sie ein Lesezeichen erstellen oder ändern, wird der Suchindex aktualisiert, und die Textmarke steht benutzern sofort zur Verfügung.

Wenn Ihre Organisation **die** in [SharePoint](http://sharepoint.com/)eingerichteten Ergebnisse heraufgestuft hat, können Sie diese Ergebnisse in Microsoft Search importieren. Mit heraufgestuften Ergebnissen können Sie Suchergebnisse schnell auffüllen, die Inhalte benutzern zur Verfügung stellen und Microsoft Search effektiver machen, sobald Sie sie einrichten. Wir empfehlen Ihnen, höhergestufte Ergebnisse aus SharePoint als Referenz zu verwenden, um zu verstehen, wie man relevante Suchergebnisse benennt und erstellt. 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>Hinzufügen oder Bearbeiten von Lesezeichen mithilfe von Browsererweiterungen
Suchadministratoren können Suchinhalte mühelos mithilfe von Browsererweiterungen erstellen. Um die Website als Lesezeichen hinzuzufügen, installieren Sie die Browsererweiterung. Wechseln Sie dann zur Website, und fügen Sie sie als Lesezeichen hinzu. Weitere Informationen finden Sie unter [Manage bookmarks](manage-bookmarks.md).

Derzeit sind Browsererweiterungen für [Microsoft Edge und](https://www.microsoft.com/windows/microsoft-edge) Google Chrome [verfügbar:](https://www.google.com) 
- Um die Edgeerweiterung herunterzuladen, wechseln Sie zum [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Um die Chrome-Erweiterung herunterzuladen, wechseln Sie zum [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="powerapps"></a>PowerApps

Durch das Hinzufügen [vorhandener PowerApps](integrate-powerapps.md) zu Ihren [Lesezeichen](manage-bookmarks.md)können Benutzer Aufgaben wie die Eingabe von Urlaubszeit oder Berichtskosten ausführen. 

Mit [PowerApps](integrate-powerapps.md)können Sie Geschäfts-Apps erstellen, die in einem Browser oder auf einem Smartphone oder Tablet ausgeführt werden. Es ist keine Programmiererfahrung erforderlich. PowerApps funktionieren in jedem Browser und auf jedem Gerät. Das Hinzufügen dauert weniger als eine Minute. Weitere Informationen zu PowerApps finden Sie in den folgenden Artikeln:
- [Geführtes Lernen](/learn/browse/?products=powerapps)
- [PowerApps-Dokumentation](/powerapps/maker/canvas-apps/get-sessionid)
- [PowerApps home](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Hinzufügen einer PowerApp zu einem Lesezeichen

1. Suchen Sie [die App-ID](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) für die PowerApp, die Sie hinzufügen möchten.
1. Wechseln Sie im Microsoft 365 [Admin Center](https://admin.microsoft.com)zu **Einstellungen**  >  **Microsoft Search**. 
1. Fügen Sie ein Lesezeichen hinzu oder suchen Sie ein vorhandenes Lesezeichen, dem Sie eine PowerApp hinzufügen möchten.
1. Wählen **Sie unter Lesezeicheneinstellungen** Power **App aus.** Wählen Sie dann **Power App hinzufügen aus.**
1. Geben Sie die **App-ID ein.** Höhe und Breite werden automatisch angepasst. [Lesezeichen können](manage-bookmarks.md) hoch- und querformatige Ausrichtungen unterstützen, die Größe kann derzeit jedoch nicht geändert werden. Um das Testen zu einfach zu machen, zeigt die Lesezeichenvorschau eine voll funktionsfähige PowerApp an.
1. Wählen Sie **Veröffentlichen** oder **Als Entwurf speichern** aus.

## <a name="qa"></a>F&A

Das Erstellen einer [Frage&A](manage-qas.md) ist wie das Erstellen von [Lesezeichen](manage-bookmarks.md). Mit Q&A können Sie Antworten auf Benutzerfragen bereitstellen, anstatt nur einen Link zur Webseite zu erstellen. Sie können Antworten in Rich Text formatieren, indem Sie verfügbare Tools verwenden. Wenn eine Textmarke und ein Q-&A dasselbe Schlüsselwort freigeben, wird zuerst das Lesezeichenergebnis gezeigt. Wie Lesezeichen wird der&A-Index unmittelbar nach dem Hinzufügen oder Ändern eines Q-&aktualisiert. 

### <a name="supported-html-tags"></a>Unterstützte HTML-Tags

Sie können HTML-Inhalte verwenden oder IHRER Antwort oder Beschreibung HTML-Tags hinzufügen. Wir unterstützen diese HTML-Tags:
 
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
> Sie können keine Q-&A-Elemente importieren, wenn Fehler in der Vorlagendatei enthalten sind. Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und alle erforderlichen Informationen enthält. Weitere Informationen zum Verhindern von [Importfehlern finden](#prevent-import-errors)Sie unter .

## <a name="locations"></a>Standorte

Mit [Locations](manage-locations.md)können Ihre Benutzer Adressen finden und die Gebäude Ihrer Organisation suchen. Die **Location-Funktion** bietet einen genauen Standort für Büros, Campus und Gebäude sowie Wegbeschreibungen und Navigation. Um optimale Ergebnisse zu erzielen, müssen Administratoren microsoft Search alle wichtigen Standorte ihrer Organisationen hinzufügen. Im [Gegensatz zu](manage-bookmarks.md) Lesezeichen und&A [wird](manage-qas.md)der Speicherortindex nicht sofort aktualisiert. Es kann mehrere Stunden dauern, bis neue oder geänderte Speicherorte in Suchergebnissen angezeigt werden.

## <a name="get-started"></a>Erste Schritte
Versuchen Sie einige der folgenden Methoden, um herauszufinden, was Ihre Benutzer benötigen und diese Informationen leicht zu erkennen:

- Ermitteln Sie die Websites und Seiten mit dem meisten Datenverkehr anhand von Intranetsuchprotokollen.
- Ermitteln Sie Apps, Websites und Tools, die täglich oder wöchentlich verwendet werden.
- Suchen Sie direkte Links für Mitarbeitervergütungen.
- Suchen Sie Richtlinien und Prozesse, die Benutzer kennen müssen.
- Entscheiden Sie, an wen Sich Benutzer wenden, um Support zu erhalten, und wie sie dies tun.
- Erhalten Sie Informationen, die regelmäßig benötigt werden, entweder auf Basis von Jahreszeiten oder basierend auf Geschäftszyklen. Ein Beispiel sind Personen, die nach Tools zum Buchen von Zeit- oder Quartals-Finanzupdates suchen.
- Sammeln von Richtlinien für regionale oder mobile Benutzer. Beispiele hierfür sind Vorteile, die je nach Standort variieren.
- Ermitteln Sie interne Websites und Informationen für häufige Websuchen. Beispiele hierfür sind Datenverkehr, Informationen zum öffentlichen Verkehr, lokales Wetter, Von Unternehmenspartnern verfügbare Rabatte sowie Gesundheits- und Fitnessprogramme.
- Suchen Sie Informationen zu vom Unternehmen geförderten Veranstaltungen, Konferenzen oder Erholungsangeboten.
- Recherchieren Sie allgemeine Probleme bei IT, Personalwesen und Support sowie häufig gestellte Fragen (FAQs) und die Antworten darauf.

## <a name="involve-smes-and-users"></a>Beteiligung von KMU und Benutzern
In einer Organisation suchen Benutzer nach einer Reihe einfacher bis komplexer Themen. Einfache Beispiele sind Office-Adressen und Mitarbeitervorteile. Komplexe Beispiele sind neue Arbeitsprozesse, technische Informationen und How-to-Do-Inhalte. Zum Erstellen oder Suchen einer solchen Vielzahl von Inhalten benötigen Sie Fachwissen in verschiedenen Feldern, Fächern und Technologien. 

Die meisten Suchadministratoren verfügen nicht über spezifische Kenntnisse zu jedem Thema. Wenn Sie die Menge der verfügbaren Inhalte ohne Hilfe von außerhalb der Ressourcen skalieren möchten, suchen Sie nach Fachwissen und Wissen von anderen Personen in Ihrer Organisation.

### <a name="get-content-from-smes"></a>Erhalten von Inhalten von KMUs
Nutzen Sie die Fachexperten (SMEs) in Ihrer Organisation, einschließlich Experten aus Personalwesen, Support, Vertrieb, Technologie und anderen wichtigen Bereichen. Kleine und mittlere Unternehmen können Inhalte direkt hinzufügen, wenn Sie sie als Microsoft Search-Editoren hinzufügen. 

### <a name="involve-your-users"></a>Einbeziehen Ihrer Benutzer
Bitten Sie Benutzer, Ressourcen als Lesezeichen vorzuschlagen. Bitten Sie benutzer außerdem, Fehler wie beschädigte oder ungültige Links zu melden.

## <a name="set-up-components"></a>Einrichten von Komponenten
Gehen Sie in den folgenden Abschnitten [vor,](manage-bookmarks.md)um einzelne oder Massenmarken , [&A](manage-qas.md)und [Speicherorte](manage-locations.md)hinzuzufügen oder zu bearbeiten. 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>Hinzufügen oder Bearbeiten einer einzelnen Lesezeichen-,&A- oder Standortkomponente
1. Wechseln Sie im Microsoft 365 [Admin Center](https://admin.microsoft.com)zu **Einstellungen**  >  **Microsoft Search**. Wählen Sie die benannte Registerkarte der Komponente aus. Die **Registerkarte Lesezeichen** ist standardmäßig ausgewählt.
1. Wenn Sie eine Komponente hinzufügen möchten, wählen **Sie Neue hinzufügen aus.** 
1. Wählen Sie zum Bearbeiten einer Komponente die Textmarke in der liste der relevanten Komponenten aus. 
1. Während Sie die Informationen hinzufügen oder bearbeiten, wird die Vorschau automatisch aktualisiert.

### <a name="bulk-add-or-edit-components"></a>Massen hinzufügen oder Bearbeiten von Komponenten
Mit den **Import-** und **Exportfeatures** können Suchadministratoren [Lesezeichen,](manage-bookmarks.md) [Fragen](manage-qas.md)und&Und Speicherorte massen erstellen oder [bearbeiten.](manage-locations.md) Dieses Feature ist hilfreich, wenn ein Administrator viele Komponenten hinzufügen oder bearbeiten möchte. 

Die Import- und Exportfeatures bieten die folgenden Funktionen:
- **Massen hinzufügen**. Fügen Sie Details in der Vorlagendatei der Komponente hinzu, und importieren Sie sie dann.
- **Massenbearbeitung**. Exportieren Sie Komponenten in eine CSV-Datei, bearbeiten Sie dann die Textmarkendetails in der exportierten CSV, und importieren Sie dann die aktualisierte CSV.
- **Importieren von heraufgestuften Websites aus [SharePoint](http://sharepoint.com/)**. Dieses Feature gilt nur für [Lesezeichen](manage-bookmarks.md).
- **Sicherung**. Exportieren von Komponenten in eine CSV-Datei.

Gehen Sie wie die folgenden Schritte vor, um Komponenten zu importieren oder zu exportieren:
1. Wählen Sie in der oberen rechten Ecke der benannten Registerkarte der Komponente **importieren aus.** 
1. Wählen Sie Exportieren aus, um alle vorhandenen Komponenten in einer **CSV-Datei herunterzuladen.**
1. Wählen Sie im rechten Bereich die Option zum Importieren mithilfe einer CSV-Datei oder aus [SharePoint aus.](http://sharepoint.com/)
1. Laden Sie die Vorlagendatei der Komponente herunter, um eine Liste der erforderlichen Felder und Details zu erhalten. 
1. Hinzufügen oder Bearbeiten von Komponentendetails in der Vorlagendatei. Speichern Sie es dann auf Ihrem Computer. 
1. Wählen Sie im Importbereich der **Komponente** die Option **Durchsuchen aus.** Wählen Sie dann die csv-Datei aus, die Sie möchten, und wählen Sie **Importieren aus.**

### <a name="template-guidelines"></a>Vorlagenrichtlinien
Beachten Sie diese Richtlinien und Einschränkungen, wenn Sie mit Vorlagendateien arbeiten:
- Bearbeiten Sie niemals Daten in diesen Feldern: *ID*, *Last Modified* und Last *Modified By*.
- Wenn Sie die *ID* einer vorhandenen Textmarke hinzufügen, wird sie durch die Informationen in der Importdatei ersetzt.
- Wenn in der vorhandenen Datei eine Textmarke mit demselben Titel oder derselben URL vorhanden ist, wird die Textmarke mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und die erforderlichen Felder variieren je nach Textmarkenstatus.
- Basierend auf dem *Feld Status* werden Lesezeichen als **Entwurf,** vorgeschlagen **oder** **geplant gespeichert.** Andernfalls werden sie automatisch veröffentlicht.
- Wenn Sie mehrere Organisationen verwalten, können Sie Ihre Lesezeichen aus einer Organisation exportieren und in eine andere importieren. Sie müssen jedoch die Daten in der Spalte *ID* vor dem Import entfernen.

> [!Note]
> Komponentenelemente können nicht importiert werden, wenn fehler in der Vorlagendatei enthalten sind. Um Fehler zu vermeiden, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und alle erforderlichen Informationen enthält.

### <a name="prevent-import-errors"></a>Vermeiden von Importfehlern

Sie erhalten eine Fehlermeldung, wenn erforderliche Daten fehlen oder ungültig sind. Eine Protokolldatei generiert mit weiteren Informationen zu den zu korrigierende Zeilen und Spalten. Nehmen Sie die erforderlichen Änderungen vor, und versuchen Sie, die Datei erneut zu importieren. Sie können lesezeichen erst importieren oder speichern, wenn alle Fehler behoben sind.

Stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist und die folgenden Anforderungen erfüllt, um Fehler zu vermeiden:
- Die Kopfzeile und alle Spalten in der Importvorlage sind enthalten.
- Die Spaltenreihenfolge ist identisch mit der Importvorlage.
- Alle Spalten haben Werte, mit Ausnahme der drei Werte, die leer sein *können:* *ID*, *Last Modified* und Last Modified By . 
- Die *Spalte Status* ist nicht leer.

### <a name="titles-and-descriptions"></a>Titel und Beschreibungen
Verbundene Titel und Beschreibungen helfen Benutzern zu bestimmen, ob Ergebnisse ihre Suchabfrage beantworten. Gute Titel und Beschreibungen spiegeln den Kernzweck des Ergebnisses wider. Ein Beispiel ist der Titel **Childcare benefits** with the description *Learn about benefits to help pay childcare costs*. Mit diesen verbundenen Daten können  Benutzer, die nach einer Kinderbetreuung suchen, Geldunterstützungsleistungen finden und einen Link erhalten, um mehr zu erfahren.

### <a name="keywords"></a>Schlüsselwörter
Mit Schlüsselwörtern können Benutzer in Ihrer Organisation relevante Inhalte suchen und suchen. Sie müssen Stichwortbegriffe ihren zugehörigen Suchergebnissen zuordnen. Microsoft Search schlägt Schlüsselwörter basierend auf dem Titel und der URL Ihrer Inhalte vor. Um weitere Schlüsselwörter zu identifizieren, erhalten Sie Antworten auf diese Fragen:

1. **Welche Suchbegriffe können die von Ihnen identifizierten Informationen finden?** Verweisen Sie auf vorhandene Terminologie in Ihrer Organisation sowie auf verwandte Variationen, Akronyme, Themen und Themen.
1. **Welche Variationen oder Wörter verwenden Die Personen, um über diese Informationen zu sprechen?** Bitten Sie Ihr Supportteam, diese Schlüsselwörter zur Verfügung zu stellen.

Wenn Sie beispielsweise ein Ergebnis erstellen, das Links zu einem  Tool  zum Übermitteln von Urlaubsanfragen enthält, sind die Schlüsselwörter Urlaub und Urlaubsanfrage übermitteln gute Optionen. Benutzer in Ihrer Organisation können auch nach Urlaubsinformationen mit Urlaub **oder** **Auszeit suchen.** Um benutzern die Suche nach relevanten Inhalten zu erleichtern, fügen Sie diese Schlüsselwörter und andere Schlüsselwörter hinzu, z. B. Senden von **Feiertagsanfrage** und **Anforderungszeit.**

### <a name="reserved-keywords"></a>Reservierte Schlüsselwörter
 Ein reserviertes Schlüsselwort ist ein eindeutiger Begriff oder Ausdruck, der ein Ergebnis auslöst. Im Gegensatz zu anderen Schlüsselwörtern sind reservierte Schlüsselwörter nur einem Ergebnis zugeordnet. Verwenden Sie reservierte Schlüsselwörter nur sparsam, damit Microsoft Search auf der Grundlage ihrer Nutzung lernen kann.

Ein Beispiel ist eine Textmarke für eine Website zum Übermitteln Ihrer Stunden. Wenn **die Protokollzeit** ein reserviertes Schlüsselwort ist, sehen Benutzer in Ihrer Organisation, die nach Protokollzeit suchen, diese Website als einziges Lesezeichen im Microsoft Search-Feld.  

### <a name="group-related-content-with-keywords"></a>Gruppieren von inhalten mit Schlüsselwörtern
Wenn Benutzer bei der Suche nach einem bestimmten Ausdruck Sätze verwandter Inhalte finden sollen, weisen Sie allen verwandten Inhalten dasselbe Schlüsselwort zu. Ein Beispiel ist eine Suche nach Prozessen und Tools rund um Änderungen des Lebenszyklusstatus. Wenn Sie Antworten zum Aktualisieren von Vorteilen, Steuerinformationen und Namens- und Aliasänderungen gruppieren möchten, geben Sie ein Schlüsselwort wie **Eheschließung an.**

### <a name="search-settings"></a>Sucheinstellungen
Mit Sucheinstellungen können Sie Ihre Inhalte und zielgruppenspezifischen Benutzergruppen anpassen. Diese Microsoft Search-Einstellungen steuern, wann ein Suchergebnis angezeigt wird und wer es sehen kann:

- **Datum**. Um zu steuern, wann Inhalte verfügbar oder nicht verfügbar sind, legen Sie ein Startdatum und ein Enddatum ein. Beispielsweise wird zeitsensibles Material in Suchergebnissen angezeigt, wenn es relevant ist.
- **Land oder Region**. Sie können Länder oder Regionen auswählen, sodass nur Benutzern an diesen Speicherorten bestimmte Inhalte angezeigt werden. Beispielsweise werden länderspezifische Informationen nur in den Suchergebnissen in diesen Ländern angezeigt.
- **Gruppeneinstellungen** stellen Ergebnisse nur für Mitglieder ausgewählter Gruppen zur Verfügung. Wenn Sie beispielsweise Websites erstellen, die sich nur auf Mitarbeiter in der Personalabteilung beziehen, ordnen Sie diese Einstellung der entsprechenden Personalsicherheitsgruppe zu.
- **Gerät oder Betriebssystem**. Wählen Sie Gerätetypen oder Betriebssysteme aus, sodass nur Benutzer, die auf diesen Geräten suchen oder diese Systeme verwenden, diese Textmarke sehen.
- **Gezielte Variationen**. Diese Einstellung variiert den Inhalt einer Textmarke basierend auf dem Gerät und dem Standort eines Benutzers.

## <a name="test-your-content"></a>Testen Von Inhalten
Nachdem Sie Lesezeichen [und](manage-bookmarks.md) [Fragen&A](manage-qas.md)erstellt haben, überprüfen Sie die folgenden Ergebnisse:
- Die richtige Textmarke oder frage&A wird angezeigt.
- Alle Inhalte, die zusammen mit Schlüsselwörtern gruppieren, werden wie geplant angezeigt.
- In den Suchantworten wird nichts Unerwartetes angezeigt.
- Das Lesezeichen oder die Frage&A enthält genügend Informationen.

Benutzer und KMUs, die zur Erstellung von Inhalten beitragen, können beim Testen und Überprüfen von Suchergebnissen helfen.

## <a name="review-and-update-periodically"></a>Überprüfen und Aktualisieren in regelmäßigen Abständen
Autorisierende Informationen wie [Bookmarks](manage-bookmarks.md) und [Q&A](manage-qas.md) müssen auf dem Neusten bleiben. Gehen Sie regelmäßig wie die folgenden Schritte vor:
- Beheben oder entfernen Sie beschädigte und ungültige URLs.
- Entfernen Sie Lesezeichen oder&A, die nicht mehr relevant sind.
- Überprüfen Sie auf Änderungen des Tools, Websitenamens oder Teamnamens.
- Überlegen Sie, ob das Lesezeichen oder&A autorisierend genug ist oder eine klarere Beschreibung benötigt.

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>Erhalten von Einblicken zu Lesezeichen, Fragen&A und Speicherorten

Microsoft Search zeigt an, wie viele [Lesezeichen,](manage-bookmarks.md) [Fragen&A](manage-qas.md)und [Speicherorte](manage-locations.md) veröffentlicht, geplant oder vorgeschlagen werden. Das [Insights-Dashboard](./usage-reports.md) zeigt Lesezeichen-,&A- und Standortsummen nach Status an:

- **Veröffentlicht**: die Anzahl der veröffentlichten Ergebnissen, die für Benutzer zur Verfügung stehen
- **Geplant:** die Anzahl der geplanten Ergebnissen in der Veröffentlichungspipeline
- **Vorgeschlagen:** die Anzahl der Vorschläge von Benutzern

Vorgeschlagene [Lesezeichen,](manage-bookmarks.md) [Fragen&A](manage-qas.md)und [Speicherorte](manage-locations.md) sind ein guter Indikator für Lücken in Ihren Inhalten. Sie helfen Ihnen zu verstehen, wofür Ihre Benutzer suchen, aber nicht finden. Diese Daten deuten möglicherweise darauf hin, dass Sie weitere Lesezeichen, Fragen&A oder Speicherorte erstellen müssen. Oder Sie müssen Ihre vorhandenen Inhalte aktualisieren, indem Sie bessere Schlüsselwörter, reservierte Schlüsselwörter und Suchzeichenfolgen verwenden, um Ihre Inhalte besser zu erkennen.

### <a name="review-top-search-queries"></a>Überprüfen der wichtigsten Suchabfragen

Um herauszufinden, welche Suchabfragen die meisten Impressionen in den letzten 90 Tagen generiert haben, überprüfen Sie Ihre wichtigsten Suchabfragen. *Impression* bedeutet, wie oft eine Seite in Suchergebnissen angezeigt wurde. Die **Karte "Top Queries"** im [Insights-Dashboard](./usage-reports.md) zeigt die 25 besten Benutzersuchen für jeden Ergebnistyp, die Gesamtzahl der Suchanfragen und die Klickrate (Click-Through Rate, CTR) an. Mit diesem Bericht können Sie das Suchabfragevolumen identifizieren und Abfragen mit hoher und niedriger Suchaktivität bestimmen.

Eine niedrige Suchanzahl kann auf unzufriedene Benutzer hinweisen. Entweder benutzer suchen nicht nach diesem Inhalt, oder sie verwenden unterschiedliche Schlüsselwörter, um ihn zu finden. Die CTR zeigt an, wie oft Benutzer die höhergestuften Ergebnisse auswählen und wie nützlich Ihre Abfrageregeln und -ergebnisse für Benutzer sind. Eine niedrige CTR gibt an, dass Benutzer den Inhalt finden, aber nicht ihren Anforderungen entsprechen. Überprüfen Sie in solchen Fällen den Inhalt. Um Inhalte an Suchabfragen auszurichten, stellen Sie sicher, dass sie den Such- und Aktualisierungstiteln, Beschreibungen und Schlüsselwörtern der Benutzer entspricht. 

### <a name="analyze-impressions-by-result-type"></a>Analysieren von Aufrufen nach Ergebnistyp

Leicht lesbare Diagramme auf  der Verteilungskarte Impression auf dem [Insights-Dashboard](./usage-reports.md) zeigen Impressionen über verschiedene Zeitrahmen. Die Zeitachse zeigt die tägliche Anzahl von Aufrufen für einen Ergebnistyp. Mit diesen Diagrammen können Sie bestimmen, welcher Ergebnistyp am häufigsten oder selten verwendet wird. Die selten verwendete Verwendung eines bestimmten Ergebnistyps bedeutet nicht unbedingt, dass der Ergebnistyp nicht gut ist. Sie zeigt nur, wie Benutzer das Suchergebnis verwenden.

 Wenn benutzer einen bestimmten Ergebnistyp bevorzugen, können Sie weitere Suchergebnisse desselben Typs erstellen. Um sicherzustellen, dass Schlüsselwörter geeignet sind, überprüfen Sie die Schlüsselwörter von Ergebnistypen mit geringer Auslastung. Mit diesem Bericht können Sie auch Änderungen am Benutzerverhalten im Laufe der Zeit sehen.