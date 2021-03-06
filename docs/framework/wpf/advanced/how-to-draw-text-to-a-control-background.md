---
title: 'Postupy: Vykreslení textu na pozadí ovládacího prvku'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 025b13d83aeb668fa3a9f8af35d7213ae677eefc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378740"
---
# <a name="how-to-draw-text-to-a-controls-background"></a>Postupy: Vykreslení textu na pozadí ovládacího prvku
Text můžete nakreslit přímo na pozadí ovládacího prvku převedením textový řetězec <xref:System.Windows.Media.FormattedText> objektu a nakreslením objektu na ovládací prvek <xref:System.Windows.Media.DrawingContext>. Tento postup můžete použít také pro kreslení na pozadí objekty odvozené z <xref:System.Windows.Controls.Panel>, jako například <xref:System.Windows.Controls.Canvas> a <xref:System.Windows.Controls.StackPanel>.  
  
 ![Ovládací prvky zobrazení textu jako pozadí](./media/drawtext2background01.png "DrawText2Background01")  
Příklad ovládacích prvků s vlastním textem pozadí  
  
## <a name="example"></a>Příklad  
 Chcete-li vykreslení na pozadí ovládacího prvku, vytvořte nový <xref:System.Windows.Media.DrawingBrush> objektu a nakreslit text převedený na objekt <xref:System.Windows.Media.DrawingContext>. Pak přiřaďte nové <xref:System.Windows.Media.DrawingBrush> na pozadí ovládacího prvku.  
  
 Následující příklad kódu ukazuje, jak vytvořit <xref:System.Windows.Media.FormattedText> objektu a vykreslení na pozadí <xref:System.Windows.Controls.Label> a <xref:System.Windows.Controls.Button> objektu.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Media.FormattedText>
- [Kreslení formátovaného textu](drawing-formatted-text.md)
