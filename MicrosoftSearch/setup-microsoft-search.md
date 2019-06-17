---
title: Einrichten von **Microsoft Search**
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Erstmaliges Einrichten von Microsoft Search.
ms.openlocfilehash: c95cc0d11d60e3d4d9a509dc691c01858ede7262
ms.sourcegitcommit: 9df9b1a5f83c9fbe62900df183bee239a8ea6d91
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "34947743"
---
# <a name="set-up-microsoft-search"></a>Einrichten von Microsoft Search

**Microsoft Search** bietet eine benutzerfreundliche Oberfläche, die Benutzern das Auffinden von Informationen erleichtert (z. B. Dateien und Dokumente, interne Websites und Unternehmenstools, Personen und Gruppen, Orte und Wegbeschreibungen, Gespräche und Antworten), indem sie in der Organisation des Benutzers sicher auf alle Datenquellen, einschließlich E-Mails, Dateien, SharePoint-Dateien, OneDrive-Inhalte und andere gemeinsam genutzte Ressourcen sowie auf das Internet zugreift.

Weitere Informationen zu den **Microsoft Search**-Features finden Sie unter [Übersicht über Microsoft Search](overview-microsoft-search.md).

## <a name="get-started"></a>Erste Schritte

**Microsoft Search** ist im Rahmen von Microsoft 365 standardmäßig für alle Microsoft-Apps aktiviert, die das Feature unterstützen. Ein Benutzer braucht sich lediglich mit seinem Geschäfts-, Schul- oder Unikonto anzumelden und einen Browser mit Bing als Standardsuchanbieter zu verwenden.

Sie können **Microsoft Search** vom **Microsoft 365 Admin Center** aus verwalten. Melden Sie sich mit Administratoranmeldeinformationen an, und wählen Sie **Administrator** aus der Liste der Office 365-Apps aus (klicken Sie auf das **App-Startfeld** in der oberen linken Ecke, um die Liste der Apps anzuzeigen). Wählen Sie im **Microsoft 365 Admin Center** im linken Navigationsbereich unter **Einstellungen** die Option **Microsoft Search** aus. 

**Hinweis:** Wenn **Microsoft Search** unter **Einstellungen** im **Microsoft 365 Admin Center** NICHT angezeigt wird, aktivieren Sie den Schalter **Vorschau ausprobieren** in der rechten oberen Ecke des Admin Centers. 

Als Administrator sollten Sie einige Dinge berücksichtigen, durch die Sie die **Microsoft Search**-Benutzeroberfläche in Ihrer Organisation effizient und benutzerfreundlich gestalten können.

## <a name="step-1-check-access-level-of-your-users"></a>Schritt 1: Zugriffsebene der Benutzer überprüfen

**Microsoft Search** respektiert die Sicherheitseinstellungen der Inhaltsquelle. Welche Suchergebnisse Benutzern angezeigt werden, hängt von ihren Berechtigungen und Zugriffsebenen ab. Überprüfen Sie die Zugriffsebenen der Benutzer in Ihrer Organisation, um sicherzustellen, dass Benutzer nur Inhalte finden, auf die sie zugreifen dürfen.

Erfahren Sie mehr über das [Planen von Berechtigungen](https://docs.microsoft.com/de-DE/sharepoint/plan-your-permissions-strategy) und das [Erstellen von Berechtigungsstufen](https://docs.microsoft.com/de-DE/sharepoint/how-to-create-and-edit-permission-levels).

## <a name="step-2-assign-search-admin-and-search-editor"></a>Schritt 2: Administratoren und Editoren für Microsoft Search ernennen

Es gibt zwei neue Rollen im **Microsoft Admin Center** – Suchadministrator und Such-Editor.  Der globale Administrator, der über vollständige Berechtigungen verfügt, weist Benutzern Administratorrollen zu, wie z. B. die Rolle des Suchadministrators. Suchadministratoren können die Rollen Suchadministrator oder Such-Editor an andere Benutzer delegieren. Weitere Informationen zu anderen Administratorrollen finden Sie unter [Informationen zu Office 365-Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide).

**Hinweis:** Die beiden neuen Rollen – Suchadministrator und Such-Editor – sind nur im **Microsoft 365 Admin Center**, nicht im alten Verwaltungsportal verfügbar. 

Microsoft Search-Administratoren können die Suchoberfläche für Endbenutzer direkt beeinflussen. Dazu gehört die Auswahl der Ergebnistypen, die Sie Ihren Benutzern zur Verfügung stellen möchten. Es kann für eine Person schwierig sein, maßgebliche Inhalte zu vielen verschiedenen Themen, nach denen Benutzer in einer Organisation suchen, auszuwählen und zu erstellen. Es wird empfohlen, dass Sie die Expertise und das Wissen von SMEs und anderen Benutzern nutzen, indem Sie sie als Editoren hinzufügen. 

In **Microsoft Search** können Sie die Sucheinstellungen und Inhalte Ihrer Organisation mit zwei neuen Rollen verwalten:
1. **Suchadministrator**: Diese Rolle kann Suchergebnisinhalte erstellen und verwalten sowie Abfrageeinstellungen für verbesserte Suchergebnisse innerhalb der Organisation definieren. Ein Suchadministrator verwaltet die Konfiguration von **Microsoft Search** und benennt Such-Editoren, die Inhalte erstellen.
2. **Such-Editor**: Erstellt, verwaltet und löscht Inhalte für **Microsoft Search** im Microsoft 365 Admin Center. Diese Rolle kann redaktionelle Inhalte wie häufig gestellte Fragen und Antworten, wichtige Orte, häufig gesuchte und genutzte Websites und Apps usw. erstellen und verwalten. Die Editoren haben jedoch keinen Zugriff auf die Verwaltung der Sucheinstellungen.

Informationen zum Zuweisen von Administratorrollen finden Sie unter [Zuweisen von Administratorrechten in Office 365 Business](https://docs.microsoft.com/de-DE/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).

## <a name="step-3-make-content-easy-to-find"></a>Schritt 3: Inhalte leicht auffindbar machen 

**Microsoft Search** stellt Administratoren Tools zur Verfügung, mit denen sie eine robuste Suchoberfläche für ihre Benutzer erstellen können. In **Microsoft Search** können Administratoren drei verschiedene Suchinhalte erstellen, um die Sucherfahrung und Auffindbarkeit von Inhalten zu verbessern:
- **Lesezeichen:** Lesezeichen ähneln den höhergestuften Ergebnis in SharePoint und tragen dazu bei, die bestmöglichen Ergebnisse für die Anfragen Ihrer Benutzer an die Spitze der Suchergebnisse zu setzen und es Ihren Benutzern so leicht zu machen, wichtige interne Websites zu finden. 
- **Fragen und Antworten:** Das Feature "Fragen und Antworten" ähnelt den häufig gestellten Fragen (FAQs) und liegen in der Regel in einem Frage- und Antwortformat vor. Hier werden die bestmöglichen Antworten auf die arbeitsbezogenen Fragen Ihrer Benutzer bereitgestellt.
- **Standort:** Standorte sind Adressen, mit denen Benutzer Gebäude, Büros, Campus Ihrer Organisation leichter finden. 

Je mehr Lesezeichen, Fragen und Antworten und Standorte Sie verwenden, desto mehr Wert und Nutzen bieten Sie den Benutzern. Zu viele dieser Elemente können jedoch einen erheblichen Verwaltungsaufwand verursachen, da sie regelmäßig überprüft und aktualisiert werden müssen, damit die Ergebnisse relevant und aktuell bleiben.

Hier sind einige Beispiele für Inhalte, für die Sie die Verwendung von Lesezeichen für Ihre Benutzer in Betracht ziehen sollten:
- Organisations-, Produkt- oder Dienstinformationen.
- Informative Inhalte, die für jedermann verfügbar sind, z. B. Informationen über das Unternehmen, Hilfe zu Windows- und Office-Apps, etc. 
- Inhalte, nach denen Personen in der Organisation im Allgemeinen bei ihrer täglichen Arbeit suchen. Allgemeine arbeitsbezogene Suchen sind z. B. Mitarbeitervergütungen, Arbeitszeit- und Spesenabrechnung, Übermittlung von Bestellungen und Hilfe von IT-Diensten. 

Informationen zum Erstellen und Verwalten von Suchinhalten finden Sie unter [Inhalte leicht auffindbar machen](make-content-easy-to-find.md).

## <a name="step-4-test-single-sign-on"></a>Schritt 4: Einmaliges Anmelden testen
**Microsoft Search** verwendet Azure Active Directory (AAD) zur Authentifizierung und Autorisierung des Zugriffs auf die Daten Ihrer Organisation.  Das bedeutet, dass Benutzer, die bereits bei einer Office 365-App oder Windows 10 angemeldet sind, automatisch mit ihrem Geschäfts-, Schul- oder Unikonto angemeldet werden.

Es wird empfohlen, dass **Microsoft Search**-Benutzer das einmalige Anmelden verwenden, um nicht so häufig zum Anmelden aufgefordert zu werden. Administratoren sollten das einmalige Anmelden mit einer kleinen Gruppe von Benutzern testen, um blockierende Konfigurationsprobleme zu identifizieren. 

Für Benutzer von Chrome unter Windows 10 funktioniert das einmalige Anmelden nur, wenn die Windows 10- und die AAD-Anmeldeerweiterung für Chrome installiert ist. Nach deren Installation könne Sie die Chrome-Erweiterung zum einfachen Authentifizieren bei AAD im Rahmen der Anmeldung bei unterstützten Websites verwenden, darunter Office 365 und Bing. Diese Funktionalität steht nur autorisierten Benutzern zur Verfügung. 

Um Windows 10 und die AAD-Anmeldeerweiterung für Chrome herunterzuladen und zu installieren, navigieren Sie zum [Chrome Web Store](https://go.microsoft.com/fwlink/?linkid=2090961).

## <a name="step-5-training-and-communication"></a>Schritt 5: Schulung und Kommunikation
Erstellen Sie Self-Service-Ressourcen, auf die Mitarbeiter selbst leicht zugreifen können. Dies hilft, die Gesamtbelastung für Sie und Ihr Team zu reduzieren, die Kommunikation ständig voranzutreiben und Mitarbeiter bei Selbststudium und -weiterbildung zu unterstützen. Bieten Sie Ihren Benutzern Kommunikation, FAQs, Videos und aufgezeichnete Schulungen oder Webinare an. Hier finden Sie einige hilfreiche Links für den Einstieg:
- [Finden erforderlicher Informationen in Office mit Microsoft Search](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Office 365-Schulungscenter](https://support.office.com/office-training-center)
- 
  [Microsoft Search Center](https://support.office.com/de-DE/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)

## <a name="trying-out-microsoft-search-in-bing"></a>Testen von **Microsoft Search** in Bing 
Der **Microsoft Search**-Administrator kann **Microsoft Search** in Bing deaktivieren. Wenn Microsoft Search deaktiviert ist, werden Benutzern in der Bing-Suche keine Inhalte der Organisation angezeigt. Standardmäßig ist **Microsoft Search** in Bing aktiviert. Wir empfehlen, **Microsoft Search** in Bing aktiviert zu lassen, damit Benutzer bessere Ergebnisse erzielen. 

Wenn Sie **Microsoft Search** auf einem Testmandanten ausprobieren oder die Suchumgebung testen möchten, bevor Sie sie allen Benutzern zur Verfügung stellen, können Sie **Microsoft Search** deaktivieren.
Um **Microsoft Search** in Bing zu aktivieren/deaktivieren, navigieren Sie zu **Dienste und Add-Ins** im **Microsoft 365 Admin Center** und **Microsoft Search in Bing ** aktivieren/deaktivieren.
