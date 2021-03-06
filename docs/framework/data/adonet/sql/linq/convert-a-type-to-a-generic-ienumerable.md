---
title: Převod typu na obecnou položku IEnumerable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: d1f4c1c4a561c893b5846e6ae0b08b2d78c3589d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509592"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a>Převod typu na obecnou položku IEnumerable
Použití <xref:System.Linq.Enumerable.AsEnumerable%2A> vrátit argument obecného typu `IEnumerable`.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (použití výchozí Obecné `Query`) by se pokusil převést dotaz SQL a spusťte na serveru. Ale `where` klauzule odkazuje na metodu uživatelem definované na straně klienta (`isValidProduct`), kterou nelze převést na SQL.  
  
 Toto řešení je k určení obecného na straně klienta <xref:System.Collections.Generic.IEnumerable%601> provádění `where` nahradit obecný <xref:System.Linq.IQueryable%601>. To provedete tak, že vyvolá <xref:System.Linq.Enumerable.AsEnumerable%2A> operátor.  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a>Viz také:
- [Příklady dotazů](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
