---
title: Erweiterte DNS-Konfiguration
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
ROBOTS: NoIndex
description: Stellen Sie eine nahtlose Anmeldung für Ihre Benutzer sicher, indem Sie Ihre DNS-Server mit einem CNAME konfigurieren.
ms.openlocfilehash: 062c43cfbc8d25c263eb2402bd05191e385411b2
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311610"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="818e1-103">Erweiterte DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="818e1-103">Advanced DNS configuration</span></span>

<span data-ttu-id="818e1-p101">Um sicherzustellen, dass Bing immer Benutzer in Ihrer Organisation identifizieren und diese erfolgreich bei ihrem Geschäfts- oder Schulkonto anmelden kann, konfigurieren Sie Ihren internen DNS-Server oder Proxyserver so, dass er von `www.bing.com` in `ms.bing.com` aufgelöst wird. Erstellen Sie hierfür einen DNS-Eintrag für `www.bing.com`, der als CNAME für `ms.bing.com` fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="818e1-p101">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="818e1-106">**Name**</span><span class="sxs-lookup"><span data-stu-id="818e1-106">**Name**</span></span>|<span data-ttu-id="818e1-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="818e1-107">**Type**</span></span>|<span data-ttu-id="818e1-108">**Wert**</span><span class="sxs-lookup"><span data-stu-id="818e1-108">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="818e1-109">CNAME</span><span class="sxs-lookup"><span data-stu-id="818e1-109">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="818e1-p102">Die Verwendung eines CNAME anstelle der IP-Adresse wird bevorzugt, da ein CNAME weiterhin funktioniert, auch wenn sich die IP-Adresse ändert. Nachdem Sie diese DNS-Änderung vorgenommen haben, werden die Ergebnisse für Ihre Benutzer weiterhin so angezeigt als würden sie von `www.bing.com` stammen.</span><span class="sxs-lookup"><span data-stu-id="818e1-p102">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="818e1-p103">Hierfür ist keine zusätzliche Konfiguration auf Clientcomputern erforderlich, und für Ihre Benutzer erfolgt alles nahtlos. Wenn Sie zu `bing.com` wechseln, werden Sie automatisch auf einheitlichere Weise angemeldet. Wenn eine automatische Anmeldung nicht möglich ist, werden sie zur Anmeldung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="818e1-p103">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>