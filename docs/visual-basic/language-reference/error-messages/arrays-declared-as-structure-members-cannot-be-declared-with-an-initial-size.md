---
title: U polí deklarovaných jako členové struktury nelze deklarovat počáteční velikost.
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 06e5e36f3e0522e0449c0ef9698f3a1b01b9cb5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549064"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>U polí deklarovaných jako členové struktury nelze deklarovat počáteční velikost.
Pole ve struktuře je deklarována s počáteční velikostí. Nelze inicializovat libovolný prvek struktury a deklarace velikost pole je jeden forma inicializace.  
  
 **ID chyby:** BC31043  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Definování pole ve struktuře jako dynamický (žádná počáteční velikost).  
  
2.  Pokud potřebujete velikost pole, můžete redimension dynamická pole [ReDim – příkaz](../../../visual-basic/language-reference/statements/redim-statement.md) při spouštění kódu. Toto dokládá následující příklad.  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a>Viz také:
- [Pole](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Postupy: Deklarace struktury](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
