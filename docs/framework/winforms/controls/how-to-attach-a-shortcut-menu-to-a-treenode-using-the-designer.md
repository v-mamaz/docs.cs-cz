---
title: 'Postupy: Připojení místní nabídky k TreeNode pomocí návrháře'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: aa161af65b7e8e1f3636398cd02139b5623eb154
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721980"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Postupy: Připojení místní nabídky k TreeNode pomocí návrháře
Windows Forms <xref:System.Windows.Forms.TreeView> ovládací prvek zobrazuje hierarchii uzlů, podobně jako u souborů a složek, na které se zobrazí v levém podokně funkci Windows Explorer v operačních systémech Windows. Tím, že nastavíte <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> vlastností, můžete zadat kontextové operace uživateli při jejich pravým tlačítkem myši <xref:System.Windows.Forms.TreeView> ovládacího prvku. Tím, že přidružíte <xref:System.Windows.Forms.ContextMenuStrip> komponenty u jednotlivých <xref:System.Windows.Forms.TreeNode> položky, můžete přidat vlastní úroveň funkce místní nabídku pro váš <xref:System.Windows.Forms.TreeView> ovládacích prvků.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>Přidružení místní nabídky k TreeNode v době návrhu  
  
1.  Přidat <xref:System.Windows.Forms.TreeView> do svého formuláře ovládací prvek a potom přidat uzly do <xref:System.Windows.Forms.TreeView> podle potřeby. Další informace najdete v tématu [jak: Přidávání a odebírání uzlů s Windows Forms TreeView – ovládací prvek](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).  
  
2.  Přidat <xref:System.Windows.Forms.ContextMenuStrip> komponentu do formuláře a pak přidejte položky nabídky do místní nabídky, která představují úrovni uzlu operace, které chcete zpřístupnit v době běhu. Další informace najdete v tématu [jak: Přidání položek nabídky do ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).  
  
3.  Znovu otevřít **TreeNodeEditor** dialogové okno pro <xref:System.Windows.Forms.TreeView> ovládací prvek, vyberte uzel, který má upravit a nastavte jeho <xref:System.Windows.Forms.ContextMenuStrip> vlastnost do místní nabídky, kterou jste přidali.  
  
4.  Pokud je tato vlastnost nastavena, zobrazí se při klepnutí pravým tlačítkem myši na uzel v místní nabídce.  
  
     Kromě toho můžete napsat kód pro zpracování <xref:System.Windows.Forms.ToolStripItem.Click> události pro tyto položky nabídky.  
  
## <a name="see-also"></a>Viz také:
- [Ovládací prvek TreeView](treeview-control-windows-forms.md)
- [Přehled ovládacího prvku TreeView](treeview-control-overview-windows-forms.md)
- [Ovládací prvek ContextMenuStrip](contextmenustrip-control.md)
