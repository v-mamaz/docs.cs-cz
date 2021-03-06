---
title: Implementace proxy zjišťování
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: f2f687912b966b03c17206f369b46ffd28d019d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634516"
---
# <a name="implementing-a-discovery-proxy"></a>Implementace proxy zjišťování
Tato část popisuje kroky potřebné k implementace zjišťování proxy. Zjišťování proxy je samostatná služba, která obsahuje úložiště služby. Klienti mohou odesílat dotazy na zjišťování proxy k vyhledání zjistitelné služby, které si je vědoma proxy serveru. Jak se proxy server služby vyplní záleží implementátora. Například můžete proxy zjišťování připojit k existující služby úložiště a zjistitelnost těchto informací, Správce může pomocí rozhraní API pro správu přidejte zjistitelné služby pro proxy server nebo proxy zjišťování můžete použít funkce oznámení pro Aktualizujte vnitřní mezipaměti.  
  
 Implementace WCF poskytuje základní třídy, které umožňují snadno vytvářet proxy server. Můžete využívat tato rozhraní API k vytvoření zjišťování proxy serveru na svém stávajícím úložišti.  
  
 Zde implementováno proxy zjišťování je stejně jako jiné služby WCF můžete také zjistitelnost proxy zjišťování a klientům vyhledat své koncové body.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: Implementace Proxy zjišťování](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 Popisuje způsob implementace zjišťování proxy.  
  
 [Postupy: Implementace zjistitelné služby, která se registruje pomocí Proxy zjišťování](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 Popisuje způsob implementace zjistitelné služby WCF, která se registruje pomocí proxy zjišťování.  
  
 [Postupy: Implementace klientské aplikace používající zjišťování Proxy k vyhledání služby](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 Popisuje způsob implementace WCF klientské aplikace používající zjišťování proxy k vyhledání pro službu.  
  
 [Postupy: Test Proxy zjišťování](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 Popisuje, jak testovat kód napsaný v předchozí tři témata.  
  
## <a name="see-also"></a>Viz také:
- [Zjišťování WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)
- [Postupy: Programové přidání možností rozpoznání do klienta a služby WCF](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
