---
title: 'Postupy: Přidružit prvku ContextMenuStrip k ovládacímu prvku'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: 4b61da8dc9f36e0a80807547e2049ef512c94747
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718330"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a>Postupy: Přidružit prvku ContextMenuStrip k ovládacímu prvku
Po vytvoření ovládacích prvků a nabídkách, následujícím postupem zobrazíte danou nabídku, když uživatel klepne pravým tlačítkem myši ovládací prvek. Tyto postupy přidružit <xref:System.Windows.Forms.ContextMenuStrip> s formuláři Windows a <xref:System.Windows.Forms.ToolStrip> ovládacího prvku.  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a>Přidružení prvku ContextMenuStrip k formuláři Windows  
  
1.  Nastavte <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> nastavte název přidruženého <xref:System.Windows.Forms.ContextMenuStrip>.  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a>Chcete-li přidružení prvku ContextMenuStrip k ovládacímu prvku ToolStrip  
  
1.  Nastavit u tohoto prvku <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> nastavte název přidruženého <xref:System.Windows.Forms.ContextMenuStrip>.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu vytvoří formulář Windows a <xref:System.Windows.Forms.ToolStrip>a přiřadí jinou <xref:System.Windows.Forms.ContextMenuStrip> ovládací prvek s každou z nich.  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Odkazy na sestavení systému, System.Data, System.Drawing a System.Windows.Forms.  
  
 Informace o vytváření tento příklad z příkazového řádku pro Visual Basic nebo Visual C# najdete v tématu [sestavení z příkazového řádku](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) nebo [sestavení pomocí příkazového řádku csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Tento příklad v sadě Visual Studio můžete také vytvořit vložením kódu do nového projektu.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [Postupy: Přidání položek nabídky do ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md)
- [Ovládací prvek ContextMenuStrip](contextmenustrip-control.md)
