---
title: Anpassen der Microsoft Search Seite
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Hinzufügen von Such-Vertikalen und Anpassen von Suchergebnissen
ms.openlocfilehash: 440b9afbbeb4c4cd86b2b9f67443e644c36ce042
ms.sourcegitcommit: 8ac77db22002d47bb461222b81b7cfc1c15a72fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58340078"
---
# <a name="customize-the-search-results-page"></a>Anpassen der Suchergebnisseite

Sie können Such-Vertikalen und Ergebnistypen erstellen, um die Suchergebnisse anzupassen, die Benutzern angezeigt werden, wenn sie in Microsoft [SharePoint,](https://sharepoint.com/) [Microsoft Office](https://office.com)und Microsoft Search in [Bing](https://bing.com)suchen. Vertikalen erleichtern benutzern das Auffinden der Informationen, für die sie über die Berechtigung zum Anzeigen verfügen. Sie können beispielsweise eine Suchsparte für Marketinganalysedaten aus Drittanbietersoftware für Ihre Benutzer in der Marketingabteilung erstellen. Sie können auch Ergebnistypen definieren und das Layout für diese Daten anpassen.  

Sie können Vertikalen und Ergebnistypen auf folgenden Ebenen erstellen:

- **Organisationsebene** – Wenn Sie eine Vertikale auf Organisationsebene hinzufügen, wird sie auf der Suchergebnisseite angezeigt, wenn Benutzer über ihre [SharePoint](https://sharepoint.com/) Startseite, auf [Office](https://office.com)oder auf [Bing](https://bing.com)suchen.
- **Standortebene** – Beispielsweise möchten Sie Ihren Kundendienstmitarbeitern ermöglichen, direkt von der SharePoint Website ihrer Abteilung aus nach Vorfällen des *Schweregrads 1* zu suchen.

## <a name="search-verticals-explained"></a>Erläuterte Such-Vertikalen

Am oberen Rand der Microsoft Search Ergebnisseite befindet sich eine Zeile mit Registerkarten. Hierbei handelt es sich um die Such-Vertikalen. Eine Such-Vertikal zeigt nur Ergebnisse eines bestimmten Typs oder von bestimmten Inhalten an. Beispiele sind **Dateien** oder **News**. Standardmäßig zeigt Microsoft Search die Vertikalen **"Alle",** **"Personen",** **"Dateien",** **"Websites"** und **"News"** an.  

Sie können Such-Vertikalen hinzufügen, die für Ihre Organisation relevant sind. Diese werden auf der Ergebnisseite Microsoft Search in [SharePoint,](https://sharepoint.com/) [Office](https://Office.com)und [Bing](https://bing.com)angezeigt. Sie können beispielsweise eine Vertikale für marketingbezogene Inhalte und eine weitere für den Vertrieb erstellen, basierend auf dem Typ der Informationen, die jede Gruppe benötigt. Sie können Vertikale hinzufügen, um nur Ergebnisse aus Inhalten anzuzeigen, die über Connectors indiziert wurden.  

### <a name="multiple-connections-in-a-vertical"></a>Mehrere Verbindungen in einer vertikalen

Eine Such vertical can now surface results from multiple connector sources. Dies bietet eine größere Flexibilität beim Entwerfen der Suchergebnisseite. Mit der vorhandenen Verwaltungsumgebung der vertikalen Einrichtung können Sie mehrere Verbindungen im Schritt "Inhaltsquelle" auswählen.
Wenn Sie so viele semantische Bezeichnungen wie möglich genau benennen, wird diese Erfahrung verbessert. Sie können semantische Bezeichnungen nach Schemadefinition und Aufnahme hinzufügen.

[Hier](configure-connector.md#step-6-assign-property-labels) finden Sie weitere Informationen zum Erstellen und Verwalten von Semantikbezeichnungen.

> [!NOTE]
> Mehrere Verbindungen in einer Vertikalen befinden sich derzeit in der Vorschau. Weitere Informationen zur Vorschau finden Sie unter [Connectors Preview Features](connectors-overview.md#what-are-the-preview-features).

### <a name="things-you-should-know"></a>Dinge, die Sie wissen sollten

1. Eine Verbindung kann nur unter einer Vertikalen als Inhaltsquelle hinzugefügt werden. Das Wiederverwenden von Verbindungen unter mehreren Vertikalen ist nicht zulässig.
2. Wenn Sie eine Abfrage für eine Such vertical einrichten müssen, in der mehrere Verbindungsquellen hinzugefügt wurden, sollten allgemeine Quelleigenschaften verwendet werden, um eine solche Abfrage zu erstellen.

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte

Bevor Sie beginnen, stellen Sie sicher, dass der Connector indiziert wurde. Je nach Dateigröße kann dies bis zu 48 Stunden dauern.

Sie können keine Vertikale für Inhalte erstellen, die sich in [SharePoint](https://sharepoint.com/)befinden.

Es gibt drei grundlegende Schritte zum Hinzufügen einer vertikalen Ebene:

1. Erstellen Sie die Vertikale. In diesem Schritt definieren Sie den vertikalen Namen, die Inhaltsquelle und den Umfang des zu durchsuchenden Inhalts.
2. Definieren Sie, wie die Ergebnisse für diese Vertikale aussehen.  
3. Aktivieren Sie die vertikale (anzuzeigende) Vertikal auf der vertikalen Listenseite.

## <a name="step-1-create-the-search-vertical"></a>SCHRITT 1: Erstellen der Such-Vertikalen

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte geführt, um den Vertikalnamen, die Inhaltsquelle und den Umfang der zu durchsuchenden Inhalte zu definieren. Die Vertikale wird in einem deaktivierten Zustand erstellt. Sie werden es später aktivieren.

Sie können einen begrenzten Satz von [KQL (Keyword Query Language)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) verwenden, um den Bereich einzugrenzen. Auf dieser Seite sind die verfügbaren Eigenschaften aufgeführt. Es wird empfohlen, Freitext-Schlüsselwörter und Eigenschaftseinschränkungen für boolesche Operatoren zum Erstellen von KQL zu verwenden.
KQL unterstützt auch die Verwendung von [Profilabfragevariablen](#profile-query-variables) zum Optimieren der Ergebnisse unter der vertikalen.

### <a name="create-a-vertical-at-the-organization-level"></a>Erstellen einer Vertikalen auf Organisationsebene

Führen Sie die folgenden Schritte aus, um die vertikale Microsoft Search in [SharePoint](https://sharepoint.com/) Zuhause, [Office](https://office.com)oder [Bing](https://bing.com)zu erstellen:

1. Wechseln [Sie](https://admin.microsoft.com)im Microsoft 365 Admin Center zu [**"Vertikalen".**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Wählen Sie **"Hinzufügen"** aus, um zu beginnen.  

### <a name="create-a-vertical-at-the-site-level"></a>Erstellen einer Vertikalen auf Websiteebene

1. Wechseln Sie auf der [SharePoint](https://sharepoint.com/) Website, auf der Sie die Vertikale verwenden möchten, zu **Einstellungen**.
2. Wählen Sie **Websiteinformationen aus,** und zeigen Sie dann **alle Websiteeinstellungen an.**
3. Suchen Sie nach dem **Abschnitt Microsoft Search,** und wählen Sie dann **Microsoft Search für diese Websitesammlung** konfigurieren aus.
4. Wechseln Sie im Navigationsbereich zu **"Benutzerdefinierte Oberfläche",** und wählen Sie dann die Registerkarte **"Vertikal" aus.**
5. Wählen Sie zum Hinzufügen einer vertikalen , **hinzufügen**.
  Oder wählen Sie eine Vertikale in der Liste aus, um sie zu bearbeiten.

Denken Sie daran, dass Vertikale in einem deaktivierten Zustand erstellt werden. Sie müssen aktiviert sein, bevor Benutzer sie sehen können.

## <a name="step-2-create-the-result-types"></a>SCHRITT 2: Erstellen der Ergebnistypen

Sie können definieren, wie Ergebnisse in der vertikalen Leiste angezeigt werden, indem Sie das Layout mithilfe von Ergebnistypen entwerfen. Mit dem Ergebnislayout können Sie wichtige Informationen direkt in den Suchergebnissen anzeigen, sodass Benutzer nicht jedes Ergebnis auswählen müssen, um festzustellen, ob sie das gesuchte Ergebnis gefunden haben.

### <a name="default-search-result-layout"></a>Standardmäßiges Suchergebnislayout

Ein standardmäßiges Suchergebnislayout wird für Connector-Inhalte angezeigt, wenn **Bezeichnungen** und **Inhaltseigenschaften** zum Zeitpunkt der Konfiguration des Connectors den Quelleigenschaften ordnungsgemäß zugeordnet wurden. Der **Bezeichnungstitel** ist die wichtigste Bezeichnung. Es wird **dringend empfohlen,** dass Dieser Bezeichnung eine Eigenschaft zugewiesen ist, um das standardmäßige Suchergebnislayout zu verwenden.

### <a name="create-your-own-result-type"></a>Erstellen Eines eigenen Ergebnistyps

Sie können ein eigenes Suchergebnislayout erstellen und das standardmäßige Suchergebnislayout überschreiben, indem Sie einen **Ergebnistyp** erstellen. Ein Ergebnistyp einer Suche ist eine Regel, die bewirkt, dass unterschiedliche Arten von Suchergebnissen auf verschiedene Weisen angezeigt werden. Ein Ergebnistyp hat folgende Bestandteile:

- **Eine oder mehrere Bedingungen,** mit denen jedes Suchergebnis verglichen werden soll, z. B. die Inhaltsquelle des Suchergebnisses.  
- Ein **Ergebnislayout, das** für Suchergebnisse verwendet werden soll, die die Bedingungen erfüllen. Das resultierende Layout steuert, wie alle Ergebnisse, die die Bedingungen erfüllen, auf einer Suchergebnisseite angezeigt werden und sich verhalten.

**Wenn keine geeignete Zuordnung zum Anzeigen des standardmäßigen Suchergebnislayouts erfolgt, müssen Sie mindestens einen Ergebnistyp erstellen, damit die Ergebnisse auf der vertikalen Seite angezeigt werden können.** Sie können für jede Vertikale mehrere Ergebnistypen erstellen, sodass Sie unterschiedliche Layouts für unterschiedliche Ergebnistypen verwenden können. Sie können z. B. Vorfälle des *Schweregrads 1* so anpassen, dass sie im Vergleich zu Vorfällen mit *Schweregrad 3* auffälligere Farben und eine größere Schriftart aufweisen.

Nachdem Sie den Assistenten gestartet haben, werden Sie durch die Schritte geführt, um den Namen, die Inhaltsquelle und die Bedingungen für den Ergebnistyp zu definieren. Sie können die Priorität des Ergebnistyps in der Listenansicht definieren.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Erstellen eines Ergebnistyps auf Organisationsebene

1. Wechseln [Sie](https://admin.microsoft.com)im Microsoft 365 Admin Center zu [**Ergebnistypen.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)
2. Wenn Sie einen Ergebnistyp hinzufügen **möchten,** wählen Sie **"Hinzufügen"** aus. Um einen Ergebnistyp zu bearbeiten, wählen Sie den Ergebnistyp in der entsprechenden Liste aus.

### <a name="create-a-results-type-at-the-site-level"></a>Erstellen eines Ergebnistyps auf Websiteebene

1. Wechseln Sie auf der [SharePoint](https://sharepoint.com/) Website, auf der Sie den Ergebnistyp erstellen möchten, zu **Einstellungen**.
2. Wählen Sie **Websiteinformationen aus,** und zeigen Sie dann **alle Websiteeinstellungen an.**
3. Suchen Sie nach dem Abschnitt Microsoft Search, und wählen Sie dann **konfigurieren Microsoft Search für diese Websitesammlung** aus.
4. Wechseln Sie im Navigationsbereich zu **"Benutzerdefinierte Oberfläche",** und wählen Sie die Registerkarte **"Ergebnistyp" aus.**
5. Um einen Ergebnistyp hinzuzufügen, wählen Sie **Hinzufügen** aus.  Oder wählen Sie zum Bearbeiten eines Ergebnistyps den Ergebnistyp in der Liste aus.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>SCHRITT 3: Anzeigen der Vertikalen nach der Aktivierung

Nachdem Sie die Vertikale aktiviert haben, dauert es einige Stunden, bis Sie sie anzeigen können. Wenn Sie nach der Aktivierung nicht warten möchten, können Sie **cacheClear=true** an die URL in [SharePoint](https://sharepoint.com/) anfügen und [Office,](https://office.com) um die Vertikale sofort anzuzeigen. Fügen [Sie für Bing](https://bing.com)&**features=uncachedVerticals** an die vertikale URL "Arbeit" an, um die Vertikalen sofort anzuzeigen.

> [!NOTE]
> Hinzugefügte Vertikale sind auf [SharePoint](https://sharepoint.com/) und [Office](https://office.com) nicht sichtbar, wenn sie in mobilen Webbrowsern angezeigt werden.

## <a name="profile-query-variables"></a>Profilabfragevariablen

Abfragevariablen werden im KQL-Abfrageabschnitt einer Vertikalen verwendet, um dynamische Daten als Eingabe für die Abfrage einer Vertikalen bereitzustellen. Sie können Profilabfragevariablen verwenden, um die Suchergebnisse für den angemeldeten Benutzer kontextbezogen zu gestalten. Profilabfragevariablen rufen Werte aus dem [Profil](/graph/api/resources/profile?view=graph-rest-beta)des angemeldeten Benutzers ab.

Wenn Sie z. B. eine Vertikale "Tickets" erstellen möchten, in der ein angemeldeter Benutzer nach zugewiesenen Supporttickets suchen kann, können Sie während der vertikalen Erstellung auf der Verwaltungsseite die folgende Abfrage im Abschnitt "Abfrage" angeben.  

**AssignedTo:{Profile.accounts.userPrincipalName}**

Dadurch werden die Suchergebnisse eingegrenzt, um nur die Elemente anzuzeigen, bei denen der Zugewiesene der Benutzer ist, der die Suche ausführt.

[Profilressource](/graph/api/resources/profile?view=graph-rest-beta) macht Eigenschaften als Sammlungen verfügbar. Beispielsweise werden Informationen im Zusammenhang mit E-Mail-Adressen über die E-Mail-Sammlung, Arbeitspositionen als Positionssammlung usw. verfügbar gemacht. Alle im Benutzerprofil verfügbaren Eigenschaften, die AAD als Quelltyp aufweisen, werden als Abfragevariablen verfügbar gemacht.

Betrachten Sie einen Benutzer mit drei E-Mail-Adressen, die in der E-Mail-Sammlung verfügbar sind, wie unten dargestellt.

```json
"emails": [{ 

        "address": "Megan.Bowen@contoso.com",
        "id": "xyz", 
        "source": { 
            "CreatedBy": "xyz", 
            "CreatedOn": "2222", 
            "Type": "official" 
        },
        "type": "main" 
    }, { 
        "address": "meganb@hotmail.com",
        "id": "abc", 
        "source": { 
            "CreatedBy": "abc",
            "CreatedOn": "3333", 
            "Type": "non-official",
        },
        "type": "work"
    }, { 
        "address": "meganb@outlook.com",
        "id": "pqr", 
        "source": { 
            "CreatedBy": "pqr", 
            "CreatedOn": "4444", 
            "Type": "personal" 
        },
        "type": "personal" 
    } 
] 
```

- Die Abfrage **"MyProperty: {Profile.emails.address}"** wird in "MyProperty" aufgelöst: "Megan.Bowen@contoso.com".  

- Wenn Sie alle Werte des Adressattributs auflösen möchten, müssen Sie die Mehrwerterweiterungssyntax verwenden. Die Abfrage **{| MyProperty:{Profile.emails.address}}** wird in ((MyProperty:"Megan.Bowen@contoso.com") OR (MyProperty: "meganb@hotmail.com") OR (MyProperty:"meganb@outlook.com")) aufgelöst.  

Der Operator "|" sollte zum Auflösen von Mehrwertvariablen verwendet werden. Weitere Beispiele zur Profilerweiterung finden Sie in der folgenden Tabelle.

| #         | Syntax |  Zurückgegebener Wert  |
| --------- | ------ | --- |
| 1     | MyProperty:{Profile.emails.address}  |   "Megan.Bowen@contoso.com"  |
| 2  | MyProperty:{Profile.emails}   |    {Profile.emails} Dies wird nicht aufgelöst, da E-Mails ein Objekt sind.|
| 3     | {? MyProperty:{Profile.emails}}  |  Dies wird nicht aufgelöst, da E-Mails ein Objekt sind. Das "?" -Operator ignoriert Abfragevariablen, die nicht aufgelöst werden. Diese Variable wird entfernt, wenn sie weiter unten im Abfragestapel übergeben wird.   |
| 4  | {&#124;MyProperty: {Profile.emails.source.Type}}    |  ((MyProperty:"official") OR (MyProperty:"non-official") OR (MyProperty:"personal"))    |

> [!NOTE]
>
> - Profilabfragevariablen werden nur für benutzerdefinierte Vertikale unterstützt, die einen [Connector](connectors-overview.md) als Inhaltsquelle verwenden.
> - Profilabfragevariablen werden im Abschnitt "Abfrage" des [vertikalen Einrichtungsprozesses](customize-search-page.md#step-1-create-the-search-vertical)definiert.
> - Profilabfragevariablen befinden sich derzeit in der Vorschau. Weitere Informationen zur Vorschau finden Sie unter [Connectors Preview Features](connectors-overview.md#what-are-the-preview-features).

## <a name="troubleshooting"></a>Problembehandlung

Hier ist eine Liste der häufig auftretenden Probleme und Aktionen zur Behebung dieser Probleme.

|Fehler  |Maßnahme  |
|---------|---------|
| Ich sehe die Fehlermeldung "Etwas ist schief gelaufen" in der Vertikalen. | Zum Abschließen des Setups sind sowohl die vertikalen als auch die Ergebnistypen erforderlich. Stellen Sie sicher, dass Sie beide für dieselbe Inhaltsquelle erstellt haben. |
| Ich sehe mein Ergebnislayout nicht, obwohl ich eins erstellt habe. | Es dauert einige Minuten, da diese Einstellungen im Allgemeinen zwischengespeichert werden. Warten Sie einige Minuten, und versuchen Sie es erneut.        |
| Ich sehe keine Inhaltsquellen auf der vertikalen Seite oder auf der Ergebnistypseite. | Stellen Sie sicher, dass Sie Connectors und indizierte Daten konfiguriert haben.   |

## <a name="next-steps"></a>Nächste Schritte

[Anpassen des Ergebnislayouts](customize-results-layout.md)
