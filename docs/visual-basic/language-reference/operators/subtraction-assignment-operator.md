---
title: -= – operátor (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: c3495c4e45fe5e1d497578ee3ee6afe874e90eed
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203042"
---
# <a name="--operator-visual-basic"></a>-= – operátor (Visual Basic)
Odečte hodnotu výrazu od hodnoty proměnnou nebo vlastnost a výsledek přiřadí proměnné nebo vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a>Součásti  
 `variableorproperty`  
 Povinný parametr. Všechny číselné proměnné nebo vlastnosti.  
  
 `expression`  
 Povinný parametr. Jakýkoli číselný výraz.  
  
## <a name="remarks"></a>Poznámky  
 Element na levé straně `-=` operátor může být jednoduché skalární proměnná, vlastnost nebo prvek pole. Proměnná nebo vlastnost nemůže být [jen pro čtení](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `-=` Operátor nejprve odečte hodnotu výrazu (na pravé straně operátoru) hodnotu proměnné nebo vlastnosti (na levé straně operátoru). Operátor, který se pak přiřadí výsledek této operace na proměnnou nebo vlastnost.  
  
## <a name="overloading"></a>Přetížení  
 [-– Operátor (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) může být *přetížené*, což znamená, že třídy nebo struktury lze znovu definovat jeho chování při operand má typ této třídě nebo struktuře. Přetížení `-` operátor má vliv na chování `-=` operátor. Pokud váš kód používá `-=` v třídě nebo struktuře, která přetížení `-`, je nutné pochopit jeho Předefinovaná chování. Další informace najdete v tématu [procedury operátoru](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `-=` operátor odečíst jeden `Integer` proměnné z jiného a přiřadit výsledek, který má tato proměnná.  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Viz také:
- [-– Operátor (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [Operátory přiřazení](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Aritmetické operátory](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Priorita operátorů v jazyce Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operátory uvedené podle funkce](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Příkazy](../../../visual-basic/programming-guide/language-features/statements.md)
