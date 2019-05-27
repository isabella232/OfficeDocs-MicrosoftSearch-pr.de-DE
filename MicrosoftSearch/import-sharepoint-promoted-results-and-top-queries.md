---
title: Importieren von höhergestuften SharePoint-Ergebnissen und wichtigsten Abfragen
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/8/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
description: Verwenden Sie Suchabfragen aus SharePoint zum Erstellen von Arbeitsergebnissen für Microsoft Search.
ms.openlocfilehash: 6e55e2000792bdb576a18a0efeb353dc3ea13605
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968451"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="bc249-103">Importieren von höhergestuften SharePoint-Ergebnissen und wichtigsten Abfragen</span><span class="sxs-lookup"><span data-stu-id="bc249-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc249-104">Die Einstellungen für Microsoft Search in Bing sind jetzt im Microsoft 365 Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bc249-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bc249-105">Beginnen Sie, indem Sie in Ihrem Admin Center[Suchadministratoren zuweisen](https://docs.microsoft.com/de-DE/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor).</span><span class="sxs-lookup"><span data-stu-id="bc249-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="bc249-106">Um Benutzerabfragen und von Ihnen in SharePoint erstellte beste Suchergebnisse zu nutzen, schließt Microsoft Search zwei Tools zum Importieren dieser Informationen als vorgeschlagene Lesezeichen mit ein: </span><span class="sxs-lookup"><span data-stu-id="bc249-106">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="bc249-107">Importieren von Abfrageregeln zu höhergestuften SharePoint-Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="bc249-107">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="bc249-108">Importieren Sie diese Regeln, die früher als „Beste Suchergebnisse“ bezeichnet wurden, als vorgeschlagene Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="bc249-108">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="bc249-109">Wenn Sie sie Ihren Benutzern zur Verfügung stellen möchten, veröffentlichen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="bc249-109">To make them available to your users, publish them.</span></span> <span data-ttu-id="bc249-110">Die Veröffentlichungszeit variiert je nach der Anzahl der von Ihnen ausgewählten Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="bc249-110">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="bc249-111">Importieren der wichtigsten SharePoint-Abfragen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc249-111">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="bc249-112">Laden Sie die wichtigsten Abfragen aus Ihrem SharePoint herunter.</span><span class="sxs-lookup"><span data-stu-id="bc249-112">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="bc249-113">Das PowerShell-Skript fordert Sie zur Eingabe Ihrer SharePoint-Administrator-Anmeldeinformationen auf.</span><span class="sxs-lookup"><span data-stu-id="bc249-113">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="bc249-114">Führen Sie eine SharePoint-Suche nach jeder der wichtigsten Abfragen aus, um das wichtigste Suchergebnis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bc249-114">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="bc249-115">Fügen Sie dem Verwaltungsportal vorgeschlagene Lesezeichen hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc249-115">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="bc249-116">Ihre wichtigsten SharePoint-Abfragen sind für Lesezeichen hervorragend geeignet.</span><span class="sxs-lookup"><span data-stu-id="bc249-116">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="bc249-117">Mithilfe des PowerShell-Skripts können Sie sie als vorgeschlagene Lesezeichen importieren.</span><span class="sxs-lookup"><span data-stu-id="bc249-117">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="bc249-118">Dieses Skript ermöglicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bc249-118">This script will:</span></span>
    
<span data-ttu-id="bc249-119">Wenn Sie Informationen zu den Anforderungen, Beispielen und verfügbaren Parametern benötigen, laden Sie das Skript herunter, und lesen Sie die Infodatei.</span><span class="sxs-lookup"><span data-stu-id="bc249-119">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="bc249-120">Nach der Ausführung des PowerShell-Skripts sollte ein Administrator oder Editor die vorgeschlagenen Lesezeichen überprüfen und alle erforderlichen Änderungen vornehmen, bevor sie veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="bc249-120">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

