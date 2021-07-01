---
title: Lokaler Agent
ms.author: rusamai
author: rsamai
manager: jameslau
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: On-prem-Agent
ms.openlocfilehash: d6dabbbb5ee34acedd92166564f560bbc64c7da7
ms.sourcegitcommit: 93fc70f0073ab45b4dbd702441ac2fc07a7668bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230925"
---
# <a name="microsoft-graph-connector-agent"></a><span data-ttu-id="38d4d-103">Microsoft Graph Connector-Agent</span><span class="sxs-lookup"><span data-stu-id="38d4d-103">Microsoft Graph connector agent</span></span>

<span data-ttu-id="38d4d-104">Für die Verwendung von lokalen Connectors müssen Sie *Microsoft Graph Connector-Agent-Software* installieren.</span><span class="sxs-lookup"><span data-stu-id="38d4d-104">Using on-prem connectors require you to install *Microsoft Graph connector agent* software.</span></span> <span data-ttu-id="38d4d-105">Es ermöglicht eine sichere Datenübertragung zwischen lokalen Daten und den Connector-APIs.</span><span class="sxs-lookup"><span data-stu-id="38d4d-105">It allows for secure data transfer between on-premises data and the connector APIs.</span></span> <span data-ttu-id="38d4d-106">Dieser Artikel führt Sie durch die Installation und Konfiguration des Agents.</span><span class="sxs-lookup"><span data-stu-id="38d4d-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="38d4d-107">Installation</span><span class="sxs-lookup"><span data-stu-id="38d4d-107">Installation</span></span>

<span data-ttu-id="38d4d-108">Laden Sie die neueste Version des Graph Connector-Agents [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) herunter, und installieren Sie die Software mithilfe des Installations-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="38d4d-108">Download the latest version of the Graph connector agent from [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) and install the software by using the installation wizard.</span></span> <span data-ttu-id="38d4d-109">Mithilfe der empfohlenen Konfiguration des unten beschriebenen Computers kann die Software bis zu drei Verbindungen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="38d4d-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="38d4d-110">Darüber hinausgehende Verbindungen können die Leistung aller Verbindungen auf dem Agent beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="38d4d-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="38d4d-111">Empfohlene Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="38d4d-111">Recommended configuration:</span></span>

* <span data-ttu-id="38d4d-112">Windows 10, Windows Server 2016 R2 und höher</span><span class="sxs-lookup"><span data-stu-id="38d4d-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="38d4d-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="38d4d-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="38d4d-114">8 Kerne, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="38d4d-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="38d4d-115">16 GB RAM, 2 GB Speicherplatz</span><span class="sxs-lookup"><span data-stu-id="38d4d-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="38d4d-116">Netzwerkzugriff auf Datenquelle und Internet über 443</span><span class="sxs-lookup"><span data-stu-id="38d4d-116">Network access to data source and internet through 443</span></span>

<span data-ttu-id="38d4d-117">Wenn die Proxyserver oder Firewalls Ihrer Organisation nach der Installation des Agents die Kommunikation mit unbekannten Domänen blockieren, fügen Sie der Zulassungsliste die folgenden hinzu.</span><span class="sxs-lookup"><span data-stu-id="38d4d-117">After you install the agent, if your organization's proxy servers or firewalls block communication to unknown domains, please add below ones to the allow list.</span></span>

1. <span data-ttu-id="38d4d-118">\*.servicebus.windows.net</span><span class="sxs-lookup"><span data-stu-id="38d4d-118">\*.servicebus.windows.net</span></span>
2. <span data-ttu-id="38d4d-119">\*.events.data.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="38d4d-119">\*.events.data.microsoft.com</span></span>
3. <span data-ttu-id="38d4d-120"> https://<span>login.microsoftonline.</span> Com</span><span class="sxs-lookup"><span data-stu-id="38d4d-120">https://<span>login.microsoftonline.</span>com</span></span>
4. <span data-ttu-id="38d4d-121"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="38d4d-121">https://<span>gcs.office.</span>com/</span></span>
5. <span data-ttu-id="38d4d-122"> https://<span>graph.microsoft.</span> com/</span><span class="sxs-lookup"><span data-stu-id="38d4d-122">https://<span>graph.microsoft.</span>com/</span></span>


## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="38d4d-123">Erstellen und Konfigurieren einer App für den Agent</span><span class="sxs-lookup"><span data-stu-id="38d4d-123">Create and configure an App for the agent</span></span>  

<span data-ttu-id="38d4d-124">Melden Sie sich zuerst an, und beachten Sie, dass die mindestens erforderliche Berechtigung für das Konto der Suchadministrator ist.</span><span class="sxs-lookup"><span data-stu-id="38d4d-124">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="38d4d-125">Der Agent fordert Sie dann auf, Authentifizierungsdetails anzugeben.</span><span class="sxs-lookup"><span data-stu-id="38d4d-125">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="38d4d-126">Führen Sie die folgenden Schritte aus, um eine App zu erstellen und die erforderlichen Authentifizierungsdetails zu generieren.</span><span class="sxs-lookup"><span data-stu-id="38d4d-126">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="38d4d-127">App erstellen</span><span class="sxs-lookup"><span data-stu-id="38d4d-127">Create an app</span></span>

1. <span data-ttu-id="38d4d-128">Wechseln Sie zum [Azure-Portal,](https://portal.azure.com) und melden Sie sich mit Administratoranmeldeinformationen für den Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="38d4d-128">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>

2. <span data-ttu-id="38d4d-129">Navigieren Sie im Navigationsbereich zu **Azure Active Directory**  ->  **App-Registrierungen,** und wählen Sie **"Neue Registrierung"** aus.</span><span class="sxs-lookup"><span data-stu-id="38d4d-129">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>

3. <span data-ttu-id="38d4d-130">Geben Sie einen Namen für die App an, und wählen Sie **"Registrieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="38d4d-130">Provide a name for the app and select **Register**.</span></span>

4. <span data-ttu-id="38d4d-131">Notieren Sie sich die Anwendungs-ID (Client-ID).</span><span class="sxs-lookup"><span data-stu-id="38d4d-131">Make a note of the Application (client) ID.</span></span>

5. <span data-ttu-id="38d4d-132">Öffnen Sie **API-Berechtigungen** im Navigationsbereich, und wählen Sie **"Berechtigung hinzufügen"** aus.</span><span class="sxs-lookup"><span data-stu-id="38d4d-132">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>

6. <span data-ttu-id="38d4d-133">Wählen Sie **Microsoft Graph** und dann **Anwendungsberechtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="38d4d-133">Select **Microsoft Graph** and then **Application permissions**.</span></span>

7. <span data-ttu-id="38d4d-134">Suchen Sie in den Berechtigungen nach "ExternalItem.ReadWrite.All" und "Directory.Read.All", und wählen Sie **"Berechtigungen hinzufügen"** aus.</span><span class="sxs-lookup"><span data-stu-id="38d4d-134">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>

8. <span data-ttu-id="38d4d-135">Wählen Sie **"Administratorzustimmung für [TenantName] erteilen" aus,** und bestätigen Sie, indem Sie **"Ja"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="38d4d-135">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>

9. <span data-ttu-id="38d4d-136">Überprüfen Sie, ob sich die Berechtigungen im Status "Erteilt" befinden.</span><span class="sxs-lookup"><span data-stu-id="38d4d-136">Check that the permissions are in the "granted" state.</span></span>

    :::image type="content" alt-text="Berechtigungen werden in grün in der rechten Spalte angezeigt." source="media/onprem-agent/granted-state.png" lightbox="media/onprem-agent/granted-state.png":::

### <a name="configure-authentication"></a><span data-ttu-id="38d4d-138">Konfigurieren einer Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="38d4d-138">Configure Authentication</span></span>

<span data-ttu-id="38d4d-139">Authentifizierungsdetails können mithilfe eines geheimen Clientschlüssels oder eines Zertifikats bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="38d4d-139">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="38d4d-140">Führen Sie die von Ihnen gewählten Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="38d4d-140">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="38d4d-141">Konfigurieren des geheimen Clientschlüssels für die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="38d4d-141">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="38d4d-142">Wechseln Sie zum [Azure-Portal,](https://portal.azure.com) und melden Sie sich mit Administratoranmeldeinformationen für den Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="38d4d-142">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>

2. <span data-ttu-id="38d4d-143">Öffnen Sie die **App-Registrierung** im Navigationsbereich, und wechseln Sie zur entsprechenden App.</span><span class="sxs-lookup"><span data-stu-id="38d4d-143">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="38d4d-144">Wählen Sie unter **"Verwalten"** **Zertifikate und geheime Schlüssel aus.**</span><span class="sxs-lookup"><span data-stu-id="38d4d-144">Under **Manage**, select **Certificates and secrets**.</span></span>

3. <span data-ttu-id="38d4d-145">Wählen Sie **"Neuer geheimer Clientschlüssel"** aus, und wählen Sie einen Ablaufdatum für den geheimen Clientschlüssel aus.</span><span class="sxs-lookup"><span data-stu-id="38d4d-145">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="38d4d-146">Kopieren Sie den generierten geheimen Schlüssel, und speichern Sie ihn, da er nicht erneut angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="38d4d-146">Copy the generated secret and save it because it won't be shown again.</span></span>

4. <span data-ttu-id="38d4d-147">Verwenden Sie diesen geheimen Clientschlüssel zusammen mit der Anwendungs-ID, um den Agent zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="38d4d-147">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="38d4d-148">Sie können keine Leerzeichen im **Feld "Name"** des Agents verwenden.</span><span class="sxs-lookup"><span data-stu-id="38d4d-148">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="38d4d-149">Alphanumerische Zeichen werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="38d4d-149">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="38d4d-150">Verwenden eines Zertifikats für die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="38d4d-150">Using a certificate for authentication</span></span>

<span data-ttu-id="38d4d-151">Es gibt drei einfache Schritte für die Verwendung der zertifikatbasierten Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="38d4d-151">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="38d4d-152">Erstellen oder Abrufen eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="38d4d-152">Create or obtain a certificate</span></span>
1. <span data-ttu-id="38d4d-153">Hochladen des Zertifikats an das Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="38d4d-153">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="38d4d-154">Zuweisen des Zertifikats zum Agent</span><span class="sxs-lookup"><span data-stu-id="38d4d-154">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="38d4d-155">Schritt 1: Abrufen eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="38d4d-155">Step 1: Get a certificate</span></span>

<span data-ttu-id="38d4d-156">Das folgende Skript kann verwendet werden, um ein selbstsigniertes Zertifikat zu generieren.</span><span class="sxs-lookup"><span data-stu-id="38d4d-156">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="38d4d-157">Ihre Organisation lässt möglicherweise keine selbstsignten Zertifikate zu.</span><span class="sxs-lookup"><span data-stu-id="38d4d-157">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="38d4d-158">Verwenden Sie in diesem Fall diese Informationen, um die Anforderungen zu verstehen und ein Zertifikat gemäß den Richtlinien Ihrer Organisation zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="38d4d-158">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

```powershell
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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="38d4d-159">Schritt 2: Hochladen des Zertifikats im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="38d4d-159">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="38d4d-160">Öffnen Sie die Anwendung, und navigieren Sie im linken Bereich zum Abschnitt "Zertifikate und geheime Schlüssel".</span><span class="sxs-lookup"><span data-stu-id="38d4d-160">Open the application and navigate to certificates and secrets section from left pane.</span></span>

1. <span data-ttu-id="38d4d-161">Wählen Sie **Hochladen Zertifikat aus,** und laden Sie die CER-Datei hoch.</span><span class="sxs-lookup"><span data-stu-id="38d4d-161">Select **Upload certificate** and upload the .cer file.</span></span>

1. <span data-ttu-id="38d4d-162">Öffnen Sie **die App-Registrierung,** und wählen Sie im Navigationsbereich **Zertifikate und geheime Schlüssel** aus.</span><span class="sxs-lookup"><span data-stu-id="38d4d-162">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="38d4d-163">Kopieren Sie den Zertifikatfingerabdruck.</span><span class="sxs-lookup"><span data-stu-id="38d4d-163">Copy the certificate thumbprint.</span></span>

:::image type="content" alt-text="Liste der Miniaturzertifikate, wenn Zertifikate und geheime Schlüssel im linken Bereich ausgewählt sind" source="media/onprem-agent/certificates.png" lightbox="media/onprem-agent/certificates.png":::

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="38d4d-165">Schritt 3: Zuweisen des Zertifikats zum Agent</span><span class="sxs-lookup"><span data-stu-id="38d4d-165">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="38d4d-166">Wenn Sie das Beispielskript zum Generieren eines Zertifikats verwendet haben, befindet sich die PFX-Datei an dem im Skript angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="38d4d-166">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="38d4d-167">Laden Sie die Pfx-Zertifikatdatei auf den Agent-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="38d4d-167">Download the certificate pfx file onto the Agent machine.</span></span>

1. <span data-ttu-id="38d4d-168">Doppelklicken Sie auf die PFX-Datei, um das Dialogfeld für die Zertifikatinstallation zu starten.</span><span class="sxs-lookup"><span data-stu-id="38d4d-168">Double-click the pfx file to launch the certificate installation dialog.</span></span>

1. <span data-ttu-id="38d4d-169">Wählen Sie bei der Installation des Zertifikats den **lokalen Computer** als Speicherort aus.</span><span class="sxs-lookup"><span data-stu-id="38d4d-169">Select **Local Machine** for store location while installing the certificate.</span></span>

1. <span data-ttu-id="38d4d-170">Öffnen Sie nach der Installation des Zertifikats **Computerzertifikate** über Startmenü verwalten.</span><span class="sxs-lookup"><span data-stu-id="38d4d-170">After installing the certificate, open **Manage computer certificates** through Start menu.</span></span>

1. <span data-ttu-id="38d4d-171">Wählen Sie das neu installierte Zertifikat unter **"Persönliche**  >  **Zertifikate" aus.**</span><span class="sxs-lookup"><span data-stu-id="38d4d-171">Select the newly installed certificate under **Personal** > **Certificates**.</span></span>

1. <span data-ttu-id="38d4d-172">Klicken Sie mit der rechten Maustaste auf das Zertifikat, und wählen Sie die Option **"Alle Aufgaben**  >  **verwalten private Schlüssel" aus.**</span><span class="sxs-lookup"><span data-stu-id="38d4d-172">Right click on the cert and select **All Tasks** > **Manage Private Keys** Option.</span></span>

1. <span data-ttu-id="38d4d-173">Wählen Sie im Dialogfeld "Berechtigungen" die Option "Hinzufügen" aus.</span><span class="sxs-lookup"><span data-stu-id="38d4d-173">In the permissions dialog, select add option.</span></span> <span data-ttu-id="38d4d-174">Schreiben Sie im Dialogfeld "Benutzerauswahl": **NT Service\GcaHostService,** und klicken Sie auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="38d4d-174">In the user selection dialog, write: **NT Service\GcaHostService** and click **OK**.</span></span> <span data-ttu-id="38d4d-175">Klicken Sie nicht auf die Schaltfläche **"Namen überprüfen".**</span><span class="sxs-lookup"><span data-stu-id="38d4d-175">Don't click the **Check Names** button.</span></span>

1. <span data-ttu-id="38d4d-176">Klicken Sie im Dialogfeld "Berechtigungen" auf "ok".</span><span class="sxs-lookup"><span data-stu-id="38d4d-176">Click okay on the permissions dialog.</span></span> <span data-ttu-id="38d4d-177">Der Agentcomputer ist jetzt so konfiguriert, dass der Agent Token mithilfe des Zertifikats generiert.</span><span class="sxs-lookup"><span data-stu-id="38d4d-177">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="38d4d-178">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="38d4d-178">Troubleshooting</span></span>

1. <span data-ttu-id="38d4d-179">Wenn eine Verbindung mit dem Fehler "1011: Der Graph Connector-Agent ist nicht erreichbar oder offline" fehlschlägt, melden Sie sich bei dem Computer an, auf dem der Agent installiert ist, und starten Sie die Agent-Anwendung, wenn er noch nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="38d4d-179">If a connection fails with the error "1011: The Graph connector agent is not reachable or offline.", log in to the machine where agent is installed and start the agent application if it isn't running already.</span></span> <span data-ttu-id="38d4d-180">Wenn die Verbindung weiterhin fehlschlägt, überprüfen Sie, ob das Zertifikat oder der geheime Clientschlüssel, der dem Agent während der Registrierung bereitgestellt wurde, nicht abgelaufen ist und über erforderliche Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="38d4d-180">If the connection continues to fail, verify that the certificate or client secret provided to the agent during registration hasn't expired and has required permissions.</span></span>
