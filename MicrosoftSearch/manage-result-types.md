---
title: Verwalten von Ergebnistypen
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Verwalten von Ergebnistypen auf der Suchergebnisseite
ms.openlocfilehash: ea6926a8923f4436f21047c9ac4cb95625ecb163
ms.sourcegitcommit: 967a02ee932f8a6cee70cfd78bb0c8b1b78d07c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127787"
---
# <a name="manage-result-types"></a>Verwalten von Ergebnistypen

Sie können definieren, wie Suchergebnisse auf der Suchergebnisseite angezeigt werden, indem Sie das Layout mithilfe von Ergebnistypen [entwerfen.](customize-results-layout.md) Mit dem Ergebnislayout können Sie nützliche Informationen direkt in den Suchergebnissen anzeigen, damit Benutzer schnell die benötigten Informationen finden können.

Integrierte Inhaltstypen wie Dateien und Personen verfügen über ein Standardlayout, das nicht geändert werden kann. Ergebnistypen werden für [Graph Connectors-Inhalt](connectors-overview.md) verwendet. Wenn Sie einen Connector mit Eigenschaftenzuordnungen konfigurieren, verwendet Microsoft Search ein standardmäßiges Suchergebnislayout für die Connector-Suchergebnisse. Der *Bezeichnungstitel* ist der wichtigste; Dieser Bezeichnung sollte immer eine Eigenschaft zugewiesen sein, um das Standardergebnislayout zu verwenden. Das Erstellen eines benutzerdefinierten Ergebnistyps für Ihre Connectorinhalte kann diese Ergebnisse jedoch für Ihre Benutzer effektiver machen.

Bei Verwendung von Vertikalen und Connectorinhalten müssen Sie einen Ergebnistyp erstellen oder die Zuordnungen für ein Standardlayout durchführen. Wenn Sie dies nicht tun, werden in der Vertikalen keine Suchergebnisse angezeigt.

## <a name="understanding-result-types"></a>Grundlegendes zu Ergebnistypen

Erstellen Sie Ein eigenes [Suchergebnislayout,](customize-results-layout.md) und überschreiben Sie das standardmäßige Suchergebnislayout, indem Sie einen Ergebnistyp erstellen. Ein Suchergebnistyp ist eine Regel, die bewirkt, dass verschiedene Arten von Suchergebnissen unterschiedlich angezeigt werden. Es besteht aus den folgenden Parametern:

- **Eine oder mehrere Bedingungen**   um die einzelnen Suchergebnisse zu vergleichen. Beispiele für Bedingungen sind Inhaltsquelle und Titel.
- Ein **Ergebnislayout, das**   für Suchergebnisse verwendet werden soll, die die Bedingungen erfüllen. Das resultierende Layout steuert, wie die Ergebnisse, die die Bedingungen erfüllen, auf der Suchergebnisseite angezeigt werden.

Sie können mehrere Ergebnistypen für Inhalte verwenden, die in einer vertikalen Leiste angezeigt werden. Dies kann wichtig sein, wenn Sie mehrere Inhaltsquellen in einer einzelnen Vertikalen kombinieren. Es kann auch für ein wirkungsvolleres Layout verwendet werden, auch wenn nur ein Inhaltstyp vorhanden ist. Beispielsweise können Sie in einer Vertikalen, in der Vorfalldetails angezeigt werden, Vorfälle mit hohem Schweregrad so anpassen, dass sie wichtigere Farben als Vorfälle mit "niedriger Schweregrad" aufweisen. Dies kann durch Definieren von Bedingungen für die Eigenschaft "Schweregrad" im Abschnitt **"Regeln"** erfolgen.

## <a name="create-or-update-result-types"></a>Erstellen oder Aktualisieren von Ergebnistypen

Die Ergebnistypverwaltung wird vom Assistenten gesteuert. Sie werden durch die Schritte zum Definieren des Namens, der Inhaltsquelle, der Regeln und des Layouts geführt. Ergebnistypen können sowohl auf Organisationsebene als auch auf SharePoint Websiteebene angepasst werden.

### <a name="manage-organization-level-result-types"></a>Verwalten von Ergebnistypen auf Organisationsebene

1. Wechseln  [Sie in Microsoft 365 Admin Center](https://admin.microsoft.com/)zur Seite [**"Ergebnistypen"**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) im Abschnitt **"Anpassung".**
2. Klicken Sie zum Erstellen eines neuen Ergebnistyps auf **"Hinzufügen",** oder wählen Sie einen vorhandenen aus, um ihn zu bearbeiten.
3. Nach dem Konfigurieren des Ergebnistyps können Sie ihn überprüfen und speichern.

### <a name="manage-site-level-result-types"></a>Verwalten von Ergebnistypen auf Websiteebene

1. Öffnen Sie auf der SharePoint-Website, auf der Sie Ergebnistypen verwalten möchten, den Einstellungsbereich, indem Sie auf den Zahnrad klicken.
2. Wählen Sie **"Websiteinformationen"** und dann **"Alle Websiteeinstellungen anzeigen"** aus.  
3. Suchen Sie nach dem Abschnitt Microsoft Search, und wählen Sie dann **"Sucheinstellungen konfigurieren"** aus.
4. Wechseln Sie im Navigationsbereich zu "Benutzerdefinierte Oberfläche", und wählen Sie den **Ergebnistyp aus.**
5. Klicken Sie zum Hinzufügen eines Ergebnistyps auf **"Hinzufügen".** Oder wählen Sie zum Bearbeiten eines Ergebnistyps den Ergebnistyp in der Liste aus.
6. Nach dem Ändern eines Ergebnistyps können Sie den Ergebnistyp überprüfen und speichern.

## <a name="troubleshooting"></a>Problembehandlung

Nachfolgend finden Sie eine Liste allgemeiner Probleme, die möglicherweise angezeigt werden, und Aktionen zum Beheben dieser Probleme.

|Problem  |Aktion  |
|---------|---------|
| Ich sehe mein Ergebnislayout nicht auf der Suchseite, obwohl ich eins erstellt habe. | Es kann zu einer Verzögerung von einigen Minuten kommen, da diese Einstellungen zwischengespeichert werden. Warten Sie einige Minuten, und versuchen Sie es erneut.        |
| Auf der Ergebnistypseite werden keine Inhaltsquellen angezeigt. | Stellen Sie sicher, dass Sie Connectors und indizierte Daten konfiguriert haben.   |
