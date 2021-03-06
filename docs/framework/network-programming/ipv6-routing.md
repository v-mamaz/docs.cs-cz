---
title: IPv6 Routing
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
ms.openlocfilehash: dabf17f85330b884918d5c6e1bc9832a7a0dbd02
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694812"
---
# <a name="ipv6-routing"></a>IPv6 Routing
Flexibilní mechanismus směrování je výhodou IPv6. Kvůli způsobu, jakým IPv4, které byly ID sítě a jsou přidělené a velké směrovací tabulky musí být udržována směrovače, které jsou na Internetu páteřních. Tyto směrovače, jestliže musíte znát všechny trasy k předávání paketů, které jsou potenciálně směrované do kteréhokoli uzlu na Internetu. S jeho schopnost agregační adresy IPv6 umožňuje flexibilní adresování a výrazně snižuje velikost směrovací tabulky. V této nové architektuře adresování zprostředkující směrovače musí sledovat pouze místní část své síti pro předávání zpráv správně.  
  
## <a name="neighbor-discovery"></a>ND  
 Některé z funkcí poskytovaných službou ND jsou:  
  
-   Zjišťování směrovačů. To umožňuje hostitelům identifikovat místního směrovače.  
  
-   Adresa řešení. To umožňuje uzly přeložit adresu linkové vrstvě pro příslušnou adresou dalšího směrování (náhrada za Address Resolution Protocol [ARP]).  
  
-   Automatické konfigurace adresy. To umožňuje hostitelům pro automatickou konfiguraci místní a globální adresy.  
  
 ND používá Internet Control Message Protocol pro protokol IPv6 (ICMPv6) zpráv, které zahrnují:  
  
-   Inzerování směrovače. Odeslaný směrovač částečně pravidelně nebo v reakci na oslovení směrovače. Směrovače IPv6 pomocí inzerování směrovače inzerovat jejich dostupnost, předpony a další parametry.  
  
-   Oslovení směrovače. Odeslaný požádat o směrovače na odkaz okamžitě poslat inzerování směrovače.  
  
-   Sousední žádostí. Odeslaný uzly pro rozpoznání adresy, detekce duplicitních adres, nebo chcete-li ověřit, že souseda je stále dostupný.  
  
-   Sousední oznámení o inzerovaném programu. Odesílá se uzly reagovat na sousední oslovení nebo oznámit okolí změnu adresy na linkové vrstvě.  
  
-   Přesměrování. Odesílá udávajících lepší adresa dalšího směrování do určitého cíle pro odesílání uzel.  
  
## <a name="see-also"></a>Viz také:
- [Protokol IP (Internet Protocol) verze 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)
- [Sokety](../../../docs/framework/network-programming/sockets.md)
