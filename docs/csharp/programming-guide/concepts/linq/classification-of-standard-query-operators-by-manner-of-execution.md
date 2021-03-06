---
title: Klasifikace standardních operátorů dotazu podle metody provedení (C#)
ms.date: 07/20/2015
ms.assetid: b9435ce5-a7cf-4182-9f01-f3468a5533dc
ms.openlocfilehash: eaf0be4faee01e94b508b31bf878a537471750a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711769"
---
# <a name="classification-of-standard-query-operators-by-manner-of-execution-c"></a>Klasifikace standardních operátorů dotazu podle metody provedení (C#)
LINQ na objekty implementace metody standardních dotazovacích operátorů provést dva hlavní způsoby: okamžité nebo odložené. Operátory dotazů, které používají odložené provedení lze dále rozdělit do dvou kategorií: vysílání datových proudů a jiných datových proudů. Pokud víte, jak provést operátory jiný dotaz, se vám můžou pomoct porozumět výsledky, které jste získali z daný dotaz. To je obzvláště hodnotu true, pokud zdroj dat se mění nebo vytváření dotazu na jiný dotaz. Toto téma klasifikuje podle jejich metody provedení standardních dotazovacích operátorů.  
  
## <a name="manners-of-execution"></a>Způsoby spouštění  
  
### <a name="immediate"></a>Okamžité  
 Okamžité spuštění znamená, že je zdroj dat pro čtení a se operace provádí v místě v kódu, ve kterém je deklarována dotazu. Všechny operátory standardního dotazu, které vracejí výsledek jeden, vyčíslitelné spustit okamžitě.  
  
### <a name="deferred"></a>Odložené  
 Odložené provedení znamená, že operace se neprovádí v místě v kódu, ve kterém je deklarována dotazu. Operace se provádí jenom v případě, že proměnná dotazu je vypočten, například pomocí `foreach` příkazu. To znamená, že výsledky provádění dotazu závisí na obsahu zdroje dat při spuštění dotazu místo Pokud je dotaz definován. Pokud proměnná dotazu je vypočten víckrát, výsledky mohou lišit pokaždé, když. Téměř všechny operátory standardního dotazu, jehož návratový typ je <xref:System.Collections.Generic.IEnumerable%601> nebo <xref:System.Linq.IOrderedEnumerable%601> spustit odložené způsobem.  
  
 Operátory dotazů, které pomocí odloženého provedení můžete kromě jsou klasifikovány jako streamování nebo jiných datových proudů.  
  
#### <a name="streaming"></a>Streamování  
 Streamování operátory nemusíte číst všechna zdrojová data před dávají elementy. V době spuštění streamování operátor provádí její činnosti na každý prvek zdroje, jako je čtení a vrací prvku v případě potřeby. Operátor streamování pokračovat ve čtení zdrojové elementy, dokud elementu výsledku je možné vytvořit. To znamená, že může být více než jeden element source číst k vytvoření jednoho elementu výsledku.  
  
#### <a name="non-streaming"></a>Streamování  
 Non-operátory pro datový proud musí číst všechna zdrojová data, před vedou k elementu výsledku. Do této kategorie patří operace, jako je řazení nebo seskupení. V době spuštění operátory dotazu bez datový proud čtení všechna zdrojová data, vložit ho do datové struktury, provést operaci a výsledný elementů yield.  
  
## <a name="classification-table"></a>Klasifikace tabulky  
 V následující tabulce klasifikuje každou metodu operátoru standardního dotazu podle její metoda spuštění.  
  
> [!NOTE]
>  Pokud operátor označení ve dvou sloupcích, operace se týká dvou vstupních sekvencí a každé posloupnosti je vyhodnocovány jinak. V těchto případech je vždy první pořadí v seznamu parametrů, který je vyhodnocen v odložené, streamování způsobem.  
  
|Standardní operátor dotazu|Návratový typ|Okamžité provedení|Odložené provedení datových proudů|Odložené bez streamování spuštění|  
|-----------------------------|-----------------|-------------------------|----------------------------------|---------------------------------------|  
|<xref:System.Linq.Enumerable.Aggregate%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.All%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Any%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.AsEnumerable%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Average%2A>|Jednu číselnou hodnotu|X|||  
|<xref:System.Linq.Enumerable.Cast%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Concat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Contains%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Count%2A>|<xref:System.Int32>|X|||  
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Distinct%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.ElementAt%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.Empty%2A>|<xref:System.Collections.Generic.IEnumerable%601>|X|||  
|<xref:System.Linq.Enumerable.Except%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.First%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.FirstOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.GroupBy%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.GroupJoin%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
<xref:System.Linq.Enumerable.Intersect%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.Join%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.Last%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.LastOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.LongCount%2A>|<xref:System.Int64>|X|||  
|<xref:System.Linq.Enumerable.Max%2A>|Jednu numerickou hodnotu, TSource nebo TResult|X|||  
|<xref:System.Linq.Enumerable.Min%2A>|Jednu numerickou hodnotu, TSource nebo TResult|X|||  
|<xref:System.Linq.Enumerable.OfType%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.OrderBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.OrderByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.Range%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Repeat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Reverse%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.Select%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SelectMany%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SequenceEqual%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Single%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.SingleOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.Skip%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SkipWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Sum%2A>|Jednu číselnou hodnotu|X|||  
|<xref:System.Linq.Enumerable.Take%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
<xref:System.Linq.Enumerable.TakeWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.ThenBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.ThenByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.ToArray%2A>|TSource pole|X|||  
|<xref:System.Linq.Enumerable.ToDictionary%2A>|<xref:System.Collections.Generic.Dictionary%602>|X|||  
|<xref:System.Linq.Enumerable.ToList%2A>|<xref:System.Collections.Generic.IList%601>|X|||  
|<xref:System.Linq.Enumerable.ToLookup%2A>|<xref:System.Linq.ILookup%602>|X|||  
|<xref:System.Linq.Enumerable.Union%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Where%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
  
## <a name="see-also"></a>Viz také:

- <xref:System.Linq.Enumerable>
- [Přehled standardních operátorů dotazu (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Syntaxe výrazu dotazu pro standardní operátory dotazu (C#)](../../../../csharp/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)
- [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
