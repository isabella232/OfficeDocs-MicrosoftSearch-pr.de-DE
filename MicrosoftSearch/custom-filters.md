---
title: Verwalten von Filtern
ms.author: v-revathib
author: revathi-b
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Verwalten von Filtern für die Verwendung im SERP
ms.openlocfilehash: c614d4b60c746f2e18fdb3352281891ea5134373
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702193"
---
# <a name="manage-filters"></a>Verwalten von Filtern

Mithilfe von Filtern können Benutzer die Ergebnisse ihrer Abfragen verfeinern und die optimierten Ergebnisse anzeigen. Sie können die Filter anpassen, die Ihren Benutzern in der Microsoft Search-Umgebung zur Verfügung stehen.

Auf der Suchseite stehen zwei Filtertypen zur Verfügung.

- Out-of-the-Box-Filter
- Benutzerdefinierte Filter

> [!NOTE]
> Benutzerdefinierte Filter befinden sich derzeit in der Vorschau für Administratoren und Endbenutzer in targeted Release. Weitere Informationen zur Vorschau finden Sie unter [Connectors Preview Features](connectors-overview.md#what-are-the-preview-features).

## <a name="out-of-the-box-filters"></a>Out-of-the-Box-Filter

Sofort einsatzbereite Filter sind standardmäßig in Such-Vertikalen wie "Alle", "Dateien", "Bilder" und "News" verfügbar. In den Vertikalen "Alle" und "Datei" wird der Filter "Dateityp" für die FileType-Eigenschaft und der Filter "Zuletzt geändert" in der LastModifiedTime-Eigenschaft angezeigt. Diese Filter sind in SharePoint Home, Office.com, SharePoint Sites und Work vertical in Bing verfügbar.

## <a name="custom-filters"></a>Benutzerdefinierte Filter

Filter können benutzerdefinierten Such-Vertikalen auf Organisations- und Websiteebene hinzugefügt werden. Verfeinerbare verwaltete Eigenschaften werden verwendet, um Filter im Assistenten für die vertikale Verwaltung zu konfigurieren.  Anschließend kann ein benutzerdefinierter Filter innerhalb einer Vertikalen basierend auf einer Verbindungseigenschaft erstellt werden. Sie können z. B. einen Filter "Veröffentlicht auf" für eine ServiceNow-Verbindung innerhalb einer Vertikalen erstellen.

Filter, die für Vertikale im Organisationsbereich konfiguriert sind, sind auf Organisationsebene verfügbar. Filter können auch im Bereich der Website konfiguriert werden.  

## <a name="create-organization-level-filters"></a>Erstellen von Filtern auf Organisationsebene

1. Wechseln  [Sie in Microsoft 365 Admin Center](https://admin.microsoft.com/)zu  [**"Verticals"**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Wählen Sie Ihre bevorzugte Vertikale aus, in der Sie einen Filter erstellen möchten, und klicken Sie auf **"Bearbeiten".**  
3. Navigieren Sie im Assistenten der vertikalen Synchronisierung zum Schritt "Filter".
4. Klicken Sie auf **"Filter hinzufügen",** um Filter für verfeinerbare verwaltete Eigenschaften zu konfigurieren.
5. Nach dem Hinzufügen von Filtern können Sie die Vertikale überprüfen und speichern.

## <a name="create-sharepoint-site-level-filters"></a>Erstellen SharePoint Filter auf Websiteebene

1. Wechseln [Sie in SharePoint Admin Center](https://sharepoint.com/)zu Einstellungen.
2. Suchen Sie nach dem Abschnitt Microsoft Search, und wählen Sie dann **konfigurieren Microsoft Search für diese Websitesammlung** aus.
3. Wechseln Sie im Navigationsbereich zu "Benutzerdefinierte Oberfläche", und wählen Sie dann  **"Vertikal" aus.**
4. Wählen Sie Ihre bevorzugte Vertikale aus, um den Filter zu erstellen, und klicken Sie auf **"Bearbeiten".**
5. Navigieren Sie im Assistenten der vertikalen Synchronisierung zum Schritt "Filter".
6. Klicken Sie auf **"Filter hinzufügen",** um Filter für verfeinerbare verwaltete Eigenschaften zu konfigurieren.
7. Nach dem Hinzufügen von Filtern können Sie die Vertikale überprüfen und speichern.

## <a name="filter-across-multiple-properties"></a>Filtern über mehrere Eigenschaften hinweg

Vertikale Elemente können mit einer oder mehreren Inhaltsquellen erstellt werden. Wenn eine vertikale Komponente mit mehreren Inhaltsquellen konfiguriert ist, zeigt die Eigenschaftenliste der Einschränkung an, zu welcher Inhaltsquelle jede verfeinerbare Eigenschaft gehört. Die allgemeinen verwalteten Eigenschaften werden basierend auf dem Namen (oder Alias) und Datentyp zusammengeführt. Filter können auch für diese allgemeinen Eigenschaften konfiguriert werden. Dazu wird der Filter für einen allgemeinen Alias erstellt, der Quelleigenschaften über die verschiedenen Verbindungen hinweg aliasiert. Sie können z. **B.** einen Author-Filter für ServiceNow- und Jira-Verbindungen erstellen, indem Sie wie folgt Aliase erstellen:

 | Verbindung | Eigenschaft | Alias |
 | --- | --- | --- |
 | Jetzt dienst | Besitzer | Ursprung |
 | Jira | Publisher | Ursprung |

## <a name="important-details"></a>Wichtige Details

- Filter können nur benutzerdefinierten Vertikalen hinzugefügt werden. Neue Filter können nicht zu vordefinierten Vertikalen wie "Alle", "Dateien", "Personen", "Websites", "News" hinzugefügt werden.
- Filter können für Text- und DateTime-Eigenschaften konfiguriert werden.
- Sie sind auf insgesamt 50 Filter beschränkt.
- Die Reihenfolge der vordefinierten Filter kann nicht angepasst werden.
- Filter werden für OneDrive Inhalt nicht unterstützt. Filterwerte, die Suchergebnissen aus OneDrive Inhalt entsprechen, werden nicht in Filtern angezeigt.
- Benutzerdefinierte Filterwerte zeigen Optionen aus SharePoint Inhalt und nicht aus One Drive-Inhalten an.Wenn Sie beispielsweise einen benutzerdefinierten Filter für "Autor" erstellen und SharePoint Inhalt nur Ergebnisse von einem Autor enthält, "Amy", und OneDrive Inhalt nur Ergebnisse von einem Autor namens "John" enthält, zeigt der benutzerdefinierte Filter "Autor" "Amy" als einzige Option an.
- Ein Filterwert, der für SharePoint Inhalt angezeigt wird, wird bei Verwendung auf OneDrive Inhalt angewendet.
