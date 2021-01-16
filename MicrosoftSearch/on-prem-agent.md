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
# <a name="graph-connector-agent"></a>Graph Connector Agent

Für die Verwendung von graph-vorkonst nen Konnektoren müssen Sie *Graph Connector* Agent Software installieren. Sie ermöglicht eine sichere Datenübertragung zwischen lokalen Daten und den Graph-Connector-APIs. Dieser Artikel führt Sie durch die Installation und Konfiguration des Agents.

## <a name="installation"></a>Installation

Laden Sie hier die neueste Version des Graph-Connector-Agents [herunter,](https://aka.ms/gcadownload) und installieren Sie die Software mithilfe des Installations-Assistenten. Mithilfe der empfohlenen Konfiguration des unten beschriebenen Computers kann die Software bis zu drei Verbindungen verarbeiten. Darüber hinausgehende Verbindungen können die Leistung aller Verbindungen auf dem Agent beeinträchtigen.

Empfohlene Konfiguration:

* Windows 10, Windows Server 2016 R2 und höher
* [.NET Core Desktop Runtime 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 Kerne, 3 GHz
* 16 GB RAM, 2 GB Speicherplatz
* Netzwerkzugriff auf Datenquelle und Internet über 443

## <a name="create-and-configure-an-app-for-the-agent"></a>Erstellen und Konfigurieren einer App für den Agent  

Melden Sie sich zuerst an, und beachten Sie, dass die mindestens erforderliche Berechtigung für das Konto der Suchadministrator ist. Der Agent fordert Sie dann auf, Authentifizierungsdetails zur Verfügung zu stellen. Verwenden Sie die folgenden Schritte, um eine App zu erstellen und die erforderlichen Authentifizierungsdetails zu generieren.

### <a name="create-an-app"></a>App erstellen

1. Wechseln Sie zum [Azure-Portal,](https://portal.azure.com) und melden Sie sich mit Administratoranmeldeinformationen für den Mandanten an.
2. Navigieren Sie im **Navigationsbereich** zu Azure Active  ->  **Directory-App-Registrierungen,** und wählen Sie **"Neue Registrierung" aus.**
3. Geben Sie einen Namen für die App an, und wählen Sie **"Registrieren" aus.**
4. Notieren Sie sich die Anwendungs-ID (Client-ID).
5. Öffnen **Sie die API-Berechtigungen** im Navigationsbereich, und wählen **Sie "Berechtigung hinzufügen" aus.**
6. Wählen **Sie Microsoft Graph** und dann **Anwendungsberechtigungen aus.**
7. Suchen Sie in den Berechtigungen nach "ExternalItem.ReadWrite.All" und "Directory.Read.All", und wählen Sie **"Berechtigungen hinzufügen" aus.**
8. Wählen **Sie "Administratorzuwilligung für [Mandantname] erteilen"** aus, und bestätigen Sie dies, indem Sie **"Ja" auswählen.**
9. Überprüfen Sie, ob sich die Berechtigungen im Status "Gewährt" befinden.
     ![Berechtigungen, die in der rechten Spalte grün angezeigt werden.](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>Konfigurieren einer Authentifizierung

Authentifizierungsdetails können mithilfe eines geheimen Clientgeheimnis oder eines Zertifikats bereitgestellt werden. Führen Sie die schritte Ihrer Wahl aus.

#### <a name="configuring-the-client-secret-for-authentication"></a>Konfigurieren des geheimen Clientgeheimnis für die Authentifizierung

1. Wechseln Sie zum [Azure-Portal,](https://portal.azure.com) und melden Sie sich mit Administratoranmeldeinformationen für den Mandanten an.
2. Öffnen **Sie die App-Registrierung** im Navigationsbereich, und wechseln Sie zur entsprechenden App. Wählen **Sie unter "Verwalten"** **zertifikate und geheime Schlüssel aus.**
3. Wählen **Sie "Neuer geheimer Client",** und wählen Sie einen Ablaufzeitraum für den geheimen Client aus. Kopieren Sie den generierten geheimen Schlüssel, und speichern Sie ihn, da er nicht erneut angezeigt wird.
4. Verwenden Sie diesen geheimen Clientgeheimnis zusammen mit der Anwendungs-ID, um den Agent zu konfigurieren. Im Feld "Name" des Agents **können** keine Leerzeichen verwendet werden. Alphanumerische Zeichen werden akzeptiert.

#### <a name="using-a-certificate-for-authentication"></a>Verwenden eines Zertifikats für die Authentifizierung

Es gibt drei einfache Schritte für die Verwendung der zertifikatbasierten Authentifizierung:

1. Erstellen oder Abrufen eines Zertifikats
1. Hochladen des Zertifikats in das Azure-Portal
1. Zuweisen des Zertifikats zum Agent

##### <a name="step-1-get-a-certificate"></a>Schritt 1: Zertifikat erhalten

Das folgende Skript kann verwendet werden, um ein selbst signiertes Zertifikat zu generieren. Ihre Organisation lässt möglicherweise keine selbst signierten Zertifikate zu. Verwenden Sie in diesem Fall diese Informationen, um die Anforderungen zu verstehen und ein Zertifikat gemäß den Richtlinien Ihrer Organisation zu erwerben.

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Schritt 2: Hochladen des Zertifikats im Azure-Portal

1. Öffnen Sie die Anwendung, und navigieren Sie im linken Bereich zum Abschnitt "Zertifikate und geheime Schlüssel".
1. Wählen Sie "Zertifikat hochladen" aus, und laden Sie die .CER-Datei hoch.
1. Öffnen **Sie die App-Registrierung,** und wählen Sie zertifikate **und** geheime Schlüssel im Navigationsbereich aus. Kopieren Sie den Zertifikatfingerabdruck.

![Liste der Miniaturzertifikate, wenn zertifikate und geheime Schlüssel im linken Bereich ausgewählt werden](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Schritt 3: Zuweisen des Zertifikats zum Agent

Wenn Sie das Beispielskript zum Generieren eines Zertifikats verwendet haben, befindet sich die PFX-Datei an dem im Skript identifizierten Speicherort.

1. Laden Sie die Zertifikat-PFX-Datei auf den Agentcomputer herunter.
1. Doppelklicken Sie auf die PFX-Datei, um das Dialogfeld für die Zertifikatinstallation zu starten.
1. Wählen Sie während der Installation des Zertifikats "Lokaler Computer" als Speicherort aus.
1. Öffnen Sie nach der Installation des Zertifikats "Computerzertifikate verwalten" über das Startmenü.
1. Wählen Sie das neu installierte Zertifikat unter "Persönlich" > "Zertifikate" aus.
1. Klicken Sie mit der rechten Maustaste auf das Zertifikat, und wählen Sie "Alle Aufgaben" > "Private Schlüssel verwalten". Option
1. Wählen Sie im Dialogfeld "Berechtigungen" die Option "Hinzufügen" aus. Schreiben Sie im Dialogfeld "Benutzerauswahl" den Namen "NT-Dienst\GcaHostService", und klicken Sie auf "OK". Klicken Sie nicht auf die Schaltfläche "Namen überprüfen".
1. Klicken Sie im Dialogfeld "Berechtigungen" auf "Ok". Der Agentcomputer ist jetzt für den Agent zum Generieren von Token mithilfe des Zertifikats konfiguriert.
