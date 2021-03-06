---
title: '##Const – direktiva (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: fb937a5a9d4688730085829350cb20172db50e97
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967045"
---
# <a name="const-directive"></a>#Const – direktiva
Definuje podmíněné konstanty kompilátoru v jazyce Visual Basic.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>Součásti  
 `constname`  
 Povinný parametr. Název je definována konstanta.  
  
 `expression`  
 Povinný parametr. Literál, jiné Konstanta podmíněné kompilátoru nebo libovolnou kombinaci, která zahrnuje některé nebo všechny aritmetické nebo logické operátory s výjimkou `Is`.  
  
## <a name="remarks"></a>Poznámky  
 Podmíněné konstanty kompilátoru jsou vždycky soukromé vzhledem k souboru, ve kterém jsou zobrazeny. Nelze vytvořit konstantu kompilátoru veřejné pomocí `#Const` direktiv; můžete je vytvořit pouze v uživatelském rozhraní nebo se `/define` – možnost kompilátoru.  
  
 Můžete použít jenom podmíněné konstanty kompilátoru a literály v `expression`. Pomocí standardní konstanta definovaná s `Const` způsobí chybu. Naopak, můžete použít konstanty definované pomocí `#Const` – klíčové slovo pouze pro podmíněnou kompilaci. Konstanty lze také také definovat, v takovém případě mají hodnotu `Nothing`.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu `#Const` směrnice.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Viz také:
- [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Direktivy #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Příkaz Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Podmíněná kompilace](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Příkaz If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
