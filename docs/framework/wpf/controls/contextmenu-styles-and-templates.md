---
title: ContextMenu – styly a šablony
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: be26156d74f3a3509bf150e5611512172f08a14e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369065"
---
# <a name="contextmenu-styles-and-templates"></a>ContextMenu – styly a šablony
Toto téma popisuje styly a šablony pro <xref:System.Windows.Controls.ContextMenu> ovládacího prvku. Můžete upravit výchozí <xref:System.Windows.Controls.ControlTemplate> poskytnout jedinečný vzhled ovládacího prvku. Další informace najdete v tématu [přizpůsobení vzhledu stávajícího ovládacího prvku vytvořením ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="contextmenu-parts"></a>ContextMenu – částí  
 <xref:System.Windows.Controls.ContextMenu> Ovládací prvek nemá žádné pojmenované součásti.  
  
 Při vytváření <xref:System.Windows.Controls.ControlTemplate> pro <xref:System.Windows.Controls.ContextMenu>, šablona může obsahovat <xref:System.Windows.Controls.ItemsPresenter> v rámci <xref:System.Windows.Controls.ScrollViewer>. ( <xref:System.Windows.Controls.ItemsPresenter> Zobrazuje každou položku v <xref:System.Windows.Controls.ContextMenu>; <xref:System.Windows.Controls.ScrollViewer> umožňuje posouvání v ovládacím prvku).  Pokud <xref:System.Windows.Controls.ItemsPresenter> není za přímé podřízeného člena <xref:System.Windows.Controls.ScrollViewer>, je třeba zadat <xref:System.Windows.Controls.ItemsPresenter> názvu, `ItemsPresenter`.  
  
## <a name="contextmenu-states"></a>ContextMenu – stavy  
 V následující tabulce jsou uvedeny vizuálních stavů pro <xref:System.Windows.Controls.ContextMenu> ovládacího prvku.  
  
|Název vizuálního stavu|Název VisualStateGroup|Popis|  
|-|-|-|  
|Platné|ValidationStates|Ovládací prvek používá <xref:System.Windows.Controls.Validation> třídy a <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> je připojená vlastnost `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Je připojená vlastnost `true` má ovládací prvek má fokus.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Je připojená vlastnost `true` má ovládací prvek nemá fokus.|  
  
## <a name="contextmenu-controltemplate-example"></a>Příklad šablony ControlTemplate ContextMenu  
 Následující příklad ukazuje, jak definovat <xref:System.Windows.Controls.ControlTemplate> pro <xref:System.Windows.Controls.ContextMenu> ovládacího prvku.  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <xref:System.Windows.Controls.ControlTemplate> Používá následující prostředky.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Úplnou ukázku najdete v tématu [stylu s ukázkou ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Styly a šablony ovládacích prvků](control-styles-and-templates.md)
- [Přizpůsobení ovládacího prvku](control-customization.md)
- [Styly a šablony](styling-and-templating.md)
- [Přizpůsobení vzhledu stávajícího ovládacího prvku vytvořením šablony ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
