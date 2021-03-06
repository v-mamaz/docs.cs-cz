---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: e1a6cecdf724603b8f4617fe4e8b5ef2c0acdeff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624558"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Určuje, že nejméně jedna deklarovaná členská proměnná odkazuje na instanci třídy, která může vyvolat události.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je proměnná definována pomocí `WithEvents`, pomocí deklarace můžete určit, že metoda zpracovává události proměnné pomocí `Handles` – klíčové slovo.  
  
 Můžete použít `WithEvents` pouze na úrovni třídy nebo modulu. To znamená, že deklarace kontext `WithEvents` proměnná musí být třídu nebo modul a nemůže být zdrojový soubor, obor názvů, struktury nebo proceduru.  
  
 Nemůžete použít `WithEvents` na člena struktury.  
  
 Můžete deklarovat pouze proměnné, jednotlivým – není pole – s `WithEvents`.  
  
## <a name="rules"></a>pravidla  
  
-   **Typy elementů.** Je třeba deklarovat `WithEvents` proměnné na proměnné objektu tak, aby může přijmout třídu instance. Však nelze deklarovat jako `Object`. Je třeba je deklarovat jako konkrétní třídy, která může vyvolat události.  
  
 `WithEvents` Modifikátor lze použít v tomto kontextu: [Příkaz Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Viz také:
- [Obslužné rutiny](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Klíčová slova](../../../visual-basic/language-reference/keywords/index.md)
- [Události](../../../visual-basic/programming-guide/language-features/events/index.md)
