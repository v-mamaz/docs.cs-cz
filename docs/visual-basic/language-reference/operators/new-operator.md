---
title: New – operátor (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: dda23ef3ff49bd32474f39f5ae1807e57bdc2a62
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980461"
---
# <a name="new-operator-visual-basic"></a>New – operátor (Visual Basic)
Zavádí `New` klauzule, která vytvoří novou instanci objektu, určuje omezení konstruktoru u parametru typu nebo identifikuje `Sub` postupu jako konstruktor třídy.  
  
## <a name="remarks"></a>Poznámky  
 V deklaraci nebo příkazu přiřazení `New` klauzuli musí být zadána s definicí třídy, ze kterého lze vytvořit instance. To znamená, že třída musí vystavit jeden nebo více konstruktorů, které volající kód může přistupovat.  
  
 Můžete použít `New` klauzuli v příkazu deklarace nebo příkazu přiřazení. Když příkaz spustíte, zavolá odpovídající konstruktor zadané třídy, prochází žádné argumenty, které jste zadali. Následující příklad ukazuje to ve vytváření instancí `Customer` třídu, která má dva konstruktory, která nepřijímá žádné parametry a ten, který se použije parametr řetězce.  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 Protože pole jsou třídy, `New` můžete vytvořit novou instanci pole, jak je znázorněno v následujícím příkladu.  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 Vyvolá common language runtime (CLR) <xref:System.OutOfMemoryException> chyby, pokud není dostatek paměti k vytvoření nové instance.  
  
> [!NOTE]
>  `New` – Klíčové slovo se také používá v seznamech parametrů typu k určení, že zadaný typ musí vystavit dostupný konstruktor bez parametrů. Další informace o parametry typu a omezení, najdete v části [seznam typů](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Chcete-li vytvořit proceduru konstruktor pro třídu, nastavte název `Sub` postup `New` – klíčové slovo. Další informace najdete v tématu [doba života objektu: Způsob vytváření a zničení objektů](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 `New` – Klíčové slovo lze použít v těchto kontextech:  
  
 [Příkaz Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [z](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Příkaz Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Viz také:
- <xref:System.OutOfMemoryException>
- [Klíčová slova](../../../visual-basic/language-reference/keywords/index.md)
- [Seznam typů](../../../visual-basic/language-reference/statements/type-list.md)
- [Obecné typy v jazyce Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Doba života objektu: Způsob vytváření a zničení objektů](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
