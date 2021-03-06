---
title: 'Postupy: Zarovnání vykresleného textu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: ab97ab713067af26455fa4261bbddaf900ec91b8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725256"
---
# <a name="how-to-align-drawn-text"></a>Postupy: Zarovnání vykresleného textu
Při provádění vlastní kreslení, můžete často center vykreslený text na formulář nebo ovládací prvek. Je možné snadno zarovnat text nakreslit <xref:System.Drawing.Graphics.DrawString%2A> nebo <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metody vytvořením správný objekt formátování a nastavení příznaků příslušném formátu.  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>Chcete-li nakreslit na střed textu pomocí GDI + (tkanicí stažení)  
  
1.  Použití <xref:System.Drawing.StringFormat> příslušnou <xref:System.Drawing.Graphics.DrawString%2A> metoda zadat text na střed.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>Chcete-li nakreslit na střed textu pomocí GDI (DrawText)  
  
1.  Použití <xref:System.Windows.Forms.TextFormatFlags> výčtu pro obtékání také vertikální i horizontální zarovnání textu příslušnou <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metody.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 V předchozích příkladech kódu jsou určeny k použití pomocí Windows Forms a vyžadují <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Viz také:
- [Postupy: Kreslení textu pomocí GDI](how-to-draw-text-with-gdi.md)
- [Použití písem a textu](using-fonts-and-text.md)
- [Postupy: Vytváření rodin písem a písem](how-to-construct-font-families-and-fonts.md)
