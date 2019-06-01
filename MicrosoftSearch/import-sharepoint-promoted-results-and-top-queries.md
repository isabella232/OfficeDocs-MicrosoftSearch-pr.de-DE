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
ROBOTS: NOINDEX
description: Verwenden Sie Suchabfragen aus SharePoint zum Erstellen von Arbeitsergebnissen für Microsoft Search.
ms.openlocfilehash: 1538c57a7b4138b36fe62e3076feb58d746b2b3e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591602"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="0d259-103">Importieren von höhergestuften SharePoint-Ergebnissen und wichtigsten Abfragen</span><span class="sxs-lookup"><span data-stu-id="0d259-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d259-104">Dieser Artikel bezieht sich auf Microsoft Search im Bing-Verwaltungsportal.</span><span class="sxs-lookup"><span data-stu-id="0d259-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="0d259-105">Wir verschieben das Portal zum Microsoft 365 Admin Center, und dann wird es entfernt.</span><span class="sxs-lookup"><span data-stu-id="0d259-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="0d259-106">Es wird empfohlen, dass Sie zu Beginn das Microsoft 365 Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d259-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="0d259-107">[Übersicht über Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="0d259-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="0d259-108">Um Benutzerabfragen und von Ihnen in SharePoint erstellte beste Suchergebnisse zu nutzen, schließt Microsoft Search zwei Tools zum Importieren dieser Informationen als vorgeschlagene Lesezeichen mit ein: </span><span class="sxs-lookup"><span data-stu-id="0d259-108">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="0d259-109">Importieren von Abfrageregeln zu höhergestuften SharePoint-Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="0d259-109">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="0d259-110">Importieren Sie diese Regeln, die früher als „Beste Suchergebnisse“ bezeichnet wurden, als vorgeschlagene Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="0d259-110">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="0d259-111">Wenn Sie sie Ihren Benutzern zur Verfügung stellen möchten, veröffentlichen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="0d259-111">To make them available to your users, publish them.</span></span> <span data-ttu-id="0d259-112">Die Veröffentlichungszeit variiert je nach der Anzahl der von Ihnen ausgewählten Lesezeichen.</span><span class="sxs-lookup"><span data-stu-id="0d259-112">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="0d259-113">Importieren der wichtigsten SharePoint-Abfragen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d259-113">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="0d259-114">Laden Sie die wichtigsten Abfragen aus Ihrem SharePoint herunter.</span><span class="sxs-lookup"><span data-stu-id="0d259-114">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="0d259-115">Das PowerShell-Skript fordert Sie zur Eingabe Ihrer SharePoint-Administrator-Anmeldeinformationen auf.</span><span class="sxs-lookup"><span data-stu-id="0d259-115">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="0d259-116">Führen Sie eine SharePoint-Suche nach jeder der wichtigsten Abfragen aus, um das wichtigste Suchergebnis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0d259-116">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="0d259-117">Fügen Sie dem Verwaltungsportal vorgeschlagene Lesezeichen hinzu.</span><span class="sxs-lookup"><span data-stu-id="0d259-117">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="0d259-118">Ihre wichtigsten SharePoint-Abfragen sind für Lesezeichen hervorragend geeignet.</span><span class="sxs-lookup"><span data-stu-id="0d259-118">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="0d259-119">Mithilfe des PowerShell-Skripts können Sie sie als vorgeschlagene Lesezeichen importieren.</span><span class="sxs-lookup"><span data-stu-id="0d259-119">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="0d259-120">Dieses Skript ermöglicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0d259-120">This script will:</span></span>
    
<span data-ttu-id="0d259-121">Wenn Sie Informationen zu den Anforderungen, Beispielen und verfügbaren Parametern benötigen, laden Sie das Skript herunter, und lesen Sie die Infodatei.</span><span class="sxs-lookup"><span data-stu-id="0d259-121">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="0d259-122">Nach der Ausführung des PowerShell-Skripts sollte ein Administrator oder Editor die vorgeschlagenen Lesezeichen überprüfen und alle erforderlichen Änderungen vornehmen, bevor sie veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="0d259-122">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

