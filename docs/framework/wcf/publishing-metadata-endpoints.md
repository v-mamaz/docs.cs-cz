---
title: Publikování kocových bodů metadat
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 5de1122a4b603e4c0cd3ae55f3ac7424a7fd77f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626588"
---
# <a name="publishing-metadata-endpoints"></a>Publikování kocových bodů metadat
Služby Windows Communication Foundation (WCF) měla být zveřejněna metadata a publikovat jednu nebo víc koncových bodů metadat. Publikování metadat služby zpřístupňuje metadata použitím standardizovaných protokolů, jako jsou žádosti o WS-MetadataExchange (MEX) a protokolu HTTP/GET. Koncové body metadat se podobně jako ostatní koncové body služby mají adresa, vazba a kontrakt a je možné je přidat k hostiteli služby prostřednictvím konfigurace nebo v kódu. Pokud chcete povolit publikování kocových bodů metadat, je nutné přidat <xref:System.ServiceModel.Description.ServiceMetadataBehavior> služeb chování ve službě.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: Publikování metadat služby promocí konfiguračního souboru](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Ukazuje, jak nakonfigurovat tak, aby klienti mohou získat metadata pomocí WS-MetadataExchange nebo pomocí požadavku HTTP/GET být zveřejněna metadata služby WCF `?wsdl` řetězec dotazu.  
  
 [Postupy: Publikování metadat služby promocí kódu](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Ukazuje, jak povolit publikování metadat služby WCF v kódu tak, aby klienti mohou získat metadata pomocí WS-MetadataExchange nebo pomocí požadavku HTTP/GET `?wsdl` řetězec dotazu.  
  
## <a name="see-also"></a>Viz také:
- [Publikování metadat](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
