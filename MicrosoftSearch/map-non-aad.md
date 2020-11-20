---
title: Zuordnen von nicht-Aad Identitäten
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Schritte zum Zuordnen von nicht Aad Identitäten
ms.openlocfilehash: cd7d0eb17678d69ec1966e4472b38c1f18c30809
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367658"
---
# <a name="map-your-non-azure-ad-identities"></a>Zuordnen Ihrer nicht Azure AD Identitäten  

Dieser Artikel führt Sie durch die Schritte zum Zuordnen Ihrer nicht Azure Aden Identitäten zu ihren Azure AD Identitäten, sodass Personen in ihrer Zugriffssteuerungsliste (ACL) mit nicht Azure Aden Identitäten Konnektor-Suchergebnisse auf diese Ebene anzeigen können.

Diese Schritte sind nur für Suchadministratoren relevant, die eine [ServiceNow](servicenow-connector.md) -oder [Salesforce](salesforce-connector.md) -Connectors von Microsoft mit Suchberechtigungen für "nur Personen mit Zugriff auf diese Datenquelle" und "nicht-Aad" für Identitätstypen einrichten.

>[!NOTE]
>Wenn Sie einen Salesforce Connector einrichten und **nur Personen mit Zugriff auf diese Datenquelle** und den Identitätstyp **Aad** auf dem Bildschirm Berechtigungen für die Suche auswählen, lesen Sie den Artikel [zuordnen Ihres Azure AD Identitäten](map-aad.md) , um Schritte zum Zuordnen Azure AD Identitäten zu erhalten.  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a>Schritte zum Zuordnen Ihrer nicht-Azure AD Eigenschaften

### <a name="1-select-an-azure-ad-user-property"></a>1. Wählen Sie eine Azure AD Benutzereigenschaft aus.  

Sie können die Azure AD Benutzereigenschaft auswählen, für die Sie die Zuordnung erstellen. Dies ist die Zieleigenschaft, der Sie Ihre nicht Azure AD Identitäten zuordnen möchten.  

Sie können eine der folgenden Azure AD Eigenschaften auswählen:

| Azure AD-Eigenschaft    | Definition           | Beispiel         |
| :------------------- | :------------------- |:--------------- |
| Benutzerprinzipalname (UPN)  | Ein UPN besteht aus einem UPN-Präfix (dem Benutzerkontonamen) und einem UPN-Suffix (DNS-Domänenname). Das Präfix wird mithilfe des @-Symbols mit dem Suffix verknüpft. | us1@contoso.onmicrosoft.com |
| Azure Ad-ID                 | Eine Azure Ad-ID für einen bestimmten Benutzer ist die eindeutige GUID des Benutzers.                 | 58006c96-9e6e-45ea-8c88-4a56851eefad            |
| Active Directory-Sicherheits-ID (SID)                  | SID (Sicherheits-ID) ist ein eindeutiger Bezeichner, den Active Directory verwendet, um Objekte als Sicherheitsprinzipal zu identifizieren.                  | S-1-5-21-453406510-812318184-4183662089             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a>2. Wählen Sie nicht Azure AD Benutzereigenschaften für die Zuordnung aus.

Sie können nicht Azure AD Eigenschaften auswählen, die von der Datenquelle abgerufen wurden, um reguläre Ausdrücke auf anzuwenden. Weitere Informationen dazu, wo diese Eigenschaften in der Datenquelle zu finden sind, finden Sie auf den Seiten [ServiceNow](servicenow-connector.md) und [Salesforce](salesforce-connector.md) .  

Sie können eine nicht Azure AD Benutzereigenschaft aus der Dropdownliste auswählen und einen regulären Ausdruck bereitstellen, der auf diese Benutzer Eigenschaftswerte angewendet werden soll. Weitere Informationen zu regulären Ausdrücken finden Sie unter [Regular Expression Reference]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference).  

Im folgenden finden Sie einige Beispiele für reguläre Ausdrücke und deren Ausgaben, die auf eine Beispielzeichenfolge angewendet werden: 

| Beispielzeichenfolge                  | Regulärer Ausdruck                 | Ausgabe des regulären Ausdrucks für die Beispielzeichenfolge           |
| :------------------- | :------------------- |:---------------|
| Alexis Vasquez  | .* | Alexis Vasquez |
| Alexis Vasquez                 | ..$                 | EZ            |
| Alexis Vasquez                  | (\w +) $                  | Vasquez             |

Sie können so viele nicht Azure ADe Benutzereigenschaften hinzufügen, wie Sie es ausdrücken möchten. Sie können verschiedene reguläre Ausdrücke auf dieselbe Benutzereigenschaft anwenden, wenn Ihre endgültige Formel dies zulässt.  

### <a name="3-create-formula-to-complete-mapping"></a>3. Formel erstellen, um die Zuordnung abzuschließen

Sie können die Ausgaben der regulären Ausdrücke, die auf die einzelnen nicht Azure AD Benutzereigenschaften angewendet werden, so kombinieren, dass Sie die in Schritt 1 ausgewählte Azure AD-Eigenschaft bilden.

Im Feld Formel {0} entspricht "" der Ausgabe des regulären Ausdrucks, der auf die *erste* nicht Azure AD Eigenschaft angewendet wurde, die Sie ausgewählt haben. " {1} " entspricht der Ausgabe des regulären Ausdrucks, der auf die *zweite* nicht Azure AD Eigenschaft angewendet wurde, die Sie ausgewählt haben. " {2} " entspricht der Ausgabe des regulären Ausdrucks, der auf die *dritte* nicht Azure AD Eigenschaft angewendet wird usw.  

Im folgenden finden Sie einige Beispiele von Formeln mit Ausgaben für Sample reguläre Ausdrücke und Formel Ausgaben: 

| Beispielformel                  | Wert von " {0} auf Beispiel Benutzer"                 | Wert von " {1} auf Beispiel Benutzer"           | Ausgabe von Formel                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1} @contoso. com  | FirstName | LastName |firstname.lastname@contoso.com
| {0}@Domain. com                 | UserID                 |             |userid@domain.com

Nachdem Sie Ihre Formel bereitgestellt haben, können Sie optional auf **Vorschau** klicken, um eine Vorschau von fünf zufälligen Benutzern aus der Datenquelle anzuzeigen, deren jeweilige Benutzerzuordnungen angewendet wurden. Die Ausgabe der Vorschau enthält den Wert der in Schritt 2 für diese Benutzer ausgewählten nicht Azure AD Benutzereigenschaften und die Ausgabe der letzten Formel, die in Schritt 3 für diesen Benutzer bereitgestellt wurde. Er gibt auch an, ob die Ausgabe der Formel über ein "Success"-oder "failed"-Symbol in einen Azure AD-Benutzer in Ihrem Mandanten aufgelöst werden kann.  

>[!NOTE]
>Sie können weiterhin mit dem Erstellen Ihrer Verbindung fortfahren, wenn eine oder mehrere Benutzerzuordnungen den Status "Fehler" aufweisen, nachdem Sie auf " **Vorschau**" klicken. In der Vorschau werden 5 zufällige Benutzer und deren Zuordnungen aus der Datenquelle angezeigt. Wenn die von Ihnen bereitgestellten Zuordnungen nicht alle Benutzer zuordnen, kann dieser Fall auftreten.

## <a name="sample-non-azure-ad-mapping"></a>Beispiel für nicht Azure AD Zuordnung

Eine beispielhafte nicht Azure AD Zuordnung finden Sie im folgenden Snapshot.

![Beispiel-Momentaufnahme des Ausfüllens der Seite "nicht Azure AD Zuordnung"](media/non-aad-mapping.png)

## <a name="limitations"></a>Einschränkungen  

- Für alle Benutzer wird nur eine Zuordnung unterstützt. Bedingte Zuordnungen werden nicht unterstützt.  

- Sie können die Zuordnung nicht mehr ändern, nachdem die Verbindung veröffentlicht wurde.  

- Für die Transformation werden derzeit nur Regex-basierte Ausdrücke für die nicht-Aad-Benutzereigenschaften unterstützt.

- Es gibt nur drei Azure AD Identitäten, denen Sie zuordnen können (UPN, Azure Ad-ID und AD-sid).