---
title: 'Postupy: Povolení přístupu k datové služby (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: d1ce582096de63f60c7f2c99925fa39710bedfb3
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091939"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a>Postupy: Povolení přístupu k datové služby (WCF Data Services)
V [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], je nutné explicitně udělit přístup k prostředkům, které jsou vystaveny datové služby. To znamená, že po vytvoření nové datové služby musí stále explicitně poskytnete přístup k jednotlivým prostředkům jako sady entit. Toto téma ukazuje, jak povolit čtení a zápis do pěti členů entity nastaví v datová služba Northwind, který je vytvořen po dokončení [rychlý Start](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Protože <xref:System.Data.Services.EntitySetRights> výčet je definován pomocí <xref:System.FlagsAttribute>, můžete použít logické nebo nastavit operátor k určení více oprávnění pro jednu entitu.  
  
> [!NOTE]
>  Libovolného klienta, který má přístup k aplikaci technologie ASP.NET můžete také přístup k prostředkům vystavené datové služby. Ve službě data produkčního prostředí Chcete-li zabránit neoprávněnému přístupu k prostředkům, je třeba také zabezpečit samotná aplikace. Další informace najdete v tématu [zabezpečení webů ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/91f66yxt(v=vs.100)).  
  
### <a name="to-enable-access-to-the-data-service"></a>Umožňuje přístup k datové službě  
  
-   V kódu pro datovou službu, nahraďte zástupný symbol kód v `InitializeService` funkce následujícím kódem:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     To umožňuje klientům ke čtení a zápis `Orders` a `Order_Details` sad entit a přístup jen pro čtení k `Customers` sady entit.  
  
## <a name="see-also"></a>Viz také:
- [Postupy: Vývoj datové služby WCF ve službě IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)
- [Konfigurace datové služby](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
