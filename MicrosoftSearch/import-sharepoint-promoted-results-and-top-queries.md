---
title: Importieren von höhergestuften SharePoint-Ergebnissen und den wichtigsten Abfragen
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
description: Verwenden von Suchabfragen aus SharePoint zum Erstellen von Arbeitsergebnissen für Microsoft Search
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508753"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="01a7c-103">Importieren von höhergestuften SharePoint-Ergebnissen und den wichtigsten Abfragen</span><span class="sxs-lookup"><span data-stu-id="01a7c-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="01a7c-104">Um Benutzer Abfragen und beste suchErgebnisse zu nutzen, die Sie in SharePoint erstellt haben, enthält die Microsoft-Suche zwei Tools zum Importieren dieser Informationen als vorgeschlagene Lesezeichen:</span><span class="sxs-lookup"><span data-stu-id="01a7c-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="01a7c-105">Importieren von von SharePoint heraufgestuften Ergebnisabfrage Regeln</span><span class="sxs-lookup"><span data-stu-id="01a7c-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="01a7c-106">Importieren Sie diese Regeln, die zuvor als beste Suchergebnisse bezeichnet wurden, als vorgeschlagene Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="01a7c-106">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="01a7c-107">Um Sie für Ihre Benutzer zur Verfügung zu stellen, veröffentlichen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="01a7c-107">To make them available to your users, publish them.</span></span> <span data-ttu-id="01a7c-108">Die Veröffentlichungszeit variiert je nach der Anzahl der ausgewählten Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="01a7c-108">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="01a7c-109">Importieren der wichtigsten SharePoint-Abfragen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="01a7c-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="01a7c-110">Laden Sie die wichtigsten Abfragen aus Ihrem SharePoint herunter.</span><span class="sxs-lookup"><span data-stu-id="01a7c-110">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="01a7c-111">Das PowerShell-Skript fordert Sie zur Bestätigung Ihrer SharePoint-Administratoranmeldeinformationen auf.</span><span class="sxs-lookup"><span data-stu-id="01a7c-111">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="01a7c-112">Führen Sie eine SharePoint-Suche für jede der häufigsten Abfragen aus, um das häufigste Suchergebnis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="01a7c-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="01a7c-113">Fügen Sie dem Administratorportal vorgeschlagene Lesezeichen hinzu.</span><span class="sxs-lookup"><span data-stu-id="01a7c-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="01a7c-114">Ihre wichtigsten SharePoint-Abfragen sind ausgezeichnete Kandidaten für Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="01a7c-114">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="01a7c-115">Verwenden Sie das PowerShell-Skript, um Sie als vorgeschlagene Lesezeichen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="01a7c-115">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="01a7c-116">Dieses Skript wird:</span><span class="sxs-lookup"><span data-stu-id="01a7c-116">This script will:</span></span>
    
<span data-ttu-id="01a7c-117">Informationen zu Anforderungen, Beispielen und verfügbaren Parametern finden Sie unter Herunterladen des Skripts und Lesen der README-Datei.</span><span class="sxs-lookup"><span data-stu-id="01a7c-117">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="01a7c-118">Nachdem das PowerShell-Skript ausgeführt wurde, sollte ein Administrator oder ein Editor die vorgeschlagenen Lesezeichen überprüfen und alle erforderlichen Änderungen vornehmen, bevor Sie veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="01a7c-118">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

