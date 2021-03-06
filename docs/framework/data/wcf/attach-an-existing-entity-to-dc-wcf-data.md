---
title: 'Postupy: Přiřazení existující Entity k prvku DataServiceContext (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 2a515609feff343b6e917bf420a06cfb9dc468df
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614221"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>Postupy: Přiřazení existující Entity k prvku DataServiceContext (WCF Data Services)
Pokud entita již existuje ve službě data [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Klientská knihovna umožňuje připojit objekt, který entitu představuje přímo na <xref:System.Data.Services.Client.DataServiceContext> bez předchozího provedení dotazu. Další informace najdete v tématu [aktualizace datové služby](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 V příkladu v tomto tématu se používá Northwind ukázková data service a automaticky vygenerovaných tříd klientské datové služby. Tuto službu a třídy dat klientů jsou vytvořeny po dokončení [rychlý start služeb WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak vytvořit existující `Customer` objekt, který obsahuje změny, které bude uložena do datové služby. Objekt je připojen ke kontextu a <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> metoda je volána k označení připojeného objektu jako <xref:System.Data.Services.Client.EntityStates.Modified> před <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> metoda je volána.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>Viz také:
- [Klientská knihovna pro WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
