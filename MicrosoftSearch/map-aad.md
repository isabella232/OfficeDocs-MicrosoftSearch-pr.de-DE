---
title: Zuordnen von Aad-Identitäten
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
description: Schritte zum Zuordnen von Aad-Identitäten
ms.openlocfilehash: db0378e596c560edebd2ceb942e6327b47a5286b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367703"
---
# <a name="map-your-azure-ad-identities"></a>Zuordnen Ihrer Azure AD Identitäten  

Dieser Artikel führt Sie durch die Schritte zum Zuordnen Ihrer Azure AD Identitäten zu einem eindeutigen Bezeichner für die Datenquelle (nicht Azure AD Identität), sodass Personen in ihrer Zugriffssteuerungsliste (ACL) mit nicht Azure Aden Identitäten Konnektor-Suchergebnisse auf Sie überprüfen können.

Diese Schritte sind nur für Suchadministratoren relevant, die einen [Salesforce](salesforce-connector.md) Connector von Microsoft mit Suchberechtigungen für "nur Personen mit Zugriff auf diese Datenquelle" und dem Identitätstyp "Aad" einrichten. In den folgenden Schritten erfahren Sie, wie Sie die Azure AD Benutzereigenschaften den **Verbund-IDs** Ihrer Benutzer zuordnen.

>[!NOTE]
>Wenn Sie einen [Salesforce Connector](salesforce-connector.md) einrichten und **nur Personen mit Zugriff auf diese Datenquelle** und den Identitätstyp " **nicht Aad** " auf dem Bildschirm "Suchberechtigungen" auswählen, lesen Sie den Artikel [zuordnen Ihres nicht Azure AD Identitäten](map-non-aad.md) , um Schritte zum Zuordnen von nicht Azure Aden Identitäten zu erhalten.  

## <a name="steps-for-mapping-your-azure-ad-properties"></a>Schritte zum Zuordnen Ihrer Azure AD Eigenschaften

### <a name="1-select-azure-ad-user-properties-to-map"></a>1. Wählen Sie Azure AD Benutzereigenschaften zur Zuordnung aus.

Sie können die Azure AD Eigenschaften auswählen, die Sie der Verbund-ID zuordnen müssen.

Sie können eine Azure AD Benutzereigenschaft aus der Dropdownliste auswählen. Sie können auch so viele Azure AD Benutzereigenschaften hinzufügen, wie Sie möchten, wenn diese Eigenschaften zum Erstellen der Verbund-ID-Zuordnung für Ihre Organisation erforderlich sind.

### <a name="2-create-formula-to-complete-mapping"></a>2. Formel erstellen, um die Zuordnung abzuschließen

Sie können die Werte der Azure AD Benutzereigenschaften kombinieren, um die eindeutige Verbund-ID zu bilden.

Im Feld Formel {0} entspricht "" der *ersten* Azure AD Eigenschaft, die Sie ausgewählt haben. " {1} " entspricht der *zweiten* Azure AD Eigenschaft, die Sie ausgewählt haben. " {2} " entspricht der *dritten* Azure AD-Eigenschaft usw.  

Im folgenden finden Sie einige Beispiele von Formeln mit Ausgaben für Sample reguläre Ausdrücke und Formel Ausgaben:

| Beispielformel                  | Wert der Eigenschaft {0} für einen Beispiel Benutzer                 | Wert der Eigenschaft {1} für einen Beispiel Benutzer           | Ausgabe von Formel                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1} @contoso. com  | FirstName | LastName |firstname.lastname@contoso.com
| {0}@Domain. com                 | UserID                 |             |userid@domain.com

Nachdem Sie Ihre Formel bereitgestellt haben, können Sie optional auf **Vorschau** klicken, um eine Vorschau von fünf zufälligen Benutzern aus der Datenquelle anzuzeigen, deren jeweilige Benutzerzuordnungen angewendet wurden. Die Ausgabe der Vorschau enthält den Wert der Azure AD Benutzereigenschaften, die in Schritt 1 für diese Benutzer ausgewählt wurden, und die Ausgabe der letzten Formel, die in Schritt 2 für diesen Benutzer bereitgestellt wurde. Er gibt auch an, ob die Ausgabe der Formel über ein "Success"-oder "failed"-Symbol in einen Azure AD-Benutzer in Ihrem Mandanten aufgelöst werden kann.  

>[!NOTE]
>Sie können weiterhin mit dem Erstellen Ihrer Verbindung fortfahren, wenn eine oder mehrere Benutzerzuordnungen den Status "Fehler" aufweisen, nachdem Sie auf " **Vorschau**" klicken. In der Vorschau werden 5 zufällige Benutzer und deren Zuordnungen aus der Datenquelle angezeigt. Wenn die von Ihnen bereitgestellten Zuordnungen nicht alle Benutzer zuordnen, kann dieser Fall auftreten.

## <a name="sample-azure-ad-mapping"></a>Beispiel Azure AD Zuordnung

Eine Beispiel Azure AD Zuordnung finden Sie im folgenden Snapshot.

![Beispiel-Momentaufnahme des Ausfüllens der Seite "Azure AD Zuordnung"](media/aad-mapping.png)

## <a name="limitations"></a>Einschränkungen  

- Für alle Benutzer wird nur eine Zuordnung unterstützt. Bedingte Zuordnungen werden nicht unterstützt.  

- Sie können die Zuordnung nicht mehr ändern, nachdem die Verbindung veröffentlicht wurde.  

- Regex-basierte Ausdrücke für die Azure AD Benutzereigenschaften werden für die Transformation der Azure AD zu Verbund-ID nicht unterstützt.