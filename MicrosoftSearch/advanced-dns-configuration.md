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
description: Stellen Sie eine nahtlose Anmeldung für Ihre Benutzer durch Konfigurieren des DNS-Servers mithilfe von CNAME sicher
ms.openlocfilehash: fa797b95f346d6d03bd020da146bb330c715e392
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612440"
---
# <a name="advanced-dns-configuration"></a>Erweiterte DNS-Konfiguration

Zur Sicherstellung Bing kann immer Identifizieren von Benutzern in Ihrer Organisation und sich erfolgreich angemeldet haben sie ihre Arbeit oder Schule Konto konfigurieren Ihrer internen DNS-Server oder einen Proxyserver zum Auflösen von `www.bing.com` auf `ms.bing.com`. Zu diesem Zweck, erstellen Sie einen DNS-Eintrag für `www.bing.com` CNAME für sein `ms.bing.com`.
  
****

|**Name**|**Typ**|**Wert**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
Einen CNAME-anstelle der IP-Adresse ist die Verwendung seit CNAME funktionsfähig weiterhin, wenn die IP-Adresse ändert. Nachdem Sie diese DNS-Änderung vorgenommen haben, weiterhin Ergebnisse für die Benutzer angezeigt werden, als ob sie stammen `www.bing.com`. 
  
Dies erfordert keine zusätzliche Konfiguration auf Clientcomputern und bietet eine nahtlose für Ihre Benutzer. Wenn sie zu wechseln `bing.com`, sie werden werden automatisch angemeldet mehr konsistent und wenn sie automatisch angemeldet werden nicht möglich, werden sie dazu aufgefordert werden.
