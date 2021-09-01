---
title: Verwalten des Zugriffs auf Dateien und Websites
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Eine Übersicht darüber, wie Administratoren sicherstellen können, dass der Zugriff auf Websites und Dateien innerhalb ihrer Organisation ordnungsgemäß eingeschränkt ist.
ms.openlocfilehash: c85cce6208743b884cce86cc11c46aab3e01254d
ms.sourcegitcommit: 70c48e470262099feb79553e36593521cc5e7abc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2021
ms.locfileid: "58835020"
---
# <a name="manage-access-to-files-and-sites"></a>Verwalten des Zugriffs auf Dateien und Websites

Nicht jede Datei oder Website sollte für jeden in Ihrer Organisation verfügbar sein. Administratoren und Benutzer können den Zugriff auf vertrauliche oder vertrauliche Informationen mithilfe von Lösungen verwalten, die ihre spezifischen Probleme am besten lösen. Wenn angemessene Zugriffssteuerungen nicht konsistent angewendet werden, kann dies zu einer Als "Überfreigabe" bezeichneten Aktion führen. Durch die Einfacherung der Suche nach informationen, die in Ihrer Organisation freigegeben wurden, können versehentlich mithilfe von Microsoft Search auf Dateien und Websites mit unzulässigen Einschränkungen zugegriffen werden.

Suchadministratoren können diese Probleme bei der Überfreigabe nicht beheben. Dateien und Websites ohne eingeschränkten Zugriff werden in internen Suchergebnissen und über andere Suchmöglichkeiten angezeigt. Wenn jedoch Steuerelemente zum Verhindern von Überfreigaben vorhanden sind, werden alle Alleen einschließlich der Suche geschlossen.

## <a name="solutions-to-prevent-oversharing"></a>Lösungen zum Verhindern von Überfreigaben

Verwenden Sie die unten aufgeführten Tools, Richtlinien und Techniken, um den Zugriff auf Informationen einzuschränken oder zu verblenden, um eine Überfreigabe zu verhindern. Die Implementierung dieser Lösungen erfordert wahrscheinlich globalen, Compliance- oder Sicherheitsadministratorzugriff. Wir empfehlen außerdem eine interne Kampagne, um Ihre Benutzer darüber zu informieren, wie sie ihre Websites und Dateien ordnungsgemäß schützen, kennzeichnen und ihre Berechtigung erteilen können.

### <a name="public-sites-or-sites-with-public-owners"></a>Öffentliche Websites oder Websites mit öffentlichen Besitzern

Eine Möglichkeit, Dateien für alle Personen in Ihrer Organisation freizugeben, sind öffentliche Websites oder Websites mit öffentlichen Besitzern. Vertraulichkeitsbezeichnungen können verhindern, dass Benutzer öffentliche Gruppen oder Websites erstellen. Dazu konfigurieren Sie alle Bezeichnungen so, dass private Gruppen erstellt werden und eine Bezeichnung für Gruppen erforderlich ist. Ausführliche Informationen finden Sie unter [Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint Websites.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) Sie müssen einen separaten Prozess definieren, damit Benutzer öffentliche Gruppen anfordern oder erstellen können.

Eine weitere Möglichkeit besteht darin, zu definieren, wer Microsoft 365 Gruppen in Ihrer Organisation erstellen kann. Weitere Informationen finden Sie unter [Erstellen einer Gruppe für Benutzer, die Microsoft 365 Gruppen erstellen müssen.](/microsoft-365/solutions/manage-creation-of-groups#step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups) Ein globaler Administrator muss einen Prozess einrichten, mit dem Benutzer Gruppenerstellungsanforderungen übermitteln können. Außerdem empfehlen wir Ihnen, Die Benutzer über diese Änderung zu informieren.

Wenn das Einschränken der Möglichkeit zum Erstellen von Gruppen für Ihre Organisation nicht möglich ist, können Sie Aktivitäten, einschließlich der Gruppenerstellung, durch Überwachung überwachen. Ausführliche Informationen zur grundlegenden und erweiterten Überwachung finden Sie unter [Überwachungslösungen in Microsoft 365.](/microsoft-365/compliance/auditing-solutions-overview)

### <a name="shared-files"></a>Freigegebene Dateien

Um den Zugriff auf alle Dateien einzuschränken, die als vertraulich eingestuft werden, können Sie Datenklassifizierungen für Ihre Organisation definieren und anwenden. Beispieldaten müssen gesammelt werden, um neue Klassifizierer zu trainieren. Ausführliche Informationen zu Voraussetzungen und Berechtigungen finden Sie unter [Informationen zur Datenklassifizierung.](/microsoft-365/compliance/data-classification-overview)

Um den Dateizugriff auf Mitglieder einer bestimmten Gruppe wie Führungskräfte einzuschränken, können Sie benutzerdefinierte Bezeichnungen erstellen, die auf eine Sicherheitsgruppe beschränkt sind. Wenn dann ein Sicherheitsgruppenmitglied die Bezeichnung anwendet, wird der Zugriff auf die Gruppe automatisch eingeschränkt. Weitere Informationen zu benutzerdefinierten Bezeichnungen finden Sie unter Erstellen und Konfigurieren von [Vertraulichkeitsbezeichnungen und deren Richtlinien](/microsoft-365/compliance/create-sensitivity-labels) und [Einschränken des Zugriffs auf Inhalte mithilfe von Vertraulichkeitsbezeichnungen zum Anwenden von Verschlüsselung.](/microsoft-365/compliance/encryption-sensitivity-labels)

Um sicherzustellen, dass Dokumente und E-Mails ordnungsgemäß gekennzeichnet sind, können Administratoren auch eine Standardbezeichnungsrichtlinie festlegen und von Benutzern verlangen, sie zu kennzeichnen. Weitere Informationen finden Sie unter [Von Benutzern fordern, dass sie eine Bezeichnung auf ihre E-Mails und Dokumente anwenden](/microsoft-365/compliance/sensitivity-labels-office-apps#require-users-to-apply-a-label-to-their-email-and-documents).

Sie können die Dateiüberteilung auch minimieren, indem Sie verhindern, dass zuletzt verwendete Dateien bei der Suche angezeigt werden. Dies kann auf Gruppenebene oder für jeden in Ihrer Organisation erfolgen. Informationen dazu, wie Sie verhindern können, dass zuletzt verwendete Dateien für eine Gruppe angezeigt werden, finden Sie unter Anpassen des [Datenschutzes für Elementeinblicke in Microsoft Graph.](/graph/insights-customize-item-insights-privacy) Ein Gruppenmitglied kann seine eigenen zuletzt verwendeten Dateien sehen, aber andere erhalten eine Meldung, dass keine Ergebnisse gefunden werden. Um die zuletzt verwendeten Dateien für alle Benutzer in Ihrer Organisation zu deaktivieren, müssen Sie Delve deaktivieren. Ausführliche Informationen finden Sie unter [Steuern des Zugriffs auf Delve](/sharepoint/delve-for-office-365-admins#control-access-to-delve).

> [!Note]
> Benutzer können weiterhin Dateien finden, die für sie in Microsoft Search Ergebnissen freigegeben wurden. Wenn Sie Elementeinblicke anpassen oder Delve deaktivieren, wird verhindert, dass Dateien in der Liste der zuletzt verwendeten Dateien eines Benutzers angezeigt werden.

### <a name="sites-and-files-between-groups"></a>Websites und Dateien zwischen Gruppen

Um die Datei- und Websitefreigabe zwischen Gruppen einzuschränken, z. B. einem Finanzteam, das vertrauliche Projekte mit einem Marketingteam verwaltet, können Sie Richtlinien für Informationsbarrieren definieren und implementieren. Diese Barrieren verhindern auch andere Aspekte der Kommunikation und Zusammenarbeit in Microsoft Teams, SharePoint und OneDrive. Ausführliche Informationen finden Sie unter [Informationen zu Informationsbarrieren in Microsoft 365.](/microsoft-365/compliance/information-barriers)

## <a name="get-access-insights"></a>Abrufen von Zugriffserkenntnissen

Die Zugriffsgovernance bietet Einblicke in Websites mit den sensibelsten Dokumenten und überlasteten Websites in Ihrer Organisation. Eine Übersicht finden Sie unter ["Neuigkeiten in Sicherheit und Compliance in SharePoint und OneDrive".](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/what-s-new-in-security-and-compliance-in-sharepoint-and-onedrive/ba-p/1696705) Sie müssen Ihre Organisation für diese Vorschau [nominieren.](https://forms.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u)
