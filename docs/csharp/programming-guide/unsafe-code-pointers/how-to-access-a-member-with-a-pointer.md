---
title: 'Postupy: přístup ke členu pomocí ukazatele - C# Průvodce programováním pro službu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: 9762b9e2487c30b81b7ef6ae22827b64e3cb02e2
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200348"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a>Postupy: přístup ke členu pomocí ukazatele (C# Programming Guide)
Pro přístup ke členu struktury, která je deklarována v nezabezpečeném kontextu, můžete použít operátor přístupu členů, jak je znázorněno v následujícím příkladu, ve kterém `p` je ukazatel [struktura](../../../csharp/language-reference/keywords/struct.md) , který obsahuje člena `x`.  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a>Příklad  
 V tomto příkladu [struktura](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, která obsahuje dvě souřadnice `x` a `y` definována a je vytvořena instance. S použitím operátor přístupu členů `->` a ukazatel na instanci `home`, `x` a `y` jsou přiřazeny hodnoty.  
  
> [!NOTE]
>  Všimněte si, že výraz `p->x` je ekvivalentní výraz `(*p).x`, a získáte stejný výsledek jedním ze dvou výrazů.  
  
 [!code-csharp[csProgGuidePointers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#9)]  
  
 [!code-csharp[csProgGuidePointers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#10)]  
  
## <a name="see-also"></a>Viz také:

- [Průvodce programováním v jazyce C#](../../../csharp/programming-guide/index.md)
- [Výrazy ukazatelů](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [Typy ukazatelů](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Typy](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed – příkaz](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
