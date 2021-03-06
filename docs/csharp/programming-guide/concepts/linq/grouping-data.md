---
title: Seskupování dat (C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 079f346435e2f21b7c46b528d68f917f5532db66
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583217"
---
# <a name="grouping-data-c"></a>Seskupování dat (C#)
Seskupení odkazuje na operace ukládání dat do skupin, aby elementy v každé skupině sdílet společný atribut.  
  
 Následující obrázek ukazuje výsledky seskupení posloupnost znaků. Klíč pro každou skupinu je znak.  
  
 ![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")  
  
 Standardní metody operátoru dotazu, které seskupují datové prvky jsou uvedeny v následující části.  
  
## <a name="methods"></a>Metody  
  
|Název metody|Popis|Syntaxe výrazu dotazu jazyka C#|Další informace|  
|-----------------|-----------------|---------------------------------|----------------------|  
|GroupBy|Seskupí elementy, které sdílejí společný atribut. Každá skupina představuje <xref:System.Linq.IGrouping%602> objektu.|`group … by`<br /><br /> -nebo-<br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|ToLookup|Vloží prvky do <xref:System.Linq.Lookup%602> (jeden na mnoho slovník) podle funkce selektoru klíče.|Nelze použít.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>Příklad syntaxe výrazu dotazu  
 Následující příklad kódu používá `group by` klauzule, která skupina celých čísel v seznamu podle toho, zda jsou sudý, nebo lichý.  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a>Viz také:

- <xref:System.Linq>
- [Přehled standardních operátorů dotazu (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [group – klauzule](../../../../csharp/language-reference/keywords/group-clause.md)
- [Postupy: Vytvoření vnořené skupiny](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)
- [Postupy: Seskupování souborů podle přípony (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)
- [Postupy: Seskupení výsledků dotazu](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)
- [Postupy: Provádění poddotazů na operace seskupení](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)
- [Postupy: Rozdělení souboru na více souborů pomocí skupin (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
