---
title: Zuordnen von AAD-Identitäten
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
description: Schritte zum Zuordnen von AAD-Identitäten
ms.openlocfilehash: 676e06d4019dabe0f07846dd8918b8070765a7ffd9deb02b11dd68f2014dc7e5
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532807"
---
# <a name="map-your-azure-ad-identities"></a>Zuordnen Ihrer Azure AD-Identitäten   

In diesem Artikel werden Sie durch die Schritte zum Zuordnen Ihrer Azure AD-Identitäten zu einem eindeutigen Bezeichner für Ihre Datenquelle (nicht Azure AD-Identität) geführt, damit Personen in Ihrer Zugriffssteuerungsliste (Access Control List, ACL) mit Nicht-Azure AD-Identitäten die entsprechenden Connector-Suchergebnisse sehen können.

Diese Schritte sind nur für Suchadministratoren relevant, die einen [Salesforce-Connector](salesforce-connector.md) von Microsoft mit Suchberechtigungen für "Nur Personen mit Zugriff auf diese Datenquelle" und Identitätstyp "AAD" einrichten. Die folgenden Schritte führen Sie durch das Zuordnen Ihrer Azure AD-Benutzereigenschaften zu den **Verbund-IDs** Ihrer Benutzer.

>[!NOTE]
>Wenn Sie einen [Salesforce-Connector](salesforce-connector.md) einrichten und auf dem Bildschirm mit den Suchberechtigungen **nur Personen mit Zugriff** auf diese Datenquelle und den Identitätstyp **"Nicht-AAD"** auswählen, finden Sie im Artikel ["Zuordnung Ihrer Nicht-Azure AD-Identitäten"](map-non-aad.md) Schritte zum Zuordnen von Nicht-Azure AD-Identitäten.  

## <a name="steps-for-mapping-your-azure-ad-properties"></a>Schritte zum Zuordnen Ihrer Azure AD-Eigenschaften

### <a name="1-select-azure-ad-user-properties-to-map"></a>1. Auswählen der zu zuordnenden Azure AD-Benutzereigenschaften

Sie können die Azure AD-Eigenschaften auswählen, die Sie benötigen, um sie der Verbund-ID zuzuordnen.

Sie können eine Azure AD-Benutzereigenschaft aus der Dropdownliste auswählen. Sie können auch beliebig viele Azure AD-Benutzereigenschaften hinzufügen, wenn diese Eigenschaften erforderlich sind, um die Zuordnung der Verbund-ID für Ihre Organisation zu erstellen.

### <a name="2-create-formula-to-complete-mapping"></a>2. Erstellen einer Formel zum Abschließen der Zuordnung

Sie können die Werte der Azure AD-Benutzereigenschaften kombinieren, um die eindeutige Verbund-ID zu bilden.

Im Formelfeld {0} entspricht " der *ersten* azure AD-Eigenschaft, die Sie ausgewählt haben. " {1} entspricht der *zweiten* azure AD-Eigenschaft, die Sie ausgewählt haben. " {2} entspricht der *dritten* Azure AD-Eigenschaft usw.  

Nachfolgend finden Sie einige Beispiele für Formeln mit Beispielausgabe für reguläre Ausdrücke und Formelausgabe:

| Beispielformel                  | Wert der Eigenschaft {0} für einen Beispielbenutzer                 | Wert der Eigenschaft {1} für einen Beispielbenutzer           | Ausgabe der Formel                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1} @contoso.com  | Firstname | Lastname |firstname.lastname@contoso.com
| {0}@domain.com                 | Userid                 |             |userid@domain.com

Nachdem Sie Ihre Formel bereitgestellt haben, können Sie optional auf **"Vorschau"** klicken, um eine Vorschau von 5 zufälligen Benutzern aus Ihrer Datenquelle mit angewendeten entsprechenden Benutzerzuordnungen anzuzeigen. Die Ausgabe der Vorschau enthält den Wert der Azure AD-Benutzereigenschaften, die in Schritt 1 für diese Benutzer ausgewählt wurden, und die Ausgabe der endgültigen Formel, die in Schritt 2 für diesen Benutzer bereitgestellt wurde. Außerdem wird angegeben, ob die Ausgabe der Formel über das Symbol "Erfolgreich" oder "Fehlgeschlagen" an einen Azure AD-Benutzer in Ihrem Mandanten aufgelöst werden kann.  

>[!NOTE]
>Sie können weiterhin mit dem Erstellen der Verbindung fortfahren, wenn eine oder mehrere Benutzerzuordnungen den Status "Fehlgeschlagen" aufweisen, nachdem Sie auf **"Vorschau"** geklickt haben. In der Vorschau werden 5 zufällige Benutzer und deren Zuordnungen aus Ihrer Datenquelle angezeigt. Wenn die von Ihnen bereitgestellte Zuordnung nicht allen Benutzern zugeordnet ist, kann dieser Fall auftreten.

## <a name="sample-azure-ad-mapping"></a>Beispiel für die Azure AD-Zuordnung

Eine Beispiel-Azure AD-Zuordnung finden Sie unten in der Momentaufnahme.

![Beispielmomentaufnahme zum Ausfüllen der Azure AD-Zuordnungsseite](media/aad-mapping.png)

## <a name="limitations"></a>Einschränkungen  

- Es wird nur eine Zuordnung für alle Benutzer unterstützt. Bedingte Zuordnungen werden nicht unterstützt.  

- Sie können ihre Zuordnung nicht mehr ändern, nachdem die Verbindung veröffentlicht wurde.  

- Regex-basierte Ausdrücke für die Azure AD-Benutzereigenschaften werden für die Transformation von Azure AD in Verbund-ID nicht unterstützt.