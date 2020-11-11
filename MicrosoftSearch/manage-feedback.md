---
title: Verwalten von Benutzer Feedback
ms.author: lebhansa
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
ROBOTS: NoIndex
description: Überprüfen und Bearbeiten von Benutzer Feedback in der Microsoft-Suche
ms.openlocfilehash: fd47403fd86be2e2fb1ba7baee7473958a8e5572
ms.sourcegitcommit: 4b2cc0a4cd3d7cdcd8eb23a8baa9703173889a73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48986958"
---
# <a name="managing-user-feedback"></a>Verwalten von Benutzer Feedback

Das Erstellen einer großen Suchumgebung für Ihre Benutzer ist eine Partnerschaft zwischen Microsoft und dem Suchadministrator. Feedback von Ihren Benutzern ermöglicht es uns, das Produkt kontinuierlich auszuwerten und für eine optimale Benutzerfreundlichkeit zu optimieren. Einige Rückmeldungen werden jedoch am besten von Ihnen behandelt.

Wir bieten jetzt Tools, mit denen Sie das Feedback, das Ihre Benutzer in der Suchumgebung bereitstellen, überprüfen und verwalten können.

## <a name="how-users-submit-feedback"></a>Übermitteln von Feedback durch Benutzer

Wenn Personen in Ihrer Organisation die Microsoft-Suche verwenden, haben Sie möglicherweise Feedback zur Erfahrung. Wenn Sie auf der Ergebnisseite auf einen Feedback Link klicken, können Sie Ihr Feedback kategorisieren und zusätzliche Kommentare hinzufügen.

![Globales Feedback Formular](media/feedback/feedback-global-dialog.png)

Benutzer haben außerdem die Möglichkeit, Ihre Abfrage und andere Diagnoseinformationen zusammen mit der Kategorie und den Kommentaren an Microsoft zu senden. Die Diagnoseinformationen umfassen einige personenbezogene Daten wie eine Benutzer-ID. [Erfahren Sie mehr](https://privacy.microsoft.com/en-US/privacystatement) über Datenschutz und wie wir diese Daten schützen. Die Diagnosedaten enthalten die wichtigsten Informationen, die Microsoft für die Verwendung des Feedback Elements für die Produktverbesserung benötigt.

Die meisten Feedback-Übermittlungen werden im Abschnitt [Feedback](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) des Microsoft Search Admin Center angezeigt. Das Feedback, das mit der Kategorie **Ich möchte vorschlagen, dass eine interne Link** Kategorie als vorgeschlagenes Lesezeichen im Abschnitt [Lesezeichen](https://admin-ignite.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) angezeigt wird, wird durch Filtern nach dem **vorgeschlagenen** Status angezeigt.

## <a name="review-feedback"></a>Feedback überprüfen

Auf der Seite [Feedback](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) können Sie Feedback überprüfen und exportieren, das Personen in Ihrer Organisation in den letzten 30 Tagen gesendet haben. Sobald ein Benutzer Feedback übermittelt hat, wird er in dieser Liste innerhalb von 20 Minuten angezeigt. Sie können die Schaltfläche Aktualisieren verwenden, um sicherzustellen, dass Sie sich die aktuellsten Daten ansehen.

Mithilfe eines Filters können Sie Feedback zu bestimmten Antworttypen anzeigen. Sie können auch nach Quelle und Datumsbereich filtern.

Sie können das Suchfeld oberhalb der Feedback Liste verwenden, um nach Feedback zu einer bestimmten Abfrage zu suchen.

In der Feedback Liste gibt die Spalte Verbatim an, welches Feedback des Benutzers auch einen Kommentar oder eine Anregung enthält. Klicken Sie zum Lesen auf die Abfrage, um den **Detail** Bereich zu öffnen.

## <a name="update-feedback-state"></a>Aktualisieren des Feedback Status

Wenn das Feedback eingeht, befindet es sich in einem *neuen* Status und bleibt dort, bis Sie es in *aufgelöst* oder *Duplizieren* geändert haben.

So ändern Sie diesen Status:

1. Wählen Sie neben der Abfrage **Weitere Optionen** (drei vertikale Punkte) aus.
1. Wählen Sie im Menü die Option **als aufgelöst markieren** oder **als Duplikat markieren aus.**
1. Die Liste wird aktualisiert und zeigt den aktualisierten Zustand an.

Sie können den Status auch für mehrere Elemente aktualisieren, wählen Sie ihn aus, und wählen Sie dann weitere Optionen im nächsten Element aus.

## <a name="export-feedback"></a>Feedback exportieren

Wenn Sie Such Feedback für andere freigeben oder länger als 30 Tage beibehalten möchten, klicken Sie auf **exportieren.** Eine CSV-Datei mit dem Namen Feedbacks mit dem Datum, wie "Feedbacks_10_31_2020.csv", wird automatisch heruntergeladen.

## <a name="send-user-feedback-to-microsoft"></a>Senden von Benutzer Feedback an Microsoft

Standardmäßig wird das Feedback aller Benutzer an Microsoft übermittelt und Ihnen hinzugefügt. Um das Senden von Feedback an Microsoft zu beenden, klicken Sie auf **Einstellungen verwalten** , und deaktivieren Sie das Kontrollkästchen **Benutzer Feedback automatisch an Microsoft senden** . Es kann bis zu 24 Stunden dauern, bis diese Änderung wirksam wird.

Wenn Sie sich entschieden haben, kein Feedback an Microsoft automatisch zu senden, können Sie dennoch einzelne Feedback Teile an Microsoft senden.

1. Wählen Sie das Feedback aus, das Sie freigeben möchten.
1. Wählen Sie in der Aktionsleiste mehr (drei Punkte) aus, und klicken Sie auf **Feedback an Microsoft senden**.

1. Der Status in der Spalte "an Microsoft gesendet" wird in "Ausstehend" geändert. Wenn das Feedback gesendet wird, wird es in Ja geändert.

Wenn Sie Feedback automatisch oder manuell freigeben, enthält es nie Abfragen und andere Diagnoseinformationen für Benutzer, die sich entschieden haben, diese Informationen nicht einzubeziehen.

## <a name="suggestions-on-how-to-use-feedback"></a>Vorschläge zur Verwendung von Feedback

Als Suchadministrator sollten Sie die wichtigsten Personen in Ihrer Organisation und die Arten von Inhalten verstehen, mit denen diese Personen in der Regel interagieren und suchen. Anhand dieses Verständnisses können Sie mithilfe von Feedback gezielte Verbesserungen an der Suchumgebung Ihrer Benutzer vornehmen.

1. "Ich habe das gesuchte nicht gefunden" und ähnliches Feedback kann verwendet werden, um die Inhalte zu identifizieren, die Benutzer wünschen, aber derzeit nicht im Suchindex enthalten sind. Das bestimmen dieser Faktoren erfordert häufig Untersuchungen und Rückschlüsse basierend auf dem Verständnis Ihrer Benutzer. Nachdem Sie gefunden haben, entscheiden Sie, welche Methoden zum einschließen dieser Inhalte am besten geeignet wären:
    1. Lesezeichen sind für Inhaltsquellen mit einer qualitativ hochwertigen Zielseite und einer begrenzten Anzahl von Suchbegriffen hilfreich, damit die Benutzercommunity ein qualitativ hochwertiges Ergebnis aus dem Lesezeichen erhält und dann effizient finden kann, wonach Sie suchen.
    1. Q&A sind hilfreich für einzelne Antworten, die relativ häufig sind, sich jedoch nicht ändern.
    1. Connectors sind nützlich für Inhaltsquellen mit einer Vielzahl von Inhalten und einer Vielzahl von Suchbegriffen.
1. "Das Ergebnis dauerte zu lange, um zu laden" & "Ich habe ein Problem gefunden" kann Indikatoren für ein breiteres Problem sein. Die tägliche Suche nach diesem Feedback kann helfen, und wenn mehrere Fälle angezeigt werden, können Sie die Suchumgebung für sich selbst überprüfen und bei Bedarf einen Supportfall bei Microsoft öffnen. Diese Art von Feedback ist auch für Microsoft wichtig und ist ein hervorragender Grund für die Übermittlung aller Feedbacks an uns.
1. "Ich möchte einen internen Link vorschlagen" kann ausgewertet werden, um als Lesezeichen oder verbundene Inhalte hinzugefügt zu werden. Ihr erster Gedanke sollte ein Lesezeichen sein; Wenn die Textmarke sehr viel verwendet wird, können Sie erwägen, Inhalte über einen Connector zu übertragen, um eine noch umfassendere Suchumgebung zu ermöglichen.
