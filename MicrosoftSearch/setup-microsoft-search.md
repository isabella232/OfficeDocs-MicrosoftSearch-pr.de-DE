---
title: Einrichten von Microsoft Search
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 08/06/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Erstmaliges Einrichten von Microsoft Search.
ms.openlocfilehash: 3b3df3e3b3cb3e94abdf57bbb2c7e2db5f174898
ms.sourcegitcommit: 3da22a2e09830672ebf199e05a32fa89b75c083b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288991"
---
# <a name="set-up-microsoft-search"></a>Einrichten von Microsoft Search

Microsoft Search bietet eine benutzerfreundliche Oberfläche, die Benutzern das Auffinden von Informationen erleichtert (z. B. Dateien und Dokumente, interne Websites und Unternehmenstools, Personen und Gruppen, Orte und Wegbeschreibungen, Gespräche und Antworten), indem sie in der Organisation des Benutzers sicher auf alle Datenquellen, einschließlich E-Mails, Dateien, SharePoint-Dateien, OneDrive-Inhalte und andere gemeinsam genutzte Ressourcen sowie auf das Internet zugreift.

Weitere Informationen zu den Microsoft Search-Features finden Sie unter [Übersicht über Microsoft Search](overview-microsoft-search.md).

## <a name="get-started"></a>Erste Schritte

Microsoft Search ist im Rahmen von Microsoft 365 standardmäßig für alle Microsoft-Apps aktiviert, die das Feature unterstützen. Ein Benutzer braucht sich lediglich mit seinem Geschäfts-, Schul- oder Unikonto anzumelden und einen Browser mit Bing als Standardsuchanbieter zu verwenden.

Sie können Microsoft Search vom Microsoft 365 Admin Center aus verwalten.

1. Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Microsoft Search**.

**Bitte beachten:** Wenn Microsoft Search unter **Einstellungen** NICHT angezeigt wird, aktivieren Sie den Schalter für **Preview testen** (Try the preview) in der rechten oberen Ecke einer beliebigen Admin Center-Seite.

Als Administrator sollten Sie einige Dinge berücksichtigen, durch die Sie die Microsoft Search-Nutzererfahrung in Ihrer Organisation effizient und benutzerfreundlich gestalten können.

## <a name="step-1-check-access-level-of-your-users"></a>Schritt 1: Zugriffsebene Ihrer Benutzer überprüfen

Microsoft Search respektiert die Sicherheitseinstellungen der Inhaltsquelle. Welche Suchergebnisse Benutzern angezeigt werden, hängt von ihren Berechtigungen und Zugriffsebenen ab. Überprüfen Sie die Zugriffsebenen der Benutzer in Ihrer Organisation, um sicherzustellen, dass Benutzer nur Inhalte finden, auf die sie zugreifen dürfen.

| Dienst         | Beschreibung                                                                                                                                                                                                                                         |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Gruppen          | [Hinzufügen oder Entfernen von Mitgliedern aus Gruppen](https://docs.microsoft.com/office365/admin/create-groups/add-or-remove-members-from-groups)                                                                                                                     |
| Kontakte          | Sie können festlegen, dass bestimmte Benutzer in Ihrer Adressliste nicht durchsucht werden, indem Sie den Parameter `HiddenFromAddressListEnabled` unter Verwendung des Cmdlets [Set-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-user) auf `true` festlegen. |
| Microsoft Teams | [Verwalten des Benutzerzugriffs auf Microsoft Teams](https://docs.microsoft.com/microsoftteams/user-access)                                                                                                                                                      |
| OneDrive        | [Verwalten der Freigabe](https://docs.microsoft.com/OneDrive/manage-sharing)                                                                                                                                                                                |
| SharePoint      | [Planung von Berechtigungen](https://docs.microsoft.com/sharepoint/plan-your-permissions-strategy)<br> [Erstellen von Berechtigungsstufen](https://docs.microsoft.com/sharepoint/how-to-create-and-edit-permission-levels)                          |
| OneNote         | In OneNote eingebettete Dateien können nicht durchsucht werden. [Ändern der Berechtigungen für ein Notizbuch auf OneDrive](https://support.office.com/article/B9600CCF-045A-40E6-9913-4A7EB02869A5)                                                                    |
| Yammer          | [Yammer-Sicherheitseinstellungen](https://docs.microsoft.com/Yammer/manage-security-and-compliance/yammer-security-settings)                                                                                                                               |

## <a name="step-2-assign-search-admin-and-search-editor"></a>Schritt 2: Suchadministratoren und Such-Editoren ernennen

In Microsoft Search können Sie die Sucheinstellungen und Inhalte Ihrer Organisation mitverwalten, indem Sie den Benutzern diese Rollen zuweisen:

1. **Suchadministrator**: Diese Rolle kann Suchergebnisinhalte erstellen und verwalten sowie Abfrageeinstellungen für verbesserte Suchergebnisse innerhalb der Organisation definieren. Der Suchadministrator verwaltet die Microsoft Search-Konfiguration und kann alle Inhaltsverwaltungsaufgaben ausführen, die ein Such-Editor durchführen darf.
2. **Such-Editor:** Erstellt, verwaltet und löscht Inhalte für Microsoft Search im Microsoft 365 Admin Center. Diese Rolle kann redaktionelle Inhalte wie häufig gestellte Fragen und Antworten, wichtige Orte, häufig gesuchte und genutzte Websites und Apps erstellen und verwalten.

Aktuell müssen die Rollen „Suchadministrator“ und „Such-Editor“ von einem globalen Administrator zugewiesen werden. Weitere Informationen finden Sie unter [Administrator-Rollen zuweisen](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide) (Assign admin roles).

Microsoft Search-Administratoren können die Suchoberfläche für Endbenutzer direkt beeinflussen. Dazu gehört die Auswahl der Ergebnistypen, die Sie Ihren Benutzern zur Verfügung stellen möchten. Es kann für eine Person schwierig sein, maßgebliche Inhalte zu vielen verschiedenen Themen, nach denen Benutzer in einer Organisation suchen, auszuwählen und zu erstellen. Es wird empfohlen, dass Sie die Expertise und das Wissen von Experten (SMEs) und anderen Benutzern nutzen, indem Sie sie als Such-Editoren hinzufügen.

## <a name="step-3-make-content-easy-to-find"></a>Schritt 3: Inhalte leicht auffindbar machen

Microsoft Search stellt Administratoren Tools zur Verfügung, mit denen sie eine robuste Suchoberfläche für ihre Benutzer erstellen können. In Microsoft Search können Administratoren drei verschiedene Suchinhalte erstellen, um die Sucherfahrung und Auffindbarkeit von Inhalten zu verbessern:

- **Lesezeichen:** Lesezeichen ähneln den höhergestuften Ergebnis in SharePoint und tragen dazu bei, die bestmöglichen Ergebnisse für die Anfragen Ihrer Benutzer an die Spitze der Suchergebnisse zu setzen und es Ihren Benutzern so leicht zu machen, wichtige interne Websites zu finden.
- **Fragen und Antworten:** Das Feature "Fragen und Antworten" ähnelt den häufig gestellten Fragen (FAQs) und liegen in der Regel in einem Frage- und Antwortformat vor. Hier werden die bestmöglichen Antworten auf die arbeitsbezogenen Fragen Ihrer Benutzer bereitgestellt.
- **Standorte:** Standorte sind Adressen, mit denen Benutzer Gebäude, Büros und Campusbereiche Ihrer Organisation leichter finden.

Je mehr Lesezeichen, Fragen und Antworten und Standorte Sie verwenden, desto mehr Wert und Nutzen bieten Sie den Benutzern. Zu viele dieser Elemente können jedoch einen erheblichen Verwaltungsaufwand verursachen, da sie regelmäßig überprüft und aktualisiert werden müssen, damit die Ergebnisse relevant und aktuell bleiben.

Hier sind einige Beispiele für Inhalte, für die Sie die Verwendung von Lesezeichen für Ihre Benutzer in Betracht ziehen sollten:

- Organisations-, Produkt- oder Dienstinformationen.
- Informative Inhalte, die für jedermann verfügbar sind, z. B. Informationen über das Unternehmen, Hilfe zu Windows- und Office-Apps, etc.
- Inhalte, nach denen Personen in der Organisation im Allgemeinen bei ihrer täglichen Arbeit suchen. Allgemeine arbeitsbezogene Suchen sind z. B. Mitarbeitervergütungen, Arbeitszeit- und Spesenabrechnung, Übermittlung von Bestellungen und Hilfe von IT-Diensten.

Informationen zum Erstellen und Verwalten von Suchinhalten finden Sie unter [Inhalte leicht auffindbar machen](make-content-easy-to-find.md).

## <a name="step-4-training-and-communication"></a>Schritt 4: Schulung und Kommunikation

Erstellen Sie Self-Service-Ressourcen, auf die Mitarbeiter selbst leicht zugreifen können. Dies hilft, die Gesamtbelastung für Sie und Ihr Team zu reduzieren, die Kommunikation ständig voranzutreiben und Mitarbeiter bei Selbststudium und -weiterbildung zu unterstützen. Bieten Sie Ihren Benutzern Kommunikation, FAQs, Videos und aufgezeichnete Schulungen oder Webinare an. Hier finden Sie einige hilfreiche Links für den Einstieg:

- [Finden erforderlicher Informationen in Office mit Microsoft Search](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446)
- [Office 365-Schulungscenter](https://support.office.com/office-training-center)
- [Microsoft Search Center](https://support.office.com/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc)