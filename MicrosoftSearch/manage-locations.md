---
title: Orte verwalten
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 8ab9aa00-cd74-405f-8410-9a1c3cfacdb9
description: Im Laufe der Zeit müssen Sie Status und Inhalt eines Ortes möglicherweise aktualisieren, damit er relevant bleibt. 
ms.openlocfilehash: 0c93e29c8c899a4b70a30cf97354cf00fc19667f
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973668"
---
# <a name="manage-locations"></a>Orte verwalten

## <a name="location"></a>Standort

Der Standort hilft Ihren Benutzern, Adressen zu finden und die Gebäude Ihrer Organisation zu lokalisieren, indem ein genauer Standort für Büros, Campus und Gebäude sowie eine Wegbeschreibung und Navigation bereitgestellt werden. Administratoren sollten alle wichtigen Standorte Ihrer Organisation hinzufügen. Im Gegensatz zu Lesezeichen und Fragen und Antworten wird der Index nicht sofort aktualisiert, und es kann mehrere Stunden dauern, bis neue oder geänderte Standorte in den Suchergebnissen angezeigt werden.

### <a name="add-or-edit-a-single-location"></a>Hinzufügen oder Bearbeiten eines einzelnen Standorts

1. Wechseln [Sie](https://admin.microsoft.com)im Microsoft 365 Admin Center zu [**"Speicherorte".**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/locations)
1. Um einen neuen Speicherort hinzuzufügen, wählen Sie **Hinzufügen** aus.
1. Wählen Sie zum Bearbeiten eines Standorts den Standort in der entsprechenden Standortliste aus.
1. Während Sie die Informationen hinzufügen oder bearbeiten, wird die Vorschau automatisch aktualisiert.
1. Speichern Sie Ihre Änderungen.

### <a name="bulk-add-or-edit-locations"></a>Massenhinzufügen oder -bearbeiten von Standorten

Administratoren können die Import- oder Exportfunktion verwenden, um Standorte per Massenvorgang hinzuzufügen oder zu bearbeiten.

Verwenden Sie die Import-/Exportfunktion zum:

1. Massenhinzufügen von Standorten – Fügen Sie Details in der Vorlagendatei für Standorte hinzu, und importieren Sie sie dann.
1. Massenbearbeiten von Standorten – Exportieren Sie Standorte in eine CSV-Datei, bearbeiten Sie dann die Standortdetails in der exportierten CSV-Datei, und importieren Sie die aktualisierte CSV-Datei.
1. Sicherungsspeicherorte – Exportieren vorhandener Speicherorte in eine .csv Datei.

So exportieren oder importieren Sie Standorte:

1. Wählen Sie in der oberen rechten Ecke der Registerkarte **Standorte** **Importieren** aus.
Wählen Sie **Exportieren** aus, um die vorhandenen Standorte in eine CSV-Datei herunterzuladen.
1. Wählen Sie im rechten Bereich die Option zum Importieren mithilfe einer CSV-Datei.
Laden Sie die Vorlagendatei herunter, um eine Liste der erforderlichen Felder und Details zu erhalten.
1. Fügen Sie Standortdetails in der Vorlagendatei hinzu oder bearbeiten Sie sie, und speichern Sie sie dann auf Ihrem Computer.
1. Klicken Sie im Bereich **Standorte importieren** auf **Durchsuchen**, und wählen Sie dann die CSV-Datei aus, die Sie importieren möchten.
1. Wählen Sie **Importieren** aus.

Hier sind einige wichtige Punkte in Bezug auf die Vorlagendatei:

- Bearbeiten Sie niemals Daten in diesen Feldern: *ID*, *Zuletzt geändert* und *Zuletzt geändert von*.
- Wenn Sie die *ID* eines vorhandenen Speicherorts angeben, wird sie durch die Informationen in der Importdatei ersetzt.
- Wenn ein Speicherort mit demselben Namen vorhanden ist, wird der Speicherort mit Informationen in der Importdatei aktualisiert.
- Nicht alle Felder in der Vorlagendatei sind erforderlich, und erforderliche Felder variieren je nach Standortstatus.
- Basierend auf dem *Feld "Status"* werden Speicherorte als Entwurf gespeichert, vorgeschlagen, geplant oder automatisch veröffentlicht.
- Für Partner, die mehrere Organisationen verwalten, können Sie Ihre Standorte aus einer Organisation exportieren und in eine andere importieren. Sie müssen jedoch die Daten in der Spalte *ID* vor dem Import entfernen.

> [!NOTE]
> Speicherorte können nicht importiert werden, wenn fehler in der Vorlagendatei vorhanden sind. Um Fehler zu verhindern, stellen Sie sicher, dass die Importdatei ordnungsgemäß formatiert ist, und geben Sie alle erforderlichen Informationen an.

Weitere Informationen zum Vermeiden von Fehlern finden Sie unter [Vermeiden von Importfehlern](manage-bookmarks.md#prevent-import-errors).
