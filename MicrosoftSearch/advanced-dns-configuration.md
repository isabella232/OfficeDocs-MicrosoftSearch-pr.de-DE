---
title: Erweiterte DNS-Konfiguration
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
ROBOTS: NoIndex
description: Stellen Sie eine nahtlose Anmeldung für Ihre Benutzer sicher, indem Sie Ihre DNS-Server mit einem CNAME konfigurieren.
ms.openlocfilehash: 05562bd9379af395ee305ffebdddbf7bfcd1e835
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727897"
---
# <a name="advanced-dns-configuration"></a>Erweiterte DNS-Konfiguration


Um sicherzustellen, dass Bing immer Benutzer in Ihrer Organisation identifizieren und diese erfolgreich bei ihrem Geschäfts- oder Schulkonto anmelden kann, konfigurieren Sie Ihren internen DNS-Server oder Proxyserver so, dass er von `www.bing.com` in `ms.bing.com` aufgelöst wird. Erstellen Sie hierfür einen DNS-Eintrag für `www.bing.com`, der als CNAME für `ms.bing.com` fungieren soll.
  
****

|**Name**|**Typ**|**Wert**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
Die Verwendung eines CNAME anstelle der IP-Adresse wird bevorzugt, da ein CNAME weiterhin funktioniert, auch wenn sich die IP-Adresse ändert. Nachdem Sie diese DNS-Änderung vorgenommen haben, werden die Ergebnisse für Ihre Benutzer weiterhin so angezeigt als würden sie von `www.bing.com` stammen. 
  
Hierfür ist keine zusätzliche Konfiguration auf Clientcomputern erforderlich, und für Ihre Benutzer erfolgt alles nahtlos. Wenn Sie zu `bing.com` wechseln, werden Sie automatisch auf einheitlichere Weise angemeldet. Wenn eine automatische Anmeldung nicht möglich ist, werden sie zur Anmeldung aufgefordert.
