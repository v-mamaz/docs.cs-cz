---
title: PasswordBox – styly a šablony
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: 7783330dd56ec5b2759e783a6935761eb3587978
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57507298"
---
# <a name="passwordbox-styles-and-templates"></a>PasswordBox – styly a šablony

Toto téma popisuje styly a šablony pro <xref:System.Windows.Controls.PasswordBox> ovládacího prvku. Můžete upravit výchozí <xref:System.Windows.Controls.ControlTemplate> poskytnout jedinečný vzhled ovládacího prvku. Další informace najdete v tématu [přizpůsobení vzhledu stávajícího ovládacího prvku vytvořením ControlTemplate](customizing-the-appearance-of-an-existing-control.md).

## <a name="passwordbox-parts"></a>Části pole pro zadání hesla

V následující tabulce jsou uvedeny pojmenované části pro <xref:System.Windows.Controls.PasswordBox> ovládacího prvku.

|Část|Typ|Popis|
|-|-|-|
|PART_ContentHost|<xref:System.Windows.FrameworkElement>|Vizuální prvek, který může obsahovat <xref:System.Windows.FrameworkElement>. Text <xref:System.Windows.Controls.PasswordBox> se zobrazí v tomto elementu.|

## <a name="passwordbox-states"></a>Stavy pole pro zadání hesla

V následující tabulce jsou uvedeny vizuálních stavů pro <xref:System.Windows.Controls.PasswordBox> ovládacího prvku.

|Název vizuálního stavu|Název VisualStateGroup|Popis|
|-|-|-|
|Normální|CommonStates|Ve výchozím stavu.|
|Myš nad|CommonStates|Je ukazatel myši umístěn nad ovládací prvek.|
|Zakázáno|CommonStates|Ovládací prvek je zakázaný.|
|Fokus|FocusStates|Ovládací prvek má fokus.|
|Bez fokusu|FocusStates|Ovládací prvek nemá fokus.|
|Platné|ValidationStates|Ovládací prvek používá <xref:System.Windows.Controls.Validation> třídy a <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> je připojená vlastnost `false`.|
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Je připojená vlastnost `true` má ovládací prvek má fokus.|
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Je připojená vlastnost `true` má ovládací prvek nemá fokus.|

## <a name="passwordbox-controltemplate-example"></a>Příklad šablony ControlTemplate pole pro zadání hesla

Následující příklad ukazuje, jak definovat <xref:System.Windows.Controls.ControlTemplate> pro <xref:System.Windows.Controls.PasswordBox> ovládacího prvku.

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

V předchozím příkladu používá jeden nebo více z následujících prostředků.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

Úplnou ukázku najdete v tématu [stylu s ukázkou ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="see-also"></a>Viz také:

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Styly a šablony ovládacích prvků](control-styles-and-templates.md)
- [Přizpůsobení ovládacího prvku](control-customization.md)
- [Styly a šablony](styling-and-templating.md)
- [Přizpůsobení vzhledu stávajícího ovládacího prvku vytvořením šablony ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
