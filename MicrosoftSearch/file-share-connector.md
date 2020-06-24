---
title: Dateifreigabe-Connector für Microsoft Search
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Richten Sie den Dateifreigabe-Konnektor für Microsoft Search ein.
ms.openlocfilehash: 2349ad753508d5f19a70648d9cbf1df495b27108
ms.sourcegitcommit: 7eda9b621def0659d7e7bc8b989f8adc929cce93
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "44861094"
---
# <a name="file-share-connector"></a>Dateifreigabe-Konnektor

Mit dem Dateifreigabe-Konnektor können Benutzer in Ihrer Organisation lokale Dateifreigaben durchsuchen. Die Suchergebnisse aus diesen Freigaben werden mit den Ergebnissen aus [SharePoint](http://sharepoint.com/) und [Microsoft OneDrive für Unternehmen](https://onedrive.live.com/about/business/)zusammengeführt.

Dieser Artikel richtet sich an [Microsoft 365](https://www.microsoft.com/microsoft-365) -Administratoren oder Personen, die einen Dateifreigabe-Konnektor konfigurieren, ausführen und überwachen. Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.

## <a name="install-a-data-gateway"></a>Installieren eines Datengateways
Um auf Ihre drittanbieterdaten zugreifen zu können, müssen Sie ein [Microsoft Power BI](https://msit.powerbi.com/) -Gateway installieren und konfigurieren. Weitere Informationen finden Sie unter [Install an on-premises Gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) .  

## <a name="content-requirements"></a>Inhaltsanforderungen
**Dateitypen**. Nur Dateien in diesen Formaten können indiziert und durchsucht werden: doc, DOCM, docx, dot, DOTX, eml, GIF, HTML, JPEG, MHT, MHTML, msg, nws, OBD, OBT, Odp, ODS, ODT, One, PDF, Pot, PPS, PPT, PPTM, PPTX, txt, XLB, XLC, xlsb, xls, xlsx, XLT, XLXM, XML, XPS und zip. Nur der Textinhalt dieser Formate wird indiziert. Alle Multimedia-Inhalte werden ignoriert.
 
**Dateigrößenbeschränkungen**. Die maximal unterstützte Dateigröße beträgt 100 MB. Dateien, die größer als 100 MB sind, werden von der Indizierung übersprungen. Der maximale Grenzwert für die Post verarbeitete Größe beträgt 4 MB. Die Verarbeitung wird angehalten, wenn die Größe einer Datei 4 MB erreicht. Einige in der Datei vorhandene Ausdrücke funktionieren daher möglicherweise nicht für die Suche.

## <a name="connect-to-a-data-source"></a>Herstellen einer Verbindung mit einer Datenquelle
Wählen Sie auf der Seite mit **Datenquelle verbinden** die Option **Dateifreigabe** aus, und geben Sie den Namen, die Verbindungs-ID und die Beschreibung an. Geben Sie auf der nächsten Seite den Pfad zur Dateifreigabe an, und wählen Sie das zuvor installierte Gateway aus. Geben Sie die Anmeldeinformationen für ein [Microsoft Windows](https://microsoft.com/windows) -Benutzerkonto mit Lesezugriff auf alle Dateien in der Freigabe ein. Durchlaufen Sie die restlichen Einstellungen, und veröffentlichen Sie die Verbindung.

## <a name="set-the-refresh-schedule"></a>Festlegen des Aktualisierungszeitplans
Das empfohlene Standardintervall für die Aktualisierungsplanung beträgt 15 Minuten, Sie können es jedoch in ein anderes Intervall ändern, das Sie bevorzugen.

## <a name="set-up-your-search-results-page"></a>Einrichten der Suchergebnisseite
Um unterschiedliche Datei Verbindungsergebnisse auf den Registerkarten **alle** und **Dateien** anzuzeigen, müssen Sie eine [SharePoint](http://sharepoint.com/) -Such Modul Ergebnisseite einrichten:
- Die Tabelle " **all** " zeigt kombinierte Ergebnisse aus ihren Datei Verbindungen, SharePoint-Dateien, [OneDrive](https://onedrive.live.com/about/business/) -Dateien und SharePoint-Websites. 
- Die **Dateien** Vertical zeigt alle Datei Ergebnisse aus ihren Verbindungen, SharePoint und OneDrive.
Ergebnisse aus Datei Verbindungen werden bereits vorhandenen Ergebnissen in den vertikalen " **all** " und " **Files** " hinzugefügt.

Führen Sie die folgenden Schritte aus, um die Suchergebnisseite einzurichten:
1. Erstellen Sie eine SharePoint-Websitesammlung mit einer modernen Such Seite.

2. Installieren Sie eine [SharePoint Online Management-Shell](https://www.microsoft.com/download/details.aspx?id=35588).

3. Öffnen Sie SharePoint Online Verwaltungsshell als Administrator, und importieren Sie das **Microsoft.SharePoint.Client.dll** -Modul, das unter vorhanden ist `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll` .

> [!NOTE]
> Dieser Pfad ist möglicherweise nicht für alle Benutzer gleich.

Um das Modul zu importieren, führen Sie diesen Befehl in [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588)aus:
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. Führen Sie nun dieses Skript aus:
```bash
$orgName = Read-Host -prompt 'Please enter your org name'
$userName = Read-Host -prompt 'Enter user name'
$userCreds = Get-Credential -UserName $userName -Message "Type the password"
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCreds

$url = Read-Host -Prompt 'Please enter the site url'
$site = Get-SPOSite -Identity $url
Set-SPOSite $url -DenyAddAndCustomizePages 0

$pwd = Read-Host -AsSecureString 'type the password'
$context = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credential = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($userName, $pwd)
$context.Credentials = $credential
$web = $context.Web
$context.Load($web)
$web.AllProperties["AllVerticalContent"] = "Combined"
$web.Update()
$context.ExecuteQuery()
$web.AllProperties["FilesVerticalContent"] = "ConnectorsOnly"
$web.Update()
$context.ExecuteQuery()
Set-SPOSite $url -DenyAddAndCustomizePages 1

Write-Host "Success" -ForegroundColor Cyan
Read-Host -Prompt 'Press enter to exit'
```

5. Geben Sie die erforderlichen Werte in [Microsoft PowerShell](https://microsoft.com/powershell)ein, beispielsweise Organisationsname, Benutzername, Kennwort und Website-URL. Wenn Ihre Administratoranmeldeinformationen **beispielsweise**sind `admin@a830edad9050849823J19081300.onmicrosoft.com` , lautet der Name Ihrer Organisation **a830edad9050849823J19081300**, und Ihre Website-URL lautet `https:// a830edad9050849823J19081300.sharepoint.com` .

> [!NOTE]
> Die Einstellung **allproperties** kann nur auf einer Websitesammlungsebene (Teams/Comms-Website) ausgeführt werden.

6. Nun können Sie nach indizierten Dateien suchen und Ergebnisse auf den Registerkarten **alle** und **Dateien** anzeigen.

## <a name="search-for-file-share-content-in-the-search-results-page"></a>Suchen nach Dateifreigabe Inhalten auf der Suchergebnisseite
Um nach indizierten Inhalten zu suchen, wechseln Sie zur [SharePoint](http://sharepoint.com/) -Startseite Ihres Testmandanten. Die Ergebnisse werden auf den Registerkarten **alle** und **Dateien** angezeigt.

Aufgrund von Browser Einschränkungen können Sie kein Datei Ergebnis auswählen, um Dateien aus den Suchvorgängen für lokale Dateifreigaben anzuzeigen oder zu öffnen. Zum Öffnen dieser Dateien kopieren Sie den Link des Datei Ergebnisses, und fügen Sie ihn in die Adressleiste des systembrowsers ein. Verwenden Sie unter [Windows](https://microsoft.com/windows)den Windows-Explorer. Anschließend können Sie die Datei auf Ihrem System öffnen.

![SharePoint-Suche mit geöffnetem Dialogfeld Link kopieren.](media/fileshare-search.png)

## <a name="troubleshooting"></a>Problembehandlung
Wenn etwas mit einer Verbindung kritisch falsch ist, wird der Status als **Fehler**angezeigt. Wenn Sie weitere Informationen zu den drei Fehlertypen erhalten möchten, wechseln Sie zur Seite Fehlerdetails, und wählen Sie die Fehler **hafte** Verbindung aus. Weitere Informationen finden Sie unter [Manage Your Connector](manage-connector.md) .
1. **Gateway nicht erreichbar (Fehlercode: 11)**. Der Gatewaycomputer für die Verbindung ist nicht aktiv. Überprüfen Sie, ob der [Power BI](https://msit.powerbi.com/) -Prozess auf dem Gatewaycomputer ausgeführt wird.
2. **Authentifizierungsfehler (Fehlercode: 12)**. Die Anmeldeinformationen, die zum Erstellen der Verbindung verwendet wurden, sind abgelaufen oder sind nicht mehr gültig. Geben Sie zum Beheben dieses Fehlers gültige Anmeldeinformationen ein.
3. **Interner Fehler (Fehlercode: nichts anderes als 11 oder 12)**. In der Connector-Infrastruktur ist ein Fehler aufgetreten. Im [Feedback](connectors-feedback.md) -Artikel erfahren Sie, wie Sie diese Fehler melden.

## <a name="limitations"></a>Einschränkungen
Der Dateifreigabe-Konnektor hat diese Einschränkungen in der Vorschauversion:
* Sie können nur Dateien mit festen Eigenschaften indizieren, keine Dateien mit benutzerdefinierten Eigenschaften.
* Dateifreigabe-Zugriffssteuerungslisten (Access Control Lists, ACLs) werden derzeit nicht unterstützt. Nur NTFS-ACL-Dateien werden unterstützt.
* Externe Identitäten werden nicht unterstützt. Sie müssen [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) Identitäten zugeordnet werden.
