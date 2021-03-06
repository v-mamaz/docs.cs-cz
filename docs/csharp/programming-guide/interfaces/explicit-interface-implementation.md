---
title: Implementace explicitního rozhraní - C# Průvodce programováním
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: 75b031773f8ac34b04f68ec01b12cd9263413bc3
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200140"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Implementace explicitního rozhraní (Průvodce programováním v C#)
Pokud [třídy](../../../csharp/language-reference/keywords/class.md) implementuje dvě rozhraní, které obsahují člena se stejnou signaturou, pak implementace člena třídy způsobí, že obě rozhraní pro použití tohoto člena jako jejich provádění. V následujícím příkladu, všechna volání do `Paint` volání stejné metody.  
  
 [!code-csharp[csProgGuideInheritance#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#39)]  
  
 Pokud dvě [rozhraní](../../../csharp/language-reference/keywords/interface.md) členy nebudete provádět má stejnou funkci, ale to může vést k nesprávná implementace jedno nebo obě rozhraní. Je možné implementovat člen rozhraní, explicitně – vytvoření člena třídy, která je jen volá prostřednictvím rozhraní a je specifické pro rozhraní. Toho lze dosáhnout pojmenování člena třídy se název rozhraní a tečku. Příklad:  
  
 [!code-csharp[csProgGuideInheritance#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#40)]  
  
 Člen třídy `IControl.Paint` je dostupná jenom `IControl` rozhraní, a `ISurface.Paint` je dostupná jenom `ISurface`. Implementace obě metody jsou oddělené a ani je k dispozici přímo ve třídě. Příklad:  
  
 [!code-csharp[csProgGuideInheritance#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#41)]  
  
 Explicitní implementaci se také používá k překladu případy, ve kterém dvě rozhraní deklarovat jiné členy se stejným názvem, jako jsou vlastnosti a metody:  
  
 [!code-csharp[csProgGuideInheritance#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#42)]  
  
 Třídy musí implementovat obě rozhraní, použijte explicitní implementaci buď pro vlastnost P nebo metoda P, nebo obojí, aby se zabránilo chybu kompilátoru. Příklad:  
  
 [!code-csharp[csProgGuideInheritance#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#43)]  
  
## <a name="see-also"></a>Viz také:

- [Průvodce programováním v jazyce C#](../../../csharp/programming-guide/index.md)
- [Třídy a struktury](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Rozhraní](../../../csharp/programming-guide/interfaces/index.md)
- [Dědičnost](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
