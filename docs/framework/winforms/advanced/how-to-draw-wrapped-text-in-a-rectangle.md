---
title: 'Postupy: Kreslení zalomeného textu do obdélníku'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: 5c4e76cda37527d0167b21c0d206749ba6dab4a9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708857"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>Postupy: Kreslení zalomeného textu do obdélníku
Můžete nakreslit zalamování textu do obdélníku pomocí <xref:System.Drawing.Graphics.DrawString%2A> přetížené metody <xref:System.Drawing.Graphics> třídu, která přijímá <xref:System.Drawing.Rectangle> nebo <xref:System.Drawing.RectangleF> parametru. Budete taky používat <xref:System.Drawing.Brush> a <xref:System.Drawing.Font>.  
  
 Můžete také nakreslit zalamování textu do obdélníku pomocí <xref:System.Windows.Forms.TextRenderer.DrawText%2A> přetížené metody <xref:System.Windows.Forms.TextRenderer> , která přijímá <xref:System.Drawing.Rectangle> a <xref:System.Windows.Forms.TextFormatFlags> parametru. Budete taky používat <xref:System.Drawing.Color> a <xref:System.Drawing.Font>.  
  
 Následující obrázek znázorňuje výstup textu vykreslen v obdélníku použijete <xref:System.Drawing.Graphics.DrawString%2A> metody.  
  
 ![Písma textu](./media/csfontstext2.png "csfontstext2")  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Kreslení zalomeného textu do obdélníku pomocí GDI +  
  
1.  Použití <xref:System.Drawing.Graphics.DrawString%2A> přetížené metody předáním text, který má <xref:System.Drawing.Rectangle> nebo <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> a <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Kreslení zalomeného textu do obdélníku pomocí GDI  
  
1.  Použití <xref:System.Windows.Forms.TextFormatFlags> hodnotu výčtu text by měl být uzavřen s <xref:System.Windows.Forms.TextRenderer.DrawText%2A> přetížené metody předáním text, který má <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> a <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Vyžadovat v předchozích příkladech:  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Viz také:
- [Postupy: Kreslení textu pomocí GDI](how-to-draw-text-with-gdi.md)
- [Použití písem a textu](using-fonts-and-text.md)
- [Postupy: Vytváření rodin písem a písem](how-to-construct-font-families-and-fonts.md)
- [Postupy: Kreslení textu v určeném umístění](how-to-draw-text-at-a-specified-location.md)
