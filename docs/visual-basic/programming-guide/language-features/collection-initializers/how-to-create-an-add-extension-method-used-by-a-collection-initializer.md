---
title: 'Postupy: Vytvoření metody přidání rozšíření používané Inicializátorem kolekce (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 458421da70aca6728f3f03945c28b4c988e44ad7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978537"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Postupy: Vytvoření metody přidání rozšíření používané Inicializátorem kolekce (Visual Basic)
Při vytvoření kolekce pomocí inicializátoru kolekce, hledá kompilátor jazyka Visual Basic `Add` metoda typu kolekce, pro kterou parametry `Add` metoda shodovat s typy hodnot v inicializátoru kolekce. To `Add` metoda se používá k naplnění kolekce s hodnotami z inicializátoru kolekce.  
  
 Pokud neexistuje odpovídající `Add` metoda existuje a nelze upravit kód pro kolekci, můžete přidat rozšiřující metoda volá `Add` , která přebírá parametry, které jsou vyžadované inicializátor kolekce. To je obvykle potřeba udělat, když použijete inicializátory kolekce pro obecné kolekce.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidat do obecné metody rozšíření <xref:System.Collections.Generic.List%601> tak, aby inicializátoru kolekce je možné přidat objekty typu `Employee`. Metody rozšíření umožňuje použít syntaxi inicializátoru kolekce zkrácené.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Viz také:
- [Inicializátory kolekcí](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Postupy: Vytvoření kolekce používané Inicializátorem kolekce](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
