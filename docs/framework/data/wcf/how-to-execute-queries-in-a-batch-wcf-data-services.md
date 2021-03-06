---
title: 'Postupy: Provádění dotazů v dávce (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
ms.openlocfilehash: 3a11a96c197cd6905d8e80fac5c869a9c5c374e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611901"
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Postupy: Provádění dotazů v dávce (WCF Data Services)
S použitím [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] klientské knihovny, můžete spustit více než jeden dotaz na datovou službu v jedné dávce. Další informace najdete v tématu [dávkování operací](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md).  
  
 V příkladu v tomto tématu se používá Northwind ukázková data service a automaticky vygenerovaných tříd klientské datové služby. Tuto službu a třídy dat klientů jsou vytvořeny po dokončení [rychlý start služeb WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak volat <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> metodu provést. pole <xref:System.Data.Services.Client.DataServiceRequest%601> objekty, které obsahuje dotazy vracející obě `Customers` a `Products` objekty z datová služba Northwind. Kolekce <xref:System.Data.Services.Client.QueryOperationResponse%601> objekty ve vráceném <xref:System.Data.Services.Client.DataServiceResponse> výčtu a kolekci objektů obsažených v každém <xref:System.Data.Services.Client.QueryOperationResponse%601> také ve výčtu.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>Viz také:
- [Klientská knihovna pro WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
