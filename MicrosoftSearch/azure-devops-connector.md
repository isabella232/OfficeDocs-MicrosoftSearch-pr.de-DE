---
title: Azure DevOps Connector für Microsoft Search
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Einrichten des Azure DevOps Connectors für Microsoft Search
ms.openlocfilehash: 1030dd2b508e5364f53f92e7c8ce8c12c040ce70
ms.sourcegitcommit: 85d40512e8616c851da1a38c137ca0e4e8625813
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359721"
---
# <a name="azure-devops-connector"></a><span data-ttu-id="ef3eb-103">Azure DevOps-Connector</span><span class="sxs-lookup"><span data-stu-id="ef3eb-103">Azure DevOps connector</span></span>

<span data-ttu-id="ef3eb-104">Mit dem Azure DevOps-Connector kann Ihre Organisation Arbeitsaufgaben in Ihrer Instanz des Azure DevOps-Diensts indizieren.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-104">With the Azure DevOps connector, your organization can index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="ef3eb-105">Nachdem Sie den Connector-und den Index Inhalt aus Azure DevOps konfiguriert haben, können Endbenutzer nach diesen Elementen in der Microsoft-Suche suchen.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

<span data-ttu-id="ef3eb-106">Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen Azure DevOps-Connector konfigurieren, ausführen und überwachen.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Azure DevOps connector.</span></span> <span data-ttu-id="ef3eb-107">Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="ef3eb-108">Der Azure DevOps-Connector unterstützt nur den Azure DevOps Cloud Service.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-108">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="ef3eb-109">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 und TFS 2013 werden von diesem Connector nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-109">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="ef3eb-110">Herstellen einer Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="ef3eb-110">Connect to a data source</span></span>

<span data-ttu-id="ef3eb-111">Um eine Verbindung mit ihrer Azure DevOps-Instanz herzustellen, benötigen Sie Ihren Azure DevOps- [Organisations](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) Namen, die APP-ID und den geheimen Client Schlüssel für die OAuth-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-111">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="ef3eb-112">Registrieren einer App</span><span class="sxs-lookup"><span data-stu-id="ef3eb-112">Register an app</span></span>

<span data-ttu-id="ef3eb-113">Sie müssen eine app in Azure DevOps registrieren, damit die Microsoft Search-App auf die Instanz zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-113">You must register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="ef3eb-114">Weitere Informationen finden Sie unter Azure DevOps-Dokumentation zum [Registrieren einer APP](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span><span class="sxs-lookup"><span data-stu-id="ef3eb-114">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="ef3eb-115">In der folgenden Tabelle finden Sie Anleitungen zum Ausfüllen des App-Registrierungsformulars:</span><span class="sxs-lookup"><span data-stu-id="ef3eb-115">The following table provides guidance on how to fill out the app registration form:</span></span>

 <span data-ttu-id="ef3eb-116">**Obligatorische Felder**</span><span class="sxs-lookup"><span data-stu-id="ef3eb-116">**Mandatory Fields**</span></span> | <span data-ttu-id="ef3eb-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ef3eb-117">**Description**</span></span>      | <span data-ttu-id="ef3eb-118">**Empfohlener Wert**</span><span class="sxs-lookup"><span data-stu-id="ef3eb-118">**Recommended Value**</span></span>
--- | --- | ---
| <span data-ttu-id="ef3eb-119">Firmenname</span><span class="sxs-lookup"><span data-stu-id="ef3eb-119">Company Name</span></span>         | <span data-ttu-id="ef3eb-120">Dies ist der Name Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-120">This is the name of your company.</span></span> | <span data-ttu-id="ef3eb-121">Verwenden eines geeigneten Werts</span><span class="sxs-lookup"><span data-stu-id="ef3eb-121">Use an appropriate value</span></span>   |
| <span data-ttu-id="ef3eb-122">Anwendungsname</span><span class="sxs-lookup"><span data-stu-id="ef3eb-122">Application name</span></span>     | <span data-ttu-id="ef3eb-123">Dieser eindeutige Wert identifiziert die Anwendung, die Sie zu autorisieren haben.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-123">This unique value identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="ef3eb-124">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="ef3eb-124">Microsoft Search</span></span>     |
| <span data-ttu-id="ef3eb-125">Anwendungswebsite</span><span class="sxs-lookup"><span data-stu-id="ef3eb-125">Application website</span></span>  | <span data-ttu-id="ef3eb-126">Dieses erforderliche Feld ist die URL der Anwendung, die während des Connector-Setups Zugriff auf Ihre Azure DevOps-Instanz anfordert.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-126">This required field is the URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span>  | <https://gcs.office.com/>                |
| <span data-ttu-id="ef3eb-127">Autorisierungs-Rückruf-URL</span><span class="sxs-lookup"><span data-stu-id="ef3eb-127">Authorization callback URL</span></span>        | <span data-ttu-id="ef3eb-128">Eine erforderliche Rückruf-URL, an die der autorisierungsserver umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-128">A required callback URL that the authorization server redirects to.</span></span> | <https://gcs.office.com/v1.0/admin/oauth/callback>|
| <span data-ttu-id="ef3eb-129">Autorisierte Bereiche</span><span class="sxs-lookup"><span data-stu-id="ef3eb-129">Authorized scopes</span></span> | <span data-ttu-id="ef3eb-130">Dies ist der Umfang des Zugriffs für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-130">This is the scope of access for the application</span></span> | <span data-ttu-id="ef3eb-131">Wählen Sie die folgenden Bereiche aus: Identity (lesen), Arbeitsaufgaben (lesen), Variablen Gruppen (lesen), Projekt und Team (lesen), Grafik (lesen)</span><span class="sxs-lookup"><span data-stu-id="ef3eb-131">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

<span data-ttu-id="ef3eb-132">Beim Registrieren der APP mit den obigen Details erhalten Sie die **App-ID** und den **geheimen Client Schlüssel** , die zum Konfigurieren des Connectors verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-132">On registering the app with the details above, you will get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="ef3eb-133">Um den Zugriff auf alle in Azure DevOps registrierten apps aufzuheben, wechseln Sie zu Benutzereinstellungen rechts oben in ihrer Azure DevOps-Instanz.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-133">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="ef3eb-134">Klicken Sie auf Profil, und klicken Sie dann im Abschnitt Sicherheit des Seitenbereichs auf Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-134">Click on Profile and then click on Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="ef3eb-135">Zeigen Sie mit der Maus auf eine autorisierte OAuth-APP, um die Schaltfläche Widerrufen an der Ecke der App-Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-135">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="ef3eb-136">Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ef3eb-136">Connection settings</span></span>

<span data-ttu-id="ef3eb-137">Nachdem Sie die Microsoft Search-App mit Azure DevOps registriert haben, können Sie den Schritt Verbindungseinstellungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-137">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="ef3eb-138">Geben Sie den Namen Ihrer Organisation, die APP-ID und den geheimen Client Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-138">Enter your organization name, App ID, and Client secret.</span></span>

![Einstellungen für die Verbindungsanwendung](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a><span data-ttu-id="ef3eb-140">Auswählen von Projekten und Feldern</span><span class="sxs-lookup"><span data-stu-id="ef3eb-140">Select projects and fields</span></span>

<span data-ttu-id="ef3eb-141">Sie können auswählen, ob die Verbindung entweder die gesamte Organisation oder bestimmte Projekte indizieren soll.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-141">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="ef3eb-142">Wenn Sie sich dafür entscheiden, die gesamte Organisation zu indizieren, werden Elemente in allen Projekten in der Organisation indiziert.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-142">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="ef3eb-143">Neue Projekte und Elemente werden während der nächsten Durchforstung indiziert, nachdem Sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-143">New projects and items will be indexed during the next crawl after they are created.</span></span> <span data-ttu-id="ef3eb-144">Wenn Sie einzelne Projekte auswählen, werden nur Arbeitsaufgaben in diesen Projekten indiziert.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-144">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Konfigurieren von Daten](media/ADO_Configure_data.png)

<span data-ttu-id="ef3eb-146">Wählen Sie als nächstes aus, welche Felder die Verbindung indizieren soll, und sehen Sie sich die Daten in diesen Feldern in der Vorschau an, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-146">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Auswählen von Eigenschaften](media/ADO_choose_properties.png)

## <a name="manage-the-search-schema"></a><span data-ttu-id="ef3eb-148">Verwalten des Suchschemas</span><span class="sxs-lookup"><span data-stu-id="ef3eb-148">Manage the search schema</span></span>

<span data-ttu-id="ef3eb-149">Konfigurieren Sie die Zuordnung für das Suchschema.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-149">Configure the search schema mapping.</span></span> <span data-ttu-id="ef3eb-150">Sie können auswählen, welche Eigenschaften **abgefragt**, **durchsuchbar** und **abrufbar**gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-150">You can choose which properties to make **queryable**, **searchable** and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="ef3eb-151">Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="ef3eb-151">Manage search permissions</span></span>

<span data-ttu-id="ef3eb-152">Der Azure DevOps-Connector unterstützt derzeit nur Suchberechtigungen **, die für alle sichtbar**sind.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-152">The Azure DevOps connector currently only supports search permissions **Visible to Everyone**.</span></span> <span data-ttu-id="ef3eb-153">Indizierte Daten werden in den Suchergebnissen für alle Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-153">Indexed data will appear in the search results for all users.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="ef3eb-154">Festlegen des Aktualisierungszeitplans</span><span class="sxs-lookup"><span data-stu-id="ef3eb-154">Set the refresh schedule</span></span>

<span data-ttu-id="ef3eb-155">Der Azure DevOps-Connector unterstützt Aktualisierungs Zeitpläne für vollständige und inkrementelle Crawls.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-155">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="ef3eb-156">Bei einer vollständigen Durchforstung werden gelöschte Arbeitsaufgaben gesucht, die zuvor mit dem Microsoft-Suchindex synchronisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-156">A full crawl finds deleted work items that were previously synced to the Microsoft Search index.</span></span> <span data-ttu-id="ef3eb-157">Eine vollständige Durchforstung wird ausgeführt, um alle Arbeitsaufgaben zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-157">A full crawl runs to sync all the work items.</span></span> <span data-ttu-id="ef3eb-158">Um neue Arbeitsaufgaben und Aktualisierungen an vorhandenen Arbeitsaufgaben zu synchronisieren, müssen Sie inkrementelle Durchforstungen planen.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-158">To sync new work items and updates to existing work items, you need to schedule incremental crawls.</span></span>

<span data-ttu-id="ef3eb-159">Der empfohlene Zeitplan beträgt eine Stunde für eine inkrementelle Durchforstung und einen Tag für eine vollständige Durchforstung.</span><span class="sxs-lookup"><span data-stu-id="ef3eb-159">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>
