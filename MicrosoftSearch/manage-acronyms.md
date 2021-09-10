---
title: Verwalten von Akronyme antworten in Microsoft Search
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Erstellen und Aktualisieren von Akronymenantworten in Microsoft Search
ms.openlocfilehash: b7b3272ba98bbce7d43562811389df0a35e9f7a2
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973661"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Verwalten von Akronymen-Antworten in Microsoft Search

Benutzern werden häufig unbekannte Akronyme und Abkürzungen angezeigt, die von ihrer Organisation oder ihrem Team verwendet werden. Ausdrücke, die für Organisationen oder Teams spezifisch sind, sind möglicherweise neu für Personen, die von einem Team in ein anderes wechseln, mit internen Partnerteams arbeiten oder neu in der Organisation sind.

Organisationen verfügen nicht immer über eine einzige Referenz für ihre Standardterminologie. Das Fehlen eines einzelnen Verweises macht es schwierig, Definitionen für diese Akronyme zu finden. Microsoft Search löst dieses Problem mit Akronymen.

## <a name="what-users-experience"></a>Benutzerfreundlichkeit

Microsoft Search Benutzer können Definitionen mit Akronymen in [Bing,](https://Bing.com) [SharePoint,](https://products.office.com/sharepoint/collaboration) [Office 365,](https://Office.com)Outlook im Web, Outlook Mobile (Android) und Teams Mobile (iOS und Android) abrufen. Im **Suchfeld** geben Benutzer Abfragen wie die folgenden Beispiele ein:

- *Was ist* DNN
- *Definieren* DNN
- DNN-Definition 
- *Erweitern* DNN
- DNN-Erweiterung 
- *Bedeutung von* DNN
- DNN *bedeutet*
- DNN *steht für*

Das Ergebnis enthält alle Bedeutungen von DNN, die innerhalb der Organisation des Benutzers vorhanden sind.

> [!NOTE]
> Benutzer müssen eine Abfrage eingeben, die die angegebenen *Schlüsselwörter* des Akronyms enthält, um die entsprechenden Antworten auszulösen. Bei Akronyonymabfragen wird die Groß-/Kleinschreibung nicht beachtet.

## <a name="set-up-acronyms-answers"></a>Einrichten von Akronymen-Antworten

Wechseln [Sie](https://admin.microsoft.com)im Microsoft 365 Admin Center zu [**Akronyme,**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)und wählen Sie dann **Akronyme hinzufügen** aus.

Microsoft Search fragt zwei Datenquellen ab, um Akronyme antworten auf die Suchvorgänge der Benutzer bereitzustellen:

1. **Vom Administrator zusammengestellt.** Bereitgestellt von IT-Administratoren im [Admin Center.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)
2. **Vom System zusammengestellt.** Entdeckt durch Microsoft Search aus den E-Mails und Dokumenten der Benutzer sowie aus öffentlich verfügbaren Daten innerhalb der Organisation.

### <a name="set-up-admin-curated-acronyms"></a>Einrichten von vom Administrator zusammengestellten Akronymen

Suchadministratoren können Akronyme auf der [Registerkarte "Akronyme"](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) im [Microsoft Search Admin Center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)hinzufügen. Sie können Akronyme von jeder internen Website oder jedem Repository zum Admin Center hinzufügen. Diese Akronyme können dem Status **"Veröffentlicht"** oder **"Entwurf"** hinzugefügt werden:

**Veröffentlichter Status**. Akronyme stehen den Benutzern der Organisation über Microsoft Search zur Verfügung.

> [!NOTE]
> Es dauert bis zu einem Tag, bis Akronyme, die dem Status "Veröffentlicht" hinzugefügt wurden, in Microsoft Search verfügbar sind.

**Entwurfsstatus**. Wenn Sie ein Akronym überprüfen möchten, bevor Sie es in Microsoft Search verfügbar machen, können Sie das Akronym in einem Entwurfsstatus hinzufügen. Akronyme im Status "Entwurf" werden in den Suchergebnissen nicht angezeigt. Sie müssen das Akronym in den Status "Veröffentlicht" verschieben, damit es in den Suchergebnissen angezeigt wird.

**Ausgeschlossener Zustand**. Wenn Sie verhindern möchten, dass ein Akronym in Microsoft Search angezeigt wird, verwenden Sie ein **Akronym ausschließen,** um es hinzuzufügen. Um zu verhindern, dass ein Akronym ausgeschlossen wird, müssen Sie das ausgeschlossene Akronym löschen und hinzufügen oder überprüfen, ob es in Ihrer veröffentlichten Liste enthalten ist.

Sie können Akronyme einzeln hinzufügen oder in einer CSV-Datei massenimportieren. Hochladen eine CSV-Datei mit den in der folgenden Tabelle angezeigten Feldern:

| Akronym (verpflichtend) | Steht für (Verpflichtend) | Url | Beschreibung  | Status (verpflichtend) | Zuletzt geändert | Zuletzt geändert von | Id |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *Rechtschreibweise Abkürzung* | *Source* |  | *Veröffentlicht, Entwurf oder ausgeschlossen* |  |  |  |

### <a name="csv-fields"></a>CSV-Felder

**Akronym**. Enthält die tatsächliche Kurzform oder das Akronyme. Ein Beispiel ist *DNN*.

**Steht für**. Enthält die Definition des Akronymens. Ein Beispiel ist *Deep Neural Network*.

**Beschreibung**. Eine kurze Beschreibung des Akronymens, die Benutzern weitere Informationen über das Akronym und dessen Definition liefert. Ein *tiefes neurales Netzwerk ist beispielsweise ein neurales Netzwerk mit einer bestimmten Komplexität, ein neurales Netzwerk mit mehr als zwei Ebenen.*

**Quelle**. Die URL der Seite oder Website, auf der Benutzer weitere Informationen zum Akronym verwenden sollen.

**Status**. Dieses Feld kann zwei Werte annehmen:

- **Entwurf**. Fügt das Akronym zum Entwurfsstatus hinzu.
- **Veröffentlicht** Fügt das Akronym zum Status "Veröffentlicht" hinzu und macht es in Microsoft Search verfügbar.
- **Ausgeschlossen.** Fügt das Akronym zum Status "Ausgeschlossen" hinzu und verhindert, dass es in Microsoft Search angezeigt wird.

### <a name="system-curated-acronyms"></a>Vom System zusammengestellte Akronyme

Es kann eine Herausforderung für Administratoren sein, alle in einer Organisation verwendeten Akronyme zu Antworten hinzuzufügen. Dieses Feature kann Akronyme finden, die Suchadministratoren nicht einmal bewusst sind. Um dies zu tun, ermittelt Microsoft Search auch Akronyme aus diesen Quellen und curates:

- E-Mails von Benutzern
- Dokumente in [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)und [Microsoft OneNote](https://www.onenote.com/)
- Öffentliche Dokumente innerhalb der Organisation, auf die Benutzer in SharePoint, OneDrive oder OneNote Zugriff haben

Microsoft Search stellt sicher, dass nur Benutzer mit Zugriff und Berechtigungen auf ein Dokument die Akronyme sehen können, die daraus erkannt werden. Wenn ein Akronym im Postfach eines Benutzers gefunden wird, kann nur dieser Benutzer dieses Akronym sehen.

> [!NOTE]
> Für vom System zusammengestellte Akronyme ist kein Setup erforderlich.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F: Wie werden vom Administrator zusammengestellte und vom System zusammengestellte Daten bewertet?**

**A:** Die Rangfolge der Ergebnisse kann von Person zu Person variieren, da die Ergebnisse für jeden Benutzer personalisiert werden. Keine dieser Kategorien hat immer Vorrang vor der anderen.

**F: Wie lösen Benutzer Akronyme aus?**

**A:** Um Akronyme antworten zu können, müssen Benutzer bestimmte Abfragemuster in ein **Suchfeld** [für Bing,](https://bing.com) [SharePoint,](https://products.office.com/sharepoint/collaboration) [Office 365,](https://Office.com)Outlook im Web, Outlook Mobile (Android) oder Teams Mobile (iOS und Android) eingeben.

**F: Können Benutzer bei der Suche nur das Akronym eingeben?**

**A:** Auf Bing können Benutzer jetzt Akronyme finden, indem sie nach einem Akronym suchen. Ein Schlüsselwort wird nicht mehr benötigt. Diese Erfahrung wird auch für andere Microsoft Search Einstiegspunkte in Phasen aktiviert.

**F: Wie lange dauert es, bis von Administratoren zusammengestellte Akronyme in Microsoft Search nach ihrer Veröffentlichung sichtbar sind?**

**A:** Es dauert bis zu einem Tag, bis Akronyme, die dem Status "Veröffentlicht" hinzugefügt wurden, in Microsoft Search verfügbar sind.

**F: Wie lange dauert es, bis vom System zusammengestellte Akronyme angezeigt werden, nachdem Sie eine neue E-Mail oder ein neues Dokument erhalten oder gesendet haben?**

**A:** In einer neuen E-Mail oder einem neuen Dokument gefundene Akronyme dauern bis zu sieben Tage, bis sie in Microsoft Search Ergebnissen angezeigt werden.

**F: Was geschieht, wenn ein Akronym sowohl ausgeschlossen als auch veröffentlicht wird?**

**A:** Das ausgeschlossene Akronym erhält Priorität und verhindert, dass das veröffentlichte Akronym in Suchergebnissen angezeigt wird. Das veröffentlichte Akronym wird nicht gelöscht oder entfernt.

**F: Wie lange dauert es, bis ein Akronym von Microsoft Search Ergebnissen ausgeschlossen wird?**

**A:** Es dauert bis zu einem Tag, bis ein ausgeschlossenes Akronym nicht mehr in den Suchergebnissen angezeigt wird.

**F: Müssen Dokumente für vom System zusammengestellte Akronyme in einem bestimmten Format vorliegen?**

**A:** Nein. Wir unterstützen alle Dateitypen außer Bild-, Ordner- und ZIP-Dateien.

**F: Erkennt Microsoft Akronyme aus Dokumenten in allen Sprachen?**

**A:** Microsoft unterstützt nur vom System zusammengestellte Akronyme aus Dokumenten in Englisch, Spanisch, Französisch, Italienisch, Deutsch und Portugiesisch. Unterstützung für andere Sprachen wird in Phasen hinzugefügt.

**F: Was geschieht, wenn meine Organisation keine vom System zusammengestellten Akronyme anzeigen möchte? Kann ich diese Art von Akronym in meinen Suchergebnissen nicht mehr anzeigen?**

**A:** Um die Anzeige von vom System zusammengestellten Akronymen in Suchergebnissen zu deaktivieren, erstellen Sie ein Kundensupportticket, indem Sie die Anweisungen unter Kontaktieren des [Supports für Geschäftsprodukte](/microsoft-365/admin/contact-support-for-business-products)befolgen.
Nachdem Sie ein Supportticket erstellt haben, dauert es bis zu 48 Stunden, bis vom System zusammengestellte Akronyme in den Suchergebnissen nicht mehr angezeigt werden.
