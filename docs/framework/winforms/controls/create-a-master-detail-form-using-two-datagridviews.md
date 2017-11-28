---
title: "Postupy: vytvoření hlavního podrobného formuláře pomocí dvou prvkům Windows Forms DataGridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b18e26ff20496248e4525bc31722cf6fcbbc3da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Postupy: Vytvoření hlavního/podrobného formuláře pomocí dvou ovládacích prvků Windows Forms DataGridView
Následující příklad kódu vytvoří hlavního a podrobného formuláře pomocí dvou <xref:System.Windows.Forms.DataGridView> ovládací prvky vázané na dva <xref:System.Windows.Forms.BindingSource> součásti. Zdroj dat je <xref:System.Data.DataSet> obsahující `Customers` a `Orders` tabulky z ukázkové databáze Northwind SQL Server spolu s <xref:System.Data.DataRelation> dva prostřednictvím vztahující se `CustomerID` sloupce.  
  
 Jeden <xref:System.Windows.Forms.BindingSource> je vázán k nadřazené `Customers` tabulky v datové sadě. Tato data se zobrazí v hlavní <xref:System.Windows.Forms.DataGridView> ovládacího prvku. Druhá <xref:System.Windows.Forms.BindingSource> je vázána na první konektor data. <xref:System.Windows.Forms.BindingSource.DataMember%2A> Vlastnost druhý <xref:System.Windows.Forms.BindingSource> je nastaven na <xref:System.Data.DataRelation> název. To způsobí, že přidružené podrobností <xref:System.Windows.Forms.DataGridView> zobrazte řádky podřízeného ovládacího prvku `Orders` tabulku, která odpovídají na aktuálním řádku v hlavní <xref:System.Windows.Forms.DataGridView> ovládacího prvku.  
  
 Úplné vysvětlení tento příklad kódu, najdete v části [návod: vytváření hlavního a podrobného formuláře pomocí dvou prvkům Windows Forms DataGridView](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="example"></a>Příklad  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
 Odkazy na systém, System.Data, System.Windows.Forms a System.XML sestavení.  
  
 Informace o sestavení z příkazového řádku pro tento příklad [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] nebo [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], najdete v části [sestavení z příkazového řádku](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) nebo [vytváření pomocí příkazového řádku csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). V tomto příkladu můžete také vytvořit [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] zadáním nebo vložením kódu do nového projektu.  Viz také [postupy: zkompilování a spuštění dokončení Windows Forms kód příklad pomocí sady Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))  
  
## <a name="net-framework-security"></a>Zabezpečení rozhraní .NET Framework  
 Ukládání citlivé informace, jako jsou hesla, v připojovacím řetězci může ovlivnit zabezpečení vaší aplikace. Bezpečnější způsob, jak řídit přístup k databázi, je ověřování systému Windows (označované také jako integrované zabezpečení). Další informace najdete v tématu [chrání informace o připojení](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Návod: Vytvoření hlavního a podrobného formuláře pomocí dvou prvkům Windows Forms DataGridView](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md)  
 [Zobrazení dat v ovládacím prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Ochrana informací o připojení](../../../../docs/framework/data/adonet/protecting-connection-information.md)