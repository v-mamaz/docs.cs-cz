---
title: 'Postupy: dotaz na informace'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f0722f83c19c1eff43606afceeda484d72691eb9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="e514a-102">Postupy: dotaz na informace</span><span class="sxs-lookup"><span data-stu-id="e514a-102">How to: Query for Information</span></span>
<span data-ttu-id="e514a-103">Dotazy v [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] používají stejnou syntaxi jako dotazy v [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e514a-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="e514a-104">Jediným rozdílem je, že objekty odkazovaný ve [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dotazy jsou namapované na elementy v databázi.</span><span class="sxs-lookup"><span data-stu-id="e514a-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="e514a-105">Další informace najdete v tématu [Úvod do dotazů LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e514a-105">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e514a-106">Přeloží dotazy, které můžete psát na ekvivalentní dotazy SQL a odešle je server pro zpracování.</span><span class="sxs-lookup"><span data-stu-id="e514a-106"> translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="e514a-107">Některé funkce [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] dotazy může být nutné zvláštní pozornost v [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="e514a-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="e514a-108">Další informace najdete v tématu [dotazu koncepty](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="e514a-108">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e514a-109">Příklad</span><span class="sxs-lookup"><span data-stu-id="e514a-109">Example</span></span>  
 <span data-ttu-id="e514a-110">Následující dotaz zobrazí seznam zákazníky z Londýna.</span><span class="sxs-lookup"><span data-stu-id="e514a-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="e514a-111">V tomto příkladu `Customers` je tabulky v ukázkové databázi Northwind.</span><span class="sxs-lookup"><span data-stu-id="e514a-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e514a-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="e514a-112">See Also</span></span>  
 [<span data-ttu-id="e514a-113">Vytváření objektový Model</span><span class="sxs-lookup"><span data-stu-id="e514a-113">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [<span data-ttu-id="e514a-114">Stažení ukázkové databáze</span><span class="sxs-lookup"><span data-stu-id="e514a-114">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="e514a-115">Dotaz na databázi</span><span class="sxs-lookup"><span data-stu-id="e514a-115">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)