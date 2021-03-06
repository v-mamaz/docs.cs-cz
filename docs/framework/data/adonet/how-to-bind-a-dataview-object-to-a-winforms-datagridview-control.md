---
title: 'Postupy: Připojení objektu DataView do ovládacího prvku Windows Forms DataGridView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: e2e8cad453311035332e5a397667835f047184b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548362"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a>Postupy: Připojení objektu DataView do ovládacího prvku Windows Forms DataGridView
<xref:System.Windows.Forms.DataGridView> Ovládacího prvku poskytuje výkonný a flexibilní způsob, jak zobrazit data ve formátu tabulky. <xref:System.Windows.Forms.DataGridView> Ovládací prvek podporuje standardní Windows Forms datový model vazby, proto vytvoří vazbu <xref:System.Data.DataView> a širokou škálu zdrojů dat. Ve většině případů však můžete vytvoří vazbu <xref:System.Windows.Forms.BindingSource> komponenta, která bude spravovat podrobnosti o práci se zdrojem dat.  
  
 Další informace o <xref:System.Windows.Forms.DataGridView> řídí, najdete v článku [Přehled ovládacího prvku DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a>Pro připojení k zobrazení dat ovládacího prvku DataGridView  
  
1.  Implementujte metodu ke zpracování detaily o načtení dat z databáze. Následující příklad kódu implementuje `GetData` metodu, která inicializuje <xref:System.Data.SqlClient.SqlDataAdapter> komponenty a použije ho k vyplnění <xref:System.Data.DataSet>. Nezapomeňte nastavit `connectionString` proměnných na hodnotu, která je vhodná pro vaši databázi. Budete potřebovat přístup k serveru s ukázkovou databází AdventureWorks SQL Server nainstalovaný.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2.  V <xref:System.Windows.Forms.Form.Load> obslužná rutina události formuláře, vytvořit vazbu <xref:System.Windows.Forms.DataGridView> ovládací prvek <xref:System.Windows.Forms.BindingSource> součást a volání `GetData` metodu pro načtení dat z databáze. <xref:System.Data.DataView> Je vytvořený z [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] dotaz nad kontaktu <xref:System.Data.DataTable> a pak je vázána na <xref:System.Windows.Forms.BindingSource> komponenty.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a>Viz také:
- [Datová vazba a LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
