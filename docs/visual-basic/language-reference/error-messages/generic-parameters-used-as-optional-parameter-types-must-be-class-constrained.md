---
title: Obecné parametry použité jako typy volitelného parametru musí mít omezení třídy.
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 7a1411daf446cbf06cd57b4e002c2c3cd77166af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507158"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>Obecné parametry použité jako typy volitelného parametru musí mít omezení třídy.
Postup je deklarován s volitelným parametrem, který používá parametr typu, který není omezen na typ odkazu.  
  
 Vždy je nutné zadat výchozí hodnotu pro každý volitelný parametr. Pokud je parametr typu odkazu, musí být Volitelná hodnota `Nothing`, což je platná hodnota pro jakéhokoliv odkazového typu. Ale pokud je parametr typu hodnoty, tento typ musí být typu základní datové předdefinovaná v nástroji Visual Basic. Je to proto složený typ hodnoty, jako je například struktura definovaný uživatelem, nemá platnou výchozí hodnotu.  
  
 Pokud použijete parametr typu pro volitelný parametr, musíte zaručeno, že se typu odkazu, abyste předešli typu hodnoty žádný platný výchozí hodnotu. To znamená, že musí omezení parametru typu, buď pomocí `Class` – klíčové slovo nebo s názvem určité třídy.  
  
 **ID chyby:** BC32124  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Omezení parametru typu tak, aby přijímal pouze typem odkazu, nebo nepoužívejte ho pro volitelný parametr.  
  
## <a name="see-also"></a>Viz také:
- [Obecné typy v jazyce Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Seznam typů](../../../visual-basic/language-reference/statements/type-list.md)
- [Příkaz Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Nepovinné parametry](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Struktury](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
