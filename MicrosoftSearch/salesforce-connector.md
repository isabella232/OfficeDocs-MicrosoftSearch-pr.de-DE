---
title: Salesforce Connector für Microsoft Search
ms.author: rusamai
author: rsamai
manager: jameslao
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Einrichten von Salesforce Connector für Microsoft Search
ms.openlocfilehash: 8de7784cae7d430bc385889bd836360c69492591
ms.sourcegitcommit: 77ec27736f3c8434b2ac47e10897ac2606ee8a03
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "48992916"
---
# <a name="salesforce-connector"></a><span data-ttu-id="58c49-103">Salesforce Connector</span><span class="sxs-lookup"><span data-stu-id="58c49-103">Salesforce connector</span></span>

<span data-ttu-id="58c49-104">Mit dem Salesforce Graph-Konnektor kann Ihre Organisation Kontakte, Verkaufschancen, Leads und Accounts-Objekte in ihrer Salesforce-Instanz indizieren.</span><span class="sxs-lookup"><span data-stu-id="58c49-104">With the Salesforce Graph connector, your organization can index Contacts, Opportunities, Leads and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="58c49-105">Nachdem Sie den Connector-und den Index Inhalt von Salesforce konfiguriert haben, können Endbenutzer nach diesen Elementen von einem beliebigen Microsoft Search-Client aus suchen.</span><span class="sxs-lookup"><span data-stu-id="58c49-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client</span></span>

<span data-ttu-id="58c49-106">Dieser Artikel richtet sich an [Microsoft 365](https://www.microsoft.com/microsoft-365) -Administratoren oder Personen, die einen Salesforce Connector konfigurieren, ausführen und überwachen.</span><span class="sxs-lookup"><span data-stu-id="58c49-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors a Salesforce connector.</span></span> <span data-ttu-id="58c49-107">Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="58c49-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="58c49-108">Der Salesforce Graph Connector unterstützt derzeit die 19 Versionen Sommer 20, Frühling 20, Winter 20 und Sommer.</span><span class="sxs-lookup"><span data-stu-id="58c49-108">The Salesforce Graph connector currently supports Summer ’20, Spring’20, Winter’20, and Summer ’19 versions.</span></span>

## <a name="connection-settings"></a><span data-ttu-id="58c49-109">Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="58c49-109">Connection settings</span></span>

<span data-ttu-id="58c49-110">Zum Herstellen einer Verbindung mit ihrer Salesforce-Instanz benötigen Sie die Salesforce-Instanz-URL, die Client-ID und den geheimen Client Schlüssel für die OAuth-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="58c49-110">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="58c49-111">In den folgenden Schritten wird erklärt, wie Sie oder Ihr Salesforce-Administrator diese Informationen von Ihrem Salesforce-Konto abrufen können:</span><span class="sxs-lookup"><span data-stu-id="58c49-111">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="58c49-112">Melden Sie sich bei ihrer Salesforce-Instanz an, und wechseln Sie zu Setup</span><span class="sxs-lookup"><span data-stu-id="58c49-112">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="58c49-113">Navigieren Sie zu apps-> App-Manager.</span><span class="sxs-lookup"><span data-stu-id="58c49-113">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="58c49-114">Wählen Sie **neue verbundene App** aus.</span><span class="sxs-lookup"><span data-stu-id="58c49-114">Select **New connected app**.</span></span>

- <span data-ttu-id="58c49-115">Schließen Sie den API-Abschnitt wie folgt ab:</span><span class="sxs-lookup"><span data-stu-id="58c49-115">Complete the API section as follows:</span></span>

    - <span data-ttu-id="58c49-116">Aktivieren Sie das Kontrollkästchen für **OAuth-Einstellungen aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="58c49-116">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="58c49-117">Geben Sie die Rückruf-URL wie folgt an: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="58c49-117">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="58c49-118">Wählen Sie diese erforderlichen OAuth-Bereiche aus.</span><span class="sxs-lookup"><span data-stu-id="58c49-118">Select these required OAuth scopes.</span></span> 

        - <span data-ttu-id="58c49-119">Zugreifen auf und Verwalten von Daten (API)</span><span class="sxs-lookup"><span data-stu-id="58c49-119">Access and manage your data (api)</span></span> 

        - <span data-ttu-id="58c49-120">Ausführen von Anforderungen in Ihrem Namen zu einem beliebigen Zeitpunkt (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="58c49-120">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span> 

    - <span data-ttu-id="58c49-121">Aktivieren Sie das Kontrollkästchen für **geheimen Webserver Fluss erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="58c49-121">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="58c49-122">Speichern Sie die app.</span><span class="sxs-lookup"><span data-stu-id="58c49-122">Save the app.</span></span>
    
      ![API-Abschnitt in Salesforce instance, nachdem Administrator alle oben aufgeführten erforderlichen Konfigurationen eingegeben hat.](media/salesforce-connector/sf1.png)

- <span data-ttu-id="58c49-124">Kopieren Sie den Consumer-Schlüssel und das Consumer-Geheimnis.</span><span class="sxs-lookup"><span data-stu-id="58c49-124">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="58c49-125">Diese werden als Client-ID und den geheimen Client Schlüssel verwendet, wenn Sie die Verbindungseinstellungen für Ihren Graph-Konnektor im Microsoft 365-Verwaltungsportal konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="58c49-125">These will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  ![Vom API-Abschnitt zurückgegebene Ergebnisse in der Salesforce-Instanz, nachdem der Administrator alle erforderlichen Konfigurationen übermittelt hat.](media/salesforce-connector/clientsecret.png)
- <span data-ttu-id="58c49-128">Führen Sie vor dem Schließen der Salesforce-Instanz die folgenden Schritte aus, um sicherzustellen, dass Aktualisierungstoken nicht ablaufen:</span><span class="sxs-lookup"><span data-stu-id="58c49-128">Before closing your Salesforce instance, perform the following steps to ensure that refresh tokens do not expire:</span></span> 
    - <span data-ttu-id="58c49-129">Wechseln Sie zu apps-> App-Manager</span><span class="sxs-lookup"><span data-stu-id="58c49-129">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="58c49-130">Suchen Sie die soeben erstellte APP, und wählen Sie die Dropdownliste rechts aus.</span><span class="sxs-lookup"><span data-stu-id="58c49-130">Find the app you just created and select the drop down on the right.</span></span> <span data-ttu-id="58c49-131">Wählen Sie **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="58c49-131">Select **Manage**</span></span>
    - <span data-ttu-id="58c49-132">Auswählen von **Richtlinien bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="58c49-132">Select **edit policies**</span></span>
    - <span data-ttu-id="58c49-133">Wählen Sie für Aktualisierungstoken-Richtlinie **die Option Aktualisierungstoken gilt bis zum Widerruf** aus.</span><span class="sxs-lookup"><span data-stu-id="58c49-133">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  ![Wählen Sie die Aktualisierungstoken-Richtlinie mit dem Namen "Aktualisierungstoken ist gültig bis Widerruf" aus.](media/salesforce-connector/oauthpolicies.png)

<span data-ttu-id="58c49-135">Sie können jetzt das [M365 Admin Center](https://admin.microsoft.com/) verwenden, um den restlichen Setupvorgang für Ihren Graph-Konnektor abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="58c49-135">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>  

<span data-ttu-id="58c49-136">Konfigurieren Sie die Verbindungseinstellungen für Ihren Graph-Konnektor wie folgt:</span><span class="sxs-lookup"><span data-stu-id="58c49-136">Configure the Connection settings for your Graph connector as follows:</span></span>

- <span data-ttu-id="58c49-137">Verwenden Sie für die Instanz-URL https://[Domäne]. My. salesforce. com, wobei Domäne die Salesforce-Domäne für Ihre Organisation wäre.</span><span class="sxs-lookup"><span data-stu-id="58c49-137">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span> 
- <span data-ttu-id="58c49-138">Geben Sie die von ihrer Salesforce-Instanz abgerufene Client-ID und den geheimen Client Schlüssel ein, und wählen Sie anmelden aus.</span><span class="sxs-lookup"><span data-stu-id="58c49-138">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>
- <span data-ttu-id="58c49-139">Wenn Sie zum ersten Mal versucht haben, sich mit diesen Einstellungen anzumelden, erhalten Sie ein Popup, in dem Sie aufgefordert werden, sich mit Ihrem Administrator-Benutzernamen und-Kennwort bei Salesforce anzumelden.</span><span class="sxs-lookup"><span data-stu-id="58c49-139">If this is the first time you have attempted to Sign in with these settings, you will get a pop up asking you to login to Salesforce with your admin username and password.</span></span> <span data-ttu-id="58c49-140">Das folgende Screenshot zeigt das Popup.</span><span class="sxs-lookup"><span data-stu-id="58c49-140">The screenshot below shows the popup.</span></span> <span data-ttu-id="58c49-141">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie anmelden aus.</span><span class="sxs-lookup"><span data-stu-id="58c49-141">Enter your credentials and select Log in.</span></span>

  ![Melden Sie sich an, und Fragen Sie nach Benutzername und Kennwort.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="58c49-143">Wenn das Popup nicht angezeigt wird, wird es möglicherweise in Ihrem Browser blockiert, sodass Sie Popups und Umleitungen zulassen müssen.</span><span class="sxs-lookup"><span data-stu-id="58c49-143">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

  >[!NOTE]
  ><span data-ttu-id="58c49-144">Wenn Ihre Organisation einmaliges Anmelden (SSO) verwendet, können Sie in der unteren rechten Ecke der Anmelde Schnittstelle die Option **benutzerdefinierte Domäne verwenden** auswählen.</span><span class="sxs-lookup"><span data-stu-id="58c49-144">If your organization uses single sign-on (SSO), you can select **Use Custom Domain** in the bottom, right-hand corner of the login interface.</span></span> <span data-ttu-id="58c49-145">Geben Sie die Domäne ein, und wählen Sie dann **weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="58c49-145">Enter the domain and then select **Continue**.</span></span> <span data-ttu-id="58c49-146">Sie wird auf Ihrer organisationsspezifischen Anmeldeseite angezeigt, auf der Sie eine Option zur Anmeldung bei SSO haben.</span><span class="sxs-lookup"><span data-stu-id="58c49-146">It will go to your organization specific login page where you will have an option to login with SSO.</span></span>

- <span data-ttu-id="58c49-147">Überprüfen Sie, ob die Verbindung erfolgreich war, indem Sie nach einem grünen Banner suchen, das besagt, dass die Verbindung erfolgreich verläuft, wie im Screenshot unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="58c49-147">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  ![Screenshot der erfolgreichen Anmeldung.](media/salesforce-connector/sf5.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="58c49-150">Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="58c49-150">Manage search permissions</span></span>
<span data-ttu-id="58c49-151">Sie müssen auswählen, welche Benutzer Suchergebnisse aus dieser Datenquelle erhalten.</span><span class="sxs-lookup"><span data-stu-id="58c49-151">You will need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="58c49-152">Wenn Sie nur bestimmten Azure-Active Directory (AAD) oder nicht-Aad-Benutzern das Anzeigen der Suchergebnisse gestatten, müssen Sie die Identitäten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="58c49-152">If you allow only certain Azure Active Directory (AAD) or Non-AAD users to see the search results, you will then need to map the identities.</span></span>

### <a name="select-permissions"></a><span data-ttu-id="58c49-153">Auswählen von Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="58c49-153">Select Permissions</span></span>
<span data-ttu-id="58c49-154">Sie können Zugriffssteuerungslisten (Access Control Lists, ACLs) aus ihrer Salesforce-Instanz aufnehmen oder jedem in Ihrer Organisation die Möglichkeit geben, Suchergebnisse aus dieser Datenquelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="58c49-154">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or you can allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="58c49-155">ACLs können Azure Active Directory (AAD)-Identitäten, nicht-Aad-Identitäten oder beides umfassen.</span><span class="sxs-lookup"><span data-stu-id="58c49-155">ACLs can include Azure Active Directory (AAD) identities, Non-AAD identities, or both.</span></span>

![Wählen Sie den Bildschirm Berechtigungen aus, der von einem Administrator abgeschlossen wurde. Der Administrator hat die Option "nur Personen mit Zugriff auf diese Datenquelle" ausgewählt und in einem Dropdownmenü mit Identitätstypen auch "Aad" ausgewählt.](media/salesforce-connector/sf6.png)

### <a name="map-non-aad-identities"></a><span data-ttu-id="58c49-157">Zuordnen von nicht Aad Identitäten</span><span class="sxs-lookup"><span data-stu-id="58c49-157">Map non-AAD identities</span></span> 
<span data-ttu-id="58c49-158">Wenn Sie eine ACL aus ihrer Salesforce-Instanz aufnehmen und "nicht-Aad" für den Identitätstyp ausgewählt haben, finden Sie Anweisungen zum Zuordnen der Identitäten unter [Zuordnen der nicht Azure AD Identitäten ](map-non-aad.md) .</span><span class="sxs-lookup"><span data-stu-id="58c49-158">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type see [Map your non-Azure AD Identities ](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="map-aad-identities"></a><span data-ttu-id="58c49-159">Zuordnen von Aad-Identitäten</span><span class="sxs-lookup"><span data-stu-id="58c49-159">Map AAD identities</span></span>
<span data-ttu-id="58c49-160">Wenn Sie eine ACL aus ihrer Salesforce-Instanz aufnehmen und "Aad" für den Identitätstyp ausgewählt haben, finden Sie Anweisungen zum Zuordnen der Identitäten unter [Zuordnen der Azure AD Identitäten](map-aad.md) .</span><span class="sxs-lookup"><span data-stu-id="58c49-160">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="58c49-161">Zuweisen von Eigenschaften Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="58c49-161">Assign property labels</span></span> 
<span data-ttu-id="58c49-162">Sie können jeder Beschriftung eine Source-Eigenschaft zuweisen, indem Sie in einem Menü mit Optionen auswählen.</span><span class="sxs-lookup"><span data-stu-id="58c49-162">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="58c49-163">Dieser Schritt ist zwar nicht zwingend erforderlich, aber einige Eigenschaften Bezeichnungen verbessern die Suchrelevanz und stellen genauere Suchergebnisse für Endbenutzer sicher.</span><span class="sxs-lookup"><span data-stu-id="58c49-163">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span> <span data-ttu-id="58c49-164">Standardmäßig wurden einigen Bezeichnungen wie "Title", "URL" und "LastModifiedBy" bereits Quelleigenschaften zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="58c49-164">By default, some of the Labels like ”Title”, “url”, and  “LastModifiedBy” have already been assigned source properties.</span></span>

![Bildschirm Eigenschaften Bezeichnungen zuweisen mit Standard Quelleigenschaften.](media/salesforce-connector/sf8.png)

## <a name="manage-schema"></a><span data-ttu-id="58c49-166">Verwalten des Schemas</span><span class="sxs-lookup"><span data-stu-id="58c49-166">Manage Schema</span></span>
<span data-ttu-id="58c49-167">Sie können auswählen, welche Quelleigenschaften indiziert werden sollen, damit Sie in den Suchergebnissen angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="58c49-167">You can select what source properties should be indexed so that they can show up in search results.</span></span> <span data-ttu-id="58c49-168">Der Verbindungs-Assistent wählt standardmäßig ein Suchschema basierend auf einer Reihe von Quelleigenschaften aus.</span><span class="sxs-lookup"><span data-stu-id="58c49-168">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="58c49-169">Sie können ihn ändern, indem Sie die Kontrollkästchen für jede Eigenschaft und jedes Attribut auf der Seite Suchschema aktivieren.</span><span class="sxs-lookup"><span data-stu-id="58c49-169">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="58c49-170">Suchschema Attribute umfassen Suche, Abfrage, abrufen und verfeinern.</span><span class="sxs-lookup"><span data-stu-id="58c49-170">Search schema attributes include Search, Query, Retrieve and Refine.</span></span> <span data-ttu-id="58c49-171">Mit verfeinern können Sie die Eigenschaften definieren, die später als benutzerdefinierte Einschränkungen oder Filter in der Suchumgebung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="58c49-171">Refine allows you to define the properties which can be later used as custom refiners or filters in the search experience.</span></span>  

![Wählen Sie das Schema für jede Source-Eigenschaft aus.](media/salesforce-connector/sf9.png)

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="58c49-174">Festlegen des Aktualisierungszeitplans</span><span class="sxs-lookup"><span data-stu-id="58c49-174">Set the refresh schedule</span></span>

<span data-ttu-id="58c49-175">Der Salesforce Connector unterstützt derzeit nur Aktualisierungs Zeitpläne für vollständige Durchforstungen.</span><span class="sxs-lookup"><span data-stu-id="58c49-175">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="58c49-176">Bei einer vollständigen Durchforstung werden gelöschte Objekte und Benutzer gesucht, die zuvor mit dem Microsoft-Suchindex synchronisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="58c49-176">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="58c49-177">Der empfohlene Zeitplan beträgt eine Woche für eine vollständige Durchforstung.</span><span class="sxs-lookup"><span data-stu-id="58c49-177">The recommended schedule is one week for a full crawl.</span></span>

## <a name="limitations"></a><span data-ttu-id="58c49-178">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="58c49-178">Limitations</span></span>

- <span data-ttu-id="58c49-179">Der Graph Connector unterstützt derzeit keine Apex-basierte, Gebiets basierte Freigabe und Freigabe mithilfe persönlicher Gruppen von salesforce.</span><span class="sxs-lookup"><span data-stu-id="58c49-179">The Graph connector does not currently support Apex based , territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="58c49-180">Es gibt einen bekannten Bug in der Salesforce-API, den der Grafik-Konnektor verwendet, wobei die privaten org Wide-Standardwerte für Leads derzeit nicht berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="58c49-180">There is a known bug in the Salesforce API that the Graph connector uses where the private org wide defaults for leads is not honored currently.</span></span>  
- <span data-ttu-id="58c49-181">Wenn ein Feld für ein Profil auf Field Level Security (FLS) festgelegt ist, nimmt der Graph Connector dieses Feld nicht für Profile in dieser Salesforce-Organisation auf. Benutzer können daher nicht nach Werten für diese Felder suchen, noch wird Sie in den Ergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58c49-181">If a field has field level security (FLS) set for a profile, the Graph connector will not ingest that field for any profiles in that Salesforce org. Users will thus not be able to search on values for those fields, nor will it  show up in the results.</span></span>  
- <span data-ttu-id="58c49-182">Alle FLS-Einstellungen werden während der vollständigen Synchronisierung des Connectors berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="58c49-182">Any FLS set up will be honored during the Full syncs of the connector.</span></span>
- <span data-ttu-id="58c49-183">Auf dem Bildschirm "Schema verwalten" werden diese allgemeinen Standardeigenschaften Namen einmal aufgeführt, und die Auswahl erfolgt, damit Sie abgefragt, durchsuchbar und abrufbar ist, für alle oder keine.</span><span class="sxs-lookup"><span data-stu-id="58c49-183">In the Manage Schema screen these common standard property names are listed once and the selection done to make them queryable, searchable and retrievable apply to all or none.</span></span>
    - <span data-ttu-id="58c49-184">Name</span><span class="sxs-lookup"><span data-stu-id="58c49-184">Name</span></span>
    - <span data-ttu-id="58c49-185">Url</span><span class="sxs-lookup"><span data-stu-id="58c49-185">Url</span></span> 
    - <span data-ttu-id="58c49-186">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58c49-186">Description</span></span>
    - <span data-ttu-id="58c49-187">Fax</span><span class="sxs-lookup"><span data-stu-id="58c49-187">Fax</span></span>
    - <span data-ttu-id="58c49-188">Phone</span><span class="sxs-lookup"><span data-stu-id="58c49-188">Phone</span></span>
    - <span data-ttu-id="58c49-189">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="58c49-189">MobilePhone</span></span>
    - <span data-ttu-id="58c49-190">E-Mails</span><span class="sxs-lookup"><span data-stu-id="58c49-190">Email</span></span>
    - <span data-ttu-id="58c49-191">Typ</span><span class="sxs-lookup"><span data-stu-id="58c49-191">Type</span></span>
    - <span data-ttu-id="58c49-192">Titel</span><span class="sxs-lookup"><span data-stu-id="58c49-192">Title</span></span>
    - <span data-ttu-id="58c49-193">AccountId</span><span class="sxs-lookup"><span data-stu-id="58c49-193">AccountId</span></span>
    - <span data-ttu-id="58c49-194">Accountname</span><span class="sxs-lookup"><span data-stu-id="58c49-194">AccountName</span></span>
    - <span data-ttu-id="58c49-195">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="58c49-195">AccountUrl</span></span>
    - <span data-ttu-id="58c49-196">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="58c49-196">AccountOwner</span></span>
    - <span data-ttu-id="58c49-197">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="58c49-197">AccountOwnerUrl</span></span>
    - <span data-ttu-id="58c49-198">Besitzer</span><span class="sxs-lookup"><span data-stu-id="58c49-198">Owner</span></span>
    - <span data-ttu-id="58c49-199">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="58c49-199">OwnerUrl</span></span>
    - <span data-ttu-id="58c49-200">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="58c49-200">CreatedBy</span></span> 
    - <span data-ttu-id="58c49-201">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="58c49-201">CreatedByUrl</span></span> 
    - <span data-ttu-id="58c49-202">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="58c49-202">LastModifiedBy</span></span> 
    - <span data-ttu-id="58c49-203">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="58c49-203">LastModifiedByUrl</span></span> 
    - <span data-ttu-id="58c49-204">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="58c49-204">LastModifiedDate</span></span>
    - <span data-ttu-id="58c49-205">ObjectName</span><span class="sxs-lookup"><span data-stu-id="58c49-205">ObjectName</span></span> 
