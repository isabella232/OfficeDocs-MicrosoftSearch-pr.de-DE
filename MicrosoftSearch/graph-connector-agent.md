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
description: On-prem-Agent
ms.openlocfilehash: a27b5225d6a9f804d9122fbb237adb453eaf34ba
ms.sourcegitcommit: 7148807ee9c857bd900916bed24176892a7d1d66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2021
ms.locfileid: "58363241"
---
# <a name="microsoft-graph-connector-agent"></a>Microsoft Graph Connector-Agent

Für die Verwendung von lokalen Connectors müssen Sie *Microsoft Graph Connector-Agent-Software* installieren. Es ermöglicht eine sichere Datenübertragung zwischen lokalen Daten und den Connector-APIs. Dieser Artikel führt Sie durch die Installation und Konfiguration des Agents.

## <a name="installation"></a>Installation

Laden Sie die neueste Version des Graph Connector-Agents [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) herunter, und installieren Sie die Software mithilfe des Installations-Assistenten. Mithilfe der empfohlenen Konfiguration des unten beschriebenen Computers kann die Software bis zu drei Verbindungen verarbeiten. Darüber hinausgehende Verbindungen können die Leistung aller Verbindungen auf dem Agent beeinträchtigen.

Empfohlene Konfiguration:

* Windows 10, Windows Server 2016 R2 und höher
* [.NET Core Desktop Runtime 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 Kerne, 3 GHz
* 16 GB RAM, 2 GB Speicherplatz
* Netzwerkzugriff auf Datenquelle und Internet über 443

Wenn die Proxyserver oder Firewalls Ihrer Organisation nach der Installation des Agents die Kommunikation mit unbekannten Domänen blockieren, fügen Sie der Zulassungsliste die folgenden hinzu.

1. *.servicebus.windows.net
2. *.events.data.microsoft.com
3. https://<span>login.microsoftonline.</span> Com
4. https://<span>gcs.office.</span> com/
5. https://<span>graph.microsoft.</span> com/

>[!NOTE]
>Proxyauthentifizierung wird nicht unterstützt. Wenn Ihre Umgebung über einen Proxy verfügt, der eine Authentifizierung erfordert, empfehlen wir, dem Connector-Agent die Umgehung des Proxys zu erlauben.

## <a name="create-and-configure-an-app-for-the-agent"></a>Erstellen und Konfigurieren einer App für den Agent  

Melden Sie sich zuerst an, und beachten Sie, dass die mindestens erforderliche Berechtigung für das Konto der Suchadministrator ist. Der Agent fordert Sie dann auf, Authentifizierungsdetails anzugeben. Führen Sie die folgenden Schritte aus, um eine App zu erstellen und die erforderlichen Authentifizierungsdetails zu generieren.

### <a name="create-an-app"></a>App erstellen

1. Wechseln Sie zum [Azure-Portal,](https://portal.azure.com) und melden Sie sich mit Administratoranmeldeinformationen für den Mandanten an.

2. Navigieren Sie im Navigationsbereich zu **Azure Active Directory**  ->  **App-Registrierungen,** und wählen Sie **"Neue Registrierung"** aus.

3. Geben Sie einen Namen für die App an, und wählen Sie **"Registrieren"** aus.

4. Notieren Sie sich die Anwendungs-ID (Client-ID).

5. Öffnen Sie **API-Berechtigungen** im Navigationsbereich, und wählen Sie **"Berechtigung hinzufügen"** aus.

6. Wählen Sie **Microsoft Graph** und dann **Anwendungsberechtigungen** aus.

7. Suchen Sie in den Berechtigungen nach "ExternalItem.ReadWrite.All" und "Directory.Read.All", und wählen Sie **"Berechtigungen hinzufügen"** aus.

8. Wählen Sie **"Administratorzustimmung für [TenantName] erteilen" aus,** und bestätigen Sie, indem Sie **"Ja"** auswählen.

9. Überprüfen Sie, ob sich die Berechtigungen im Status "Erteilt" befinden.

    :::image type="content" alt-text="Berechtigungen werden in grün in der rechten Spalte angezeigt." source="media/onprem-agent/granted-state.png" lightbox="media/onprem-agent/granted-state.png":::

### <a name="configure-authentication"></a>Konfigurieren einer Authentifizierung

Authentifizierungsdetails können mithilfe eines geheimen Clientschlüssels oder eines Zertifikats bereitgestellt werden. Führen Sie die von Ihnen gewählten Schritte aus.

#### <a name="configuring-the-client-secret-for-authentication"></a>Konfigurieren des geheimen Clientschlüssels für die Authentifizierung

1. Wechseln Sie zum [Azure-Portal,](https://portal.azure.com) und melden Sie sich mit Administratoranmeldeinformationen für den Mandanten an.

2. Öffnen Sie die **App-Registrierung** im Navigationsbereich, und wechseln Sie zur entsprechenden App. Wählen Sie unter **"Verwalten"** **Zertifikate und geheime Schlüssel aus.**

3. Wählen Sie **"Neuer geheimer Clientschlüssel"** aus, und wählen Sie einen Ablaufdatum für den geheimen Clientschlüssel aus. Kopieren Sie den generierten geheimen Schlüssel, und speichern Sie ihn, da er nicht erneut angezeigt wird.

4. Verwenden Sie diesen geheimen Clientschlüssel zusammen mit der Anwendungs-ID, um den Agent zu konfigurieren. Sie können keine Leerzeichen im **Feld "Name"** des Agents verwenden. Alphanumerische Zeichen werden akzeptiert.

#### <a name="using-a-certificate-for-authentication"></a>Verwenden eines Zertifikats für die Authentifizierung

Es gibt drei einfache Schritte für die Verwendung der zertifikatbasierten Authentifizierung:

1. Erstellen oder Abrufen eines Zertifikats
2. Hochladen des Zertifikats an das Azure-Portal
3. Zuweisen des Zertifikats zum Agent

##### <a name="step-1-get-a-certificate"></a>Schritt 1: Abrufen eines Zertifikats

Das folgende Skript kann verwendet werden, um ein selbstsigniertes Zertifikat zu generieren. Ihre Organisation lässt möglicherweise keine selbstsignten Zertifikate zu. Verwenden Sie in diesem Fall diese Informationen, um die Anforderungen zu verstehen und ein Zertifikat gemäß den Richtlinien Ihrer Organisation zu erwerben.

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Schritt 2: Hochladen des Zertifikats im Azure-Portal

1. Öffnen Sie die Anwendung, und navigieren Sie im linken Bereich zum Abschnitt "Zertifikate und geheime Schlüssel".

2. Wählen Sie **Hochladen Zertifikat aus,** und laden Sie die CER-Datei hoch.

3. Öffnen Sie **die App-Registrierung,** und wählen Sie im Navigationsbereich **Zertifikate und geheime Schlüssel** aus. Kopieren Sie den Zertifikatfingerabdruck.

:::image type="content" alt-text="Liste der Miniaturzertifikate, wenn Zertifikate und geheime Schlüssel im linken Bereich ausgewählt sind" source="media/onprem-agent/certificates.png" lightbox="media/onprem-agent/certificates.png":::

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Schritt 3: Zuweisen des Zertifikats zum Agent

Wenn Sie das Beispielskript zum Generieren eines Zertifikats verwendet haben, befindet sich die PFX-Datei an dem im Skript angegebenen Speicherort.

1. Laden Sie die Pfx-Zertifikatdatei auf den Agent-Computer herunter.

2. Doppelklicken Sie auf die PFX-Datei, um das Dialogfeld für die Zertifikatinstallation zu starten.

3. Wählen Sie bei der Installation des Zertifikats den **lokalen Computer** als Speicherort aus.

4. Öffnen Sie nach der Installation des Zertifikats **Computerzertifikate** über Startmenü verwalten.

5. Wählen Sie das neu installierte Zertifikat unter **"Persönliche**  >  **Zertifikate" aus.**

6. Klicken Sie mit der rechten Maustaste auf das Zertifikat, und wählen Sie die Option **"Alle Aufgaben**  >  **verwalten private Schlüssel" aus.**

7. Wählen Sie im Dialogfeld "Berechtigungen" die Option "Hinzufügen" aus. Es wird ein neues Fenster geöffnet. Wählen Sie darin die Option "Standorte" aus. Wählen Sie den Computer aus, auf dem der Agent installiert ist, in der Liste der angezeigten Speicherorte, und klicken Sie auf **"OK".**

8. Schreiben Sie im Dialogfeld "Benutzerauswahl": **NT Service\GcaHostService,** und klicken Sie auf **"OK".** Klicken Sie nicht auf die Schaltfläche **"Namen überprüfen".**

9. Klicken Sie im Dialogfeld "Berechtigungen" auf "ok". Der Agentcomputer ist jetzt so konfiguriert, dass der Agent Token mithilfe des Zertifikats generiert.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="installation-failure"></a>Installationsfehler

Wenn die Installation fehlschlägt, überprüfen Sie die Installationsprotokolle, indem Sie "msiexec /i " < Pfad zu msi >\GcaInstaller.msi" /L*V "< Zielpfad >\install.log" ausführen. Wenn die Fehler nicht aufgelöst werden können, erreichen Sie die Unterstützung für MicrosoftGraphConnectorsFeedback@service.microsoft.com mit den Protokollen.

### <a name="registration-failure"></a>Registrierungsfehler

Wenn die Anmeldung bei der Konfigurations-App fehlschlägt mit dem Fehler "Anmeldung fehlgeschlagen. Klicken Sie auf die Anmeldeschaltfläche, um es erneut zu versuchen." Öffnen Sie auch nach erfolgreicher Browserauthentifizierung "services.msc", und überprüfen Sie, ob GcaHostService ausgeführt wird. Wenn dies nicht der Typ ist, starten Sie ihn manuell.

Wenn der Dienst nicht mit dem Fehler "Der Dienst wurde aufgrund eines Anmeldefehlers nicht gestartet" gestartet werden kann, überprüfen Sie, ob das virtuelle Konto NT Service\GcaHostService über die Berechtigung zum Anmelden als Dienst auf dem Computer verfügt. Anweisungen finden Sie [unter diesem Link.](/windows/security/threat-protection/security-policy-settings/log-on-as-a-service) Wenn die Option zum Hinzufügen von Benutzern oder Gruppen in den lokalen Richtlinien\Zuweisung von Benutzerrechten ausgegraut ist, bedeutet dies, dass der Benutzer, der versucht, dieses Konto hinzuzufügen, keine Administratorrechte auf diesem Computer hat oder dass eine Gruppenrichtlinie überschreibt. Die Gruppenrichtlinie muss aktualisiert werden, damit sich der Hostdienst als Dienst anmelden kann.

### <a name="connection-failure"></a>Verbindungsfehler

Wenn die Aktion "Verbindung testen" beim Erstellen einer Verbindung mit dem Fehler "Benutzername/Kennwort und Datenquellenpfad überprüfen" fehlschlägt, auch wenn der angegebene Benutzername und das Kennwort korrekt sind, stellen Sie sicher, dass das Benutzerkonto über interaktive Anmelderechte für den Computer verfügt, auf dem Graph Connector-Agent installiert ist. Informationen zur Überprüfung der Anmelderechte finden Sie in der Dokumentation zur Verwaltung von [Anmelderichtlinien.](/windows/security/threat-protection/security-policy-settings/allow-log-on-locally#policy-management) Stellen Sie außerdem sicher, dass sich die Datenquelle und der Agentcomputer im selben Netzwerk befinden.

Wenn eine Verbindung mit dem Fehler "1011: Der Graph Connector-Agent ist nicht erreichbar oder offline" fehlschlägt, melden Sie sich bei dem Computer an, auf dem der Agent installiert ist, und starten Sie die Agent-Anwendung, wenn er noch nicht ausgeführt wird. Wenn die Verbindung weiterhin fehlschlägt, stellen Sie sicher, dass das Zertifikat oder der geheime Clientschlüssel, der dem Agent während der Registrierung bereitgestellt wurde, nicht abgelaufen ist und über erforderliche Berechtigungen verfügt.
