---
title: 'Postupy: Nastavení zarážek v kresleném textu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 2b3d019db1fd3e9eeb9def1c18b54d293e5faca9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722422"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Postupy: Nastavení zarážek v kresleném textu
Tabulátoru pro text můžete nastavit pomocí volání <xref:System.Drawing.StringFormat.SetTabStops%2A> metodu <xref:System.Drawing.StringFormat> objektu a následné předání, který <xref:System.Drawing.StringFormat> objektu <xref:System.Drawing.Graphics.DrawString%2A> metodu <xref:System.Drawing.Graphics> třídy.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> Fakturuje se nepodporuje přidání zarážky kresleném textu, i když rozšiřujete existující kartu přestane používat <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> příznak.  
  
## <a name="example"></a>Příklad  
 Následující příklad nastaví zarážek na 150, 250 a 350. Potom kód zobrazí seznam s kartami názvy a skóre v testech.  
  
 Následující obrázek znázorňuje s kartami text.  
  
 ![Písma textu](./media/fontstext4.png "fontstext4")  
  
 Následující kód předá dva argumenty <xref:System.Drawing.StringFormat.SetTabStops%2A> metody. Druhý argument je pole, která obsahuje kartu posunů. První argument předaný metodě <xref:System.Drawing.StringFormat.SetTabStops%2A> je 0, což znamená, že první posunutí v poli se měří z pozice 0, je levý okraj ohraničující obdélník.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
  
-   V předchozím příkladu je určený k použití pomocí Windows Forms a vyžaduje <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Viz také:
- [Použití písem a textu](using-fonts-and-text.md)
- [Postupy: Kreslení textu pomocí GDI](how-to-draw-text-with-gdi.md)
