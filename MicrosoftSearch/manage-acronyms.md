---
title: Verwalten von Akronym-Antworten in der Microsoft-Suche
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Antworten zum Erstellen und Aktualisieren von Akronymen in Microsoft Search
ms.openlocfilehash: ff79e3d741e10d401873c29d86739e61c9f53329
ms.sourcegitcommit: e6ceb07cae208648dadd5452a077414ab5a4513f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "49728006"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Verwalten von Akronymen Antworten in der Microsoft-Suche

Benutzer führen häufig unbekannte Akronyme und Abkürzungen aus, die von Ihrer Organisation oder Ihrem Team verwendet werden. Begriffe, die für Organisationen oder Teams spezifisch sind, sind möglicherweise neu für Personen, die von einem Team in ein anderes umziehen, mit internen Partnerteams arbeiten oder neu in der Organisation sind.

Organisationen haben nicht immer einen einzigen Verweis für Ihre Standardterminologie. Durch das Fehlen eines einzelnen Verweises ist es schwer, Definitionen oder Erweiterungen für diese Akronyme zu finden. Microsoft Search löst dieses Problem mit Akronymen.

## <a name="what-users-experience"></a>Benutzererfahrung

Microsoft Search-Benutzer können Definitionen mit Akronymen in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)und [Office 365](https://Office.com)abrufen. In das **Suchfeld** geben Benutzer Abfragen wie diese Beispiele ein:

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

Wechseln Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Akronyme**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), und wählen Sie dann **Akronym hinzufügen** aus.

Microsoft Search fragt zwei Datenquellen ab, um Akronyme Antworten auf die Suchvorgänge von Benutzern bereitzustellen:

1. **Admin-kuratiert**. Von IT-Administratoren im [Admin Center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)bereitgestellt.
2. **System-kuratiert**. Von der Microsoft-Suche anhand von e-Mails und Dokumenten sowie öffentlich verfügbaren Daten in der Organisation ermittelt.

### <a name="set-up-admin-curated-acronyms"></a>Einrichten von admin-kuratierten Akronymen

Suchadministratoren können Akronyme auf der [Registerkarte Akronyme](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) im  [Microsoft Search Admin Center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)hinzufügen. Sie können Akronyme aus einer internen Website oder einem Repository zum Admin Center hinzufügen. Diese Akronyme können dem **veröffentlichten** oder dem **Entwurfs** Status hinzugefügt werden:

**Veröffentlichter Status**. Akronyme stehen den Benutzern der Organisation über die Microsoft-Suche zur Verfügung.

> [!NOTE]
> Es kann bis zu drei Tage dauern, bis Akronyme zum veröffentlichten Status hinzugefügt wurden, um in Microsoft Search verfügbar zu sein.

**Entwurfsstatus**. Wenn Sie ein Akronym überprüfen möchten, bevor Sie es in Microsoft Search verfügbar machen, können Sie das Akronym in einem Entwurfsstatus hinzufügen. Akronyme im Entwurfsstatus werden in den Suchergebnissen nicht angezeigt. Sie müssen das Akronym in den veröffentlichten Zustand versetzen, damit es in den Suchergebnissen angezeigt wird.

Sie können Akronyme einzeln hinzufügen oder Sie in einer CSV-Datei Massenimportieren. Laden Sie eine CSV-Datei mit den in der folgenden Tabelle gezeigten Feldern hoch:

| Akronym (obligatorisch) | Expansion (obligatorisch) | Beschreibung  | Source | Status (obligatorisch) |
| --------- | --------- | ---------- | --------- |--------- |
| *XXX* | *Abkürzung für buchstabiert* |  | *URL* | *Veröffentlicht oder Entwurf* |

### <a name="csv-fields"></a>CSV-Felder

**Akronym**. Enthält das tatsächliche kurze Formular oder Akronym. Ein Beispiel ist *DNN*.

**Erweiterung**. Enthält die Erweiterung des Akronyms. Ein Beispiel ist ein *tiefes neuronales Netzwerk*.

**Beschreibung**. Eine kurze Beschreibung des Akronyms, mit der Benutzer weitere Informationen zum Akronym und seiner Erweiterung erhalten. *Ein tiefes neuronales Netzwerk ist beispielsweise ein neuronales Netzwerk mit einem gewissen Grad an Komplexität, ein neuronales Netzwerk mit mehr als zwei Schichten*.

**Quelle**. Die URL der Seite oder Website, auf der Benutzer weitere Informationen zum Akronym erhalten möchten.

**State**. Dieses Feld kann zwei Werte annehmen:

- **Entwurf**. Das Akronym wird dem Status Entwurf hinzugefügt.
- **Veröffentlicht** Das Akronym wird dem veröffentlichten Zustand hinzugefügt und wird in der Microsoft-Suche zur Verfügung gestellt.

### <a name="system-curated-acronyms"></a>Vom System kuratierte Akronyme

Es kann eine Herausforderung für Administratoren sein, alle in einer Organisation verwendeten Akronyme für Antworten hinzuzufügen. Dieses Feature kann Akronyme finden, von denen die Suchadministratoren gar nicht wissen. Dafür erkennt und kuratiert Microsoft Search auch Akronyme aus diesen Quellen:

- Benutzer-e-Mails
- Dokumente in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)und [Microsoft OneNote](https://www.onenote.com/)
- Öffentliche Dokumente in der Organisation, auf die Benutzer in SharePoint, OneDrive oder OneNote zugreifen können

Bei der Microsoft-Suche wird sichergestellt, dass nur Benutzer mit Zugriff und Berechtigungen für ein Dokument die von ihm ermittelten Akronyme sehen können. Wenn ein Akronym im Postfach eines Benutzers gefunden wird, kann nur dieser Benutzer dieses Akronym sehen.

> [!NOTE]
> Für vom Administrator kuratierte Akronyme ist kein Setup erforderlich.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F.: wie werden die vom Administrator kuratierten und die System kuratierten Daten bewertet?**

**A:** Die Rangfolge der Ergebnisse kann von Person zu Person variieren, da die Ergebnisse für jeden Benutzer personalisiert werden. Keine dieser Kategorien hat immer Vorrang vor der anderen Kategorie.

**F.: wie lange dauert es, bis admin-kuratierte Akronyme in der Microsoft-Suche sichtbar sind, nachdem Sie veröffentlicht wurden?**

**A:**  Es dauert bis zu drei Tage, bis Akronyme zum veröffentlichten Status hinzugefügt wurden, um in Microsoft Search verfügbar zu sein.

**F.: wie lösen Benutzer Akronyme Antworten aus?**

**A**: um Akronyme Antworten zu erhalten, müssen Benutzer bestimmte Abfragemuster in ein [Bing](https://bing.com)-, [SharePoint](https://products.office.com/sharepoint/collaboration)-oder [Office 365](https://Office.com) **Suchfeld** eingeben.

**F.: wie lange dauert es, bis die vom System kuratierten Akronyme angezeigt werden, nachdem Sie eine neue e-Mail oder ein neues Dokument empfangen oder gesendet haben?**

**A:** In einer neuen e-Mail oder einem Dokument gefundene Akronyme benötigen bis zu sieben Tage, um in Microsoft-Suchergebnissen angezeigt zu werden.

**F.: müssen Dokumente in einem bestimmten Format vorliegen, damit Sie von Mining abgeholt werden können?**

**A:** Nein. Wir unterstützen alle Dateitypen außer Bild, Ordner und ZIP-Dateien.

**F.: wird Microsoft Akronyme aus Dokumenten in allen Sprachen ermitteln?**

**A**: Microsoft unterstützt nur das Mining von Dokumenten in englischer Sprache. Unterstützung für andere Sprachen wird in Phasen hinzugefügt.

**F.: Was geschieht, wenn meine Organisation keine vom System kuratierten Akronyme anzeigen möchte? Kann ich die Anzeige dieser Art von Akronym in meinen Suchergebnissen beenden?**

**A**: um das Anzeigen von System-kuratierten Akronymen in Suchergebnissen zu deaktivieren, erstellen Sie ein Kundensupport Ticket, indem Sie den Anweisungen unter [Contact Support for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)folgen.
Nachdem Sie ein Support Ticket erstellt haben, dauert es bis zu 48 Stunden, damit die vom System kuratierten Akronyme nicht mehr in den Suchergebnissen angezeigt werden.
