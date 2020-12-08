---
title: Lokaler Agent
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
ms.openlocfilehash: 5dbca392fefdcc11de253fd244cc98a6adcee68a
ms.sourcegitcommit: e8d770fa72ac83e074a5de57098cb55d06d8db07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588367"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="4eaa6-103">Grafik-Connector-Agent</span><span class="sxs-lookup"><span data-stu-id="4eaa6-103">Graph connector agent</span></span>

<span data-ttu-id="4eaa6-104">Bei Verwendung von on-Prem Graph Connectors müssen Sie die *Graph Connector Agent* -Software installieren.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="4eaa6-105">Es ermöglicht eine sichere Datenübertragung zwischen lokalen Daten und den Graph Connector-APIs.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="4eaa6-106">Dieser Artikel führt Sie durch das Installieren und Konfigurieren des Agents.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="4eaa6-107">Installation</span><span class="sxs-lookup"><span data-stu-id="4eaa6-107">Installation</span></span>

<span data-ttu-id="4eaa6-108">Laden Sie die neueste Version von Graph Connector Agent [hier](https://aka.ms/gcadownload) herunter, und installieren Sie die Software mithilfe des Installations-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="4eaa6-109">Mit der empfohlenen Konfiguration des unten beschriebenen Computers kann die Software bis zu drei Verbindungen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="4eaa6-110">Alle Verbindungen, die darüber hinausgehen, beeinträchtigen möglicherweise die Leistung aller Verbindungen auf dem Agent.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="4eaa6-111">Empfohlene Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="4eaa6-111">Recommended configuration:</span></span>

* <span data-ttu-id="4eaa6-112">Windows 10, Windows Server 2016 R2 und höher</span><span class="sxs-lookup"><span data-stu-id="4eaa6-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="4eaa6-113">.Net Core Desktop Runtime 3,1 (x64)</span><span class="sxs-lookup"><span data-stu-id="4eaa6-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="4eaa6-114">8 Prozessorkerne, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="4eaa6-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="4eaa6-115">16 GB RAM, 2 GB Speicherplatz</span><span class="sxs-lookup"><span data-stu-id="4eaa6-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="4eaa6-116">Netzwerkzugriff auf Datenquelle und Internet über 443</span><span class="sxs-lookup"><span data-stu-id="4eaa6-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="4eaa6-117">Erstellen und Konfigurieren einer APP für den Agent</span><span class="sxs-lookup"><span data-stu-id="4eaa6-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="4eaa6-118">Bevor Sie den Agent verwenden, müssen Sie eine APP erstellen und die Authentifizierungsdetails konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-118">Before using the agent, you must create an app and configure the authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="4eaa6-119">Erstellen einer APP</span><span class="sxs-lookup"><span data-stu-id="4eaa6-119">Create an app</span></span>

1. <span data-ttu-id="4eaa6-120">Wechseln Sie zum [Azure-Portal](https://portal.azure.com) , und melden Sie sich mit den Administratoranmeldeinformationen für den Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-120">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="4eaa6-121">Navigieren Sie im Navigationsbereich zu **Azure Active Directory**  ->  **App-Registrierungen** , und wählen Sie **neue Registrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-121">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="4eaa6-122">Geben Sie einen Namen für die APP ein, und wählen Sie **registrieren** aus.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-122">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="4eaa6-123">Notieren Sie sich die Anwendungs-ID (Client).</span><span class="sxs-lookup"><span data-stu-id="4eaa6-123">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="4eaa6-124">Öffnen Sie **API-Berechtigungen** aus dem Navigationsbereich, und wählen Sie **Berechtigung hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-124">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="4eaa6-125">Wählen Sie **Microsoft Graph** und dann **Anwendungsberechtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-125">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="4eaa6-126">Suchen Sie nach "ExternalItem. ReadWrite. all" und "Directory. Read. all" aus den Berechtigungen, und wählen Sie **Berechtigungen hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-126">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="4eaa6-127">Wählen Sie **Administrator Zustimmung für [Mandanten] erteilen** aus, und bestätigen Sie mit **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-127">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="4eaa6-128">Stellen Sie sicher, dass sich die Berechtigungen im Status "erteilt" befinden.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-128">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="4eaa6-129">![Berechtigungen, die in der rechten Spalte in grüner Form gewährt werden.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="4eaa6-129">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="4eaa6-130">Konfigurieren einer Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4eaa6-130">Configure Authentication</span></span>

<span data-ttu-id="4eaa6-131">Authentifizierungsdetails können mit einem geheimen Client Schlüssel oder einem Zertifikat bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-131">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="4eaa6-132">Befolgen Sie die Schritte Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-132">Follow the steps for your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="4eaa6-133">Konfigurieren des geheimen Client Schlüssels für die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4eaa6-133">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="4eaa6-134">Wechseln Sie zum [Azure-Portal](https://portal.azure.com) , und melden Sie sich mit den Administratoranmeldeinformationen für den Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-134">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="4eaa6-135">Öffnen Sie die **App-Registrierung** im Navigationsbereich, und wechseln Sie zur entsprechenden app.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-135">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="4eaa6-136">Wählen Sie unter **Verwalten** die Option **Zertifikate und Geheimnisse** aus.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-136">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="4eaa6-137">Wählen Sie **neuer geheimer Client Schlüssel** aus, und wählen Sie einen Ablaufzeitraum für den geheimen Schlüssel aus.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-137">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="4eaa6-138">Kopieren Sie den generierten geheimen Schlüssel, und speichern Sie ihn, da er nicht erneut angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-138">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="4eaa6-139">Verwenden Sie diesen geheimen Client Schlüssel zusammen mit der Anwendungs-ID, um den Agent zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-139">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="4eaa6-140">Im Feld **Name** des Agents können keine Leerzeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-140">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="4eaa6-141">Alpha numerische Zeichen werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-141">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="4eaa6-142">Verwenden eines Zertifikats für die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4eaa6-142">Using a certificate for authentication</span></span>

<span data-ttu-id="4eaa6-143">Es gibt drei einfache Schritte für die Verwendung der zertifikatbasierten Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="4eaa6-143">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="4eaa6-144">Erstellen oder Abrufen eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="4eaa6-144">Create or obtain a certificate</span></span>
1. <span data-ttu-id="4eaa6-145">Hochladen des Zertifikats in das Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="4eaa6-145">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="4eaa6-146">Zuweisen des Zertifikats zum Agent</span><span class="sxs-lookup"><span data-stu-id="4eaa6-146">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="4eaa6-147">Schritt 1: Abrufen eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="4eaa6-147">Step 1: Get a certificate</span></span>

<span data-ttu-id="4eaa6-148">Das folgende Skript kann zum Generieren eines selbstsignierten Zertifikats verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-148">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="4eaa6-149">In Ihrer Organisation dürfen selbstsignierte Zertifikate nicht zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-149">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="4eaa6-150">Verwenden Sie in diesem Fall diese Informationen, um die Anforderungen zu verstehen und ein Zertifikat entsprechend den Richtlinien Ihrer Organisation zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-150">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

```Powershell
$dnsName = "<TenantDomain like agent.onmicrosoft.com>" # Your DNS name
$password = "<password>" # Certificate password
$folderPath = "D:\New folder\" # Where do you want the files to get saved to? The folder needs to exist.
$fileName = "agentcert" # What do you want to call the cert files? without the file extension
$yearsValid = 10 # Number of years until you need to renew the certificate
$certStoreLocation = "cert:\LocalMachine\My"
$expirationDate = (Get-Date).AddYears($yearsValid)
$certificate = New-SelfSignedCertificate -DnsName $dnsName -CertStoreLocation $certStoreLocation -NotAfter $expirationDate -KeyExportPolicy Exportable -KeySpec Signature
$certificatePath = $certStoreLocation + '\' + $certificate.Thumbprint
$filePath = $folderPath + '\' + $fileName
$securePassword = ConvertTo-SecureString -String $password -Force -AsPlainText
Export-Certificate -Cert $certificatePath -FilePath ($filePath + '.cer')
Export-PfxCertificate -Cert $certificatePath -FilePath ($filePath + '.pfx') -Password $securePassword
```

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="4eaa6-151">Schritt 2: Hochladen des Zertifikats im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="4eaa6-151">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="4eaa6-152">Öffnen der Anwendung und navigieren zu Zertifikaten und geheimen Schlüsseln im linken Bereich</span><span class="sxs-lookup"><span data-stu-id="4eaa6-152">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="4eaa6-153">Wählen Sie "Zertifikat hochladen" aus, und laden Sie die CER-Datei hoch</span><span class="sxs-lookup"><span data-stu-id="4eaa6-153">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="4eaa6-154">Öffnen Sie die **App-Registrierung** , und wählen Sie im Navigationsbereich **Zertifikate und Geheimnisse** aus.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-154">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="4eaa6-155">Kopieren Sie den Fingerabdruck des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-155">Copy the certificate thumbprint.</span></span>

![Liste der thumbrint-Zertifikate, wenn Zertifikate und Geheimnisse im linken Bereich ausgewählt sind](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="4eaa6-157">Schritt 3: Zuweisen des Zertifikats zum Agent</span><span class="sxs-lookup"><span data-stu-id="4eaa6-157">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="4eaa6-158">Wenn Sie das Beispielskript zum Generieren eines Zertifikats verwendet haben, kann die PFX-Datei an dem im Skript angegebenen Speicherort gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-158">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="4eaa6-159">Laden Sie die PFX-Zertifikatdatei auf den Agentcomputer herunter.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-159">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="4eaa6-160">Doppelklicken Sie auf die PFX-Datei, um das Zertifikat Installationsdialogfeld zu starten.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-160">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="4eaa6-161">Wählen Sie "lokaler Computer" für den Speicher Speicherort aus, während Sie das Zertifikat installieren.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-161">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="4eaa6-162">Öffnen Sie nach der Installation des Zertifikats im Startmenü die Option "Computerzertifikate verwalten".</span><span class="sxs-lookup"><span data-stu-id="4eaa6-162">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="4eaa6-163">Wählen Sie das neu installierte Zertifikat unter "persönlich"-> ' Certificates ' aus.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-163">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="4eaa6-164">Klicken Sie mit der rechten Maustaste auf das Zertifikat, und wählen Sie "alle Aufgaben"-> "private Schlüssel verwalten..." aus.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-164">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="4eaa6-165">Option</span><span class="sxs-lookup"><span data-stu-id="4eaa6-165">Option</span></span>
1. <span data-ttu-id="4eaa6-166">Klicken Sie im Dialogfeld Berechtigungen auf Option hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-166">In the permissions dialog, select add option.</span></span> <span data-ttu-id="4eaa6-167">Schreiben Sie im Dialogfeld Benutzerauswahl Folgendes: "NT Service\GcaHostService" und klicken Sie auf "OK".</span><span class="sxs-lookup"><span data-stu-id="4eaa6-167">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="4eaa6-168">Klicken Sie nicht auf die Schaltfläche Namen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-168">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="4eaa6-169">Klicken Sie im Dialogfeld Berechtigungen auf OK.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-169">Click okay on the permissions dialog.</span></span> <span data-ttu-id="4eaa6-170">Der Agentcomputer ist jetzt für Agent zum Generieren von Token mit dem Zertifikat konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4eaa6-170">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
