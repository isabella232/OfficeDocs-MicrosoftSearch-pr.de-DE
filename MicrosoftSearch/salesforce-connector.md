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
description: Einrichten des Salesforce Graph-Connectors für Microsoft Search
ms.openlocfilehash: 4bef771538934722deaa5deac3959f21246e4529
ms.sourcegitcommit: 93fc70f0073ab45b4dbd702441ac2fc07a7668bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230934"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="d209e-103">Salesforce Graph Connector (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="d209e-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="d209e-104">Der Salesforce Graph Connector ermöglicht Ihrer Organisation das Indizieren von Kontakten, Verkaufschancen, Leads und Kontenobjekten in Ihrer Salesforce-Instanz.</span><span class="sxs-lookup"><span data-stu-id="d209e-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="d209e-105">Nachdem Sie den Connector konfiguriert und Inhalte von Salesforce indiziert haben, können Endbenutzer von einem beliebigen Microsoft Search Client nach diesen Elementen suchen.</span><span class="sxs-lookup"><span data-stu-id="d209e-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="d209e-106">Lesen Sie den Artikel [**"Setup for your Graph connector",**](configure-connector.md) um die allgemeinen Anweisungen zum Einrichten Graph Connectors zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="d209e-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="d209e-107">Dieser Artikel richtet sich an alle Personen, die einen Salesforce Graph Connector konfigurieren, ausführen und überwachen.</span><span class="sxs-lookup"><span data-stu-id="d209e-107">This article is for anyone who configures, runs, and monitors a Salesforce Graph connector.</span></span> <span data-ttu-id="d209e-108">Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Salesforce Graph Connector gelten.</span><span class="sxs-lookup"><span data-stu-id="d209e-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="d209e-109">Dieser Artikel enthält auch Informationen zu [Einschränkungen.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="d209e-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="d209e-110">Der Salesforce Graph Connector unterstützt derzeit Summer '19 oder höher.</span><span class="sxs-lookup"><span data-stu-id="d209e-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="d209e-111">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="d209e-111">Before you get started</span></span>

<span data-ttu-id="d209e-112">Um eine Verbindung mit Ihrer Salesforce-Instanz herzustellen, benötigen Sie ihre Salesforce-Instanz-URL, die Client-ID und den geheimen Clientschlüssel für die OAuth-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d209e-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="d209e-113">In den folgenden Schritten wird erläutert, wie Sie oder Ihr Salesforce-Administrator diese Informationen aus Ihrem Salesforce-Konto abrufen können:</span><span class="sxs-lookup"><span data-stu-id="d209e-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="d209e-114">Melden Sie sich bei Ihrer Salesforce-Instanz an, und wechseln Sie zum Setup</span><span class="sxs-lookup"><span data-stu-id="d209e-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="d209e-115">Navigieren Sie zum App-> App-Manager.</span><span class="sxs-lookup"><span data-stu-id="d209e-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="d209e-116">Wählen Sie **"Neue verbundene App" aus.**</span><span class="sxs-lookup"><span data-stu-id="d209e-116">Select **New connected app**.</span></span>

- <span data-ttu-id="d209e-117">Führen Sie den API-Abschnitt wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d209e-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="d209e-118">Aktivieren Sie das Kontrollkästchen für **Oauth Einstellungen aktivieren.**</span><span class="sxs-lookup"><span data-stu-id="d209e-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="d209e-119">Geben Sie die Rückruf-URL folgendermaßen an: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="d209e-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="d209e-120">Wählen Sie diese erforderlichen OAuth-Bereiche aus.</span><span class="sxs-lookup"><span data-stu-id="d209e-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="d209e-121">Zugreifen auf und Verwalten Ihrer Daten (API)</span><span class="sxs-lookup"><span data-stu-id="d209e-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="d209e-122">Jederzeit Anforderungen in Ihrem Auftrag ausführen (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="d209e-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="d209e-123">Aktivieren Sie das Kontrollkästchen für **"Geheimen Schlüssel für Webserverfluss anfordern".**</span><span class="sxs-lookup"><span data-stu-id="d209e-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="d209e-124">Speichern Sie die App.</span><span class="sxs-lookup"><span data-stu-id="d209e-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="d209e-125">![API-Abschnitt in Salesforce-Instanz, nachdem der Administrator alle oben aufgeführten erforderlichen Konfigurationen eingegeben hat.](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="d209e-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="d209e-126">Kopieren Sie den Verbraucherschlüssel und den geheimen Verbraucherschlüssel.</span><span class="sxs-lookup"><span data-stu-id="d209e-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="d209e-127">Diese Informationen werden als Client-ID und geheimer Clientschlüssel verwendet, wenn Sie die Verbindungs-Einstellungen für Ihren Graph Connector im Microsoft 365 Verwaltungsportal konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d209e-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="d209e-128">![Ergebnisse, die vom API-Abschnitt in der Salesforce-Instanz zurückgegeben werden, nachdem der Administrator alle erforderlichen Konfigurationen übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="d209e-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="d209e-129">Der Verbraucherschlüssel befindet sich oben in der linken Spalte, und der geheime Verbraucherschlüssel befindet sich oben in der rechten Spalte.](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="d209e-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="d209e-130">Führen Sie vor dem Schließen der Salesforce-Instanz die folgenden Schritte aus, um sicherzustellen, dass Aktualisierungstoken nicht ablaufen:</span><span class="sxs-lookup"><span data-stu-id="d209e-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="d209e-131">Wechseln Sie zu "Apps > App Manager"</span><span class="sxs-lookup"><span data-stu-id="d209e-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="d209e-132">Suchen Sie die von Ihnen erstellte App, und wählen Sie die Dropdownliste auf der rechten Seite aus.</span><span class="sxs-lookup"><span data-stu-id="d209e-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="d209e-133">Wählen Sie **"Verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="d209e-133">Select **Manage**</span></span>
    - <span data-ttu-id="d209e-134">Auswählen von **Bearbeitungsrichtlinien**</span><span class="sxs-lookup"><span data-stu-id="d209e-134">Select **edit policies**</span></span>
    - <span data-ttu-id="d209e-135">Wählen Sie für die Aktualisierungstokenrichtlinie die Option **"Aktualisierungstoken ist gültig bis widerrufen"** aus.</span><span class="sxs-lookup"><span data-stu-id="d209e-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="d209e-136">![Wählen Sie die Aktualisierungstokenrichtlinie mit dem Namen "Aktualisierungstoken ist gültig bis zum Widerrufen" aus.](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="d209e-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="d209e-137">Sie können jetzt das [Microsoft 365 Admin Center](https://admin.microsoft.com/) verwenden, um den restlichen Setupprozess für Ihren Graph Connector abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d209e-137">You can now use the [Microsoft 365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="d209e-138">Schritt 1: Hinzufügen eines Graph Connectors im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="d209e-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="d209e-139">Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="d209e-139">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="d209e-140">Schritt 2: Benennen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="d209e-140">Step 2: Name the connection</span></span>

<span data-ttu-id="d209e-141">Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="d209e-141">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="d209e-142">Schritt 3: Konfigurieren der Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="d209e-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="d209e-143">Verwenden Sie für die Instanz-URL https://[domain].my.salesforce.com</a0>, wobei domäne die Salesforce-Domäne für Ihre Organisation wäre.</span><span class="sxs-lookup"><span data-stu-id="d209e-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="d209e-144">Geben Sie die Client-ID und den geheimen Clientschlüssel ein, die Sie von Ihrer Salesforce-Instanz erhalten haben, und wählen Sie "Anmelden" aus.</span><span class="sxs-lookup"><span data-stu-id="d209e-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="d209e-145">Wenn Sie zum ersten Mal versucht haben, sich mit diesen Einstellungen anzumelden, erhalten Sie ein Popup, in dem Sie aufgefordert werden, sich mit Ihrem Administratorbenutzernamen und -kennwort bei Salesforce anzumelden.</span><span class="sxs-lookup"><span data-stu-id="d209e-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="d209e-146">Der screenshot unten zeigt das Popup.</span><span class="sxs-lookup"><span data-stu-id="d209e-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="d209e-147">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie "Anmelden" aus.</span><span class="sxs-lookup"><span data-stu-id="d209e-147">Enter your credentials and select "Log In".</span></span>

  ![Melden Sie sich an und fragen Sie nach Benutzername und Kennwort.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="d209e-149">Wenn das Popup nicht angezeigt wird, wird es möglicherweise in Ihrem Browser blockiert, daher müssen Sie Popups und Umleitungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="d209e-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="d209e-150">Überprüfen Sie, ob die Verbindung erfolgreich war, indem Sie nach einem grünen Banner suchen, das "Verbindung erfolgreich" anzeigt, wie im screenshot unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d209e-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="d209e-151">![Screenshot der erfolgreichen Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="d209e-151">![Screenshot of successful login.</span></span> <span data-ttu-id="d209e-152">Das grüne Banner mit der Bezeichnung "Verbindung erfolgreich" befindet sich unter dem Feld für Ihre Salesforce-Instanz-URL.](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="d209e-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="d209e-153">Schritt 4: Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="d209e-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="d209e-154">Sie müssen auswählen, welche Benutzer Suchergebnisse aus dieser Datenquelle sehen.</span><span class="sxs-lookup"><span data-stu-id="d209e-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="d209e-155">Wenn Sie nur bestimmten Azure Active Directory (Azure AD) oder Nicht-Azure AD-Benutzern erlauben, die Suchergebnisse anzuzeigen, stellen Sie sicher, dass Sie die Identitäten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d209e-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

### <a name="step-4a-select-permissions"></a><span data-ttu-id="d209e-156">Schritt 4.a: Auswählen von Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d209e-156">Step 4.a: Select permissions</span></span>

<span data-ttu-id="d209e-157">Sie können auswählen, ob Sie Zugriffssteuerungslisten (Access Control Lists, ACLs) aus Ihrer Salesforce-Instanz erfassen möchten, oder allen Benutzern in Ihrer Organisation ermöglichen, Suchergebnisse aus dieser Datenquelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d209e-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="d209e-158">ACLs können Azure Active Directory (AAD)-Identitäten (Benutzer, die von Azure AD mit Salesforce verbunden sind), Nicht-Azure AD-Identitäten (systemeigene Salesforce-Benutzer, die über entsprechende Identitäten in Azure AD verfügen) oder beides umfassen.</span><span class="sxs-lookup"><span data-stu-id="d209e-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="d209e-159">Wenn Sie einen Identitätsanbieter eines Drittanbieters wie Ping-ID oder secureAuth verwenden, sollten Sie "Nicht-AAD" als Identitätstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="d209e-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d209e-160">![Bildschirm "Berechtigungen auswählen", der von einem Administrator abgeschlossen wurde. Der Administrator hat die Option "Nur Personen mit Zugriff auf diese Datenquelle" ausgewählt und auch "AAD" aus einem Dropdownmenü mit Identitätstypen ausgewählt.](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="d209e-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="d209e-161">Wenn Sie sich entschieden haben, eine ACL aus Ihrer Salesforce-Instanz zu erfassen, und "nicht-AAD" für den Identitätstyp ausgewählt haben, finden Sie anweisungen zum Zuordnen der Identitäten zu [Ihren Nicht-Azure AD-Identitäten.](map-non-aad.md)</span><span class="sxs-lookup"><span data-stu-id="d209e-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="step-4b-map-aad-identities"></a><span data-ttu-id="d209e-162">Schritt 4.b: Zuordnen von AAD-Identitäten</span><span class="sxs-lookup"><span data-stu-id="d209e-162">Step 4.b: Map AAD identities</span></span>

<span data-ttu-id="d209e-163">Wenn Sie sich entschieden haben, eine ACL aus Ihrer Salesforce-Instanz zu erfassen, und "AAD" für den Identitätstyp ausgewählt haben, finden Sie unter ["Zuordnen Ihrer Azure AD-Identitäten"](map-aad.md) Anweisungen zum Zuordnen der Identitäten.</span><span class="sxs-lookup"><span data-stu-id="d209e-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="d209e-164">Informationen zum Einrichten von Azure AD SSO für Salesforce finden Sie in diesem [Lernprogramm.](/azure/active-directory/saas-apps/salesforce-tutorial)</span><span class="sxs-lookup"><span data-stu-id="d209e-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

### <a name="apply-user-mapping-to-sync-your-salesforce-identities-to-azure-ad-identities"></a><span data-ttu-id="d209e-165">Anwenden der Benutzerzuordnung zum Synchronisieren Ihrer Salesforce-Identitäten mit Azure AD-Identitäten</span><span class="sxs-lookup"><span data-stu-id="d209e-165">Apply user mapping to sync your Salesforce identities to Azure AD identities</span></span>

<span data-ttu-id="d209e-166">In diesem Video sehen Sie, wie Sie sich bei Ihrer Salesforce-Instanz authentifizieren, Ihre nicht Azure Active Directory Identitäten mit Ihren Azure Active Directory Identitäten synchronisieren und die richtigen Sicherheitskürzungen auf Ihre Salesforce-Elemente anwenden.</span><span class="sxs-lookup"><span data-stu-id="d209e-166">In this video you can see the process to authenticate to your Salesforce instance, sync your non-Azure Active Directory identities to your Azure Active Directory identities, and apply the proper security trimmings to your Salesforce items.</span></span>

> [!VIDEO https://www.youtube-nocookie.com/embed/SZYiFxZMKcM]

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="d209e-167">Schritt 5: Zuweisen von Eigenschaftenbeschriftungen</span><span class="sxs-lookup"><span data-stu-id="d209e-167">Step 5: Assign property labels</span></span>

<span data-ttu-id="d209e-168">Sie können jeder Bezeichnung eine Quelleigenschaft zuweisen, indem Sie aus einem Menü mit Optionen auswählen.</span><span class="sxs-lookup"><span data-stu-id="d209e-168">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="d209e-169">Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaftenbezeichnungen verbessern die Suchrelevanz und stellen bessere Suchergebnisse für Endbenutzer sicher.</span><span class="sxs-lookup"><span data-stu-id="d209e-169">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="d209e-170">Standardmäßig wurden einigen Bezeichnungen wie "Title", "URL", "CreatedBy" und "LastModifiedBy" bereits Quelleigenschaften zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d209e-170">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="d209e-171">Schritt 6: Verwalten des Schemas</span><span class="sxs-lookup"><span data-stu-id="d209e-171">Step 6: Manage schema</span></span>

<span data-ttu-id="d209e-172">Sie können auswählen, welche Quelleigenschaften indiziert werden sollen, damit sie in suchergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d209e-172">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="d209e-173">Der Verbindungs-Assistent wählt standardmäßig ein Suchschema aus, das auf einer Reihe von Quelleigenschaften basiert.</span><span class="sxs-lookup"><span data-stu-id="d209e-173">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="d209e-174">Sie können sie ändern, indem Sie die Kontrollkästchen für jede Eigenschaft und jedes Attribut auf der Suchschemaseite aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d209e-174">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="d209e-175">Zu den Suchschemaattributen gehören Suche, Abfrage, Abrufen und Verfeinern.</span><span class="sxs-lookup"><span data-stu-id="d209e-175">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="d209e-176">Mit der Verfeinerung können Sie die Eigenschaften definieren, die später als benutzerdefinierte Einschränkungen oder Filter in der Suchumgebung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d209e-176">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d209e-177">![Wählen Sie das Schema für jede Quelleigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="d209e-177">![Select the schema for each source property.</span></span> <span data-ttu-id="d209e-178">Die Optionen sind "Abfrage", "Suchen", "Abrufen" und "Verfeinern".](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="d209e-178">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="d209e-179">Schritt 7: Festlegen des Aktualisierungszeitplans</span><span class="sxs-lookup"><span data-stu-id="d209e-179">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="d209e-180">Der Salesforce-Connector unterstützt derzeit nur Aktualisierungszeitpläne für vollständige Durchforstungen.</span><span class="sxs-lookup"><span data-stu-id="d209e-180">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d209e-181">Bei einer vollständigen Durchforstung werden gelöschte Objekte und Benutzer gefunden, die zuvor mit dem Microsoft Search-Index synchronisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d209e-181">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="d209e-182">Der empfohlene Zeitplan ist eine Woche für eine vollständige Durchforstung.</span><span class="sxs-lookup"><span data-stu-id="d209e-182">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="d209e-183">Schritt 8: Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="d209e-183">Step 8: Review connection</span></span>

<span data-ttu-id="d209e-184">Folgen Sie den allgemeinen [Setupanweisungen.](./configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="d209e-184">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="d209e-185">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="d209e-185">Limitations</span></span>

- <span data-ttu-id="d209e-186">Der Graph Connector unterstützt derzeit keine Apex-basierte, gebietsbasierte Freigabe und Freigabe mit persönlichen Gruppen von Salesforce.</span><span class="sxs-lookup"><span data-stu-id="d209e-186">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="d209e-187">Es gibt einen bekannten Fehler in der Salesforce-API, den der Graph Connector verwendet, bei dem die privaten organisationsweiten Standardwerte für Leads derzeit nicht berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="d209e-187">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="d209e-188">Wenn für ein Feld die Sicherheit auf Feldebene (FLS) für ein Profil festgelegt ist, erfasst der Graph Connector dieses Feld nicht für Profile in dieser Salesforce-Organisation. Daher können Benutzer weder nach Werten für diese Felder suchen noch in den Ergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d209e-188">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="d209e-189">Im Bildschirm "Schema verwalten" werden diese allgemeinen Standardeigenschaftsnamen einmal aufgelistet. Die Optionen sind **"Abfrage",** **"Suchen",** **"Abrufen"** und **"Verfeinern"** und gelten für alle oder keine.</span><span class="sxs-lookup"><span data-stu-id="d209e-189">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="d209e-190">Name</span><span class="sxs-lookup"><span data-stu-id="d209e-190">Name</span></span>
    - <span data-ttu-id="d209e-191">Url</span><span class="sxs-lookup"><span data-stu-id="d209e-191">Url</span></span>
    - <span data-ttu-id="d209e-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d209e-192">Description</span></span>
    - <span data-ttu-id="d209e-193">Fax</span><span class="sxs-lookup"><span data-stu-id="d209e-193">Fax</span></span>
    - <span data-ttu-id="d209e-194">Telefon</span><span class="sxs-lookup"><span data-stu-id="d209e-194">Phone</span></span>
    - <span data-ttu-id="d209e-195">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="d209e-195">MobilePhone</span></span>
    - <span data-ttu-id="d209e-196">E-Mails</span><span class="sxs-lookup"><span data-stu-id="d209e-196">Email</span></span>
    - <span data-ttu-id="d209e-197">Typ</span><span class="sxs-lookup"><span data-stu-id="d209e-197">Type</span></span>
    - <span data-ttu-id="d209e-198">Titel</span><span class="sxs-lookup"><span data-stu-id="d209e-198">Title</span></span>
    - <span data-ttu-id="d209e-199">Accountid</span><span class="sxs-lookup"><span data-stu-id="d209e-199">AccountId</span></span>
    - <span data-ttu-id="d209e-200">AccountName</span><span class="sxs-lookup"><span data-stu-id="d209e-200">AccountName</span></span>
    - <span data-ttu-id="d209e-201">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="d209e-201">AccountUrl</span></span>
    - <span data-ttu-id="d209e-202">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="d209e-202">AccountOwner</span></span>
    - <span data-ttu-id="d209e-203">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="d209e-203">AccountOwnerUrl</span></span>
    - <span data-ttu-id="d209e-204">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d209e-204">Owner</span></span>
    - <span data-ttu-id="d209e-205">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="d209e-205">OwnerUrl</span></span>
    - <span data-ttu-id="d209e-206">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="d209e-206">CreatedBy</span></span>
    - <span data-ttu-id="d209e-207">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="d209e-207">CreatedByUrl</span></span>
    - <span data-ttu-id="d209e-208">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="d209e-208">LastModifiedBy</span></span>
    - <span data-ttu-id="d209e-209">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="d209e-209">LastModifiedByUrl</span></span>
    - <span data-ttu-id="d209e-210">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="d209e-210">LastModifiedDate</span></span>
    - <span data-ttu-id="d209e-211">ObjectName</span><span class="sxs-lookup"><span data-stu-id="d209e-211">ObjectName</span></span>
