---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: edee47e41ca78175a6fb24ed5eac255c03de0901
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972558"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Určuje, že argument se předává takovým způsobem, že volaná procedura nebo vlastnost nelze změnit hodnotu proměnné základní argumentu ve volajícím kódu.  
  
## <a name="remarks"></a>Poznámky  
 `ByVal` Modifikátor lze použít v těchto kontextech:  
  
 [Příkaz Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Příkaz Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Příkaz Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Příkaz Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Příkaz Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `ByVal` předávání mechanismus s argumentem reference typu parametru. V tomto příkladu je argument `c1`, instance třídy `Class1`. `ByVal` zabrání změně podkladovou hodnotu argument odkazu kód v postupech `c1`, ale nechrání dostupná pole a vlastnosti `c1`.  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a>Viz také:
- [Klíčová slova](../../../visual-basic/language-reference/keywords/index.md)
- [Předávání argumentů podle hodnoty a reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
