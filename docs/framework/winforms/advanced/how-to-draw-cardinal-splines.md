---
title: 'Postupy: Kreslení základních křivek'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 687143273a07acba4b4d60acb1be25eee165b91d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710482"
---
# <a name="how-to-draw-cardinal-splines"></a>Postupy: Kreslení základních křivek
Křivky mohutnosti je křivku plynule prochází danou sadu body. K nakreslení křivky mohutnosti, vytvořit <xref:System.Drawing.Graphics> objektu a předat adresu pole odkazuje na <xref:System.Drawing.Graphics.DrawCurve%2A> metoda.  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>Kreslení ve tvaru zvonu křivky mohutnosti  
  
-   Následující příklad kreslení ve tvaru zvonu základní křivka vyhlazení, který prochází pět bodů určené. Následující obrázek znázorňuje křivky a pět bodů.  
  
     ![Křivky mohutnosti](./media/cardinalspline1.png "CardinalSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>Kreslení uzavřené křivky mohutnosti  
  
-   Použití <xref:System.Drawing.Graphics.DrawClosedCurve%2A> metodu <xref:System.Drawing.Graphics> třídy kreslení uzavřené křivky mohutnosti. V uzavřené křivky mohutnosti křivka pokračuje přes poslední bod v poli a připojí se s prvním bodem v poli. Následující příklad kreslení uzavřené vyhlazení, který prochází šest určené body. Následující obrázek znázorňuje uzavřené křivky spolu s šest bodů.  
  
 ![Křivky mohutnosti](./media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>Změna ohyb křivky mohutnosti  
  
-   Změnit způsob předáním napětí argument zatáčkách křivky mohutnosti <xref:System.Drawing.Graphics.DrawCurve%2A> metody. Následující příklad kreslení tři křivky mohutnosti, které prochází stejnou sadu body. Následující obrázek znázorňuje tři křivky spolu s příslušnými hodnotami napětí. Všimněte si, že 0 po hodnotu napětí body jsou spojeny čarami přímo.  
  
 ![Křivky mohutnosti](./media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Předchozí příklady jsou určeny k použití pomocí Windows Forms a vyžadují <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.Control.Paint> obslužné rutiny události.  
  
## <a name="see-also"></a>Viz také:
- [Čáry, křivky a obrazce](lines-curves-and-shapes.md)
- [Sestavování a kreslení křivek](constructing-and-drawing-curves.md)
