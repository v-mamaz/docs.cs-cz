---
title: "Postupy: projektu nový typ (technologie LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7d3deb826bdccdc2a24db84c006fe317a2321442
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="e3bff-102">Postupy: projektu nový typ (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e3bff-102">How to: Project a New Type (LINQ to XML) (C#)</span></span>
<span data-ttu-id="e3bff-103">Další příklady v této části ukázaly, dotazy, které vracejí výsledky jako <xref:System.Collections.Generic.IEnumerable%601> z <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> z `string`, a <xref:System.Collections.Generic.IEnumerable%601> z `int`.</span><span class="sxs-lookup"><span data-stu-id="e3bff-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="e3bff-104">Toto jsou běžné typy výsledků, ale nejsou vhodná pro každý scénář.</span><span class="sxs-lookup"><span data-stu-id="e3bff-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="e3bff-105">V mnoha případech můžete své dotazy vrátit <xref:System.Collections.Generic.IEnumerable%601> některé typu.</span><span class="sxs-lookup"><span data-stu-id="e3bff-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3bff-106">Příklad</span><span class="sxs-lookup"><span data-stu-id="e3bff-106">Example</span></span>  
 <span data-ttu-id="e3bff-107">Tento příklad ukazuje, jak k vytváření instancí objektů v `select` klauzule.</span><span class="sxs-lookup"><span data-stu-id="e3bff-107">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="e3bff-108">Kód nejdřív definuje novou třídu s konstruktor a pak upravením `select` příkaz tak, aby výraz novou instanci třídy novou třídu.</span><span class="sxs-lookup"><span data-stu-id="e3bff-108">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="e3bff-109">Tento příklad používá následující dokumentu XML: [ukázkový soubor XML: typické nákupní objednávka (technologie LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="e3bff-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
class NameQty {  
    public string name;  
    public int qty;  
    public NameQty(string n, int q)  
    {  
        name = n;  
        qty = q;  
    }  
};  
  
class Program {  
    public static void Main() {  
        XElement po = XElement.Load("PurchaseOrder.xml");  
  
        IEnumerable<NameQty> nqList =  
            from n in po.Descendants("Item")  
            select new NameQty(  
                    (string)n.Element("ProductName"),  
                    (int)n.Element("Quantity")  
                );  
  
        foreach (NameQty n in nqList)  
            Console.WriteLine(n.name + ":" + n.qty);  
    }  
}  
```  
  
 <span data-ttu-id="e3bff-110">Tento příklad používá `M:System.Xml.Linq.XElement.Element` metoda, která byla zavedená v tématu [postupy: načtení jeden podřízený Element (technologie LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e3bff-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="e3bff-111">Také používá k načtení hodnoty prvků, které se vrátí pomocí položky CAST `M:System.Xml.Linq.XElement.Element` metoda.</span><span class="sxs-lookup"><span data-stu-id="e3bff-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="e3bff-112">Tento příklad vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="e3bff-112">This example produces the following output:</span></span>  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3bff-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="e3bff-113">See Also</span></span>  
 [<span data-ttu-id="e3bff-114">Projekce a transformace (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e3bff-114">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)