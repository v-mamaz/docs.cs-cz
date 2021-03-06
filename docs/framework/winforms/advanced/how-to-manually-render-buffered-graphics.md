---
title: 'Postupy: Ruční zobrazení grafiky uložené do vyrovnávací paměti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually rendering graphics
- graphics [Windows Forms], rendering
ms.assetid: 5192295e-bd8e-45f7-8bd6-5c4f6bd21e61
ms.openlocfilehash: f9763620d5fe56a0720d5d5f4ad53ec2ef18531c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705802"
---
# <a name="how-to-manually-render-buffered-graphics"></a>Postupy: Ruční zobrazení grafiky uložené do vyrovnávací paměti
Pokud spravujete ve vyrovnávací paměti grafiky, musíte být schopni vytvořit a vykreslit grafické vyrovnávací paměti. Můžete vytvořit instance <xref:System.Drawing.BufferedGraphics> třídu, která je přidružený k vykreslení plochy na obrazovce voláním <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> metody. Tato metoda vytvoří <xref:System.Drawing.BufferedGraphics> instanci, která souvisí s konkrétním vykreslovací plochu, jako je například formulář nebo ovládací prvek. Po vytvoření <xref:System.Drawing.BufferedGraphics> instance, můžete nakreslit grafiky do vyrovnávací paměti představuje prostřednictvím <xref:System.Drawing.BufferedGraphics.Graphics%2A> vlastnost. Po provedení všech operací grafiky, můžete zkopírovat obsah vyrovnávací paměti na obrazovku voláním <xref:System.Drawing.BufferedGraphics.Render%2A> metody.  
  
> [!NOTE]
>  Pokud provádíte vlastní vykreslování, zvýší využití paměti, ale zvýšení může být pouze mírné.  
  
### <a name="to-manually-display-buffered-graphics"></a>Chcete-li ručně zobrazit ukládány do vyrovnávací paměti grafiky  
  
1.  Získání odkazu na instanci <xref:System.Drawing.BufferedGraphicsContext> třídy. Další informace najdete v tématu [jak: Ruční správa grafiky uložené do vyrovnávací paměti](how-to-manually-manage-buffered-graphics.md).  
  
2.  Vytvoření instance <xref:System.Drawing.BufferedGraphics> třídy voláním <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> způsob, jak je znázorněno v následujícím příkladu kódu.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#21)]  
  
3.  Vykreslení grafiky do vyrovnávací paměti grafiky nastavením <xref:System.Drawing.BufferedGraphics.Graphics%2A> vlastnost. Příklad:  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#22)]  
  
4.  Po dokončení všech operací vykreslování do vyrovnávací paměti grafiky, zavolejte <xref:System.Drawing.BufferedGraphics.Render%2A> metoda k vykreslení vyrovnávací paměti, buď na návrhovém povrchu spojené s vyrovnávací paměti nebo na návrhovém povrchu, jak je znázorněno v následujícím příkladu kódu.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#23)]  
  
5.  Po dokončení vykreslování grafiky volání `Dispose` metodu <xref:System.Drawing.BufferedGraphics> instance uvolnit systémové prostředky.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#24)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#24)]  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphics>
- [Grafiky s dvojitou vyrovnávací pamětí](double-buffered-graphics.md)
- [Postupy: Ruční správa grafiky uložené do vyrovnávací paměti](how-to-manually-manage-buffered-graphics.md)
