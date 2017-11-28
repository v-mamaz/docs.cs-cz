---
title: "SqlTypes a datové sady"
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
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 86132e266b4421cce048ea38fc91967267a6ae6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="sqltypes-and-the-dataset"></a><span data-ttu-id="2f020-102">SqlTypes a datové sady</span><span class="sxs-lookup"><span data-stu-id="2f020-102">SqlTypes and the DataSet</span></span>
<span data-ttu-id="2f020-103">ADO.NET 2.0 zavedená rozšířenou podporu typ `DataSet` prostřednictvím <xref:System.Data.SqlTypes> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="2f020-103">ADO.NET 2.0 introduced enhanced type support for the `DataSet` through the  <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="2f020-104">Typy v <xref:System.Data.SqlTypes> poskytují datové typy jako typy dat v databázi systému SQL Server se stejnou sémantiku a přesnosti.</span><span class="sxs-lookup"><span data-stu-id="2f020-104">The types in <xref:System.Data.SqlTypes> are designed to provide data types with the same semantics and precision as the data types in a SQL Server database.</span></span> <span data-ttu-id="2f020-105">Každý typ dat v <xref:System.Data.SqlTypes> ekvivalentní datový typ je v systému SQL Server se stejnou základní reprezentaci data.</span><span class="sxs-lookup"><span data-stu-id="2f020-105">Each data type in <xref:System.Data.SqlTypes> has an equivalent data type in SQL Server, with the same underlying data representation.</span></span>  
  
 <span data-ttu-id="2f020-106">Pomocí <xref:System.Data.SqlTypes> přímo v <xref:System.Data.DataSet> poskytuje několik výhod při práci s datovými typy systému SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2f020-106">Using <xref:System.Data.SqlTypes> directly in a <xref:System.Data.DataSet> confers several benefits when working with SQL Server data types.</span></span> <span data-ttu-id="2f020-107"><xref:System.Data.SqlTypes>podporuje stejnou sémantiku jako nativní datové typy systému SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2f020-107"><xref:System.Data.SqlTypes> supports the same semantics as SQL Server native data types.</span></span> <span data-ttu-id="2f020-108">Zadáním jednoho z <xref:System.Data.SqlTypes> v definici <xref:System.Data.DataColumn> eliminuje ztrátu přesnosti, který může nastat při převodu desítkový nebo číselný datový typy na jednu z běžné typy dat language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2f020-108">Specifying one of the <xref:System.Data.SqlTypes> in the definition of a <xref:System.Data.DataColumn> eliminates the loss of precision that can occur when converting decimal or numeric data types to one of the common language runtime (CLR) data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f020-109">Příklad</span><span class="sxs-lookup"><span data-stu-id="2f020-109">Example</span></span>  
 <span data-ttu-id="2f020-110">Následující příklad vytvoří <xref:System.Data.DataTable> objekt, explicitně definování <xref:System.Data.DataColumn> datové typy pomocí <xref:System.Data.SqlTypes> místo typy CLR.</span><span class="sxs-lookup"><span data-stu-id="2f020-110">The following example creates a <xref:System.Data.DataTable> object, explicitly defining the <xref:System.Data.DataColumn> data types by using <xref:System.Data.SqlTypes> instead of CLR types.</span></span> <span data-ttu-id="2f020-111">Vyplní celé kód <xref:System.Data.DataTable> s daty z Sales.SalesOrderDetail tabulky v databázi AdventureWorks v systému SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2f020-111">The code fills the <xref:System.Data.DataTable> with data from the Sales.SalesOrderDetail table in the AdventureWorks database in SQL Server.</span></span> <span data-ttu-id="2f020-112">V okně konzoly zobrazí výstup ukazuje datový typ jednotlivých sloupců a hodnoty načíst ze serveru SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2f020-112">The output displayed in the console window shows the data type of each column, and the values retrieved from SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2f020-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="2f020-113">See Also</span></span>  
 [<span data-ttu-id="2f020-114">Mapování datového typu SQL Server</span><span class="sxs-lookup"><span data-stu-id="2f020-114">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="2f020-115">Konfigurace parametrů a datové typy parametrů</span><span class="sxs-lookup"><span data-stu-id="2f020-115">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="2f020-116">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="2f020-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)