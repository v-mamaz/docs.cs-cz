---
title: 'Postupy: Volání databázových funkcí'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: 5b3af3b74f79d436f39ca0515661b69d66d2d191
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825573"
---
# <a name="how-to-call-database-functions"></a>Postupy: Volání databázových funkcí
<xref:System.Data.Objects.SqlClient.SqlFunctions> Třída obsahuje metody, které zpřístupnění funkcí systému SQL Server pomocí v technologii LINQ dotazy na entity. Při použití <xref:System.Data.Objects.SqlClient.SqlFunctions> metody v jazyce LINQ dotazy na entity, odpovídající funkce databáze jsou provedeny v databázi.  
  
> [!NOTE]
>  Databázové funkce, které provádí výpočet na sadu hodnot a vrací jedinou hodnotu (označované také jako databáze agregační funkce) lze vyvolat přímo. Jiné kanonické funkce lze volat pouze jako součást dotazu LINQ to Entities. Agregační funkci volat přímo, je nutné předat <xref:System.Data.Objects.ObjectQuery%601> funkci. Další informace najdete ve druhém příkladu níže.  
  
> [!NOTE]
>  Metody v <xref:System.Data.Objects.SqlClient.SqlFunctions> třídy jsou specifické pro funkce serveru SQL Server. Podobně jako třídy, která zpřístupňují funkce databáze může být k dispozici prostřednictvím dalších poskytovatelů.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples). V příkladu provede LINQ to Entities dotaz, který používá <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> metody, která vrátí všechny kontakty, jejichž příjmení začíná "Si":  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples). Příklad volá agregace <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> metoda přímo. Všimněte si, že <xref:System.Data.Objects.ObjectQuery%601> je předán do funkce, což umožňuje volat bez se zapojil dotazu LINQ to Entities.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a>Viz také:
- [Volání funkcí v dotazech LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
- [Dotazy v technologii LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
