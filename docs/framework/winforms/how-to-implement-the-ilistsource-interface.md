---
title: 'Postupy: Implementace rozhraní IListSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], implementing
- IListSource interface
ms.assetid: 63ce27aa-2e23-4fbd-8228-0c1726f6c421
ms.openlocfilehash: ee63d092eb14bd5c8ab928852e02d30e653baf48
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713173"
---
# <a name="how-to-implement-the-ilistsource-interface"></a>Postupy: Implementace rozhraní IListSource
Implementace <xref:System.ComponentModel.IListSource> rozhraní pro vytvoření třídy s možností vazby, který neimplementuje <xref:System.Collections.IList> , ale místo toho poskytuje seznam z jiného umístění.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak implementovat <xref:System.ComponentModel.IListSource> rozhraní. Součást s názvem `EmployeeListSource` zpřístupňuje <xref:System.Collections.IList> pro datovou vazbu implementací <xref:System.ComponentModel.IListSource.GetList%2A> metoda.  
  
 [!code-csharp[System.ComponentModel.IListSource#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/EmployeeListSource.cs#1)]
 [!code-vb[System.ComponentModel.IListSource#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/EmployeeListSource.vb#1)]  
  
 [!code-csharp[System.ComponentModel.IListSource#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/Employee.cs#10)]
 [!code-vb[System.ComponentModel.IListSource#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/Employee.vb#10)]  
  
 [!code-csharp[System.ComponentModel.IListSource#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/BusinessObjectBase.cs#100)]
 [!code-vb[System.ComponentModel.IListSource#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/BusinessObjectBase.vb#100)]  
  
 [!code-csharp[System.ComponentModel.IListSource#1000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IListSource/CS/Form1.cs#1000)]
 [!code-vb[System.ComponentModel.IListSource#1000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IListSource/VB/Form1.vb#1000)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Odkazy na sestavení System.Drawing a System.Windows.Forms.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ComponentModel.IListSource>
- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [Datové vazby a Windows Forms](data-binding-and-windows-forms.md)
