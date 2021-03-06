---
title: 'Postupy: Načtení souvisejících entit (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: a05d294f80943e771a298b4442a521de86ff2f19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616963"
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Postupy: Načtení souvisejících entit (WCF Data Services)
Pokud potřebujete načíst související entity v [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], můžete použít <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> metodu <xref:System.Data.Services.Client.DataServiceContext> třídy. Můžete také použít <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> metodu <xref:System.Data.Services.Client.DataServiceQuery%601> vyžadovat, například související entity načíst stejné odpovědi na dotaz.  
  
 V příkladu v tomto tématu se používá Northwind ukázková data service a automaticky vygenerovaných tříd klientské datové služby. Tuto službu a třídy dat klientů jsou vytvořeny po dokončení [rychlý start služeb WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak pro explicitní načtení `Customer` , která souvisí s každou vrátil `Orders` instance.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> metoda vrátí `Order Details` , která patří `Orders` vrácených dotazem.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>Viz také:
- [Dotazování v datové službě](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
