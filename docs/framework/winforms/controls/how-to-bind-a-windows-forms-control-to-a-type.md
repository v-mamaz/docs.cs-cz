---
title: 'Postupy: Vytvoření vazby ovládacího prvku Windows Forms k typu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
ms.openlocfilehash: 8d6522f12944e2f1571fa6cbf0773991c54965c4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724905"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a>Postupy: Vytvoření vazby ovládacího prvku Windows Forms k typu
Při vytváření ovládacích prvků, které pracují s daty, někdy najdete je nezbytné pro vytvoření vazby ovládacího prvku do typu, nikoli objekt. K této situaci dochází především v době návrhu, když dat nemusí být k dispozici, ale své ovládací prvky vázané na data potřebují k zobrazení informací z veřejného rozhraní typu. Například může vytvořit vazbu <xref:System.Windows.Forms.DataGridView> ovládací prvek na objekt zveřejněné jako webová služba a chcete <xref:System.Windows.Forms.DataGridView> ovládací prvek popisek její sloupce v době návrhu s členem názvů vlastního typu.  
  
 Můžete snadno vytvoření vazby ovládacího prvku na typ s <xref:System.Windows.Forms.BindingSource> komponenty.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak vytvořit vazbu <xref:System.Windows.Forms.DataGridView> ovládacího prvku pomocí vlastního typu <xref:System.Windows.Forms.BindingSource> komponenty. Při spuštění v příkladu, můžete si všimnout <xref:System.Windows.Forms.DataGridView> je označené jako sloupce, které odpovídají vlastnosti `Customer` objektu před ovládací prvek naplněný daty. V příkladu má tlačítko Přidat zákazníka k přidání dat <xref:System.Windows.Forms.DataGridView> ovládacího prvku. Když kliknete na tlačítko Nový `Customer` přidán <xref:System.Windows.Forms.BindingSource>. Ve skutečném scénáři může být volání webové služby nebo jiného zdroje dat získat data.  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Odkazy na sestavení systému a System.Windows.Forms.  
  
 Informace o vytváření tento příklad z příkazového řádku pro Visual Basic nebo Visual C# najdete v tématu [sestavení z příkazového řádku](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) nebo [sestavení pomocí příkazového řádku csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Tento příklad v sadě Visual Studio můžete také vytvořit vložením kódu do nového projektu.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Komponenta BindingSource](bindingsource-component.md)
