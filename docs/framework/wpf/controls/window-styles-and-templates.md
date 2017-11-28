---
title: "Styly a šablony oken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0415bfae8e1065759efaac1a779655444451fa24
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="88a4a-102">Styly a šablony oken</span><span class="sxs-lookup"><span data-stu-id="88a4a-102">Window Styles and Templates</span></span>
<span data-ttu-id="88a4a-103">Toto téma popisuje styly a šablony pro <xref:System.Windows.Window> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="88a4a-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="88a4a-104">Můžete upravit výchozí <xref:System.Windows.Controls.ControlTemplate> poskytnout jedinečný vzhledu ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="88a4a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="88a4a-105">Další informace najdete v tématu [přizpůsobení vzhledu existujícího ovládacího prvku tak, že vytvoříte ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="88a4a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="88a4a-106">Části okna</span><span class="sxs-lookup"><span data-stu-id="88a4a-106">Window Parts</span></span>  
 <span data-ttu-id="88a4a-107"><xref:System.Windows.Window> Ovládací prvek nemá žádné pojmenované částí.</span><span class="sxs-lookup"><span data-stu-id="88a4a-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="88a4a-108">Okno stavy</span><span class="sxs-lookup"><span data-stu-id="88a4a-108">Window States</span></span>  
 <span data-ttu-id="88a4a-109">Následující tabulka uvádí visual stavy pro <xref:System.Windows.Window> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="88a4a-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="88a4a-110">Název VisualState</span><span class="sxs-lookup"><span data-stu-id="88a4a-110">VisualState Name</span></span>|<span data-ttu-id="88a4a-111">Název VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="88a4a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="88a4a-112">Popis</span><span class="sxs-lookup"><span data-stu-id="88a4a-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="88a4a-113">Platné</span><span class="sxs-lookup"><span data-stu-id="88a4a-113">Valid</span></span>|<span data-ttu-id="88a4a-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="88a4a-114">ValidationStates</span></span>|<span data-ttu-id="88a4a-115">Ovládací prvek používá <xref:System.Windows.Controls.Validation> třídy a <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> je přidružená vlastnost `false`.</span><span class="sxs-lookup"><span data-stu-id="88a4a-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="88a4a-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="88a4a-116">InvalidFocused</span></span>|<span data-ttu-id="88a4a-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="88a4a-117">ValidationStates</span></span>|<span data-ttu-id="88a4a-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Je přidružená vlastnost `true` má ovládací prvek má právě fokus.</span><span class="sxs-lookup"><span data-stu-id="88a4a-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="88a4a-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="88a4a-119">InvalidUnfocused</span></span>|<span data-ttu-id="88a4a-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="88a4a-120">ValidationStates</span></span>|<span data-ttu-id="88a4a-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Je přidružená vlastnost `true` má ovládací prvek nemá fokus.</span><span class="sxs-lookup"><span data-stu-id="88a4a-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="88a4a-122">Příklad ControlTemplate okna</span><span class="sxs-lookup"><span data-stu-id="88a4a-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="88a4a-123">Následující příklad ukazuje, jak definovat <xref:System.Windows.Controls.ControlTemplate> pro <xref:System.Windows.Window> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="88a4a-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="88a4a-124"><xref:System.Windows.Controls.ControlTemplate> Používá jeden nebo více z následujících prostředků.</span><span class="sxs-lookup"><span data-stu-id="88a4a-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="88a4a-125">Kompletní příklad, najdete v části [styly s ukázkou ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="88a4a-125">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88a4a-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="88a4a-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="88a4a-127">Styly ovládacího prvku a šablony</span><span class="sxs-lookup"><span data-stu-id="88a4a-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="88a4a-128">Přizpůsobení ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="88a4a-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="88a4a-129">Stylů a ukázka</span><span class="sxs-lookup"><span data-stu-id="88a4a-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="88a4a-130">Přizpůsobení vzhledu existujícího ovládacího prvku tak, že vytvoříte ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="88a4a-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)