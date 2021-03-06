---
title: 'Postupy: Translate Image Colors'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 81aecddb28903649ff2d59e80fc90368df5e2db4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703020"
---
# <a name="how-to-translate-image-colors"></a>Postupy: Translate Image Colors
Překlad přidá hodnotu na jeden nebo více součástí čtyři barvy. Matice položek barev, které představují překlady jsou uvedeny v následující tabulce.  
  
|Součást, kterou přeložit|Přehled vstupu|  
|--------------------------------|------------------|  
|Červená|[4][0]|  
|Zelená|[4][1]|  
|Modrá|[4][2]|  
|Alpha|[4][3]|  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří <xref:System.Drawing.Image> objekt ze souboru ColorBars.bmp. Potom kód přidá 0,75 červené každý pixel na obrázku. Původní bitové kopie nakreslen spolu s transformovaný bitové kopie.  
  
 Následující obrázek znázorňuje původní obrázek na levé straně a transformovaná image na pravé straně.  
  
 ![Translate Colors](./media/colortrans2.png "colortrans2")  
  
 Následující tabulka uvádí vektory barvu pro čtyři pruhy před a po červenou překladu. Mějte na paměti, protože maximální hodnota složky barvy je 1, červené ve druhém řádku nezmění. (Podobně, minimální hodnota složky barvy je 0.)  
  
|Původní|Přeložit|  
|--------------|----------------|  
|Černé (0, 0, 0, 1)|(0.75, 0, 0, 1)|  
|Červená (1, 0, 0, 1)|(1, 0, 0, 1)|  
|Zelená (0, 1, 0, 1)|(0.75, 1, 0, 1)|  
|Modré (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 V předchozím příkladu je určený k použití pomocí Windows Forms a vyžaduje <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.Control.Paint> obslužné rutiny události. Nahraďte `ColorBars.bmp` název souboru bitové kopie a cestu, která jsou platné ve vašem systému.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafika a kreslení v modelu Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Přebarvení obrázků](recoloring-images.md)
