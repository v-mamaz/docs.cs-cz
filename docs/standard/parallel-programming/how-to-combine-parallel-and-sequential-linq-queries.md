---
title: "Postupy: Kombinování paralelních a sekvenčních LINQ dotazů"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4da91ff535059b181baa637164a854cd75d06334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="80d70-102">Postupy: Kombinování paralelních a sekvenčních LINQ dotazů</span><span class="sxs-lookup"><span data-stu-id="80d70-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>
<span data-ttu-id="80d70-103">Tento příklad ukazuje způsob použití <xref:System.Linq.ParallelEnumerable.AsSequential%2A> metoda k vynucení PLINQ postupně zpracovat všechny následné operátory v dotazu.</span><span class="sxs-lookup"><span data-stu-id="80d70-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="80d70-104">I když je obecně pomalejší než paralelní zpracování sekvenčních, někdy je nezbytné pro správné výsledky.</span><span class="sxs-lookup"><span data-stu-id="80d70-104">Although sequential processing is generally slower than parallel, sometimes it is necessary to produce correct results.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="80d70-105">Tento příklad je určený k předvedení využití a nemusí být možné spustit rychleji, než ekvivalentní sekvenčních LINQ na objekty dotazu.</span><span class="sxs-lookup"><span data-stu-id="80d70-105">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="80d70-106">Další informace o zrychlení najdete v tématu [porozumění zrychlení v PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="80d70-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="80d70-107">Příklad</span><span class="sxs-lookup"><span data-stu-id="80d70-107">Example</span></span>  
 <span data-ttu-id="80d70-108">Následující příklad ukazuje jeden scénář, ve kterém <xref:System.Linq.ParallelEnumerable.AsSequential%2A> je potřeba, a to zachování pořadí, které bylo vytvořeno v předchozí klauzuli dotazu.</span><span class="sxs-lookup"><span data-stu-id="80d70-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="80d70-109">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="80d70-109">Compiling the Code</span></span>  
 <span data-ttu-id="80d70-110">Pro zkompilování a spuštění tohoto kódu, vložte jej do [ukázková Data pro PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) projekt, přidejte řádek zavolat metodu z `Main`, a stiskněte klávesu F5.</span><span class="sxs-lookup"><span data-stu-id="80d70-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d70-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="80d70-111">See Also</span></span>  
 [<span data-ttu-id="80d70-112">Paralelní LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="80d70-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)