---
title: 'Postupy: Vytvoření připojení v kódu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 666dbb4e2de0e8a7a83d6e0dfda50822cfdfd860
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371183"
---
# <a name="how-to-create-a-binding-in-code"></a>Postupy: Vytvoření připojení v kódu
Tento příklad ukazuje, jak vytvořit a nastavit <xref:System.Windows.Data.Binding> v kódu.  
  
## <a name="example"></a>Příklad  
 <xref:System.Windows.FrameworkElement> Třídy a <xref:System.Windows.FrameworkContentElement> třídy i vystavit `SetBinding` metoda. Pokud se vazba element, který dědí buď z těchto tříd, můžete volat <xref:System.Windows.FrameworkElement.SetBinding%2A> metoda přímo.  
  
 Následující příklad vytvoří třídu s názvem, `MyData`, který obsahuje vlastnost s názvem `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 Následující příklad ukazuje, jak vytvořit objekt binding nastavit zdroj vazby.  V příkladu se používá <xref:System.Windows.FrameworkElement.SetBinding%2A> vytvořit vazbu <xref:System.Windows.Controls.TextBlock.Text%2A> vlastnost `myText`, což je <xref:System.Windows.Controls.TextBlock> ovládací prvek, na `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Kompletní vzorek kódu, naleznete v tématu [pouze pro kód ukázkové vazby](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).  
  
 Namísto volání metody <xref:System.Windows.FrameworkElement.SetBinding%2A>, můžete použít <xref:System.Windows.Data.BindingOperations.SetBinding%2A> statickou metodu <xref:System.Windows.Data.BindingOperations> třídy. Následující příklad, volání <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> místo <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> svázat `myText` k `myDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>Viz také:
- [Přehled datových vazeb](data-binding-overview.md)
- [Témata s postupy](data-binding-how-to-topics.md)
