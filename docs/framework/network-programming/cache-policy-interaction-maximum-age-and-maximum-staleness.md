---
title: "Interakce zásad do mezipaměti – maximální stáří a maximální typu Prošlostí"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maximum staleness
- freshness of cached resources
- time, cached resources
- maximum age policy
- staleness of cached resources
- age of cached resources
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: baec376501feb70e4a9ceb3f33ac66fa76b91ac1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="cache-policy-interactionmaximum-age-and-maximum-staleness"></a>Interakce zásad do mezipaměti – maximální stáří a maximální typu Prošlostí
K zajištění, že nejčerstvější obsah se vrátí do klientské aplikace, výsledkem interakce klienta mezipaměti zásad a server opětovné ověření požadavků vždy nejvíce konzervativní zásady ukládání do mezipaměti. V příkladech v tomto tématu ilustrují zásady ukládání do mezipaměti pro prostředek, který se uloží do mezipaměti na 1. ledna a jeho platnost vyprší v lednu 4.  
  
 V následujících příkladech, hodnota maximální typu prošlostí (`maxStale`) se používá ve spojení s maximální stáří (`maxAge`):  
  
-   Pokud je nastaví zásady ukládání do mezipaměti `maxAge` = 5 dní a neurčuje `maxStale` hodnoty, podle `maxAge` hodnota, obsah je až 6 leden použitelné. V souladu s požadavky opětovné ověření serveru, ale obsah vyprší na leden 4. Protože datum vypršení platnosti obsahu je více konzervativní (dříve), pak má přednost před `maxAge` zásad. Obsah, tedy vyprší na leden 4 a musí být obnoveny, i když nedosáhla své maximální stáří.  
  
-   Pokud je nastaví zásady ukládání do mezipaměti `maxAge` = 5 dní a `maxStale` = 3 dny, podle požadavků `maxAge` hodnota, obsah je až 6 leden použitelné. Podle požadavků `maxStale` hodnota, obsah je až 7 leden použitelné. Proto získá obsahu obnoveny v lednu 6.  
  
-   Pokud je nastaví zásady ukládání do mezipaměti `maxAge` = 5 dní a `maxStale` = 1 den, podle požadavků `maxAge` hodnota, obsah je až 6 leden použitelné. Podle požadavků `maxStale` hodnota, obsah je až 5 leden použitelné. Proto získá obsahu obnoveny v lednu 5.  
  
 Když maximální stáří je menší než datum vypršení platnosti obsahu, mají vždycky přednost více konzervativní chování ukládání do mezipaměti a hodnota typu maximální prošlostí nemá žádný vliv. Následující příklady ilustrují účinek nastavení maximální typu prošlostí (`maxStale`) hodnotu v případě maximální stáří (`maxAge`) je dosažen předtím, než vyprší platnost obsahu:  
  
-   Pokud je nastaví zásady ukládání do mezipaměti `maxAge` = 1 den a neurčuje hodnotu `maxStale` hodnotu, obsah je znovu ověřeny v lednu 2, i když nevypršela platnost.  
  
-   Pokud je nastaví zásady ukládání do mezipaměti `maxAge` = 1 den a `maxStale` = 3 dny, obsah je znovu ověřeny v lednu 2 k vynucení více konzervativní nastavení zásad.  
  
-   Pokud je nastaví zásady ukládání do mezipaměti `maxAge` = 1 den a `maxStale` = 1 den, obsah je znovu ověřeny v lednu 2.  
  
## <a name="see-also"></a>Viz také  
 [Správa mezipaměti pro síťové aplikace](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [Zásady mezipaměti](../../../docs/framework/network-programming/cache-policy.md)  
 [Na základě umístění mezipaměti zásad](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [Zásady založené na čase mezipaměti](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [Konfigurace ukládání do mezipaměti v síťových aplikací](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [Interakce zásad do mezipaměti – maximální stáří a minimální aktuálnosti](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)