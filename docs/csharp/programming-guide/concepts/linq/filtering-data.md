---
title: Filtrování dat (C#)
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: dc31a73a8ebbe52f7d22984cd747a038e2556c28
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634633"
---
# <a name="filtering-data-c"></a>Filtrování dat (C#)
Filtrování odkazuje na operaci omezení sady výsledků do obsahovat pouze prvky, které splňují zadanou podmínku. Je také označován jako výběr.  
  
 Následující obrázek ukazuje výsledky filtrování posloupnost znaků. Predikát pro filtrování operace určuje, že znak musí být "A".  
  
 ![Filtrování operace LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")  
  
 V následující části jsou uvedeny standardní metody operátoru dotazu, které provádějí výběru.  
  
## <a name="methods"></a>Metody  
  
|Název metody|Popis|Syntaxe výrazu dotazu jazyka C#|Další informace|  
|-----------------|-----------------|---------------------------------|----------------------|  
|OfType|Vybere hodnoty v závislosti na jejich schopnost převést na zadaný typ.|Nelze použít.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|Where|Vybere hodnoty, které jsou založeny na funkce predikátu.|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>Příklad syntaxe výrazu dotazu  
 V následujícím příkladu `where` klauzule můžete filtrovat z pole těchto řetězců, které mají určité délky.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a>Viz také:

- <xref:System.Linq>
- [Přehled standardních operátorů dotazu (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [where – klauzule](../../../../csharp/language-reference/keywords/where-clause.md)
- [Postupy: Dynamické určování filtrů predikátů při běhu](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
- [Postupy: Dotazu na Metadata sestavení s reflexí (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [Postupy: Dotaz pro soubory s konkrétním atributem či názvem (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [Postupy: Řazení nebo filtrování textových dat podle libovolného slova či pole (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
