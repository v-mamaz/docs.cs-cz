---
title: 'Postupy: Nastavení sloupců jen pro čtení v ovládacím prvku Windows Forms DataGridView pomocí návrháře'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 0219f0cf50d9cce630dc44a37dd3c16d26874012
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718555"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Postupy: Nastavení sloupců jen pro čtení v ovládacím prvku Windows Forms DataGridView pomocí návrháře
Ve výchozím nastavení, mohou uživatelé upravovat textu a číselných dat zobrazovat ve formuláři Windows <xref:System.Windows.Forms.DataGridView> ovládacího prvku. Pokud chcete zobrazit data, která není určená pro úpravy, musíte udělat sloupce, které obsahují data jen pro čtení. Informace o tom, jak nastavit ovládací prvek zcela jen pro čtení najdete v tématu [jak: Zamezení přidávání řádků a odstranění v Windows Forms DataGridView pomocí návrháře](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).  
  
 Následující postup vyžaduje, **aplikace Windows** projektu s formulář obsahující <xref:System.Windows.Forms.DataGridView> ovládacího prvku. Informace o nastavení takový projekt, naleznete v tématu [jak: Vytvoření projektu aplikace Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) a [jak: Přidání ovládacích prvků Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-make-a-column-read-only-by-using-the-designer"></a>Chcete-li sloupec jen pro čtení pomocí návrháře  
  
1.  Klikněte na inteligentní označit piktogram (![piktogram inteligentní](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) v pravém horním rohu <xref:System.Windows.Forms.DataGridView> ovládací prvek a potom vyberte **upravit sloupce**.  
  
2.  Vyberte sloupec **vybrané sloupce** seznamu.  
  
3.  V **vlastnosti sloupce** mřížky, nastavte <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> vlastnost `true`.  
  
    > [!NOTE]
    >  Můžete provést také sloupec jen pro čtení při přidání tak, že vyberete **jen pro čtení** zaškrtávací políčko **přidat sloupec** dialogové okno.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Postupy: Přidávání a odebírání sloupců v ovládacím prvku Windows Forms DataGridView pomocí návrháře](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Postupy: Zabránit řádku přidání a odstranění v ovládacím prvku Windows Forms DataGridView pomocí návrháře](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [Postupy: Vytvoření projektu aplikace Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Postupy: Přidání ovládacích prvků do formulářů Windows](how-to-add-controls-to-windows-forms.md)
