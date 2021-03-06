---
title: 'Postupy: Vytvoření jednoduše vázaného ovládacího prvku ve formuláři Windows'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: f481b85c07a107b10d88d47c4873b555191bac7f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708337"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>Postupy: Vytvoření jednoduše vázaného ovládacího prvku ve formuláři Windows
S *jednoduchá vazba*, jeden datový prvek, jako je například hodnota sloupce z tabulky datovou sadu, můžete zobrazit v ovládacím prvku. Vám může jednoduché bind nějaká vlastnost ovládacího prvku na hodnotu data.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-simple-bind-a-control"></a>Ovládací prvek jednoduché metody Bind  
  
1.  Připojení ke zdroji dat. Další informace najdete v tématu [připojení ke zdroji dat](../data/adonet/connecting-to-a-data-source.md).  
  
2.  Ve formuláři, vyberte ovládací prvek a zobrazí **vlastnosti** okna.  
  
3.  Rozbalte **(DataBindings)** vlastnost.  
  
     Zobrazí se vlastnosti nejčastěji vázané pod **(DataBindings)** vlastnost. Například ve většině ovládacích prvků **Text** vlastnost nejčastěji vázána.  
  
4.  Pokud vlastnost, kterou chcete bind není jedním z nejčastěji vázané vlastnosti, klikněte na tlačítko **tlačítko se třemi tečkami** tlačítko (![snímek obrazovky VisualStudioEllipsesButton](./media/vbellipsesbutton.png "vbEllipsesButton") ) v **(rozšířené)** pole zobrazíte **formátování a rozšířené vazby** dialogové okno s kompletní seznam vlastností pro ovládací prvek.  
  
5.  Vyberte vlastnost, kterou chcete vytvořit vazbu a klikněte na šipku rozevíracího seznamu v části **vazby**.  
  
     Zobrazí se seznam dostupných datových zdrojů.  
  
6.  Rozbalení zdroje dat, kterou chcete svázat, dokud nenajdete jeden datový element, který chcete. Pokud vytváříte vazbu na hodnotu sloupce v tabulce datové sady, rozbalte název datové sady a potom rozbalte název tabulky, chcete-li zobrazit názvy sloupců.  
  
7.  Klikněte na název elementu k vytvoření vazby.  
  
8.  Pokud jste pracovali **formátování a rozšířené vazby** dialogovém okně klikněte na tlačítko **OK** se vraťte do **vlastnosti** okno.  
  
9. Pokud chcete vytvořit vazbu další vlastnosti ovládacího prvku, opakujte kroky 3 až 7.  
  
    > [!NOTE]
    >  Protože ovládacích prvků vázaných na jednoduchý zobrazit pouze jeden datový prvek, je velmi obvykle obsahují logiku navigace ve formuláři Windows pomocí ovládacích prvků vázaných na jednoduché.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Forms.Binding>
- [Windows Forms – datová vazba](windows-forms-data-binding.md)
- [Datové vazby a Windows Forms](data-binding-and-windows-forms.md)
