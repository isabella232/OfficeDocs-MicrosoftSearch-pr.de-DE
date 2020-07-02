---
title: Verwalten von Akronym-Antworten in der Microsoft-Suche
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
description: Antworten zum Erstellen und Aktualisieren von Akronymen in Microsoft Search
ms.openlocfilehash: 9d58306751f735cef77eba4404597c73c0528c11
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996076"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Verwalten von Akronymen Antworten in der Microsoft-Suche

Benutzer führen häufig unbekannte Akronyme und Abkürzungen aus, die von Ihrer Organisation oder Ihrem Team verwendet werden. Begriffe, die für Organisationen oder Teams spezifisch sind, sind möglicherweise neu für Personen, die von einem Team in ein anderes umziehen, die mit internen Partnerteams arbeiten oder neu in der Organisation sind.

Organisationen haben nicht immer einen einzigen Verweis für Ihre Standardterminologie. Durch das Fehlen eines einzelnen Verweises ist es schwer, Definitionen oder Erweiterungen für diese Akronyme zu finden. Microsoft Search löst dieses Problem mit Akronymen.

## <a name="what-users-experience"></a>Benutzererfahrung

Microsoft Search-Benutzer können Definitionen mit Akronymen in [Bing](https://Bing.com)abrufen. In das **Suchfeld** geben Benutzer Abfragen wie diese Beispiele ein:

- *Was ist* DNN
- *Definieren* Sie DNN
- DNN- *Definition*
- *Erweitern* Sie DNN
- DNN- *Erweiterung*
- *Bedeutung von* DNN
- DNN *bedeutet*

Das Ergebnis enthält alle Bedeutungen von DNN, die in der Organisation des Benutzers vorhanden sind.

> [!NOTE]
> Benutzer müssen eine Abfrage eingeben, die die angegebenen *Schlüsselwörter* für das Akronym enthält, um die entsprechenden Antworten auszulösen. Bei Akronym-Abfragen wird die Groß-/Kleinschreibung nicht beachtet.

## <a name="set-up-acronyms-answers"></a>Antworten zum Einrichten von Akronymen

Wechseln Sie im Microsoft 365 [Admin Center](https://admin.microsoft.com)zu **Einstellungen**  >  **Microsoft Search**  >  **Answers**  >  [**Akronyme**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), und wählen Sie dann **Akronyme hinzufügen**aus.

Microsoft Search fragt zwei Datenquellen ab, um Akronyme Antworten auf die Suchvorgänge von Benutzern bereitzustellen:

1. **Redaktionelle Akronyme**. Von IT-Administratoren im [Admin Center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)bereitgestellt.
2. **Verminte Akronyme**. Durch die Microsoft-Suche von den persönlichen e-Mails und Dokumenten und öffentlich verfügbaren Daten innerhalb der Organisation abgebaut.

### <a name="set-up-editorial-acronyms"></a>Einrichten von redaktionellen Akronymen

Suchadministratoren können redaktionelle Akronyme auf der [Registerkarte Akronyme](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) im [Microsoft Search Admin Center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)einrichten. Sie können Akronyme aus einer internen Website oder einem Repository zum Admin Center hinzufügen. Redaktionelle Akronyme können dem **veröffentlichten** oder dem **Entwurfs** Status hinzugefügt werden:

**Veröffentlichter Status**. Akronyme stehen den Mitarbeitern der Organisation über die Microsoft-Suche zur Verfügung.

> [!NOTE]
> Es kann bis zu drei Tage dauern, bis Akronyme zum veröffentlichten Status hinzugefügt wurden, um in Microsoft Search verfügbar zu sein.

**Entwurfsstatus**. Wenn Administratoren Akronyme Antworten überprüfen möchten, bevor Sie in Microsoft Search verfügbar gemacht werden, können Sie die Akronyme dem Entwurfsstatus hinzufügen. Akronyme, die dem Entwurfsstatus hinzugefügt werden, sind in der Microsoft-Suche nicht verfügbar. Administratoren müssen die Akronyme dem veröffentlichten Status hinzufügen, damit Sie verfügbar sind.

Administratoren können Akronyme einzeln hinzufügen oder Sie in einer CSV-Datei Massenimportieren. Laden Sie eine CSV-Datei mit den in der folgenden Tabelle gezeigten Feldern hoch:

| Akronym (obligatorisch) | Expansion (obligatorisch) | Beschreibung  | Quelle | Status (obligatorisch) |
| --------- | --------- | ---------- | --------- |--------- |
| *XXX* | *Abkürzung für buchstabiert* |  | *URL* | *Veröffentlicht oder Entwurf* |

### <a name="csv-fields"></a>CSV-Felder

**Akronym**. Enthält das tatsächliche kurze Formular oder Akronym. Ein Beispiel ist *DNN*.

**Erweiterung**. Enthält die Erweiterung des Akronyms. Ein Beispiel ist ein *tiefes neuronales Netzwerk*.

**Beschreibung**. Eine kurze Beschreibung des Akronyms, mit der Benutzer schnell Einblicke in die Bedeutung des Akronyms und seiner Erweiterung erhalten. *Ein tiefes neuronales Netzwerk ist beispielsweise ein neuronales Netzwerk mit einem gewissen Grad an Komplexität, ein neuronales Netzwerk mit mehr als zwei Schichten*.

**Source**. Die URL der Seite oder Website, auf der Benutzer weitere Informationen zum Akronym erhalten möchten.

**State**. Dieses Feld kann zwei Werte annehmen:

- **Entwurf**. Das Akronym wird dem Status Entwurf hinzugefügt.
- **Veröffentlicht** Das Akronym wird dem veröffentlichten Zustand hinzugefügt und wird in der Microsoft-Suche zur Verfügung gestellt.

### <a name="mined-acronyms"></a>Verminte Akronyme

Es kann eine Herausforderung für Administratoren sein, alle in einer Organisation verwendeten Akronyme für Antworten hinzuzufügen. Dieses Feature kann Akronyme finden, von denen die Suchadministratoren gar nicht wissen. Dafür werden in Microsoft Search auch Akronyme aus folgenden Quellen untersucht:

- Benutzer-e-Mails.
- Dokumente in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/) und [Microsoft OneNote](http://www.onenote.com/).
- Öffentliche Dokumente innerhalb der Organisation, auf die Benutzer in SharePoint, OneDrive oder OneNote zugreifen können.

Die Microsoft-Suche stellt sicher, dass nur Benutzer mit Zugriff und Berechtigungen für ein Dokument die von dieser abgebauten Akronyme sehen können. Wenn ein Akronym aus dem Postfach eines Benutzers abgebaut wird, kann nur dieser Benutzer dieses Akronym sehen.

> [!NOTE]
> Für verminte Akronyme ist kein Setup erforderlich.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F.: wie werden redaktionelle und verminte Daten bewertet?**

**A:** Das Feature zählt derzeit redaktionelle Akronyme oberhalb der abgebauten Akronyme.

**F.: wie lange dauert es, bis redaktionelle Akronyme in der Microsoft-Suche sichtbar sind, nachdem Sie veröffentlicht wurden?**

**A:**  Es dauert bis zu drei Tage, bis Akronyme zum veröffentlichten Status hinzugefügt wurden, um in Microsoft Search verfügbar zu sein.

**F.: wie lösen Benutzer Akronyme Antworten aus?**

**A**: um Akronyme Antworten zu erhalten, müssen Benutzer bestimmte Abfragemuster in ein [Bing](https://bing.com) - **Suchfeld** eingeben. Derzeit sind Akronym-Antworten in [Office 365](https://Office.com) oder [SharePoint](https://products.office.com/sharepoint/collaboration)nicht verfügbar.

**F.: wie lange dauert es, bis abgebaute Akronyme angezeigt werden, nachdem Sie eine neue e-Mail oder ein neues Dokument empfangen oder gesendet haben?**

**A:** Verminte Akronyme aus einer neuen e-Mail oder einem Dokument benötigen bis zu sieben Tage, um in Microsoft-Suchergebnissen angezeigt zu werden.

**F.: müssen Dokumente in einem bestimmten Format vorliegen, damit Sie von Mining abgeholt werden können?**

**A:** Nein. Wir unterstützen alle Dateitypen außer Bild, Ordner und ZIP-Dateien.

**F.: werden Microsoft-Akronyme aus Dokumenten in allen Sprachen erhalten?**

**A**: Microsoft unterstützt nur das Mining von Dokumenten in englischer Sprache. Unterstützung für andere Sprachen wird in Phasen hinzugefügt.

**F.: Was geschieht, wenn meine Organisation keine verminten Akronyme anzeigen möchte? Kann ich das Anzeigen von verminten Akronymen in Suchergebnissen beenden?**

**A**: um die Anzeige von verminten Akronymen in Suchergebnissen zu deaktivieren, erstellen Sie ein Kundensupport Ticket, indem Sie die Anweisungen unter [Contact Support for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)befolgen.
Nachdem Sie ein Support Ticket erstellt haben, dauert es bis zu 48 Stunden, damit verminte Akronyme nicht mehr in den Suchergebnissen angezeigt werden.

**F.: Wann werden Akronyme Antworten in [Office 365](https://Office.com) und [SharePoint Online](https://products.office.com/sharepoint/collaboration)angezeigt?**

**A**.: Akronyme Antworten in Office 365 und SharePoint Online sind Teil unserer Produkt-Roadmap, aber wir können derzeit kein Datum oder keinen Zeitrahmen bereitstellen.
