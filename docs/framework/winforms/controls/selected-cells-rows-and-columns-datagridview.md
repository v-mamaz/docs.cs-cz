---
title: 'Postupy: Získání vybraných buněk, řádků a sloupců v ovládacím prvku Windows Forms DataGridView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: ad6e704b64e3f25f456b98691dfe12c13f8440a2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713295"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a>Postupy: Získání vybraných buněk, řádků a sloupců v ovládacím prvku Windows Forms DataGridView
Můžete získat vybraných buněk, řádků nebo sloupců z <xref:System.Windows.Forms.DataGridView> ovládacího prvku pomocí odpovídajících vlastností: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, a <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. V následujících postupech se získání vybraných buněk a zobrazí jejich řádků a sloupců indexy <xref:System.Windows.Forms.MessageBox>.  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a>K získání vybraných buněk v ovládacím prvku DataGridView  
  
-   Použití <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> vlastnost.  
  
    > [!NOTE]
    >  Použití <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> metody, aby nedocházelo k zobrazení potenciálně velký počet buněk.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a>Chcete-li získat vybraných řádků v ovládacím prvku DataGridView  
  
-   Použití <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> vlastnost. Pokud chcete povolit uživatelům výběr řádků, je nutné nastavit <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> vlastnost <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> nebo <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a>Chcete-li získat z vybraných sloupců v ovládacím prvku DataGridView  
  
-   Použití <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> vlastnost. Pokud chcete povolit uživatelům výběr sloupce, je nutné nastavit <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> vlastnost <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> nebo <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   <xref:System.Windows.Forms.Button> ovládací prvky s názvem `selectedCellsButton`, `selectedRowsButton`, a `selectedColumnsButton`, každý s obslužnými rutinami pro <xref:System.Windows.Forms.Control.Click> připojené události.  
  
-   A <xref:System.Windows.Forms.DataGridView> ovládací prvek s názvem `dataGridView1`.  
  
-   Odkazy <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, a <xref:System.Text?displayProperty=nameWithType> sestavení.  
  
## <a name="robust-programming"></a>Robustní programování  
 Kolekce je popsáno v tomto tématu neprovádějte efektivně vybrání velký počet buněk, řádků nebo sloupců. Další informace o použití těchto kolekcí s velkými objemy dat, naleznete v tématu [osvědčené postupy pro změnu velikosti ovládacího prvku Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [Výběr a používání schránky s ovládacím prvkem Windows Forms DataGridView](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
