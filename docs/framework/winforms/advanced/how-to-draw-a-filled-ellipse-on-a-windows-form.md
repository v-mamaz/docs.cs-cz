---
title: 'Postupy: Kreslení plné elipsy ve formuláři Windows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
ms.openlocfilehash: 42316cd0d55b5154b21b4462157e044b30674ebd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716277"
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a>Postupy: Kreslení plné elipsy ve formuláři Windows
V tomto příkladu kreslení plné elipsy ve formuláři.  
  
## <a name="example"></a>Příklad  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tuto metodu nelze volat <xref:System.Windows.Forms.Form.Load> obslužné rutiny události. Vykreslený obsah aktivním, pokud je velikost nebo zakryto jiný formulář. formuláře. Chcete-li obsah automaticky repaint, by měly přepsat <xref:System.Windows.Forms.Control.OnPaint%2A> metody.  
  
## <a name="robust-programming"></a>Robustní programování  
 Vždy byste měli zavolat <xref:System.IDisposable.Dispose%2A> na všechny objekty, které využívají systémové prostředky, jako například <xref:System.Drawing.Brush> a <xref:System.Drawing.Graphics> objekty.  
  
## <a name="see-also"></a>Viz také:
- [Grafika a kreslení v modelu Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Začínáme s programováním grafiky](getting-started-with-graphics-programming.md)
- [Alfa míchání čar a výplní](alpha-blending-lines-and-fills.md)
- [Použití štětce k vyplnění obrazců](using-a-brush-to-fill-shapes.md)
