---
title: 'Postupy: Řazení a seskupení dat použitím zobrazení XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: 01cbd113502c3f953bd701930df6db090844fefa
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351421"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Postupy: Řazení a seskupení dat použitím zobrazení XAML
Tento příklad ukazuje postup vytvoření zobrazení datové kolekce v [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Zobrazení umožňují funkce seskupení, řazení, filtrování a pojem s aktuální položkou.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu statický prostředek s názvem *umístí* je definována jako kolekce *místo* objekty, ve nichž každý *místo* objektu se skládal z název města a stav. Předpona, která *src* je namapována na obor názvů kde zdroj dat *míst* je definována. Předpona, která *scm* mapuje `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` a *dat* mapuje `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 Následující příklad vytvoří zobrazení shromažďování dat, který je seřazený podle název města a seskupených podle stavu.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 Zobrazení pak může být zdrojem vazby, jako v následujícím příkladu:  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 U vazeb k datům XML s definovaný v <xref:System.Windows.Data.XmlDataProvider> prostředků, zadejte před název XML @ symbol.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Data.CollectionViewSource>
- [Načtení výchozího zobrazení datové kolekce](how-to-get-the-default-view-of-a-data-collection.md)
- [Přehled datových vazeb](data-binding-overview.md)
- [Témata s postupy](data-binding-how-to-topics.md)
