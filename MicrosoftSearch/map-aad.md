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
# <a name="map-your-azure-ad-identities"></a><span data-ttu-id="342b3-103">Zuordnen Ihrer Azure AD Identitäten</span><span class="sxs-lookup"><span data-stu-id="342b3-103">Map your Azure AD Identities</span></span>  

<span data-ttu-id="342b3-104">Dieser Artikel führt Sie durch die Schritte zum Zuordnen Ihrer Azure AD Identitäten zu einem eindeutigen Bezeichner für die Datenquelle (nicht Azure AD Identität), sodass Personen in ihrer Zugriffssteuerungsliste (ACL) mit nicht Azure Aden Identitäten Konnektor-Suchergebnisse auf Sie überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="342b3-104">This article walks you through the steps of mapping your Azure AD identities to a unique identifier for your data source (non-Azure AD identity) so that people in your Access Control List (ACL) with non-Azure AD identities can see connector search results scoped to them.</span></span>

<span data-ttu-id="342b3-105">Diese Schritte sind nur für Suchadministratoren relevant, die einen [Salesforce](salesforce-connector.md) Connector von Microsoft mit Suchberechtigungen für "nur Personen mit Zugriff auf diese Datenquelle" und dem Identitätstyp "Aad" einrichten.</span><span class="sxs-lookup"><span data-stu-id="342b3-105">These steps are only relevant to search administrators who are setting up a [Salesforce](salesforce-connector.md) connector by Microsoft with search permissions for "Only people with access to this data source" and identity type "AAD."</span></span> <span data-ttu-id="342b3-106">In den folgenden Schritten erfahren Sie, wie Sie die Azure AD Benutzereigenschaften den **Verbund-IDs** Ihrer Benutzer zuordnen.</span><span class="sxs-lookup"><span data-stu-id="342b3-106">The following steps walk you through how to map your Azure AD user properties to your users' **Federation IDs**.</span></span>

>[!NOTE]
><span data-ttu-id="342b3-107">Wenn Sie einen [Salesforce Connector](salesforce-connector.md) einrichten und **nur Personen mit Zugriff auf diese Datenquelle** und den Identitätstyp " **nicht Aad** " auf dem Bildschirm "Suchberechtigungen" auswählen, lesen Sie den Artikel [zuordnen Ihres nicht Azure AD Identitäten](map-non-aad.md) , um Schritte zum Zuordnen von nicht Azure Aden Identitäten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="342b3-107">If you are setting up a [Salesforce connector](salesforce-connector.md) and select **Only people with access to this data source** and identity type **non-AAD** on the search permissions screen, refer to the [Map your non-Azure AD Identities](map-non-aad.md) article for steps on how to map non-Azure AD identities.</span></span>  

## <a name="steps-for-mapping-your-azure-ad-properties"></a><span data-ttu-id="342b3-108">Schritte zum Zuordnen Ihrer Azure AD Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="342b3-108">Steps for mapping your Azure AD properties</span></span>

### <a name="1-select-azure-ad-user-properties-to-map"></a><span data-ttu-id="342b3-109">1. Wählen Sie Azure AD Benutzereigenschaften zur Zuordnung aus.</span><span class="sxs-lookup"><span data-stu-id="342b3-109">1. Select Azure AD user properties to map</span></span>

<span data-ttu-id="342b3-110">Sie können die Azure AD Eigenschaften auswählen, die Sie der Verbund-ID zuordnen müssen.</span><span class="sxs-lookup"><span data-stu-id="342b3-110">You can select the Azure AD properties you need to map to the Federation ID.</span></span>

<span data-ttu-id="342b3-111">Sie können eine Azure AD Benutzereigenschaft aus der Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="342b3-111">You can select an Azure AD user property from the dropdown.</span></span> <span data-ttu-id="342b3-112">Sie können auch so viele Azure AD Benutzereigenschaften hinzufügen, wie Sie möchten, wenn diese Eigenschaften zum Erstellen der Verbund-ID-Zuordnung für Ihre Organisation erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="342b3-112">You can also add as many Azure AD user properties as you would like if these properties are necessary to create the Federation ID mapping for your organization.</span></span>

### <a name="2-create-formula-to-complete-mapping"></a><span data-ttu-id="342b3-113">2. Formel erstellen, um die Zuordnung abzuschließen</span><span class="sxs-lookup"><span data-stu-id="342b3-113">2. Create formula to complete mapping</span></span>

<span data-ttu-id="342b3-114">Sie können die Werte der Azure AD Benutzereigenschaften kombinieren, um die eindeutige Verbund-ID zu bilden.</span><span class="sxs-lookup"><span data-stu-id="342b3-114">You can combine the values of the Azure AD user properties to form the unique Federation ID.</span></span>

<span data-ttu-id="342b3-115">Im Feld Formel {0} entspricht "" der *ersten* Azure AD Eigenschaft, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="342b3-115">In the formula box, "{0}" corresponds to the *first* Azure AD property you selected.</span></span> <span data-ttu-id="342b3-116">" {1} " entspricht der *zweiten* Azure AD Eigenschaft, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="342b3-116">"{1}" corresponds to the *second* Azure AD property you selected.</span></span> <span data-ttu-id="342b3-117">" {2} " entspricht der *dritten* Azure AD-Eigenschaft usw.</span><span class="sxs-lookup"><span data-stu-id="342b3-117">"{2}" corresponds to the *third* Azure AD property, and so on.</span></span>  

<span data-ttu-id="342b3-118">Im folgenden finden Sie einige Beispiele von Formeln mit Ausgaben für Sample reguläre Ausdrücke und Formel Ausgaben:</span><span class="sxs-lookup"><span data-stu-id="342b3-118">Below are some examples of formulas with sample regular expression outputs and formula outputs:</span></span>

| <span data-ttu-id="342b3-119">Beispielformel</span><span class="sxs-lookup"><span data-stu-id="342b3-119">Sample formula</span></span>                  | <span data-ttu-id="342b3-120">Wert der Eigenschaft {0} für einen Beispiel Benutzer</span><span class="sxs-lookup"><span data-stu-id="342b3-120">Value of property {0} for a sample user</span></span>                 | <span data-ttu-id="342b3-121">Wert der Eigenschaft {1} für einen Beispiel Benutzer</span><span class="sxs-lookup"><span data-stu-id="342b3-121">Value of property {1} for a sample user</span></span>           | <span data-ttu-id="342b3-122">Ausgabe von Formel</span><span class="sxs-lookup"><span data-stu-id="342b3-122">Output of formula</span></span>                  |
| :------------------- | :------------------- |:---------------|:---------------|
| <span data-ttu-id="342b3-123">{0}.{1} @contoso. com</span><span class="sxs-lookup"><span data-stu-id="342b3-123">{0}.{1}@contoso.com</span></span>  | <span data-ttu-id="342b3-124">FirstName</span><span class="sxs-lookup"><span data-stu-id="342b3-124">firstname</span></span> | <span data-ttu-id="342b3-125">LastName</span><span class="sxs-lookup"><span data-stu-id="342b3-125">lastname</span></span> |<span data-ttu-id="342b3-126">firstname.lastname@contoso.com</span><span class="sxs-lookup"><span data-stu-id="342b3-126">firstname.lastname@contoso.com</span></span>
| <span data-ttu-id="342b3-127">{0}@Domain. com</span><span class="sxs-lookup"><span data-stu-id="342b3-127">{0}@domain.com</span></span>                 | <span data-ttu-id="342b3-128">UserID</span><span class="sxs-lookup"><span data-stu-id="342b3-128">userid</span></span>                 |             |<span data-ttu-id="342b3-129">userid@domain.com</span><span class="sxs-lookup"><span data-stu-id="342b3-129">userid@domain.com</span></span>

<span data-ttu-id="342b3-130">Nachdem Sie Ihre Formel bereitgestellt haben, können Sie optional auf **Vorschau** klicken, um eine Vorschau von fünf zufälligen Benutzern aus der Datenquelle anzuzeigen, deren jeweilige Benutzerzuordnungen angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="342b3-130">After you provide your formula, you can optionally click **Preview** to see a preview of 5 random users from your data source with their respective user mappings applied.</span></span> <span data-ttu-id="342b3-131">Die Ausgabe der Vorschau enthält den Wert der Azure AD Benutzereigenschaften, die in Schritt 1 für diese Benutzer ausgewählt wurden, und die Ausgabe der letzten Formel, die in Schritt 2 für diesen Benutzer bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="342b3-131">The output of the preview includes the value of the Azure AD user properties selected in step 1 for those users and the output of the final formula provided in step 2 for that user.</span></span> <span data-ttu-id="342b3-132">Er gibt auch an, ob die Ausgabe der Formel über ein "Success"-oder "failed"-Symbol in einen Azure AD-Benutzer in Ihrem Mandanten aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="342b3-132">It also indicates whether the output of the formula could be resolved to an Azure AD user in your tenant via a "Success" or "Failed" icon.</span></span>  

>[!NOTE]
><span data-ttu-id="342b3-133">Sie können weiterhin mit dem Erstellen Ihrer Verbindung fortfahren, wenn eine oder mehrere Benutzerzuordnungen den Status "Fehler" aufweisen, nachdem Sie auf " **Vorschau**" klicken.</span><span class="sxs-lookup"><span data-stu-id="342b3-133">You can still proceed with creating your connection if one or more user mappings have a "Failed" status after you click **Preview**.</span></span> <span data-ttu-id="342b3-134">In der Vorschau werden 5 zufällige Benutzer und deren Zuordnungen aus der Datenquelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="342b3-134">The preview shows 5 random users and their mappings from your data source.</span></span> <span data-ttu-id="342b3-135">Wenn die von Ihnen bereitgestellten Zuordnungen nicht alle Benutzer zuordnen, kann dieser Fall auftreten.</span><span class="sxs-lookup"><span data-stu-id="342b3-135">If the mapping you provide does not map all users, you may experience this case.</span></span>

## <a name="sample-azure-ad-mapping"></a><span data-ttu-id="342b3-136">Beispiel Azure AD Zuordnung</span><span class="sxs-lookup"><span data-stu-id="342b3-136">Sample Azure AD mapping</span></span>

<span data-ttu-id="342b3-137">Eine Beispiel Azure AD Zuordnung finden Sie im folgenden Snapshot.</span><span class="sxs-lookup"><span data-stu-id="342b3-137">See the snapshot below for a sample Azure AD mapping.</span></span>

![Beispiel-Momentaufnahme des Ausfüllens der Seite "Azure AD Zuordnung"](media/aad-mapping.png)

## <a name="limitations"></a><span data-ttu-id="342b3-139">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="342b3-139">Limitations</span></span>  

- <span data-ttu-id="342b3-140">Für alle Benutzer wird nur eine Zuordnung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="342b3-140">Only one mapping is supported for all users.</span></span> <span data-ttu-id="342b3-141">Bedingte Zuordnungen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="342b3-141">Conditional mappings are not supported.</span></span>  

- <span data-ttu-id="342b3-142">Sie können die Zuordnung nicht mehr ändern, nachdem die Verbindung veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="342b3-142">You cannot change your mapping once the connection is published.</span></span>  

- <span data-ttu-id="342b3-143">Regex-basierte Ausdrücke für die Azure AD Benutzereigenschaften werden für die Transformation der Azure AD zu Verbund-ID nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="342b3-143">Regex-based expressions against the Azure AD user properties are not supported for the Azure AD to Federation ID transformation.</span></span>