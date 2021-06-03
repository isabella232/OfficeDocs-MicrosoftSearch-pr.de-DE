---
title: Azure DevOps Graph Connector für Microsoft Search
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
description: Einrichten des Azure DevOps Graph für Microsoft Search
ms.openlocfilehash: bfe04a022360a968424b673ad03ba05f27c8c333
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720952"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="9d1d2-103">Azure DevOps Graph Connector (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="9d1d2-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="9d1d2-104">Der Azure DevOps Graph ermöglicht Ihrer Organisation das Indizieren von Arbeitsaufgaben in ihrer Instanz des Azure DevOps Diensts.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="9d1d2-105">Nachdem Sie den Connector und den Indexinhalt aus Azure DevOps konfiguriert haben, können Endbenutzer in Microsoft Search nach diesen Elementen suchen.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="9d1d2-106">Lesen Sie [**den Artikel Setup für Graph Connector,**](configure-connector.md) um die Allgemeinen Anweisungen Graph Connectors zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="9d1d2-107">Dieser Artikel ist für alle Benutzer, die einen Connector konfigurieren, Azure DevOps Graph werden.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-107">This article is for anyone who configures, runs, and monitors an Azure DevOps Graph connector.</span></span> <span data-ttu-id="9d1d2-108">Es ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Azure DevOps Graph gelten.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-108">It supplements the general setup process, and shows instructions that apply only for the Azure DevOps Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9d1d2-109">Der Azure DevOps unterstützt nur den Azure DevOps Clouddienst.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="9d1d2-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 und TFS 2013 werden von diesem Connector nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="9d1d2-111">Schritt 1: Hinzufügen eines Graph im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="9d1d2-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="9d1d2-112">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9d1d2-112">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="9d1d2-113">Schritt 2: Benennen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="9d1d2-113">Step 2: Name the connection</span></span>

<span data-ttu-id="9d1d2-114">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9d1d2-114">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="9d1d2-115">Schritt 3: Konfigurieren der Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="9d1d2-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="9d1d2-116">Um eine Verbindung mit ihrer Azure DevOps herzustellen, benötigen [](/azure/devops/organizations/accounts/create-organization) Sie Azure DevOps Namen der Organisation, die App-ID und den geheimen Client für die OAuth-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="9d1d2-117">Registrieren einer App</span><span class="sxs-lookup"><span data-stu-id="9d1d2-117">Register an app</span></span>

<span data-ttu-id="9d1d2-118">Registrieren Sie eine App in Azure DevOps, damit die Microsoft Search-App auf die Instanz zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="9d1d2-119">Weitere Informationen finden Sie in Azure DevOps dokumentation zum Registrieren [einer App](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app).</span><span class="sxs-lookup"><span data-stu-id="9d1d2-119">To learn more, see Azure DevOps documentation on how to [register an app](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="9d1d2-120">In der folgenden Tabelle finden Sie Anleitungen zum Ausfüllen des App-Registrierungsformulars:</span><span class="sxs-lookup"><span data-stu-id="9d1d2-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="9d1d2-121">Obligatorische Felder</span><span class="sxs-lookup"><span data-stu-id="9d1d2-121">Mandatory Fields</span></span> | <span data-ttu-id="9d1d2-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d1d2-122">Description</span></span> | <span data-ttu-id="9d1d2-123">Empfohlener Wert</span><span class="sxs-lookup"><span data-stu-id="9d1d2-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="9d1d2-124">Firmenname</span><span class="sxs-lookup"><span data-stu-id="9d1d2-124">Company Name</span></span>         | <span data-ttu-id="9d1d2-125">Der Name Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-125">The name of your company.</span></span> | <span data-ttu-id="9d1d2-126">Verwenden eines geeigneten Werts</span><span class="sxs-lookup"><span data-stu-id="9d1d2-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="9d1d2-127">Name der Anwendung</span><span class="sxs-lookup"><span data-stu-id="9d1d2-127">Application name</span></span>     | <span data-ttu-id="9d1d2-128">Ein eindeutiger Wert, der die Anwendung identifiziert, die Sie autorisieren.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="9d1d2-129">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="9d1d2-129">Microsoft Search</span></span>     |
| <span data-ttu-id="9d1d2-130">Anwendungswebsite</span><span class="sxs-lookup"><span data-stu-id="9d1d2-130">Application website</span></span>  | <span data-ttu-id="9d1d2-131">Die URL der Anwendung, die während der Connectoreinrichtung Zugriff auf Azure DevOps Instanz anfordern wird.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="9d1d2-132">(Erforderlich).</span><span class="sxs-lookup"><span data-stu-id="9d1d2-132">(Required).</span></span>  | <span data-ttu-id="9d1d2-133"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="9d1d2-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="9d1d2-134">Autorisierungsrückruf-URL</span><span class="sxs-lookup"><span data-stu-id="9d1d2-134">Authorization callback URL</span></span>        | <span data-ttu-id="9d1d2-135">Eine erforderliche Rückruf-URL, an die der Autorisierungsserver umleite.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="9d1d2-136"> https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="9d1d2-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="9d1d2-137">Autorisierte Bereiche</span><span class="sxs-lookup"><span data-stu-id="9d1d2-137">Authorized scopes</span></span> | <span data-ttu-id="9d1d2-138">Der Zugriffsbereich für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="9d1d2-138">The scope of access for the application</span></span> | <span data-ttu-id="9d1d2-139">Wählen Sie die folgenden Bereiche aus: Identität (Lesen), Arbeitsaufgaben (lesen), Variable Gruppen (Lesen), Project und Team (lesen), Graph (Lesen)</span><span class="sxs-lookup"><span data-stu-id="9d1d2-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

>[!IMPORTANT]
><span data-ttu-id="9d1d2-140">Die autorisierten Bereiche, die Sie für die App auswählen, sollten genau den oben aufgeführten Bereich entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-140">The authorized scopes that you select for the app should match the scopes exactly as listed above.</span></span> <span data-ttu-id="9d1d2-141">Wenn Sie einen der autorisierten Bereiche in der Liste auslassen oder einen anderen Bereich hinzufügen, wird bei der Autorisierung ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-141">If you omit one of the authorized scopes in the list, or add another scope, the authorization will fail.</span></span>

<span data-ttu-id="9d1d2-142">Wenn Sie die App mit den oben genannten Details registrieren, erhalten Sie die **App-ID** und den geheimen Clientgeheimnis, die zum Konfigurieren des Connectors verwendet werden. </span><span class="sxs-lookup"><span data-stu-id="9d1d2-142">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="9d1d2-143">Wenn Sie den Zugriff auf eine app widerrufen möchten, die in Azure DevOps registriert ist, wechseln Sie zu Benutzereinstellungen rechts oben in Azure DevOps Instanz.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-143">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="9d1d2-144">Wählen Sie Profil und dann Autorisierungen im Abschnitt Sicherheit des Seitenbereichs aus.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-144">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="9d1d2-145">Zeigen Sie auf eine autorisierte OAuth-App, um die Schaltfläche Widerrufen in der Ecke der App-Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-145">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="9d1d2-146">Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="9d1d2-146">Connection settings</span></span>

<span data-ttu-id="9d1d2-147">Nachdem Sie die Microsoft Search-App bei Azure DevOps registriert haben, können Sie den Verbindungseinstellungen-Schritt abschließen.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-147">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="9d1d2-148">Geben Sie Ihren Organisationsnamen, Die App-ID und den geheimen Clientgeheimnis ein.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-148">Enter your organization name, App ID, and Client secret.</span></span>

![Verbindungsanwendungs-Einstellungen](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="9d1d2-150">Konfigurieren von Daten: Auswählen von Projekten und Feldern</span><span class="sxs-lookup"><span data-stu-id="9d1d2-150">Configure data: select projects and fields</span></span>

<span data-ttu-id="9d1d2-151">Sie können die Verbindung auswählen, um entweder die gesamte Organisation oder bestimmte Projekte zu indizieren.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-151">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="9d1d2-152">Wenn Sie die gesamte Organisation indizieren möchten, werden Elemente in allen Projekten in der Organisation indiziert.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-152">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="9d1d2-153">Neue Projekte und Elemente werden während der nächsten Durchforstung indiziert, nachdem sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-153">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="9d1d2-154">Wenn Sie einzelne Projekte auswählen, werden nur Arbeitselemente in diesen Projekten indiziert.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-154">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Konfigurieren von Daten](media/ADO_Configure_data.png)

<span data-ttu-id="9d1d2-156">Wählen Sie als Nächstes aus, welche Felder die Verbindung in diesen Feldern indizieren und anzeigen soll, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-156">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Auswählen von Eigenschaften](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="9d1d2-158">Schritt 4: Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="9d1d2-158">Step 4: Manage search permissions</span></span>

<span data-ttu-id="9d1d2-159">Der Azure DevOps unterstützt Suchberechtigungen, die nur personen mit Zugriff  **auf** diese Datenquelle oder **Jeder angezeigt werden.**</span><span class="sxs-lookup"><span data-stu-id="9d1d2-159">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="9d1d2-160">Wenn Sie **Nur** Personen mit Zugriff auf diese Datenquelle auswählen, werden indizierte Daten in den Suchergebnissen für Benutzer angezeigt, die auf der Grundlage von Berechtigungen für Benutzer oder Gruppen auf der Pfadebene "Organisation", "Project" oder "Bereich" in Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-160">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="9d1d2-161">Wenn Sie Jeder **auswählen,** werden indizierte Daten für alle Benutzer in den Suchergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-161">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="9d1d2-162">Schritt 5: Zuweisen von Eigenschaftsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="9d1d2-162">Step 5: Assign property labels</span></span>

<span data-ttu-id="9d1d2-163">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9d1d2-163">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="9d1d2-164">Schritt 6: Verwalten des Schemas</span><span class="sxs-lookup"><span data-stu-id="9d1d2-164">Step 6: Manage schema</span></span>

<span data-ttu-id="9d1d2-165">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9d1d2-165">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="9d1d2-166">Schritt 7: Auswählen von Aktualisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="9d1d2-166">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="9d1d2-167">Der Azure DevOps unterstützt Aktualisierungszeitpläne für vollständige und inkrementelle Durchforstungen.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-167">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="9d1d2-168">Der empfohlene Zeitplan beträgt eine Stunde für eine inkrementelle Durchforstung und einen Tag für eine vollständige Durchforstung.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-168">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="9d1d2-169">Schritt 8: Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="9d1d2-169">Step 8: Review connection</span></span>

<span data-ttu-id="9d1d2-170">Befolgen Sie die [allgemeinen Setupanweisungen](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9d1d2-170">Follow the general [setup instructions](./configure-connector.md).</span></span>

>[!TIP]
><span data-ttu-id="9d1d2-171">**Standardergebnistyp**</span><span class="sxs-lookup"><span data-stu-id="9d1d2-171">**Default Result type**</span></span>
>* <span data-ttu-id="9d1d2-172">Der Azure DevOps registriert automatisch einen [Ergebnistyp,](./customize-search-page.md#step-2-create-the-result-types) nachdem der Connector veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-172">The Azure DevOps connector automatically registers a [result type](./customize-search-page.md#step-2-create-the-result-types) once the connector is published.</span></span> <span data-ttu-id="9d1d2-173">Der Ergebnistyp verwendet ein dynamisch generiertes [Ergebnislayout](./customize-results-layout.md) basierend auf den in Schritt 3 ausgewählten Feldern.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-173">The result type uses a dynamically generated [result layout](./customize-results-layout.md) based on the fields selected in step 3.</span></span> 
>* <span data-ttu-id="9d1d2-174">Sie können den Ergebnistyp verwalten, indem Sie zu Ergebnistypen [**im**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) [Microsoft 365 navigieren.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9d1d2-174">You can manage the result type by navigating to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="9d1d2-175">Der Standardergebnistyp wird als `ConnectionId` "Standard" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-175">The default result type will be named as "`ConnectionId`Default".</span></span> <span data-ttu-id="9d1d2-176">Wenn Ihre Verbindungs-ID z. B. ist, wird Ihr Ergebnislayout mit dem Namen `AzureDevOps` "AzureDevOpsDefault" benannt.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-176">For example, if your connection id is `AzureDevOps`, your result layout will be named: "AzureDevOpsDefault"</span></span>
>* <span data-ttu-id="9d1d2-177">Außerdem können Sie bei Bedarf einen eigenen Ergebnistyp erstellen.</span><span class="sxs-lookup"><span data-stu-id="9d1d2-177">Also, you can choose to create your own result type if needed.</span></span>

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->