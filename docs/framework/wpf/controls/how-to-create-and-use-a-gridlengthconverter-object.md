---
title: 'Postupy: Vytvoření a použití objektu GridLengthConverter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 0455d91eff820e5c087af20207ece1313f6f3a39
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352253"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a>Postupy: Vytvoření a použití objektu GridLengthConverter
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak vytvořit a použít instanci <xref:System.Windows.GridLengthConverter>. Příklad definuje vlastní metodu s názvem `changeCol`, která předá <xref:System.Windows.Controls.ListBoxItem> k <xref:System.Windows.GridLengthConverter> , která převede <xref:System.Windows.Controls.ContentControl.Content%2A> z <xref:System.Windows.Controls.ListBoxItem> do instance <xref:System.Windows.GridLength>. Převedená hodnota je pak předán zpět jako hodnotu <xref:System.Windows.Controls.ColumnDefinition.Width%2A> vlastnost <xref:System.Windows.Controls.ColumnDefinition> elementu.  
  
 Příklad také definuje druhá vlastní metoda volána `changeColVal`. Tato vlastní metoda převede <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> z <xref:System.Windows.Controls.Slider> k <xref:System.String> a pak předá, které hodnotu zpět na <xref:System.Windows.Controls.ColumnDefinition> jako <xref:System.Windows.Controls.ColumnDefinition.Width%2A> elementu.  
  
 Všimněte si, že samostatné [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] soubor definuje obsah <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>
