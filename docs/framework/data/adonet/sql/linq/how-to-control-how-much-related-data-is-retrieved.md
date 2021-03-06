---
title: 'Postupy: Ovládací prvek, kolik souvisejících dat'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
ms.openlocfilehash: 3b52e2cdefefce011be7d729569b76f919f9bb33
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715605"
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a>Postupy: Ovládací prvek, kolik souvisejících dat
Použití <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> metody k určení, která data související s vaší hlavní cíl by měly být načteny současně. Například pokud víte, budete potřebovat informace o objednávek zákazníků, můžete použít <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> abyste měli jistotu, že je ve stejnou dobu jako informace o zákaznících načíst informace o objednávce. Tento přístup za následek jenom jednu cestu k databázi pro obě sady informace.  
  
> [!NOTE]
>  Můžete načíst data související s hlavním cílem dotazu načtením mezi produkty jako jeden velký projekce, třeba načítání objednávek, při použití prostředí zákazníků. Ale tento přístup má často nevýhody. Například výsledky jsou pouze projekce a není entity, které je možné změnit a určen na základě [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. A můžete načítají velké množství dat, která není nutné.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu všechny `Orders` pro všechny `Customers` kdo jsou umístěny v Londýně jsou načteny při spuštění dotazu. V důsledku toho po sobě jdoucích přístup k `Orders` vlastnosti `Customer` objekt neaktivuje nový databázový dotaz.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Viz také:
- [Dotazování na databázi](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
