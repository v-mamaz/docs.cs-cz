---
title: 'Postupy: Kombinování delegátů (vícesměroví delegáti)- C# Průvodce programováním'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 426b9f91d3e3328522ec5c7ab043d5074ececc43
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970104"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a>Postupy: Kombinování delegátů (vícesměroví delegáti) (C# Průvodce programováním v)
Tento příklad ukazuje, jak vytvořit vícesměroví delegáti. Užitečné vlastnost [delegovat](../../../csharp/language-reference/keywords/delegate.md) objekty je, že více objektů lze přiřadit instanci jednoho delegáta pomocí `+` operátor. Vícesměrového vysílání delegát obsahuje seznam přiřazenou delegáti. Při volání vícesměrového vysílání delegáta vyvolá Delegáti v seznamu, v pořadí. Můžete kombinovat pouze delegáti stejného typu.  
  
 `-` Operátor slouží k odebrání delegáta součásti vícesměrového vysílání delegáta.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a>Viz také:

- <xref:System.MulticastDelegate>
- [Průvodce programováním v jazyce C#](../../../csharp/programming-guide/index.md)
- [Události](../../../csharp/programming-guide/events/index.md)
