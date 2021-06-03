---
title: Salesforce Graph Connector für Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Salesforce Graph Connector für Microsoft Search
ms.openlocfilehash: d4d19c05f82ddb28c4dc3e6719bf8ea8d7284cc3
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720988"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="add86-103">Salesforce Graph Connector (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="add86-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="add86-104">Der Salesforce Graph-Connector ermöglicht Es Ihrer Organisation, Kontakte, Verkaufschancen, Leads und Accounts-Objekte in Ihrer Salesforce-Instanz zu indizieren.</span><span class="sxs-lookup"><span data-stu-id="add86-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="add86-105">Nachdem Sie den Connector und den Indexinhalt aus Salesforce konfiguriert haben, können Endbenutzer in jedem Microsoft Search-Client nach diesen Elementen suchen.</span><span class="sxs-lookup"><span data-stu-id="add86-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="add86-106">Lesen Sie [**den Artikel Setup für Graph Connector,**](configure-connector.md) um die Allgemeinen Anweisungen Graph Connectors zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="add86-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="add86-107">Dieser Artikel ist für alle Benutzer verfügbar, die einen Salesforce-Graph konfigurieren, Graph werden.</span><span class="sxs-lookup"><span data-stu-id="add86-107">This article is for anyone who configures, runs, and monitors a Salesforce Graph connector.</span></span> <span data-ttu-id="add86-108">Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Salesforce-Graph gelten.</span><span class="sxs-lookup"><span data-stu-id="add86-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="add86-109">Dieser Artikel enthält auch Informationen zu [Einschränkungen](#limitations).</span><span class="sxs-lookup"><span data-stu-id="add86-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="add86-110">Der Salesforce Graph-Connector unterstützt derzeit Sommer '19 oder höher.</span><span class="sxs-lookup"><span data-stu-id="add86-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="add86-111">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="add86-111">Before you get started</span></span>

<span data-ttu-id="add86-112">Zum Herstellen einer Verbindung mit Ihrer Salesforce-Instanz benötigen Sie die Salesforce-Instanz-URL, die Client-ID und den geheimen Client für die OAuth-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="add86-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="add86-113">In den folgenden Schritten wird erläutert, wie Sie oder Ihr Salesforce-Administrator diese Informationen aus Ihrem Salesforce-Konto erhalten können:</span><span class="sxs-lookup"><span data-stu-id="add86-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="add86-114">Melden Sie sich bei Ihrer Salesforce-Instanz an, und wechseln Sie zu Setup</span><span class="sxs-lookup"><span data-stu-id="add86-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="add86-115">Navigieren Sie zu Apps -> App Manager.</span><span class="sxs-lookup"><span data-stu-id="add86-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="add86-116">Wählen **Sie Neue verbundene App aus.**</span><span class="sxs-lookup"><span data-stu-id="add86-116">Select **New connected app**.</span></span>

- <span data-ttu-id="add86-117">Führen Sie den Abschnitt API wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="add86-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="add86-118">Aktivieren Sie das Kontrollkästchen **Oauth-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="add86-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="add86-119">Geben Sie die Rückruf-URL wie folgt an: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="add86-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="add86-120">Wählen Sie diese erforderlichen OAuth-Bereiche aus.</span><span class="sxs-lookup"><span data-stu-id="add86-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="add86-121">Zugreifen und Verwalten Ihrer Daten (API)</span><span class="sxs-lookup"><span data-stu-id="add86-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="add86-122">Durchführen von Anforderungen in Ihrem Namen jederzeit (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="add86-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="add86-123">Aktivieren Sie das Kontrollkästchen Schlüssel **für Webserverfluss erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="add86-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="add86-124">Speichern Sie die App.</span><span class="sxs-lookup"><span data-stu-id="add86-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="add86-125">![API-Abschnitt in der Salesforce-Instanz, nachdem der Administrator alle oben aufgeführten erforderlichen Konfigurationen eingegeben hat.](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="add86-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="add86-126">Kopieren Sie den Verbraucherschlüssel und den Verbraucherschlüssel.</span><span class="sxs-lookup"><span data-stu-id="add86-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="add86-127">Diese Informationen werden als Client-ID und geheimer Clientgeheimnis verwendet, wenn Sie die Verbindungs-Einstellungen für Ihren Graph Connector im Microsoft 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="add86-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="add86-128">![Ergebnisse, die vom API-Abschnitt in der Salesforce-Instanz zurückgegeben werden, nachdem der Administrator alle erforderlichen Konfigurationen übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="add86-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="add86-129">Der Verbraucherschlüssel befindet sich oben in der linken Spalte, und der Geheime Verbraucherschlüssel befindet sich oben in der rechten Spalte.](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="add86-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="add86-130">Führen Sie vor dem Schließen Ihrer Salesforce-Instanz die folgenden Schritte aus, um sicherzustellen, dass Aktualisierungstoken nicht ablaufen:</span><span class="sxs-lookup"><span data-stu-id="add86-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="add86-131">Wechseln sie zu Apps -> App Manager</span><span class="sxs-lookup"><span data-stu-id="add86-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="add86-132">Suchen Sie die app, die Sie erstellt haben, und wählen Sie die Dropdownliste auf der rechten Seite aus.</span><span class="sxs-lookup"><span data-stu-id="add86-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="add86-133">Wählen Sie **Verwalten aus**</span><span class="sxs-lookup"><span data-stu-id="add86-133">Select **Manage**</span></span>
    - <span data-ttu-id="add86-134">Auswählen **von Bearbeitungsrichtlinien**</span><span class="sxs-lookup"><span data-stu-id="add86-134">Select **edit policies**</span></span>
    - <span data-ttu-id="add86-135">Wählen Sie für aktualisierungstokenrichtlinie die Option **Aktualisierungstoken ist gültig, bis sie widerrufen wurde.**</span><span class="sxs-lookup"><span data-stu-id="add86-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="add86-136">![Wählen Sie die Aktualisierungstokenrichtlinie mit dem Namen "Aktualisierungstoken ist gültig, bis widerrufen" aus.](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="add86-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="add86-137">Sie können nun das [M365 Admin Center](https://admin.microsoft.com/) verwenden, um den restlichen Setupvorgang für Ihren Graph abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="add86-137">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="add86-138">Schritt 1: Hinzufügen eines Graph im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="add86-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="add86-139">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="add86-139">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="add86-140">Schritt 2: Benennen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="add86-140">Step 2: Name the connection</span></span>

<span data-ttu-id="add86-141">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="add86-141">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="add86-142">Schritt 3: Konfigurieren der Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="add86-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="add86-143">Verwenden Sie für die Instanz-URL https://[domäne].my.salesforce.com, wobei Domäne die #A0 für Ihre Organisation wäre.</span><span class="sxs-lookup"><span data-stu-id="add86-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="add86-144">Geben Sie die Client-ID und den geheimen Clientgeheimnis ein, die Sie von Ihrer Salesforce-Instanz erhalten haben, und wählen Sie Anmelden aus.</span><span class="sxs-lookup"><span data-stu-id="add86-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="add86-145">Wenn Sie sich zum ersten Mal mit diesen Einstellungen anmelden möchten, erhalten Sie ein Popup, in dem Sie aufgefordert werden, sich mit Ihrem Administratorbenutzernamen und Kennwort bei Salesforce zu anmelden.</span><span class="sxs-lookup"><span data-stu-id="add86-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="add86-146">Der folgende Screenshot zeigt das Popup.</span><span class="sxs-lookup"><span data-stu-id="add86-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="add86-147">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie "Anmelden" aus.</span><span class="sxs-lookup"><span data-stu-id="add86-147">Enter your credentials and select "Log In".</span></span>

  ![Login pop up asking for Username and password.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="add86-149">Wenn das Popup nicht angezeigt wird, wird es möglicherweise in Ihrem Browser blockiert, sodass Sie Popups und Umleitungen zulassen müssen.</span><span class="sxs-lookup"><span data-stu-id="add86-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="add86-150">Überprüfen Sie, ob die Verbindung erfolgreich war, indem Sie nach einem grünen Banner suchen, das "Verbindung erfolgreich" heißt, wie im screenshot unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="add86-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="add86-151">![Screenshot der erfolgreichen Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="add86-151">![Screenshot of successful login.</span></span> <span data-ttu-id="add86-152">Das grüne Banner mit dem Namen "Verbindung erfolgreich" befindet sich unter dem Feld für Ihre Salesforce-Instanz-URL.](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="add86-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="add86-153">Schritt 4: Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="add86-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="add86-154">Sie müssen auswählen, welche Benutzer Suchergebnisse aus dieser Datenquelle sehen.</span><span class="sxs-lookup"><span data-stu-id="add86-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="add86-155">Wenn Sie nur bestimmten Azure Active Directory (Azure AD) oder Nicht-Azure AD-Benutzern erlauben, die Suchergebnisse anzuzeigen, stellen Sie sicher, dass Sie die Identitäten zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="add86-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

### <a name="step-4a-select-permissions"></a><span data-ttu-id="add86-156">Schritt 4.a: Auswählen von Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="add86-156">Step 4.a: Select permissions</span></span>

<span data-ttu-id="add86-157">Sie können zugriffssteuerungslisten (Access Control Lists, ACLs) aus Ihrer Salesforce-Instanz ingesten oder jedem Benutzer in Ihrer Organisation erlauben, Suchergebnisse aus dieser Datenquelle zu sehen.</span><span class="sxs-lookup"><span data-stu-id="add86-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="add86-158">ACLs können Azure Active Directory (AAD)-Identitäten (Benutzer, die von Azure AD zu Salesforce partneriert sind), Nicht-Azure AD-Identitäten (systemeigene Salesforce-Benutzer, die über entsprechende Identitäten in Azure AD verfügen) oder beides umfassen.</span><span class="sxs-lookup"><span data-stu-id="add86-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="add86-159">Wenn Sie einen Identitätsanbieter eines Drittanbieters wie Ping ID oder secureAuth verwenden, sollten Sie "Nicht-AAD" als Identitätstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="add86-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="add86-160">![Wählen Sie den Berechtigungsbildschirm aus, der von einem Administrator abgeschlossen wurde. Der Administrator hat die Option "Nur Personen mit Zugriff auf diese Datenquelle" ausgewählt und auch "AAD" aus einem Dropdownmenü mit Identitätstypen ausgewählt.](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="add86-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="add86-161">Wenn Sie eine ACL aus Ihrer Salesforce-Instanz aufgenommen und "Nicht-AAD" für den Identitätstyp ausgewählt haben, finden Sie unter [Map your non-Azure AD Identities](map-non-aad.md) Anweisungen zum Zuordnen der Identitäten.</span><span class="sxs-lookup"><span data-stu-id="add86-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="step-4b-map-aad-identities"></a><span data-ttu-id="add86-162">Schritt 4.b: Zuordnung von AAD-Identitäten</span><span class="sxs-lookup"><span data-stu-id="add86-162">Step 4.b: Map AAD identities</span></span>

<span data-ttu-id="add86-163">Wenn Sie eine ACL aus Ihrer Salesforce-Instanz aufgenommen und "AAD" für den Identitätstyp ausgewählt haben, finden Sie unter [Map your Azure AD Identities](map-aad.md) Anweisungen zum Zuordnen der Identitäten.</span><span class="sxs-lookup"><span data-stu-id="add86-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="add86-164">Informationen zum Einrichten von Azure AD SSO für Salesforce finden Sie in diesem [Lernprogramm](/azure/active-directory/saas-apps/salesforce-tutorial).</span><span class="sxs-lookup"><span data-stu-id="add86-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

### <a name="apply-user-mapping-to-sync-your-salesforce-identities-to-azure-ad-identities"></a><span data-ttu-id="add86-165">Anwenden der Benutzerzuordnung zum Synchronisieren Ihrer Salesforce-Identitäten mit Azure AD-Identitäten</span><span class="sxs-lookup"><span data-stu-id="add86-165">Apply user mapping to sync your Salesforce identities to Azure AD identities</span></span>

<span data-ttu-id="add86-166">In diesem Video können Sie sehen, wie Sie sich bei Ihrer Salesforce-Instanz authentifizieren, Ihre Nicht-Azure Active Directory-Identitäten mit Ihren Azure Active Directory-Identitäten synchronisieren und die richtigen Sicherheitstrimmer auf Ihre Salesforce-Elemente anwenden.</span><span class="sxs-lookup"><span data-stu-id="add86-166">In this video you can see the process to authenticate to your Salesforce instance, sync your non-Azure Active Directory identities to your Azure Active Directory identities, and apply the proper security trimmings to your Salesforce items.</span></span>

> [!VIDEO https://www.youtube.com/watch?v=SZYiFxZMKcM]

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="add86-167">Schritt 5: Zuweisen von Eigenschaftsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="add86-167">Step 5: Assign property labels</span></span>

<span data-ttu-id="add86-168">Sie können jeder Bezeichnung eine Quelleigenschaft zuweisen, indem Sie aus einem Menü mit Optionen auswählen.</span><span class="sxs-lookup"><span data-stu-id="add86-168">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="add86-169">Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaftsbezeichnungen verbessern die Suchrelevanz und sorgen für bessere Suchergebnisse für Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="add86-169">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="add86-170">Standardmäßig wurden einigen Bezeichnungen wie "Title", "URL", "CreatedBy" und "LastModifiedBy" bereits Quelleigenschaften zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="add86-170">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="add86-171">Schritt 6: Verwalten des Schemas</span><span class="sxs-lookup"><span data-stu-id="add86-171">Step 6: Manage schema</span></span>

<span data-ttu-id="add86-172">Sie können auswählen, welche Quelleigenschaften indiziert werden sollen, damit sie in den Suchergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="add86-172">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="add86-173">Der Verbindungs-Assistent wählt standardmäßig ein Suchschema basierend auf einer Reihe von Quelleigenschaften aus.</span><span class="sxs-lookup"><span data-stu-id="add86-173">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="add86-174">Sie können dies ändern, indem Sie die Kontrollkästchen für jede Eigenschaft und jedes Attribut auf der Suchschemaseite aktivieren.</span><span class="sxs-lookup"><span data-stu-id="add86-174">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="add86-175">Suchschemaattribute sind Search, Query, Retrieve und Refine.</span><span class="sxs-lookup"><span data-stu-id="add86-175">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="add86-176">Mit Einschränkungen können Sie die Eigenschaften definieren, die später als benutzerdefinierte Einschränkungen oder Filter in der Sucherfahrung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="add86-176">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="add86-177">![Wählen Sie das Schema für jede Quelleigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="add86-177">![Select the schema for each source property.</span></span> <span data-ttu-id="add86-178">Die Optionen sind Query, Search, Retrieve und Refine.](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="add86-178">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="add86-179">Schritt 7: Festlegen des Aktualisierungszeitplans</span><span class="sxs-lookup"><span data-stu-id="add86-179">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="add86-180">Der Salesforce-Connector unterstützt derzeit nur Aktualisierungszeitpläne für vollständige Durchforstungen.</span><span class="sxs-lookup"><span data-stu-id="add86-180">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="add86-181">Bei einer vollständigen Durchforstung werden gelöschte Objekte und Benutzer gefunden, die zuvor mit dem Microsoft Search-Index synchronisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="add86-181">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="add86-182">Der empfohlene Zeitplan ist eine Woche für eine vollständige Durchforstung.</span><span class="sxs-lookup"><span data-stu-id="add86-182">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="add86-183">Schritt 8: Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="add86-183">Step 8: Review connection</span></span>

<span data-ttu-id="add86-184">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="add86-184">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="add86-185">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="add86-185">Limitations</span></span>

- <span data-ttu-id="add86-186">Der Graph unterstützt derzeit keine Apex-basierte, gebietsbasierte Freigabe und Freigabe mithilfe persönlicher Gruppen aus Salesforce.</span><span class="sxs-lookup"><span data-stu-id="add86-186">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="add86-187">Es gibt einen bekannten Fehler in der Salesforce-API, die der Graph-Connector verwendet, wobei die privaten organisationsweiten Standardwerte für Leads derzeit nicht berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="add86-187">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="add86-188">Wenn für ein Feld die Sicherheit auf Feldebene (Field Level Security, FLS) für ein Profil festgelegt ist, wird das Feld vom Graph-Connector nicht für Profile in dieser Salesforce-Organisation aufgenommen. Daher können Benutzer nicht nach Werten für diese Felder suchen, und sie werden auch nicht in den Ergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="add86-188">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="add86-189">Im Bildschirm Schema verwalten werden diese allgemeinen Standardeigenschaftsnamen einmal aufgelistet, die Optionen **sind Query,** **Search,** **Retrieve** und **Refine** und gelten für alle oder keine.</span><span class="sxs-lookup"><span data-stu-id="add86-189">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="add86-190">Name</span><span class="sxs-lookup"><span data-stu-id="add86-190">Name</span></span>
    - <span data-ttu-id="add86-191">Url</span><span class="sxs-lookup"><span data-stu-id="add86-191">Url</span></span>
    - <span data-ttu-id="add86-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="add86-192">Description</span></span>
    - <span data-ttu-id="add86-193">Fax</span><span class="sxs-lookup"><span data-stu-id="add86-193">Fax</span></span>
    - <span data-ttu-id="add86-194">Telefon</span><span class="sxs-lookup"><span data-stu-id="add86-194">Phone</span></span>
    - <span data-ttu-id="add86-195">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="add86-195">MobilePhone</span></span>
    - <span data-ttu-id="add86-196">E-Mails</span><span class="sxs-lookup"><span data-stu-id="add86-196">Email</span></span>
    - <span data-ttu-id="add86-197">Typ</span><span class="sxs-lookup"><span data-stu-id="add86-197">Type</span></span>
    - <span data-ttu-id="add86-198">Titel</span><span class="sxs-lookup"><span data-stu-id="add86-198">Title</span></span>
    - <span data-ttu-id="add86-199">AccountId</span><span class="sxs-lookup"><span data-stu-id="add86-199">AccountId</span></span>
    - <span data-ttu-id="add86-200">AccountName</span><span class="sxs-lookup"><span data-stu-id="add86-200">AccountName</span></span>
    - <span data-ttu-id="add86-201">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="add86-201">AccountUrl</span></span>
    - <span data-ttu-id="add86-202">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="add86-202">AccountOwner</span></span>
    - <span data-ttu-id="add86-203">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="add86-203">AccountOwnerUrl</span></span>
    - <span data-ttu-id="add86-204">Besitzer</span><span class="sxs-lookup"><span data-stu-id="add86-204">Owner</span></span>
    - <span data-ttu-id="add86-205">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="add86-205">OwnerUrl</span></span>
    - <span data-ttu-id="add86-206">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="add86-206">CreatedBy</span></span>
    - <span data-ttu-id="add86-207">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="add86-207">CreatedByUrl</span></span>
    - <span data-ttu-id="add86-208">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="add86-208">LastModifiedBy</span></span>
    - <span data-ttu-id="add86-209">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="add86-209">LastModifiedByUrl</span></span>
    - <span data-ttu-id="add86-210">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="add86-210">LastModifiedDate</span></span>
    - <span data-ttu-id="add86-211">ObjectName</span><span class="sxs-lookup"><span data-stu-id="add86-211">ObjectName</span></span>
