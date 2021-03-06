---
title: 'Postupy: Store a opakované použití dotazů'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a012bd79-1809-45e3-adea-0229532396cc
ms.openlocfilehash: a913839ab8e6048b18270061a75ca632e2797fb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630763"
---
# <a name="how-to-store-and-reuse-queries"></a>Postupy: Store a opakované použití dotazů
Až budete mít aplikaci, která se spustí v mnoha případech strukturálně podobné dotazy, můžete často zvýšit výkon kompilaci dotazu jednou a spustíte ji několikrát s různými parametry. Například aplikace může mít k načtení všech zákazníků, kteří jsou v konkrétní Město, ve kterém Město je uživatel zadá za běhu ve formuláři. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] podporuje použití *kompilaci dotazů* pro tento účel.  
  
> [!NOTE]
>  Tento vzor využití představuje nejběžnějším využitím kompilované dotazy. Další postupy jsou možné. Například kompilované dotazy mohou být uloženy jako statické členy na částečné třídy, která rozšiřuje kód generovaný návrhářem.  
  
## <a name="example"></a>Příklad  
 V mnoha případech můžete chtít znovu použít dotazy napříč hranicemi vlákna. V takovém případě je zvláště efektivní ukládání kompilované dotazy ve statické proměnné. Následující příklad kódu předpokládá `Queries` třída určená k ukládání zkompilován dotazy a předpokládá Northwind třídu, která představuje silného typu <xref:System.Data.Linq.DataContext>.  
  
 [!code-csharp[DLinqQuerying#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#6)]
 [!code-vb[DLinqQuerying#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#6)]  
  
 [!code-csharp[DLinqQuerying#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#7)]
 [!code-vb[DLinqQuerying#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#7)]  
  
## <a name="example"></a>Příklad  
 Nemůžete momentálně úložiště (v statické proměnné) dotazy, které vracejí *anonymního typu*, protože typ nemá žádný název poskytnout jako obecný argument. Následující příklad ukazuje, jak můžete tento problém obejít tím, že vytvoříte typ, který představuje výsledek a pak použít jako obecný argument.  
  
 [!code-csharp[DLinqQuerying#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#8)]
 [!code-vb[DLinqQuerying#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#8)]  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Data.Linq.CompiledQuery>
- [Koncepty dotazů](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [Dotazování na databázi](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
