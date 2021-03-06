---
title: 'Postupy: Automatické generování sloupců v ovládacím prvku DataGridView vázaných na Data Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
ms.openlocfilehash: a788504862c61c56ba68c13cc70668200fbb7d18
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703110"
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a>Postupy: Automatické generování sloupců v ovládacím prvku DataGridView vázaných na Data Windows Forms
Následující příklad kódu ukazuje, jak zobrazit sloupce ze zdroje vázaných dat v <xref:System.Windows.Forms.DataGridView> ovládacího prvku. Když <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> hodnota vlastnosti je `true` (výchozí), <xref:System.Windows.Forms.DataGridViewColumn> se vytvoří pro každý sloupec v tabulce zdroje dat.  
  
 Pokud <xref:System.Windows.Forms.DataGridView> ovládací prvek již má sloupce při nastavení <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> vlastnost, je mez existující sloupce jsou ve srovnání s sloupce ve zdroji dat a zachovají pokaždé, když je nalezena shoda. Nevázaných sloupců se vždy zachovají. Svázané sloupce, pro které není nalezena žádná shoda ve zdroji dat, se odeberou. Sloupce ve zdroji dat, pro který není nalezena žádná shoda v ovládacím prvku generovat nový <xref:System.Windows.Forms.DataGridViewColumn> objekty, které jsou přidány na konec objektu <xref:System.Windows.Forms.DataGridView.Columns%2A> kolekce.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   A <xref:System.Windows.Forms.DataGridView> ovládací prvek s názvem `customersDataGridView`.  
  
-   A <xref:System.Data.DataSet> objekt s názvem `customersDataSet` , který obsahuje tabulku s názvem `Customers`.  
  
-   Odkazy <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, a <xref:System.Xml?displayProperty=nameWithType> sestavení.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>
- [Zobrazení dat v ovládacím prvku Windows Forms DataGridView](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Postupy: Odebrání automaticky vygenerovaných sloupců z ovládacího prvku Windows Forms DataGridView](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
