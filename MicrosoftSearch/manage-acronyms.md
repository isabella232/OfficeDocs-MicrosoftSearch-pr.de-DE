---
title: Verwalten von Akronymantworten in Microsoft Search
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
description: Erstellen und Aktualisieren von Akronymantworten in Microsoft Search
ms.openlocfilehash: 013510da28599f41c9dc4bf74da99efa2f6c3e97
ms.sourcegitcommit: 62cb7b8c6a311760cc728f2c70a9a22ca76e977e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408714"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Verwalten von Akronymantworten in Microsoft Search

Benutzer werden häufig in nicht vertraute Akronyme und Abkürzungen bzw. Abkürzungen ihrer Organisation oder ihres Teams bzw. Teams ausgeführt. Spezifisch für Organisationen oder Teams sind möglicherweise neue Bedingungen für Personen, die von einem Team in ein anderes wechseln, mit internen Partnerteams arbeiten oder neu in der Organisation sind.

Organisationen verfügen nicht immer über einen einzigen Verweis für ihre Standardterminologie. Das Fehlen eines einzelnen Verweises macht es schwierig, Definitionen für diese Akronyme zu finden. Microsoft Search löst dieses Problem mit Akronymen.

## <a name="what-users-experience"></a>Benutzererfahrungen

Microsoft Search-Benutzer können Definitionen mit Akronymen in [Bing,](https://Bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)und [Office 365 erhalten.](https://Office.com) Im Feld **Suchen** geben Benutzer Abfragen wie die folgenden Beispiele ein:

- *Was ist* DNN
- *Define* DNN
- DNN-Definition 
- *Erweitern* DNN
- DNN-Erweiterung 
- *Bedeutung von* DNN
- DNN *bedeutet*
- DNN *steht für*

Das Ergebnis enthält alle Bedeutungen von DNN, die in der Organisation des Benutzers vorhanden sind.

> [!NOTE]
> Benutzer müssen eine Abfrage eingeben, die die  angegebenen Schlüsselwörter des Akronyms enthält, um die entsprechenden Antworten auszulösen. Bei Akronymabfragen wird die Kleinschreibung nicht beachtet.

## <a name="set-up-acronyms-answers"></a>Einrichten von Akronymantworten

Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Akronyme,**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)und wählen Sie **dann Akronym hinzufügen aus.**

Microsoft Search fragt zwei Datenquellen ab, um Akronyme Antworten auf die Suchanfragen von Benutzern zu geben:

1. **Admin-curated**. Bereitgestellt von IT-Administratoren im [Admin Center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).
2. **Vom System kuratiert**. Von Microsoft Search aus E-Mails und Dokumenten von Benutzern sowie öffentlich verfügbaren Daten innerhalb der Organisation ermittelt.

### <a name="set-up-admin-curated-acronyms"></a>Einrichten von von Administratoren kuratierten Akronymen

Suchadministratoren können Akronyme auf der Registerkarte [Akronyme](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) im [Microsoft Search Admin Center hinzufügen.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) Sie können Akronyme von einer beliebigen internen Website oder einem Repository zum Admin Center hinzufügen. Diese Akronyme können dem Status **Veröffentlicht** oder **Entwurf hinzugefügt** werden:

**Veröffentlichter Status**. Akronyme stehen den Benutzern der Organisation über Microsoft Search zur Verfügung.

> [!NOTE]
> Es kann bis zu drei Tage dauern, bis Akronyme, die dem Status Veröffentlicht hinzugefügt wurden, in Microsoft Search verfügbar werden.

**Entwurfszustand**. Wenn Sie ein Akronym überprüfen möchten, bevor Sie es in Microsoft Search verfügbar machen, können Sie das Akronym in einem Entwurfsstatus hinzufügen. Akronyme im Entwurfszustand werden in den Suchergebnissen nicht angezeigt. Sie müssen das Akronym in den Status Veröffentlicht verschieben, damit es in den Suchergebnissen angezeigt wird.

**Ausgeschlossener Status**. Wenn Sie verhindern möchten, dass ein Akronym in Microsoft Search angezeigt wird, verwenden Sie **Ein Akronym** ausschließen, um es hinzuzufügen. Um zu verhindern, dass ein Akronym ausgeschlossen wird, müssen Sie das ausgeschlossene Akronym löschen und es hinzufügen oder überprüfen, ob es in Der veröffentlichten Liste enthalten ist.

Sie können Akronyme einzeln oder massenimportieren in eine CSV-Datei hinzufügen. Laden Sie eine CSV-Datei mit den in der folgenden Tabelle angezeigten Feldern hoch:

| Akronym (verpflichtend) | Steht für (Verpflichtend) | Url | Beschreibung  | Status (verpflichtend) | Last Modified | Zuletzt geändert von | Id |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *Kurzschreibkürzung* | *Quelle* |  | *Veröffentlicht, Entwurf oder Ausgeschlossen* |  |  |  |

### <a name="csv-fields"></a>CSV-Felder

**Akronym**. Enthält das tatsächliche Kurzformular oder Akronym. Ein Beispiel ist *DNN*.

**Steht für**. Enthält die Definition des Akronyms. Ein Beispiel ist *Deep Neural Network*.

**Beschreibung**. Eine kurze Beschreibung des Akronyms, das Benutzern mehr Informationen über das Akronym und seine Definition bietet. Ein tiefes neurales Netzwerk ist beispielsweise ein neurales Netzwerk mit einer bestimmten Komplexität, ein neurales Netzwerk mit mehr *als zwei Ebenen.*

**Quelle**. Die URL der Seite oder Website, auf der Benutzer weitere Informationen zum Akronym erhalten möchten.

**Status**. Dieses Feld kann zwei Werte enthalten:

- **Entwurf**. Fügt das Akronym zum Entwurfszustand hinzu.
- **Veröffentlicht** Fügt das Akronym dem Status Veröffentlicht hinzu und stellt es in Microsoft Search zur Verfügung.
- **Ausgeschlossen.** Fügt das Akronym dem Status Ausgeschlossen hinzu und verhindert, dass es in Microsoft Search angezeigt wird.

### <a name="system-curated-acronyms"></a>Vom System kuratierte Akronyme

Es kann eine Herausforderung für Administratoren sein, antworten alle in einer Organisation verwendeten Akronyme hinzuzufügen. Dieses Feature kann Akronyme finden, die Suchadministratoren nicht einmal kennen. Hierzu ermittelt und kuschelt Microsoft Search auch Akronyme aus den folgenden Quellen:

- E-Mails der Benutzer
- Dokumente in [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)und [Microsoft OneNote](https://www.onenote.com/)
- Öffentliche Dokumente innerhalb der Organisation, auf die Benutzer in SharePoint, OneDrive oder OneNote zugreifen können

Microsoft Search stellt sicher, dass nur Benutzer mit Zugriff und Berechtigungen für ein Dokument die Akronyme sehen können, die aus dem Dokument erkannt werden. Wenn ein Akronym im Postfach eines Benutzers gefunden wird, kann nur dieser Benutzer dieses Akronym sehen.

> [!NOTE]
> Für vom System kuratierte Akronyme ist keine Einrichtung erforderlich.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F: Wie werden vom Administrator kuratierte und vom System kuratierte Daten bewertet?**

**A:** Die Rangfolge der Ergebnisse kann von Person zu Person variieren, da die Ergebnisse für jeden Benutzer personalisiert werden. Keine dieser Kategorien hat immer Vorrang vor der anderen.

**F: Wie lange dauert es, bis von Administratoren kuratierte Akronyme in Microsoft Search angezeigt werden, nachdem sie veröffentlicht wurden?**

**A:**  Es dauert bis zu einem Tag, bis Akronyme, die dem Status Veröffentlicht hinzugefügt wurden, in Microsoft Search verfügbar werden.

**F: Wie lösen Benutzer Akronymantworten aus?**

**A:** Um Akronyme antworten zu können, müssen Benutzer bestimmte Abfragemuster in ein [Bing-,](https://bing.com) [SharePoint-](https://products.office.com/sharepoint/collaboration)oder [Office 365-Suchfeld](https://Office.com) **eingeben.**

**F: Wie lange dauert es, bis vom System kuratierte Akronyme angezeigt werden, nachdem Sie eine neue E-Mail oder ein neues Dokument empfangen oder gesendet haben?**

**A:** Akronyme, die in einer neuen E-Mail oder einem neuen Dokument gefunden werden, dauern bis zu sieben Tage, bis sie in den Microsoft-Suchergebnissen angezeigt werden.

**F: Was geschieht, wenn ein Akronym ausgeschlossen und veröffentlicht wird?**

**A:** Das ausgeschlossene Akronym hat Priorität und verhindert, dass das veröffentlichte Akronym in suchergebnissen angezeigt wird. Das veröffentlichte Akronym wird nicht gelöscht oder entfernt.

**F: Wie lange dauert es, bis ein Akronym aus den Microsoft-Suchergebnissen ausgeschlossen wird?**

**A**: Es dauert bis zu einem Tag, bis ein ausgeschlossenes Akronym nicht mehr in den Suchergebnissen angezeigt wird.

**F: Müssen Dokumente für vom System kuratierte Akronyme ein bestimmtes Format haben?**

**A:** Nein. Wir unterstützen alle Dateitypen mit Ausnahme von Bild-, Ordner- und ZIP-Dateien.

**F: Wird Microsoft Akronyme aus Dokumenten in allen Sprachen ermitteln?**

**A:** Microsoft unterstützt nur vom System kuratierte Akronyme aus Dokumenten in Englisch, Spanisch, Französisch, Italienisch, Deutsch und Portugiesisch. Unterstützung für andere Sprachen wird in Phasen hinzugefügt.

**F: Was passiert, wenn meine Organisation keine vom System kuratierten Akronyme anzeigen möchte? Kann ich diese Art von Akronym nicht mehr in meinen Suchergebnissen anzeigen?**

**A**: Um die Anzeige von vom System kuratierten Akronymen in den Suchergebnissen zu deaktivieren, erstellen Sie ein Kundensupportticket, indem Sie die Anweisungen unter [Contact support for business products befolgen.](/microsoft-365/admin/contact-support-for-business-products)
Nachdem Sie ein Supportticket erstellt haben, dauert es bis zu 48 Stunden, bis vom System kuratierte Akronyme nicht mehr in den Suchergebnissen angezeigt werden.
