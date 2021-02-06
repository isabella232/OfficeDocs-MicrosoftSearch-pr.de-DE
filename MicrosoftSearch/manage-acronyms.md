---
title: Verwalten von Antworten auf Akronyme in Microsoft Search
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
description: Erstellen und Aktualisieren von Antworten auf Akronyme in Microsoft Search
ms.openlocfilehash: 45d3cc7b33f27d2f4e77d8099fbfa91e01aabcbb
ms.sourcegitcommit: ef94ffd6111acb929c8343f0f4f82ea109b68fb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122156"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Verwalten von Antworten auf Akronyme in Microsoft Search

Benutzer erhalten häufig unbekannte Akronyme und Abkürzungen, die von ihrer Organisation oder ihrem Team verwendet werden. Spezifisch für Organisationen oder Teams sind möglicherweise neue Begriffe für Personen, die von einem Team in ein anderes wechseln, mit internen Partnerteams zusammenarbeiten oder neu in der Organisation sind.

Organisationen verfügen nicht immer über einen einzigen Verweis für ihre Standardterminologie. Das Fehlen eines einzigen Verweises macht es schwierig, Definitionen oder Erweiterungen für diese Akronyme zu finden. Microsoft Search löst dieses Problem mit Akronymen.

## <a name="what-users-experience"></a>Benutzererfahrung

Microsoft Search-Benutzer können Definitionen mit Akronymen in [Bing,](https://Bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)und [Office 365 erhalten.](https://Office.com) Im **Suchfeld** geben Benutzer Abfragen wie die folgenden Beispiele ein:

- *Was ist* DNN
- *Definieren* DNN
- DNN-Definition 
- *Erweitern* DNN
- DNN-Erweiterung 
- *Bedeutung von* DNN
- DNN *bedeutet*

Das Ergebnis enthält alle Bedeutungen von DNN, die innerhalb der Organisation des Benutzers vorhanden sind.

> [!NOTE]
> Benutzer müssen eine Abfrage eingeben, die die angegebenen Schlüsselwörter des Akronyms enthält, um *die* entsprechenden Antworten auszulösen. Bei Akronymabfragen wird die Kleinschreibung nicht beachtet.

## <a name="set-up-acronyms-answers"></a>Einrichten von Akronymantworten

Wechseln Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com)zu [**Akronyme,**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)und wählen Sie dann **"Akronym hinzufügen" aus.**

Microsoft Search fragt zwei Datenquellen ab, um Akronyme antworten auf Benutzersuchen zu liefern:

1. **Admin-curated**. Bereitgestellt von IT-Administratoren im [Admin Center.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)
2. **Systemverkn tzt**. Von Microsoft Search aus E-Mails und Dokumenten von Benutzern und öffentlich verfügbaren Daten innerhalb der Organisation ermittelt.

### <a name="set-up-admin-curated-acronyms"></a>Einrichten von vom Administrator verwalteten Akronymen

Suchadministratoren können Akronyme auf der Registerkarte ["Akronyme"](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) im [Microsoft Search Admin Center hinzufügen.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) Sie können Akronyme von jeder internen Website oder jedem Repository zum Admin Center hinzufügen. Diese Akronyme können dem Status **"Veröffentlicht"** oder **"Entwurf" hinzugefügt** werden:

**Veröffentlichter Status**. Akronyme stehen den Benutzern der Organisation über Microsoft Search zur Verfügung.

> [!NOTE]
> Es kann bis zu drei Tage dauern, bis Akronyme, die zum Status "Veröffentlicht" hinzugefügt wurden, in Microsoft Search verfügbar werden.

**Entwurfsstatus**. Wenn Sie ein Akronym überprüfen möchten, bevor Sie es in Microsoft Search zur Verfügung stellen, können Sie das Akronym im Entwurfszustand hinzufügen. Akronyme im Entwurfsstatus werden in den Suchergebnissen nicht angezeigt. Sie müssen das Akronym in den Status "Veröffentlicht" verschieben, damit es in den Suchergebnissen angezeigt wird.

Sie können Akronyme einzeln oder massenimportieren sie in eine CSV-Datei hinzufügen. Laden Sie eine CSV-Datei mit den in der folgenden Tabelle aufgeführten Feldern hoch:

| Akronym (verpflichtend) | Erweiterung (verpflichtend) | Url | Beschreibung  | Status (verpflichtend) | Zuletzt geändert | Zuletzt geändert von | Id |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *Kurzschreibkürzung* | *Source* |  | *Veröffentlicht oder Entwurf* |  |  |  |

### <a name="csv-fields"></a>CSV-Felder

**Akronym**. Enthält die tatsächliche Kurzform oder das Akronym. Ein Beispiel ist *DNN*.

**Erweiterung**. Enthält die Erweiterung des Akronyms. Ein Beispiel ist *"Deep Neural Network".*

**Beschreibung**. Eine kurze Beschreibung des Akronyms, mit dem Benutzer weitere Informationen über das Akronym und dessen Erweiterung erhalten. Ein tiefes neurales Netzwerk ist beispielsweise ein neurales Netzwerk mit einer bestimmten *Komplexitätsstufe,* ein neurales Netzwerk mit mehr als zwei Ebenen.

**Quelle**. Die URL der Seite oder Website, auf der Benutzer weitere Informationen zum Akronym erhalten möchten.

**Status**. Dieses Feld kann zwei Werte enthalten:

- **Entwurf**. Fügt das Akronym dem Entwurfsstatus hinzu.
- **Veröffentlicht** Fügt das Akronym dem Status "Veröffentlicht" hinzu und stellt es in Microsoft Search zur Verfügung.

### <a name="system-curated-acronyms"></a>Vom System behandelte Akronyme

Es kann eine Herausforderung für Administratoren sein, alle in einer Organisation verwendeten Akronyme zu Antworten hinzuzufügen. Dieses Feature kann Akronyme finden, die Suchadministratoren nicht einmal kennen. Hierzu ermittelt und kuratiert Microsoft Search auch Akronyme aus diesen Quellen:

- E-Mails von Benutzern
- Dokumente in [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)und [Microsoft OneNote](https://www.onenote.com/)
- Öffentliche Dokumente innerhalb der Organisation, auf die Benutzer in SharePoint, OneDrive oder OneNote Zugriff haben

Microsoft Search stellt sicher, dass nur Benutzer mit Zugriff und Berechtigungen für ein Dokument die Akronyme sehen können, die von diesem erkannt werden. Wenn ein Akronym im Postfach eines Benutzers gefunden wird, kann nur dieser Benutzer dieses Akronym sehen.

> [!NOTE]
> Für vom Administrator verwaltete Akronyme ist kein Setup erforderlich.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**F: Wie werden vom Administrator verwaltete und vom System behandelte Daten bewertet?**

**A:** Die Rangfolge der Ergebnisse kann von Person zu Person variieren, da die Ergebnisse für jeden Benutzer personalisiert werden. Keine dieser Kategorien hat immer Vorrang vor der anderen.

**F: Wie lange dauert es, bis vom Administrator verwaltete Akronyme in Microsoft Search sichtbar sind, nachdem sie veröffentlicht wurden?**

**A:**  Es dauert bis zu drei Tage, bis Akronyme, die zum Status "Veröffentlicht" hinzugefügt wurden, in Microsoft Search verfügbar werden.

**F: Wie lösen Benutzer Antworten auf Akronyme aus?**

**A:** Um Antworten auf Akronyme zu erhalten, müssen Benutzer bestimmte Abfragemuster in ein [Bing-,](https://bing.com) [SharePoint-](https://products.office.com/sharepoint/collaboration)oder [Office 365-Suchfeld](https://Office.com)  eingeben.

**F: Wie lange dauert es, bis vom System behandelte Akronyme angezeigt werden, nachdem Sie eine neue E-Mail oder ein neues Dokument erhalten oder gesendet haben?**

**A:** Es dauert bis zu sieben Tage, bis Akronyme in einer neuen E-Mail oder einem neuen Dokument in den Microsoft Search-Ergebnissen angezeigt werden.

**F: Müssen Dokumente in einem bestimmten Format für das Mining vorliegen, um sie wieder auf ihre Bedürfnisse zu nehmen?**

**A:** Nein. Wir unterstützen alle Dateitypen mit Ausnahme von Bild-, Ordner- und ZIP-Dateien.

**F: Wird Microsoft Akronyme aus Dokumenten in allen Sprachen entdecken?**

**A:** Microsoft unterstützt nur das Mining aus Dokumenten in Englisch. Unterstützung für andere Sprachen wird in Phasen hinzugefügt.

**F: Was passiert, wenn meine Organisation keine systemverkn tzten Akronyme anzeigen möchte? Kann ich die Anzeige dieses Akronymtyps in meinen Suchergebnissen beenden?**

**A:** Um die Anzeige systemverkn tzter Akronyme in suchergebnissen zu deaktivieren, erstellen Sie ein Kundensupportticket, indem Sie die Anweisungen unter "Kontaktieren des Support für [Geschäftsprodukte" befolgen.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
Nachdem Sie ein Supportticket erstellt haben, dauert es bis zu 48 Stunden, bis vom System behandelte Akronyme nicht mehr in den Suchergebnissen angezeigt werden.
