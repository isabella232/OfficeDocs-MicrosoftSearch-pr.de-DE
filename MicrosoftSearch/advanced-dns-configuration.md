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
description: Stellen Sie eine nahtlose Anmeldung für Ihre Benutzer durch Konfigurieren des DNS-Servers mithilfe von CNAME sicher
ms.openlocfilehash: f08fc4c29c4c4356a1616faab67fdebdd6c85839
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378779"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="7a050-103">Erweiterte DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7a050-103">Advanced DNS configuration</span></span>

<span data-ttu-id="7a050-p101">Zur Sicherstellung Bing kann immer Identifizieren von Benutzern in Ihrer Organisation und sich erfolgreich angemeldet haben sie ihre Arbeit oder Schule Konto konfigurieren Ihrer internen DNS-Server oder einen Proxyserver zum Auflösen von `www.bing.com` auf `ms.bing.com`. Zu diesem Zweck, erstellen Sie einen DNS-Eintrag für `www.bing.com` CNAME für sein `ms.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="7a050-p101">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="7a050-106">**Name**</span><span class="sxs-lookup"><span data-stu-id="7a050-106">**Name**</span></span>|<span data-ttu-id="7a050-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="7a050-107">**Type**</span></span>|<span data-ttu-id="7a050-108">**Wert**</span><span class="sxs-lookup"><span data-stu-id="7a050-108">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="7a050-109">CNAME</span><span class="sxs-lookup"><span data-stu-id="7a050-109">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="7a050-p102">Einen CNAME-anstelle der IP-Adresse ist die Verwendung seit CNAME funktionsfähig weiterhin, wenn die IP-Adresse ändert. Nachdem Sie diese DNS-Änderung vorgenommen haben, weiterhin Ergebnisse für die Benutzer angezeigt werden, als ob sie stammen `www.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="7a050-p102">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="7a050-p103">Dies erfordert keine zusätzliche Konfiguration auf Clientcomputern und bietet eine nahtlose für Ihre Benutzer. Wenn sie zu wechseln `bing.com`, sie werden werden automatisch angemeldet mehr konsistent und wenn sie automatisch angemeldet werden nicht möglich, werden sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7a050-p103">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
