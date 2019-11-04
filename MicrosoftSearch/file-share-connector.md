---
title: Dateifreigabe-Connector für Microsoft Search
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.date: 10/08/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Richten Sie den Dateifreigabe-Konnektor für Microsoft Search ein.
ms.openlocfilehash: d5fbc1af2868ce7baa70017f617a9731340fb19a
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949783"
---
# <a name="file-share-connector"></a><span data-ttu-id="c875a-103">Dateifreigabe-Konnektor</span><span class="sxs-lookup"><span data-stu-id="c875a-103">File share connector</span></span>

<span data-ttu-id="c875a-104">Mit dem Dateifreigabe-Konnektor können Benutzer in Ihrer Organisation lokale Dateifreigaben durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="c875a-104">With the File share connector, users in your organization can search on-premises file shares.</span></span> <span data-ttu-id="c875a-105">Die Suchergebnisse aus diesen Freigaben werden mit den Ergebnissen aus SharePoint und Microsoft OneDrive für Unternehmen zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="c875a-105">The search results from these shares merge with the results from SharePoint and Microsoft OneDrive for Business.</span></span>

<span data-ttu-id="c875a-106">Dieser Artikel richtet sich an Microsoft 365-Administratoren oder Personen, die einen Dateifreigabe-Konnektor konfigurieren, ausführen und überwachen.</span><span class="sxs-lookup"><span data-stu-id="c875a-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a File share connector.</span></span> <span data-ttu-id="c875a-107">Es wird erläutert, wie Sie die Connector-und connectorfunktionen, Einschränkungen und Techniken zur Problembehandlung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c875a-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-a-data-gateway"></a><span data-ttu-id="c875a-108">Installieren eines Datengateways</span><span class="sxs-lookup"><span data-stu-id="c875a-108">Install a data gateway</span></span>
<span data-ttu-id="c875a-109">Um auf Ihre drittanbieterdaten zugreifen zu können, müssen Sie ein Microsoft Power BI-Gateway installieren und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c875a-109">In order to access your third-party data, you must install and configure a Microsoft Power BI gateway.</span></span> <span data-ttu-id="c875a-110">Weitere Informationen finden Sie unter [Install and on-premises Gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) .</span><span class="sxs-lookup"><span data-stu-id="c875a-110">See [Install and on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) to learn more.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="c875a-111">Herstellen einer Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="c875a-111">Connect to a data source</span></span>
<span data-ttu-id="c875a-112">Erstellen Sie auf der Seite mit der **Datenquelle verbinden** einen Ordner, und geben Sie einen Pfad zur Dateifreigabe an.</span><span class="sxs-lookup"><span data-stu-id="c875a-112">On the **Connect to data source** page, create a folder and provide a path to the file share.</span></span> <span data-ttu-id="c875a-113">Wählen Sie dann das zuvor installierte Gateway aus.</span><span class="sxs-lookup"><span data-stu-id="c875a-113">Then select your previously installed gateway.</span></span> <span data-ttu-id="c875a-114">Geben Sie die Anmeldeinformationen für ein Windows-Benutzerkonto mit **Lesezugriff** auf alle Dateien in der Freigabe ein.</span><span class="sxs-lookup"><span data-stu-id="c875a-114">Enter the credentials for a Windows user account with **read access** to all the files in the share.</span></span> <span data-ttu-id="c875a-115">Anschließend können Sie die in der Freigabe vorhandenen Dateien überprüfen und alle abgerufenen Metadaten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c875a-115">You can then verify the files present in the share and see all the fetched metadata.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="c875a-116">Verwalten von Suchberechtigungen</span><span class="sxs-lookup"><span data-stu-id="c875a-116">Manage search permissions</span></span>
<span data-ttu-id="c875a-117">Der Dateifreigabe-Konnektor unterstützt nur Suchberechtigungen, die für **alle**sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="c875a-117">The File share connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="c875a-118">Indizierte Daten werden in den Suchergebnissen angezeigt und sind für alle Benutzer in der Organisation sichtbar.</span><span class="sxs-lookup"><span data-stu-id="c875a-118">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="c875a-119">Festlegen des Aktualisierungszeitplans</span><span class="sxs-lookup"><span data-stu-id="c875a-119">Set the refresh schedule</span></span>
<span data-ttu-id="c875a-120">Das empfohlene Standardintervall für die Aktualisierungsplanung beträgt 15 Minuten, Sie können es jedoch in ein anderes Intervall ändern, das Sie bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="c875a-120">The recommended default refresh schedule interval is 15 minutes, but you can change it to another interval that you prefer.</span></span>

## <a name="set-up-your-search-results-page"></a><span data-ttu-id="c875a-121">Einrichten der Suchergebnisseite</span><span class="sxs-lookup"><span data-stu-id="c875a-121">Set up your search results page</span></span>
<span data-ttu-id="c875a-122">Um unterschiedliche Datei Verbindungsergebnisse auf den Registerkarten **alle** und **Dateien** anzuzeigen, müssen Sie eine SharePoint-Such Modul Ergebnisseite einrichten:</span><span class="sxs-lookup"><span data-stu-id="c875a-122">To display different file connection results in the **All** and **Files** tabs, you need to set up a SharePoint search engine results page:</span></span>
- <span data-ttu-id="c875a-123">Die Tabelle " **all** " zeigt kombinierte Ergebnisse aus ihren Datei Verbindungen, SharePoint-Dateien, OneDrive-Dateien und SharePoint-Websites.</span><span class="sxs-lookup"><span data-stu-id="c875a-123">The **All** table shows combined results from your file connections, SharePoint files, OneDrive files, and SharePoint sites.</span></span> 
- <span data-ttu-id="c875a-124">Die **Dateien** Vertical zeigt alle Datei Ergebnisse aus ihren Verbindungen, SharePoint und OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c875a-124">The **Files** vertical shows all file results from your connections, SharePoint, and OneDrive.</span></span>
<span data-ttu-id="c875a-125">Ergebnisse aus Datei Verbindungen werden bereits vorhandenen Ergebnissen in den vertikalen " **all** " und " **Files** " hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c875a-125">Results from file connections are added to already existing results in both the **All** and **Files** verticals.</span></span>

<span data-ttu-id="c875a-126">Führen Sie die folgenden Schritte aus, um die Suchergebnisseite einzurichten:</span><span class="sxs-lookup"><span data-stu-id="c875a-126">To set up your search results page, take these steps:</span></span>
1. <span data-ttu-id="c875a-127">Erstellen Sie eine SharePoint-Websitesammlung mit einer modernen Such Seite.</span><span class="sxs-lookup"><span data-stu-id="c875a-127">Create a SharePoint site collection with a modern search page.</span></span>

2. <span data-ttu-id="c875a-128">Installieren Sie eine [SharePoint Online Management-Shell](https://www.microsoft.com/download/details.aspx?id=35588).</span><span class="sxs-lookup"><span data-stu-id="c875a-128">Install a [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

3. <span data-ttu-id="c875a-129">Öffnen Sie SharePoint Online Verwaltungsshell als Administrator, und importieren Sie das **Microsoft. SharePoint. Client. dll** - `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`Modul, das unter vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c875a-129">Open SharePoint Online Management Shell as an administrator and import the **Microsoft.SharePoint.Client.dll** module present at `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`.</span></span>

> [!NOTE]
> <span data-ttu-id="c875a-130">Dieser Pfad ist möglicherweise nicht für alle Benutzer gleich.</span><span class="sxs-lookup"><span data-stu-id="c875a-130">This path might not be the same for all users.</span></span>

<span data-ttu-id="c875a-131">Um das Modul zu importieren, führen Sie diesen Befehl in SharePoint Online Management Shell aus:</span><span class="sxs-lookup"><span data-stu-id="c875a-131">To import the module, run this command in SharePoint Online Management Shell:</span></span>
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. <span data-ttu-id="c875a-132">Führen Sie nun dieses Skript aus:</span><span class="sxs-lookup"><span data-stu-id="c875a-132">Now run this script:</span></span>
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

5. <span data-ttu-id="c875a-133">Geben Sie die erforderlichen Werte in PowerShell ein, beispielsweise Organisationsname, Benutzername, Kennwort und Website-URL.</span><span class="sxs-lookup"><span data-stu-id="c875a-133">Enter the required values in PowerShell, such as organization name, username, password, and site URL.</span></span> <span data-ttu-id="c875a-134">Wenn Ihre Administratoranmeldeinformationen **beispielsweise**sind `admin@a830edad9050849823J19081300.onmicrosoft.com`, lautet der Name Ihrer Organisation **a830edad9050849823J19081300**, und Ihre Website-URL lautet `https:// a830edad9050849823J19081300.sharepoint.com`.</span><span class="sxs-lookup"><span data-stu-id="c875a-134">As an **example**, if your admin credentials are `admin@a830edad9050849823J19081300.onmicrosoft.com`, then your organization name is **a830edad9050849823J19081300**, and your site URL is `https:// a830edad9050849823J19081300.sharepoint.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="c875a-135">Die Einstellung **allproperties** kann nur auf einer Websitesammlungsebene (Teams/Comms-Website) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c875a-135">The **AllProperties** setting can only be done at a site collection level (Teams/Comms site).</span></span>

6. <span data-ttu-id="c875a-136">Nun können Sie nach indizierten Dateien suchen und Ergebnisse auf den Registerkarten **alle** und **Dateien** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c875a-136">Now you can search for indexed files and see results in both the **All** and **Files** tabs.</span></span>

## <a name="search-for-file-share-content-in-the-search-results-page"></a><span data-ttu-id="c875a-137">Suchen nach Dateifreigabe Inhalten auf der Suchergebnisseite</span><span class="sxs-lookup"><span data-stu-id="c875a-137">Search for file share content in the search results page</span></span>
<span data-ttu-id="c875a-138">Um nach indizierten Inhalten zu suchen, wechseln Sie zur SharePoint-Startseite Ihres Testmandanten.</span><span class="sxs-lookup"><span data-stu-id="c875a-138">To search for indexed content, go to the SharePoint home page of your test tenant.</span></span> <span data-ttu-id="c875a-139">Die Ergebnisse werden auf den Registerkarten **alle** und **Dateien** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c875a-139">Results will be displayed in the **All** and **Files** tabs.</span></span>

<span data-ttu-id="c875a-140">Aufgrund von Browser Einschränkungen können Sie kein Datei Ergebnis auswählen, um Dateien aus den Suchvorgängen für lokale Dateifreigaben anzuzeigen oder zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c875a-140">Because of browser restrictions, you can't select a file result to view or open files from local file share searches.</span></span> <span data-ttu-id="c875a-141">Zum Öffnen dieser Dateien kopieren Sie den Link des Datei Ergebnisses, und fügen Sie ihn in die Adressleiste des systembrowsers ein.</span><span class="sxs-lookup"><span data-stu-id="c875a-141">To open these files, copy the file result's link and paste it into the address bar of your system's browser.</span></span> <span data-ttu-id="c875a-142">Verwenden Sie unter Windows den Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="c875a-142">For Windows, use Windows Explorer.</span></span> <span data-ttu-id="c875a-143">Anschließend können Sie die Datei auf Ihrem System öffnen.</span><span class="sxs-lookup"><span data-stu-id="c875a-143">Then you can open the file on your system.</span></span>

![SharePoint-Suche mit geöffnetem Dialogfeld Link kopieren.](media/fileshare-search.png)

## <a name="troubleshooting"></a><span data-ttu-id="c875a-145">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="c875a-145">Troubleshooting</span></span>
<span data-ttu-id="c875a-146">Wenn etwas mit einer Verbindung kritisch falsch ist, wird der Status als **Fehler**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c875a-146">If something is critically wrong with a connection, its status shows as **failed**.</span></span> <span data-ttu-id="c875a-147">Wenn Sie weitere Informationen zu den drei Fehlertypen erhalten möchten, wechseln Sie zur Seite Fehlerdetails, und wählen Sie die Fehler **hafte** Verbindung aus.</span><span class="sxs-lookup"><span data-stu-id="c875a-147">To get more information on the three types of errors, go to the **error details** page and select the failing connection.</span></span> <span data-ttu-id="c875a-148">Weitere Informationen finden Sie unter [Manage Your Connector](manage-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="c875a-148">See [Manage your connector](manage-connector.md) to learn more.</span></span>
1. <span data-ttu-id="c875a-149">**Gateway nicht erreichbar (Fehlercode: 11)**.</span><span class="sxs-lookup"><span data-stu-id="c875a-149">**Gateway not reachable (error code: 11)**.</span></span> <span data-ttu-id="c875a-150">Der Gatewaycomputer für die Verbindung ist nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="c875a-150">The gateway machine for the connection is down.</span></span> <span data-ttu-id="c875a-151">Überprüfen Sie, ob der Microsoft Power BI-Prozess auf dem Gatewaycomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c875a-151">Verify if the Microsoft Power BI process runs on the gateway machine.</span></span>
2. <span data-ttu-id="c875a-152">**Authentifizierungsfehler (Fehlercode: 12)**.</span><span class="sxs-lookup"><span data-stu-id="c875a-152">**Authentication error (error code: 12)**.</span></span> <span data-ttu-id="c875a-153">Die Anmeldeinformationen, die zum Erstellen der Verbindung verwendet wurden, sind abgelaufen oder sind nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="c875a-153">The credentials that were used for creating the connection expired or are no longer valid.</span></span> <span data-ttu-id="c875a-154">Geben Sie zum Beheben dieses Fehlers gültige Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="c875a-154">To resolve this error, enter valid credentials.</span></span>
3. <span data-ttu-id="c875a-155">**Interner Fehler (Fehlercode: nichts anderes als 11 oder 12)**.</span><span class="sxs-lookup"><span data-stu-id="c875a-155">**Internal error (error code: anything other than 11 or 12)**.</span></span> <span data-ttu-id="c875a-156">In der Connector-Infrastruktur ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c875a-156">There's an error in the connector infrastructure.</span></span> <span data-ttu-id="c875a-157">Im [Feedback](connectors-feedback.md) -Artikel erfahren Sie, wie Sie diese Fehler melden.</span><span class="sxs-lookup"><span data-stu-id="c875a-157">See the [Feedback](connectors-feedback.md) article to find out how to report these errors.</span></span>

## <a name="limitations"></a><span data-ttu-id="c875a-158">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c875a-158">Limitations</span></span>
<span data-ttu-id="c875a-159">Der Dateifreigabe-Konnektor hat diese Einschränkungen in der Vorschauversion:</span><span class="sxs-lookup"><span data-stu-id="c875a-159">The File share connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="c875a-160">Sie können nur Dateien mit festen Eigenschaften indizieren, keine Dateien mit benutzerdefinierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c875a-160">You can only index files with fixed properties, not files with custom properties.</span></span>
* <span data-ttu-id="c875a-161">Dateifreigabe-Zugriffssteuerungslisten (Access Control Lists, ACLs) werden derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c875a-161">File share Access Control Lists (ACLs) aren't currently supported.</span></span>
* <span data-ttu-id="c875a-162">Externe Identitäten werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c875a-162">External identities aren't supported.</span></span> <span data-ttu-id="c875a-163">Sie müssen Azure Active Directory Identitäten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="c875a-163">They must be mapped to Azure Active Directory identities.</span></span>