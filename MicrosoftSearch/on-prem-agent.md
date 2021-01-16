---
title: Lokale Agent
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
description: Agent vor Ort
ms.openlocfilehash: 31220196849fe90ab2611e9c2b83a1cec0a02b34
ms.sourcegitcommit: a04f1df14a3221776ccd141f6060328612d80e06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876498"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="4317b-103">Graph Connector Agent</span><span class="sxs-lookup"><span data-stu-id="4317b-103">Graph connector agent</span></span>

<span data-ttu-id="4317b-104">Für die Verwendung von graph-vorkonst nen Konnektoren müssen Sie *Graph Connector* Agent Software installieren.</span><span class="sxs-lookup"><span data-stu-id="4317b-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="4317b-105">Sie ermöglicht eine sichere Datenübertragung zwischen lokalen Daten und den Graph-Connector-APIs.</span><span class="sxs-lookup"><span data-stu-id="4317b-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="4317b-106">Dieser Artikel führt Sie durch die Installation und Konfiguration des Agents.</span><span class="sxs-lookup"><span data-stu-id="4317b-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="4317b-107">Installation</span><span class="sxs-lookup"><span data-stu-id="4317b-107">Installation</span></span>

<span data-ttu-id="4317b-108">Laden Sie hier die neueste Version des Graph-Connector-Agents [herunter,](https://aka.ms/gcadownload) und installieren Sie die Software mithilfe des Installations-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="4317b-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="4317b-109">Mithilfe der empfohlenen Konfiguration des unten beschriebenen Computers kann die Software bis zu drei Verbindungen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4317b-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="4317b-110">Darüber hinausgehende Verbindungen können die Leistung aller Verbindungen auf dem Agent beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="4317b-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="4317b-111">Empfohlene Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="4317b-111">Recommended configuration:</span></span>

* <span data-ttu-id="4317b-112">Windows 10, Windows Server 2016 R2 und höher</span><span class="sxs-lookup"><span data-stu-id="4317b-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="4317b-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="4317b-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="4317b-114">8 Kerne, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="4317b-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="4317b-115">16 GB RAM, 2 GB Speicherplatz</span><span class="sxs-lookup"><span data-stu-id="4317b-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="4317b-116">Netzwerkzugriff auf Datenquelle und Internet über 443</span><span class="sxs-lookup"><span data-stu-id="4317b-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="4317b-117">Erstellen und Konfigurieren einer App für den Agent</span><span class="sxs-lookup"><span data-stu-id="4317b-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="4317b-118">Melden Sie sich zuerst an, und beachten Sie, dass die mindestens erforderliche Berechtigung für das Konto der Suchadministrator ist.</span><span class="sxs-lookup"><span data-stu-id="4317b-118">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="4317b-119">Der Agent fordert Sie dann auf, Authentifizierungsdetails zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="4317b-119">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="4317b-120">Verwenden Sie die folgenden Schritte, um eine App zu erstellen und die erforderlichen Authentifizierungsdetails zu generieren.</span><span class="sxs-lookup"><span data-stu-id="4317b-120">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="4317b-121">App erstellen</span><span class="sxs-lookup"><span data-stu-id="4317b-121">Create an app</span></span>

1. <span data-ttu-id="4317b-122">Wechseln Sie zum [Azure-Portal,](https://portal.azure.com) und melden Sie sich mit Administratoranmeldeinformationen für den Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="4317b-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="4317b-123">Navigieren Sie im **Navigationsbereich** zu Azure Active  ->  **Directory-App-Registrierungen,** und wählen Sie **"Neue Registrierung" aus.**</span><span class="sxs-lookup"><span data-stu-id="4317b-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="4317b-124">Geben Sie einen Namen für die App an, und wählen Sie **"Registrieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="4317b-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="4317b-125">Notieren Sie sich die Anwendungs-ID (Client-ID).</span><span class="sxs-lookup"><span data-stu-id="4317b-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="4317b-126">Öffnen **Sie die API-Berechtigungen** im Navigationsbereich, und wählen **Sie "Berechtigung hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="4317b-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="4317b-127">Wählen **Sie Microsoft Graph** und dann **Anwendungsberechtigungen aus.**</span><span class="sxs-lookup"><span data-stu-id="4317b-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="4317b-128">Suchen Sie in den Berechtigungen nach "ExternalItem.ReadWrite.All" und "Directory.Read.All", und wählen Sie **"Berechtigungen hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="4317b-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="4317b-129">Wählen **Sie "Administratorzuwilligung für [Mandantname] erteilen"** aus, und bestätigen Sie dies, indem Sie **"Ja" auswählen.**</span><span class="sxs-lookup"><span data-stu-id="4317b-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="4317b-130">Überprüfen Sie, ob sich die Berechtigungen im Status "Gewährt" befinden.</span><span class="sxs-lookup"><span data-stu-id="4317b-130">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="4317b-131">![Berechtigungen, die in der rechten Spalte grün angezeigt werden.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="4317b-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="4317b-132">Konfigurieren einer Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4317b-132">Configure Authentication</span></span>

<span data-ttu-id="4317b-133">Authentifizierungsdetails können mithilfe eines geheimen Clientgeheimnis oder eines Zertifikats bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4317b-133">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="4317b-134">Führen Sie die schritte Ihrer Wahl aus.</span><span class="sxs-lookup"><span data-stu-id="4317b-134">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="4317b-135">Konfigurieren des geheimen Clientgeheimnis für die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4317b-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="4317b-136">Wechseln Sie zum [Azure-Portal,](https://portal.azure.com) und melden Sie sich mit Administratoranmeldeinformationen für den Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="4317b-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="4317b-137">Öffnen **Sie die App-Registrierung** im Navigationsbereich, und wechseln Sie zur entsprechenden App.</span><span class="sxs-lookup"><span data-stu-id="4317b-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="4317b-138">Wählen **Sie unter "Verwalten"** **zertifikate und geheime Schlüssel aus.**</span><span class="sxs-lookup"><span data-stu-id="4317b-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="4317b-139">Wählen **Sie "Neuer geheimer Client",** und wählen Sie einen Ablaufzeitraum für den geheimen Client aus.</span><span class="sxs-lookup"><span data-stu-id="4317b-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="4317b-140">Kopieren Sie den generierten geheimen Schlüssel, und speichern Sie ihn, da er nicht erneut angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4317b-140">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="4317b-141">Verwenden Sie diesen geheimen Clientgeheimnis zusammen mit der Anwendungs-ID, um den Agent zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4317b-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="4317b-142">Im Feld "Name" des Agents **können** keine Leerzeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4317b-142">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="4317b-143">Alphanumerische Zeichen werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4317b-143">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="4317b-144">Verwenden eines Zertifikats für die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4317b-144">Using a certificate for authentication</span></span>

<span data-ttu-id="4317b-145">Es gibt drei einfache Schritte für die Verwendung der zertifikatbasierten Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="4317b-145">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="4317b-146">Erstellen oder Abrufen eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="4317b-146">Create or obtain a certificate</span></span>
1. <span data-ttu-id="4317b-147">Hochladen des Zertifikats in das Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="4317b-147">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="4317b-148">Zuweisen des Zertifikats zum Agent</span><span class="sxs-lookup"><span data-stu-id="4317b-148">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="4317b-149">Schritt 1: Zertifikat erhalten</span><span class="sxs-lookup"><span data-stu-id="4317b-149">Step 1: Get a certificate</span></span>

<span data-ttu-id="4317b-150">Das folgende Skript kann verwendet werden, um ein selbst signiertes Zertifikat zu generieren.</span><span class="sxs-lookup"><span data-stu-id="4317b-150">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="4317b-151">Ihre Organisation lässt möglicherweise keine selbst signierten Zertifikate zu.</span><span class="sxs-lookup"><span data-stu-id="4317b-151">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="4317b-152">Verwenden Sie in diesem Fall diese Informationen, um die Anforderungen zu verstehen und ein Zertifikat gemäß den Richtlinien Ihrer Organisation zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="4317b-152">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="4317b-153">Schritt 2: Hochladen des Zertifikats im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="4317b-153">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="4317b-154">Öffnen Sie die Anwendung, und navigieren Sie im linken Bereich zum Abschnitt "Zertifikate und geheime Schlüssel".</span><span class="sxs-lookup"><span data-stu-id="4317b-154">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="4317b-155">Wählen Sie "Zertifikat hochladen" aus, und laden Sie die .CER-Datei hoch.</span><span class="sxs-lookup"><span data-stu-id="4317b-155">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="4317b-156">Öffnen **Sie die App-Registrierung,** und wählen Sie zertifikate **und** geheime Schlüssel im Navigationsbereich aus.</span><span class="sxs-lookup"><span data-stu-id="4317b-156">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="4317b-157">Kopieren Sie den Zertifikatfingerabdruck.</span><span class="sxs-lookup"><span data-stu-id="4317b-157">Copy the certificate thumbprint.</span></span>

![Liste der Miniaturzertifikate, wenn zertifikate und geheime Schlüssel im linken Bereich ausgewählt werden](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="4317b-159">Schritt 3: Zuweisen des Zertifikats zum Agent</span><span class="sxs-lookup"><span data-stu-id="4317b-159">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="4317b-160">Wenn Sie das Beispielskript zum Generieren eines Zertifikats verwendet haben, befindet sich die PFX-Datei an dem im Skript identifizierten Speicherort.</span><span class="sxs-lookup"><span data-stu-id="4317b-160">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="4317b-161">Laden Sie die Zertifikat-PFX-Datei auf den Agentcomputer herunter.</span><span class="sxs-lookup"><span data-stu-id="4317b-161">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="4317b-162">Doppelklicken Sie auf die PFX-Datei, um das Dialogfeld für die Zertifikatinstallation zu starten.</span><span class="sxs-lookup"><span data-stu-id="4317b-162">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="4317b-163">Wählen Sie während der Installation des Zertifikats "Lokaler Computer" als Speicherort aus.</span><span class="sxs-lookup"><span data-stu-id="4317b-163">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="4317b-164">Öffnen Sie nach der Installation des Zertifikats "Computerzertifikate verwalten" über das Startmenü.</span><span class="sxs-lookup"><span data-stu-id="4317b-164">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="4317b-165">Wählen Sie das neu installierte Zertifikat unter "Persönlich" > "Zertifikate" aus.</span><span class="sxs-lookup"><span data-stu-id="4317b-165">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="4317b-166">Klicken Sie mit der rechten Maustaste auf das Zertifikat, und wählen Sie "Alle Aufgaben" > "Private Schlüssel verwalten".</span><span class="sxs-lookup"><span data-stu-id="4317b-166">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="4317b-167">Option</span><span class="sxs-lookup"><span data-stu-id="4317b-167">Option</span></span>
1. <span data-ttu-id="4317b-168">Wählen Sie im Dialogfeld "Berechtigungen" die Option "Hinzufügen" aus.</span><span class="sxs-lookup"><span data-stu-id="4317b-168">In the permissions dialog, select add option.</span></span> <span data-ttu-id="4317b-169">Schreiben Sie im Dialogfeld "Benutzerauswahl" den Namen "NT-Dienst\GcaHostService", und klicken Sie auf "OK".</span><span class="sxs-lookup"><span data-stu-id="4317b-169">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="4317b-170">Klicken Sie nicht auf die Schaltfläche "Namen überprüfen".</span><span class="sxs-lookup"><span data-stu-id="4317b-170">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="4317b-171">Klicken Sie im Dialogfeld "Berechtigungen" auf "Ok".</span><span class="sxs-lookup"><span data-stu-id="4317b-171">Click okay on the permissions dialog.</span></span> <span data-ttu-id="4317b-172">Der Agentcomputer ist jetzt für den Agent zum Generieren von Token mithilfe des Zertifikats konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4317b-172">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
