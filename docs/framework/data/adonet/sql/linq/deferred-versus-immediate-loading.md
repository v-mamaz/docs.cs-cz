---
title: Odložené versus okamžité načítání
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1d7247f-a3b7-460b-b342-5c1a2365aa1a
ms.openlocfilehash: c78f608225d64a428b768fbc8d03f71a393d980d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516964"
---
# <a name="deferred-versus-immediate-loading"></a>Odložené versus okamžité načítání
Když odešlete dotaz na objekt, ve skutečnosti načíst pouze na objekt, který jste požádali. *Související* objekty nejsou vyvolány automaticky ve stejnou dobu. (Další informace najdete v tématu [dotazování napříč vztahy](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).) Skutečnost, že souvisejících objektů, které ještě nejsou načtená, nejde zobrazit, protože pokus o přístup k těmto vytvoří požadavek, který je obnovuje.  
  
 Například můžete dotazovat na konkrétní sadu objednávky a jenom občas odeslat e-mailové oznámení pro konkrétní zákazníky. Můžete nemusí nutně zpočátku načíst všechna data zákazníků se každých pořadí. Odložené načítání můžete odložit načítání dodatečné informace, dokud je nezbytně nutné. Vezměte v úvahu v následujícím příkladu:  
  
 [!code-csharp[DLinqQueryConcepts#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#1)]
 [!code-vb[DLinqQueryConcepts#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#1)]  
  
 Opak může mít také hodnotu true. Může mít aplikaci, která se má zobrazit daty odběratele a objednávky ve stejnou dobu. Víte, že je nutné, aby obě sady dat. Víte, že vaše aplikace potřebuje informace o objednávkách pro každého zákazníka, co nejdříve získat výsledky. Není vhodné odesílat jednotlivé dotazy na objednávky pro každý zákazník. Co chcete je načíst data objednávky společně se zákazníky.  
  
 [!code-csharp[DLinqQueryConcepts#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#2)]
 [!code-vb[DLinqQueryConcepts#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#2)]  
  
 Můžete také připojit zákazníci a objednávky v dotazu tak, že vytváříme mezi produkty a načítání relativní bitů dat jako jeden velký projekce. Ale tyto výsledky nejsou entity. (Další informace najdete v tématu [The LINQ to SQL objektový Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)). Entity jsou objekty, které mají identity a že můžete upravit, zatímco tyto výsledky budou projekce, které nelze změnit a trvalé. Ještě hůř by se dostáváte spoustu redundantních dat jako každého zákazníka se opakuje pro každý příkaz v výstup plochá spojení.  
  
 Co je skutečně potřeba je způsob, jak načíst sadu souvisejících objektů ve stejnou dobu. Sada je vymezen části grafu tak, že by nikdy být dostáváte víc nebo míň než nezbytné pro zamýšlený účel. Pro tento účel [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] poskytuje <xref:System.Data.Linq.DataLoadOptions> pro okamžité načítání oblasti objektového modelu. Metody patří:  
  
-   <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> Metoda okamžitě načíst data související s hlavní cíl.  
  
-   <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> Metoda chcete filtrovat objekty načíst pro konkrétní vztah.  
  
## <a name="see-also"></a>Viz také:
- [Koncepty dotazů](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
