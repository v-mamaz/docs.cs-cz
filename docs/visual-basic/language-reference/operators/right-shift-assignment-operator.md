---
title: '>>= – operátor (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: 0ae4eb16727b2b297088170ada04cfd07d6c7a0a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980110"
---
# <a name="-operator-visual-basic"></a>>>= – operátor (Visual Basic)
Provede aritmetický posunutí doprava na základě hodnoty proměnnou nebo vlastnost a přiřadí výsledek zpět na proměnnou nebo vlastnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Součásti  
 `variableorproperty`  
 Povinný parametr. Proměnná nebo vlastnost celočíselného typu (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, nebo `ULong`).  
  
 `amount`  
 Povinný parametr. Číselný výraz datový typ, který rozšiřuje na `Integer`.  
  
## <a name="remarks"></a>Poznámky  
 Element na levé straně `>>=` operátor může být jednoduché skalární proměnná, vlastnost nebo prvek pole. Proměnná nebo vlastnost nemůže být [jen pro čtení](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `>>=` Operátor nejprve provádí aritmetické posunutí doprava na hodnotě proměnné nebo vlastnosti. Operátor, který se pak přiřadí výsledek této operace zpět na proměnnou nebo vlastnost.  
  
 Aritmetické staffhubu nejsou cyklické, což znamená, že nejsou na druhém konci znovuzavedeno bity posunuly jeden konec výsledek. V aritmetické posunutí doprava bity posunuta nad rámec úplně vpravo bitová pozice se zahodí a bit nejvíce vlevo je postoupena do bitové pozice uvolněné na levé straně. To znamená, že pokud `variableorproperty` má zápornou hodnotu uvolněných pozic jsou nastavené na jednu. Pokud `variableorproperty` kladné, nebo pokud je jeho datový typ je typ bez znaménka, uvolněných pozic nastaveny na hodnotu nula.  
  
## <a name="overloading"></a>Přetížení  
 [>> Operátor](../../../visual-basic/language-reference/operators/right-shift-operator.md) může být *přetížené*, což znamená, že třídy nebo struktury lze znovu definovat jeho chování při operand má typ této třídě nebo struktuře. Přetížení `>>` operátor má vliv na chování `>>=` operátor. Pokud váš kód používá `>>=` v třídě nebo struktuře, která přetížení `>>`, je nutné pochopit jeho Předefinovaná chování. Další informace najdete v tématu [procedury operátoru](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `>>=` operátor shift bitový vzor z `Integer` proměnnou přímo na určenou dobu a přiřadit výsledek do proměnné.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Viz také:
- [>> – operátor](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [Operátory přiřazení](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operátory bitového posunu](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Priorita operátorů v jazyce Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operátory uvedené podle funkce](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Příkazy](../../../visual-basic/programming-guide/language-features/statements.md)
