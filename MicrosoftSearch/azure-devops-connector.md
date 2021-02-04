---
title: Azure DevOps Graph Connector für Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Azure DevOps Graph-Connectors für Microsoft Search
ms.openlocfilehash: 8fe783c847c672223e051f4433af3e41678fe367
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097403"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="09f89-103">Azure DevOps Graph Connector (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="09f89-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="09f89-104">Mit dem Azure DevOps -Graph-Connector kann Ihre Organisation Arbeitsaufgaben in ihrer Instanz des Azure DevOps-Diensts indizieren.</span><span class="sxs-lookup"><span data-stu-id="09f89-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="09f89-105">Nachdem Sie den Connector konfiguriert und Inhalte aus Azure DevOps indiziert haben, können Endbenutzer in Microsoft Search nach diesen Elementen suchen.</span><span class="sxs-lookup"><span data-stu-id="09f89-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="09f89-106">Lesen Sie [**den Artikel "Setup für Ihren Graph-Connector",**](configure-connector.md) um den allgemeinen Einrichtungsprozess für Graph Connectors zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="09f89-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="09f89-107">Dieser Artikel ist für jeden Benutzer, der einen Azure DevOps Graph-Connector konfiguriert, ausgeführt und überwacht.</span><span class="sxs-lookup"><span data-stu-id="09f89-107">This article is for anyone who configures, runs, and monitors an Azure DevOps Graph connector.</span></span> <span data-ttu-id="09f89-108">Sie ergänzt den allgemeinen Einrichtungsprozess und zeigt Anweisungen, die nur für den Azure DevOps Graph-Connector gelten.</span><span class="sxs-lookup"><span data-stu-id="09f89-108">It supplements the general setup process, and shows instructions that apply only for the Azure DevOps Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="09f89-109">Der Azure DevOps-Connector unterstützt nur den Azure DevOps-Clouddienst.</span><span class="sxs-lookup"><span data-stu-id="09f89-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="09f89-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 und TFS 2013 werden von diesem Connector nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="09f89-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="09f89-111">Schritt 1: Hinzufügen eines Graph-Connectors im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="09f89-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="09f89-112">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="09f89-112">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="09f89-113">Schritt 2: Benennen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="09f89-113">Step 2: Name the connection</span></span>

<span data-ttu-id="09f89-114">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="09f89-114">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="09f89-115">Schritt 3: Konfigurieren der Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="09f89-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="09f89-116">Um eine Verbindung mit Ihrer Azure DevOps-Instanz [](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) herzustellen, benötigen Sie den Azure DevOps-Organisationsnamen, die App-ID und den geheimen Clientgeheimnis für die OAuth-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="09f89-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="09f89-117">Registrieren einer App</span><span class="sxs-lookup"><span data-stu-id="09f89-117">Register an app</span></span>

<span data-ttu-id="09f89-118">Registrieren Sie eine App in Azure DevOps, damit die Microsoft Search-App auf die Instanz zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="09f89-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="09f89-119">Weitere Informationen finden Sie in der Azure DevOps-Dokumentation zum Registrieren [einer App.](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="09f89-119">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true).</span></span>

<span data-ttu-id="09f89-120">Die folgende Tabelle enthält Anleitungen zum Ausfüllen des App-Registrierungsformulars:</span><span class="sxs-lookup"><span data-stu-id="09f89-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="09f89-121">Pflichtfelder</span><span class="sxs-lookup"><span data-stu-id="09f89-121">Mandatory Fields</span></span> | <span data-ttu-id="09f89-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09f89-122">Description</span></span> | <span data-ttu-id="09f89-123">Empfohlener Wert</span><span class="sxs-lookup"><span data-stu-id="09f89-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="09f89-124">Firmenname</span><span class="sxs-lookup"><span data-stu-id="09f89-124">Company Name</span></span>         | <span data-ttu-id="09f89-125">Der Name Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="09f89-125">The name of your company.</span></span> | <span data-ttu-id="09f89-126">Verwenden eines geeigneten Werts</span><span class="sxs-lookup"><span data-stu-id="09f89-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="09f89-127">Anwendungsname</span><span class="sxs-lookup"><span data-stu-id="09f89-127">Application name</span></span>     | <span data-ttu-id="09f89-128">Ein eindeutiger Wert, der die Anwendung identifiziert, die Sie autorisieren.</span><span class="sxs-lookup"><span data-stu-id="09f89-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="09f89-129">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="09f89-129">Microsoft Search</span></span>     |
| <span data-ttu-id="09f89-130">Anwendungswebsite</span><span class="sxs-lookup"><span data-stu-id="09f89-130">Application website</span></span>  | <span data-ttu-id="09f89-131">Die URL der Anwendung, die während der Connectoreinrichtung Zugriff auf Ihre Azure DevOps-Instanz anfordern wird.</span><span class="sxs-lookup"><span data-stu-id="09f89-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="09f89-132">(Erforderlich).</span><span class="sxs-lookup"><span data-stu-id="09f89-132">(Required).</span></span>  | <span data-ttu-id="09f89-133"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="09f89-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="09f89-134">Autorisierungsrückruf-URL</span><span class="sxs-lookup"><span data-stu-id="09f89-134">Authorization callback URL</span></span>        | <span data-ttu-id="09f89-135">Eine erforderliche Rückruf-URL, an die der Autorisierungsserver umleite.</span><span class="sxs-lookup"><span data-stu-id="09f89-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="09f89-136"> https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="09f89-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="09f89-137">Autorisierte Bereiche</span><span class="sxs-lookup"><span data-stu-id="09f89-137">Authorized scopes</span></span> | <span data-ttu-id="09f89-138">Der Zugriffsbereich für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="09f89-138">The scope of access for the application</span></span> | <span data-ttu-id="09f89-139">Wählen Sie die folgenden Bereiche aus: Identität (gelesen), Arbeitsaufgaben (gelesen), Variable Gruppen (lesen), Projekt und Team (gelesen), Graph (lesen)</span><span class="sxs-lookup"><span data-stu-id="09f89-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

<span data-ttu-id="09f89-140">Bei der Registrierung der App mit den oben genannten Details erhalten Sie die **App-ID** und den **geheimen Clientgeheimnis,** die zum Konfigurieren des Connectors verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="09f89-140">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="09f89-141">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span><span class="sxs-lookup"><span data-stu-id="09f89-141">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="09f89-142">Wählen Sie "Profil" und dann "Autorisierungen" im Abschnitt "Sicherheit" im Seitenbereich aus.</span><span class="sxs-lookup"><span data-stu-id="09f89-142">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="09f89-143">Zeigen Sie auf eine autorisierte OAuth-App, um die Schaltfläche "Widerrufen" in der Ecke der App-Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="09f89-143">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="09f89-144">Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="09f89-144">Connection settings</span></span>

<span data-ttu-id="09f89-145">Nach der Registrierung der Microsoft Search-App bei Azure DevOps können Sie den Verbindungseinstellungsschritt abschließen.</span><span class="sxs-lookup"><span data-stu-id="09f89-145">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="09f89-146">Geben Sie den Namen Ihrer Organisation, die App-ID und den geheimen Clientgeheimnis ein.</span><span class="sxs-lookup"><span data-stu-id="09f89-146">Enter your organization name, App ID, and Client secret.</span></span>

![Verbindungsanwendungseinstellungen](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="09f89-148">Konfigurieren von Daten: Auswählen von Projekten und Feldern</span><span class="sxs-lookup"><span data-stu-id="09f89-148">Configure data: select projects and fields</span></span>

<span data-ttu-id="09f89-149">Sie können die Verbindung auswählen, um entweder die gesamte Organisation oder bestimmte Projekte zu indizieren.</span><span class="sxs-lookup"><span data-stu-id="09f89-149">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="09f89-150">Wenn Sie die gesamte Organisation indizieren, werden Elemente in allen Projekten in der Organisation indiziert.</span><span class="sxs-lookup"><span data-stu-id="09f89-150">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="09f89-151">Neue Projekte und Elemente werden während der nächsten Durchforstung indiziert, nachdem sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="09f89-151">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="09f89-152">Wenn Sie einzelne Projekte auswählen, werden nur Arbeitsaufgaben in diesen Projekten indiziert.</span><span class="sxs-lookup"><span data-stu-id="09f89-152">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Konfigurieren von Daten](media/ADO_Configure_data.png)

<span data-ttu-id="09f89-154">Wählen Sie als Nächstes aus, welche Felder die Verbindung in diesen Feldern indizieren und anzeigen soll, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="09f89-154">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Auswählen von Eigenschaften](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="09f89-156">Schritt 4: Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="09f89-156">Step 4: Manage search permissions</span></span>

<span data-ttu-id="09f89-157">Der Azure DevOps-Connector unterstützt Suchberechtigungen, die nur für Personen mit Zugriff  **auf** diese Datenquelle oder für jeden sichtbar **sind.**</span><span class="sxs-lookup"><span data-stu-id="09f89-157">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="09f89-158">Wenn Sie "Nur Personen mit Zugriff auf diese Datenquelle" **auswählen,** werden indizierte Daten in den Suchergebnissen für Benutzer angezeigt, die auf der Grundlage von Berechtigungen für Benutzer oder Gruppen auf der Pfadebene "Organisation", "Projekt" oder "Bereich" in Azure DevOps darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="09f89-158">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="09f89-159">Wenn Sie **"Jeder"** auswählen, werden indizierte Daten in den Suchergebnissen für alle Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="09f89-159">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="09f89-160">Schritt 5: Zuweisen von Eigenschaftsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="09f89-160">Step 5: Assign property labels</span></span>

<span data-ttu-id="09f89-161">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="09f89-161">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="09f89-162">Schritt 6: Verwalten des Schemas</span><span class="sxs-lookup"><span data-stu-id="09f89-162">Step 6: Manage schema</span></span>

<span data-ttu-id="09f89-163">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="09f89-163">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="09f89-164">Schritt 7: Auswählen von Aktualisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="09f89-164">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="09f89-165">Der Azure DevOps Connector unterstützt Aktualisierungszeitpläne für vollständige und inkrementelle Durchforstungen.</span><span class="sxs-lookup"><span data-stu-id="09f89-165">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="09f89-166">Der empfohlene Zeitplan beträgt eine Stunde für eine inkrementelle Durchforstung und einen Tag für eine vollständige Durchforstung.</span><span class="sxs-lookup"><span data-stu-id="09f89-166">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="09f89-167">Schritt 8: Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="09f89-167">Step 8: Review connection</span></span>

<span data-ttu-id="09f89-168">Befolgen Sie die allgemeinen [Setupanweisungen.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="09f89-168">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
