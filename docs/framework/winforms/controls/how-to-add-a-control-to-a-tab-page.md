---
title: 'Postupy: Přidání ovládacího prvku do stránky karty'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 6eb509fd10a5000a5423d624cec5b6d126990d73
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723940"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a>Postupy: Přidání ovládacího prvku do stránky karty
Můžete použít Windows Forms <xref:System.Windows.Forms.TabControl> zobrazíte další ovládací prvky uspořádané způsobem. Následující postup ukazuje, jak přidat tlačítko první karta. Informace o přidání ikony na popisek část stránky karty, najdete v části [jak: Změna vzhledu ovládacího prvku Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).  
  
### <a name="to-add-a-control-programmatically"></a>Přidání ovládacího prvku prostřednictvím kódu programu  
  
1.  Použití <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> metoda kolekci vrácené poskytovatelem <xref:System.Windows.Forms.Control.Controls%2A> vlastnost <xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a>Viz také:
- [Ovládací prvek TabControl](tabcontrol-control-windows-forms.md)
- [Přehled ovládacího prvku TabControl](tabcontrol-control-overview-windows-forms.md)
- [Postupy: Změna vzhledu ovládacího prvku Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [Postupy: Zákaz stránek karet](how-to-disable-tab-pages.md)
- [Postupy: Přidání a odebrání karet pomocí ovládacího prvku Windows Forms TabControl](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
