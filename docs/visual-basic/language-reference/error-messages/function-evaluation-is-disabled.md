---
title: Vyhodnocení funkce je zakázáno, protože při vyhodnocování předchozí verze vypršel časový limit.
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 6c3b0d3b86e871228c4bf3b30f0871015641a730
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718270"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Vyhodnocení funkce je zakázáno, protože při vyhodnocování předchozí verze vypršel časový limit.
Vyhodnocení funkce je zakázaná, protože předchozímu vyhodnocení funkce vypršel. Chcete-li znovu povolit vyhodnocení funkce, proveďte krok znovu nebo restartujte ladění.  
  
 Výraz v ladicím programu sady Visual Studio určuje volání procedury, ale vypršel limit jiného vyhodnocení.  
  
 Možné příčiny vypršení časového limitu volání procedury patří nekonečná smyčka nebo *vznik nekonečné smyčky*. Další informace najdete v tématu [pro... Další příkaz](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Zvláštním případem nekonečné smyčky je *rekurze*. Další informace najdete v tématu [rekurzivní procedury](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **ID chyby:** BC30957  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Je-li to možné, určete, o jaké dřívější vyhodnocení funkce se jedná a co způsobilo vypršení jejího časového limitu. Jinak může k této chybě dojít znovu.  
  
2.  Proveďte krok ladicího programu znovu nebo ladění ukončete a znovu spusťte.  
  
## <a name="see-also"></a>Viz také:
- [Ladění v sadě Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Procházení kódu s ladicím programem](/visualstudio/debugger/navigating-through-code-with-the-debugger)
