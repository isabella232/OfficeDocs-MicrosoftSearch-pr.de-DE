---
title: Auf dem Prem-Agent
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: On-Prem-Agent
ms.openlocfilehash: 487c5b179e09fd99fa26ae7a237e89ca38b7be4d
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408942"
---
# <a name="on-prem-agent"></a><span data-ttu-id="913cd-103">On-Prem-Agent</span><span class="sxs-lookup"><span data-stu-id="913cd-103">On-Prem Agent</span></span>

## <a name="graph-connector-agent"></a><span data-ttu-id="913cd-104">Grafik-Connector-Agent</span><span class="sxs-lookup"><span data-stu-id="913cd-104">Graph connector agent</span></span>

<span data-ttu-id="913cd-105">Für on-Prem Graph Connectors müssen Sie die *Graph Connector Agent* -Software installieren.</span><span class="sxs-lookup"><span data-stu-id="913cd-105">On-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="913cd-106">Es ermöglicht eine schnelle und sichere Datenübertragung zwischen lokalen Daten und Cloud-Diensten.</span><span class="sxs-lookup"><span data-stu-id="913cd-106">It allows quick and secure data transfer between on-premises data and cloud services.</span></span> <span data-ttu-id="913cd-107">Dieser Artikel führt Sie durch die Schritte zum Installieren und Konfigurieren der Software.</span><span class="sxs-lookup"><span data-stu-id="913cd-107">This article guides you through the steps of installing and configuring the software.</span></span> <span data-ttu-id="913cd-108">Sobald die Konfiguration konfiguriert wurde, ist Sie für die Erstellung von Verbindungen mit Ihren on-Prem-Datenquellen aus dem [Microsoft 365 Admin Center](https://admin.microsoft.com)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="913cd-108">Once configured, it will be available for creating connections to your on-prem data sources from the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

## <a name="installation"></a><span data-ttu-id="913cd-109">Installation</span><span class="sxs-lookup"><span data-stu-id="913cd-109">Installation</span></span>

<span data-ttu-id="913cd-110">Laden Sie die neueste Version des Graph Connector-Agents mithilfe [dieses Links](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) herunter, und installieren Sie die Software mithilfe des Installations-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="913cd-110">Download the latest version of Graph connector agent using [this link](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) and install the software using the installation wizard.</span></span> <span data-ttu-id="913cd-111">Mit der empfohlenen Konfiguration des unten beschriebenen Computers kann die Software nahtlos bis zu drei Verbindungen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="913cd-111">With the recommended configuration of the machine described below, the software can seamlessly handle up to three connections.</span></span> <span data-ttu-id="913cd-112">Verbindungen darüber hinaus können die Leistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="913cd-112">Any connections beyond that might degrade the performance.</span></span>

<span data-ttu-id="913cd-113">Empfohlene Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="913cd-113">Recommended configuration:</span></span>

* <span data-ttu-id="913cd-114">Windows 10, Windows Server 2012 R2 und höher</span><span class="sxs-lookup"><span data-stu-id="913cd-114">Windows 10, Windows Server 2012 R2 and above</span></span>
* <span data-ttu-id="913cd-115">8 Kerne, 3GHz</span><span class="sxs-lookup"><span data-stu-id="913cd-115">8 cores, 3GHz</span></span>
* <span data-ttu-id="913cd-116">16GB RAM, 1GB Festplattenspeicherplatz</span><span class="sxs-lookup"><span data-stu-id="913cd-116">16GB RAM, 1GB Disk Space</span></span>
* <span data-ttu-id="913cd-117">Netzwerkzugriff auf Datenquelle und Internet über 443</span><span class="sxs-lookup"><span data-stu-id="913cd-117">Network access to data source and internet through 443</span></span>

## <a name="creating-app-for-the-agent"></a><span data-ttu-id="913cd-118">Erstellen einer APP für den Agent</span><span class="sxs-lookup"><span data-stu-id="913cd-118">Creating App for the agent</span></span>  

<span data-ttu-id="913cd-119">Die Agent-Instanz muss vor dem Erstellen von Verbindungen nur wenige wichtige Parameter eingezogen werden.</span><span class="sxs-lookup"><span data-stu-id="913cd-119">The agent instance needs to be fed few critical parameters before you create connections.</span></span> <span data-ttu-id="913cd-120">Diese Parameter umfassen Authentifizierungsdetails, die für die Verwendung von Graph-Einnahme-APIs erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="913cd-120">These parameters include authentication details required for using Graph ingestion APIs.</span></span>  

<span data-ttu-id="913cd-121">Schritte zum Erstellen einer APP für den Agent.</span><span class="sxs-lookup"><span data-stu-id="913cd-121">Steps for creating App for the agent.</span></span>

1. <span data-ttu-id="913cd-122">Wechseln Sie zum [Azure-Portal](https://portal.azure.com) , und melden Sie sich mit den Administratoranmeldeinformationen für den Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="913cd-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="913cd-123">Navigieren Sie im Navigationsbereich zu **Azure Active Directory**  ->  **App-Registrierungen** , und wählen Sie **neue Registrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="913cd-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="913cd-124">Geben Sie einen Namen für die APP ein, und wählen Sie **registrieren** aus.</span><span class="sxs-lookup"><span data-stu-id="913cd-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="913cd-125">Notieren Sie sich die Anwendungs-ID (Client).</span><span class="sxs-lookup"><span data-stu-id="913cd-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="913cd-126">Öffnen Sie **API-Berechtigungen** aus dem Navigationsbereich, und wählen Sie **Berechtigung hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="913cd-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="913cd-127">Wählen Sie **Microsoft Graph** und dann **Anwendungsberechtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="913cd-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="913cd-128">Suchen Sie nach "ExternalItem. ReadWrite. all" und "Directory. Read. all" aus den Berechtigungen, und wählen Sie **Berechtigungen hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="913cd-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="913cd-129">Wählen Sie **Administrator Zustimmung für [Mandanten] erteilen** aus, und bestätigen Sie mit **Ja**.</span><span class="sxs-lookup"><span data-stu-id="913cd-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="913cd-130">Stellen Sie sicher, dass die Berechtigungen den Status erteilt aufweisen.</span><span class="sxs-lookup"><span data-stu-id="913cd-130">Check that the permissions are in the granted state.</span></span>
     <span data-ttu-id="913cd-131">![Berechtigungen, die in der rechten Spalte in grüner Form gewährt werden.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="913cd-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

## <a name="configuring-graph-connector-agent"></a><span data-ttu-id="913cd-132">Konfigurieren des Graph Connector-Agents</span><span class="sxs-lookup"><span data-stu-id="913cd-132">Configuring Graph connector agent</span></span>

<span data-ttu-id="913cd-133">Nachdem Sie die APP für den Agent erstellt haben, müssen Sie den Agent mit den entsprechenden Authentifizierungsdetails konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="913cd-133">Once you have created the App for the agent, you must configure the agent with appropriate authentication details.</span></span>

<span data-ttu-id="913cd-134">Authentifizierungsdetails können in einem der folgenden Formulare bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="913cd-134">Authentication details can be provided in one of the following forms.</span></span>

### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="913cd-135">Konfigurieren des geheimen Client Schlüssels für die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="913cd-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="913cd-136">Wechseln Sie zum [Azure-Portal](https://portal.azure.com) , und melden Sie sich mit den Administratoranmeldeinformationen für den Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="913cd-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="913cd-137">Öffnen Sie die **App-Registrierung** im Navigationsbereich, und wechseln Sie zur entsprechenden app.</span><span class="sxs-lookup"><span data-stu-id="913cd-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="913cd-138">Wählen Sie unter **Verwalten** die Option **Zertifikate und Geheimnisse** aus.</span><span class="sxs-lookup"><span data-stu-id="913cd-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="913cd-139">Wählen Sie **neuer geheimer Client Schlüssel** aus, und wählen Sie einen Ablaufzeitraum für den geheimen Schlüssel aus.</span><span class="sxs-lookup"><span data-stu-id="913cd-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="913cd-140">Kopieren Sie den generierten geheimen Schlüssel, und speichern Sie ihn, da er nicht erneut angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="913cd-140">Copy the generated secret and save it because it will not be shown again.</span></span>
4. <span data-ttu-id="913cd-141">Verwenden Sie diesen geheimen Client Schlüssel zusammen mit der Anwendungs-ID, um den Agent zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="913cd-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="913cd-142">Verwenden Sie im Feld **Name** des Agents keine Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="913cd-142">Do not use any blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="913cd-143">Alpha numerische Zeichen werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="913cd-143">Alpha numeric characters are accepted.</span></span>

## <a name="using-thumbprint-certificate-for-authentication"></a><span data-ttu-id="913cd-144">Verwenden des Fingerabdruck Zertifikats für die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="913cd-144">Using thumbprint certificate for authentication</span></span>

<span data-ttu-id="913cd-145">Wenn Sie die Authentifizierungsdetails bereits konfiguriert haben, indem Sie [den geheimen Client Schlüssel für die Authentifizierung konfigurieren](#configuring-the-client-secret-for-authentication) , können Sie direkt zur [Setup Übersicht](configure-connector.md)wechseln.</span><span class="sxs-lookup"><span data-stu-id="913cd-145">If you have already configured the authentication details by following [Configuring the client secret for authentication](#configuring-the-client-secret-for-authentication) , then you can jump directly to [Setup overview](configure-connector.md).</span></span>

1. <span data-ttu-id="913cd-146">Öffnen Sie die **App-Registrierung** , und wählen Sie im Navigationsbereich **Zertifikate und Geheimnisse** aus.</span><span class="sxs-lookup"><span data-stu-id="913cd-146">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="913cd-147">Kopieren Sie den Fingerabdruck des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="913cd-147">Copy the certificate thumbprint.</span></span>
<span data-ttu-id="913cd-148">![Liste der thumbrint-Zertifikate, wenn Zertifikate und Geheimnisse im linken Bereich ausgewählt sind](media/onprem-agent/certificates.png)</span><span class="sxs-lookup"><span data-stu-id="913cd-148">![List of thumbrint certificates when Certificates and secrets is selected in the left pane](media/onprem-agent/certificates.png)</span></span>
2. <span data-ttu-id="913cd-149">Verwenden Sie entweder den geheimen Client Schlüssel oder den Fingerabdruck, um den Graph Connector-Agent zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="913cd-149">Use either the client secret or thumbprint to register the Graph connector agent.</span></span>
<span data-ttu-id="913cd-150">![Registrieren eines Formulars, in dem der Name, die APP-ID, der Anmeldeinformationstyp und das Zertifikat gefragt werden](media/onprem-agent/register.png)</span><span class="sxs-lookup"><span data-stu-id="913cd-150">![Register form asking for name, app id, credential type, and certificate](media/onprem-agent/register.png)</span></span>
