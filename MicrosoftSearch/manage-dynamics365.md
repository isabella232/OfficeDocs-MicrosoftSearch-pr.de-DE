---
title: Dynamics 365-Verbundsuche (Vorschau)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Verwalten der Darstellung von Dynamics 365-Inhalten in Suchergebnissen
ms.openlocfilehash: ff7b1d86716233910ba6c1ba3141fbe13beb5a98
ms.sourcegitcommit: e5d56d6ce1cd285c5af3e0472ce169cb34883017
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2021
ms.locfileid: "58470230"
---
# <a name="dynamics-365-federation-search-preview"></a>Dynamics 365-Verbundsuche (Vorschau)

## <a name="microsoft-search-federation-and-connectors"></a>Microsoft Search Partnerverbund und Connectors

Um Microsoft Search nützlicher zu machen, führen wir Microsoft Search-Partnerverbund ein. Mit der Sammelsuche können Organisationen Daten in diesen Szenarien in Microsoft Search zugänglich machen:

* Daten in Systemen, die strengen Complianceanforderungen unterliegen
* Daten, die keine Systemgrenzen überschreiten können
* Vertrauliche Daten, die lokal gespeichert werden und die Von Ihrer Organisation nicht in der Cloud indiziert werden sollen

Daten, auf die über eine Sammelsuche zugegriffen wird, werden nicht in Microsoft Search indiziert. Darüber hinaus ist es mithilfe integrierter Connectors von Microsoft einfach, Sammelsuchverbindungen einzurichten. Unser Dynamics 365-Connector befindet sich derzeit in der Vorschau. Wenn Sie an der Vorschau teilnehmen möchten, teilen Sie uns dies unter [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview)mit. Informationen zum Zeitrahmen für die Veröffentlichung finden Sie in der [Microsoft Search Roadmap.](https://www.microsoft.com/microsoft-365/roadmap?filters=Microsoft%20Search)

## <a name="dynamics-365-federation-connector"></a>Dynamics 365-Verbundconnector

Microsoft Dynamics 365 ist eine Reihe intelligenter Geschäftsanwendungen, die für die Planung von Unternehmensressourcen und die Verwaltung von Kundenbeziehungen entwickelt wurden. Mit dem Dynamics 365-Partnerverbund bietet Microsoft Search eine nahtlose Suchumgebung, sodass Benutzer auf einfache Weise die relevantesten Kunden- und Geschäftsdaten finden können, die in Dynamics 365 gespeichert sind. Der Dynamics 365-Verbundconnector bietet einige wichtige Vorteile:

* **Einfache Verwaltung:** Optimierter Prozess zum Konfigurieren und Verwalten der Suchverbindung mit einer Dynamics 365-Instanz.
* **Einfach zu verwenden:** Benutzer können wichtige Informationen, die in Dynamics 365 gespeichert sind, ganz einfach und schnell finden, einschließlich Konten, Kontakten, offenen Möglichkeiten und mehr.
* **Umfangreichere Inhalte:** Um dynamics 365-Suchergebnisse nützlicher zu machen, enthalten sie wichtige Informationen wie Leads, Kontakte und Kontodetails.
* **Integrierter Datenschutz:** Dynamics 365-Ergebnisse werden nur für Benutzer angezeigt, die Zugriff auf die verbundene Instanz haben.
* **Einheitliche Suchumgebung:** Um eine einheitliche Benutzererfahrung zu gewährleisten, sind die Dynamics 365-Ergebnisse über alle Sucheinstiegspunkte hinweg konsistent. Überall dort, wo Sie suchen, erhalten Sie dieselben Ergebnisse mit demselben Aussehen und Verhalten.

## <a name="what-users-experience"></a>Benutzerfreundlichkeit

Dynamics 365-Antworten werden in suchergebnissen in allen Microsoft Search Canvases angezeigt, einschließlich SharePoint Online, Bing und Office.

:::image type="content" alt-text="Screenshot der Dynamics 365-Antworten auf SharePoint, Bing und Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

Aus der Antwort ist es einfach, weitere Dynamics 365-Suchergebnisse mithilfe des Links **"Weitere Dynamics 365-Ergebnisse"** anzuzeigen. Sie führt Benutzer zu einer dedizierten Dynamics 365-Ergebnisseite mit weiteren Ergebnissen, die für ihre Abfrage relevant sind.

:::image type="content" alt-text="Screenshot der vertikalen Dynamics 365-Branche und Ergebnisse zu SharePoint, Bing und Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

Durch Klicken oder Tippen auf ein beliebiges Ergebnis wird Dynamics 365 geöffnet und die detaillierten Informationen angezeigt.

:::image type="content" alt-text="Screenshot der Detailseite in Dynamics 365." source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

Unabhängig davon, wo Ihre Benutzer mit der Suche beginnen, ist ihre Oberfläche konsistent und ermöglicht es ihnen, schnell die relevantesten Dynamics 365-Ergebnisse zu finden. Sehen Sie sich unser Microsoft Build 2021-Video für eine Demonstration an.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4P83t]

## <a name="supported-query-patterns"></a>Unterstützte Abfragemuster

Abfragen natürlicher Sprache und Produktnamen werden unterstützt, wenn sie Microsoft Search verwenden, um Dynamics 365-Ergebnisse zu finden. Außerdem wird bei Dynamics 365-Abfragen die Groß-/Kleinschreibung nicht beachtet. Verwenden Sie natürliche Sprachmuster, um Kontakt-, Konto- und Geschäftsmöglichkeiten nach Kundennamen oder Standort und anderen häufig verwendeten Abfragen zu suchen. Hier ein paar Beispiele:

* Wer ist der Kontakt für Contoso.
* Offene Möglichkeiten für Contoso
* Was sind offene Möglichkeiten in Seattle?
* Was sind die Konten in Seattle?
* Was sind die Kontakte in Seattle?
* Was sind meine Leads, die in diesem Monat geschlossen werden?
* Telefonanruf mit hoher Priorität
* Kontakt fehlende E-Mails

Produktnamenmuster unterstützen eine Reihe von Dynamics 365-Anwendungen und lösen Dynamics 365-Ergebnisse unabhängig davon aus, wo sie in einer Abfrage angezeigt werden:

* D365
* Dynamics 365
* Dynamics365
* Dynamics CRM
* Dynamics Sales
* Dynamics Customer Service
* Dynamics Service
* Dynamics Field Service

## <a name="configure-the-dynamics-365-connector"></a>Konfigurieren des Dynamics 365-Connectors

Mit dieser einfachen Konfiguration können Sie die Dynamics 365-Verbundsuche für Personen in Ihrer Organisation aktivieren.

1. Wechseln [Sie](https://admin.microsoft.com)im Microsoft 365 Admin Center zu [Datenquellen.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors)

2. Wählen Sie im Abschnitt "Microsoft-Apps und -Dienste" unter Microsoft Dynamics 365 die Option **"Verwalten"** aus, um den Bereich Microsoft Dynamics 365 zu öffnen.

3. Aktivieren Sie den Connector für Ihre Organisation.

4. Wählen Sie in der **Liste "Endpunkte"** Ihre Dynamics 365-Umgebung aus.

5. Geben Sie in der **Verbindungs-ID** eine eindeutige ID für diese Verbindung ein.

6. Überprüfen Sie das Kontrollkästchen "Zustimmung", und aktivieren Sie es.

7. Wählen Sie **"Speichern"** aus, um die Verbindungseinrichtung abzuschließen.

:::image type="content" alt-text="Screenshot des Dynamics 365-Einrichtungsbereichs im Microsoft 365 Admin Center." source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

Wenn die Einrichtung abgeschlossen ist, werden Dynamics 365-Antworten und -Vertikalen nur für Benutzer mit einer gültigen Dynamics 365-Lizenz und Zugriff auf die verbundene Dynamics 365-Umgebung angezeigt. Sie können jederzeit zu diesen Einstellungen zurückkehren und die Verbindungsendpunktumgebung ändern oder die Verbindung deaktivieren.
