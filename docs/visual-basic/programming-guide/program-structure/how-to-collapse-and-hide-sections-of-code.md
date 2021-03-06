---
title: 'Postupy: Sbalení a skrytí sekcí kódu (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: bbce0e4a2427843ed9d9d51b25684db8c54ba69a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980123"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Postupy: Sbalení a skrytí sekcí kódu (Visual Basic)
`#Region` – Direktiva umožňuje sbalit a skrýt části kódu v souborech Visual Basicu. `#Region` Umožňuje určit blok kódu, které můžete rozbalit nebo sbalit při použití editoru kódu sady Visual Studio. Možnost Skrýt kódu selektivně díky soubory spravovatelné a snadněji čitelné. Další informace najdete v tématu [Osnova](/visualstudio/ide/outlining).  
  
 `#Region` direktivy podporují sémantiku bloku kódu, jako je například `#If...#End If`. To znamená, že nemůže začínat v jedné bloku a končit v jiné; spuštění a ukončení musí být ve stejném bloku. `#Region` direktivy nejsou podporovány v rámci funkcí.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Pokud chcete sbalit a skrýt části kódu  
  
-   Umístit části kódu mezi `#Region` a `#End Region` příkazy jako v následujícím příkladu:  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     `#Region` Bloku lze použít více než jednou v souboru kódu; proto uživatelé mohou definovat vlastní bloky postupů a třídy, které můžou zase, sbalit. `#Region` bloky také může být vnořena v jiné `#Region` bloky.  
  
    > [!NOTE]
    >  Skrytí kódu nebrání je kompilovaná a nemá vliv na `#If...#End If` příkazy.  
  
## <a name="see-also"></a>Viz také:
- [Podmíněná kompilace](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Direktiva #Region](../../../visual-basic/language-reference/directives/region-directive.md)
- [Direktivy #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Sbalení](/visualstudio/ide/outlining)
