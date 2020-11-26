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
ms.openlocfilehash: 763904f8dd96c5db8b0633e36795443502afe7d0
ms.sourcegitcommit: 0ed8ec8b3c4e0f5f669005081fd8b2219f07b4f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420833"
---
# <a name="graph-connector-agent"></a>Grafik-Connector-Agent

Bei Verwendung von on-Prem Graph Connectors müssen Sie die *Graph Connector Agent* -Software installieren. Es ermöglicht eine sichere Datenübertragung zwischen lokalen Daten und den Graph Connector-APIs. Dieser Artikel führt Sie durch das Installieren und Konfigurieren des Agents.

## <a name="installation"></a>Installation

Laden Sie die neueste Version von Graph Connector Agent [hier](https://aka.ms/gcadownload) herunter, und installieren Sie die Software mithilfe des Installations-Assistenten. Mit der empfohlenen Konfiguration des unten beschriebenen Computers kann die Software bis zu drei Verbindungen verarbeiten. Alle Verbindungen, die darüber hinausgehen, beeinträchtigen möglicherweise die Leistung aller Verbindungen auf dem Agent.

Empfohlene Konfiguration:

* Windows 10, Windows Server 2016 R2 und höher
* 8 Prozessorkerne, 3 GHz
* 16 GB RAM, 2 GB Speicherplatz
* Netzwerkzugriff auf Datenquelle und Internet über 443

## <a name="create-and-configure-an-app-for-the-agent"></a>Erstellen und Konfigurieren einer APP für den Agent  

Bevor Sie den Agent verwenden, müssen Sie eine APP erstellen und die Authentifizierungsdetails konfigurieren.

### <a name="create-an-app"></a>Erstellen einer APP

1. Wechseln Sie zum [Azure-Portal](https://portal.azure.com) , und melden Sie sich mit den Administratoranmeldeinformationen für den Mandanten an.
2. Navigieren Sie im Navigationsbereich zu **Azure Active Directory**  ->  **App-Registrierungen** , und wählen Sie **neue Registrierung** aus.
3. Geben Sie einen Namen für die APP ein, und wählen Sie **registrieren** aus.
4. Notieren Sie sich die Anwendungs-ID (Client).
5. Öffnen Sie **API-Berechtigungen** aus dem Navigationsbereich, und wählen Sie **Berechtigung hinzufügen** aus.
6. Wählen Sie **Microsoft Graph** und dann **Anwendungsberechtigungen** aus.
7. Suchen Sie nach "ExternalItem. ReadWrite. all" und "Directory. Read. all" aus den Berechtigungen, und wählen Sie **Berechtigungen hinzufügen** aus.
8. Wählen Sie **Administrator Zustimmung für [Mandanten] erteilen** aus, und bestätigen Sie mit **Ja**.
9. Stellen Sie sicher, dass sich die Berechtigungen im Status "erteilt" befinden.
     ![Berechtigungen, die in der rechten Spalte in grüner Form gewährt werden.](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>Konfigurieren einer Authentifizierung

Authentifizierungsdetails können mit einem geheimen Client Schlüssel oder einem Zertifikat bereitgestellt werden. Befolgen Sie die Schritte Ihrer Wahl.

#### <a name="configuring-the-client-secret-for-authentication"></a>Konfigurieren des geheimen Client Schlüssels für die Authentifizierung

1. Wechseln Sie zum [Azure-Portal](https://portal.azure.com) , und melden Sie sich mit den Administratoranmeldeinformationen für den Mandanten an.
2. Öffnen Sie die **App-Registrierung** im Navigationsbereich, und wechseln Sie zur entsprechenden app. Wählen Sie unter **Verwalten** die Option **Zertifikate und Geheimnisse** aus.
3. Wählen Sie **neuer geheimer Client Schlüssel** aus, und wählen Sie einen Ablaufzeitraum für den geheimen Schlüssel aus. Kopieren Sie den generierten geheimen Schlüssel, und speichern Sie ihn, da er nicht erneut angezeigt wird.
4. Verwenden Sie diesen geheimen Client Schlüssel zusammen mit der Anwendungs-ID, um den Agent zu konfigurieren. Im Feld **Name** des Agents können keine Leerzeichen verwendet werden. Alpha numerische Zeichen werden akzeptiert.

#### <a name="using-a-certificate-for-authentication"></a>Verwenden eines Zertifikats für die Authentifizierung

Es gibt drei einfache Schritte für die Verwendung der zertifikatbasierten Authentifizierung:

1. Erstellen oder Abrufen eines Zertifikats
1. Hochladen des Zertifikats in das Azure-Portal
1. Zuweisen des Zertifikats zum Agent

##### <a name="step-1-get-a-certificate"></a>Schritt 1: Abrufen eines Zertifikats

Das folgende Skript kann zum Generieren eines selbstsignierten Zertifikats verwendet werden. In Ihrer Organisation dürfen selbstsignierte Zertifikate nicht zugelassen werden. Verwenden Sie in diesem Fall diese Informationen, um die Anforderungen zu verstehen und ein Zertifikat entsprechend den Richtlinien Ihrer Organisation zu erwerben.

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

1. Öffnen der Anwendung und navigieren zu Zertifikaten und geheimen Schlüsseln im linken Bereich
1. Wählen Sie "Zertifikat hochladen" aus, und laden Sie die CER-Datei hoch
1. Öffnen Sie die **App-Registrierung** , und wählen Sie im Navigationsbereich **Zertifikate und Geheimnisse** aus. Kopieren Sie den Fingerabdruck des Zertifikats.

![Liste der thumbrint-Zertifikate, wenn Zertifikate und Geheimnisse im linken Bereich ausgewählt sind](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Schritt 3: Zuweisen des Zertifikats zum Agent

Wenn Sie das Beispielskript zum Generieren eines Zertifikats verwendet haben, kann die PFX-Datei an dem im Skript angegebenen Speicherort gefunden werden.

1. Laden Sie die PFX-Zertifikatdatei auf den Agentcomputer herunter.
1. Doppelklicken Sie auf die PFX-Datei, um das Zertifikat Installationsdialogfeld zu starten.
1. Wählen Sie "lokaler Computer" für den Speicher Speicherort aus, während Sie das Zertifikat installieren.
1. Öffnen Sie nach der Installation des Zertifikats im Startmenü die Option "Computerzertifikate verwalten".
1. Wählen Sie das neu installierte Zertifikat unter "persönlich"-> ' Certificates ' aus.
1. Klicken Sie mit der rechten Maustaste auf das Zertifikat, und wählen Sie "alle Aufgaben"-> "private Schlüssel verwalten..." aus. Option
1. Klicken Sie im Dialogfeld Berechtigungen auf Option hinzufügen. Schreiben Sie im Dialogfeld Benutzerauswahl Folgendes: "NT Service\GcaHostService" und klicken Sie auf "OK". Klicken Sie nicht auf die Schaltfläche Namen überprüfen.
1. Klicken Sie im Dialogfeld Berechtigungen auf OK. Der Agentcomputer ist jetzt für Agent zum Generieren von Token mit dem Zertifikat konfiguriert.
