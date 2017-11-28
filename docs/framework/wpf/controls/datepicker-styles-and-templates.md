---
title: "Ovládací prvek DatePicker styly a šablony"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fbe8a3935da2d9aa928467b4c64da455f3b53c5f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="datepicker-styles-and-templates"></a><span data-ttu-id="a4df7-102">Ovládací prvek DatePicker styly a šablony</span><span class="sxs-lookup"><span data-stu-id="a4df7-102">DatePicker Styles and Templates</span></span>
<span data-ttu-id="a4df7-103">Toto téma popisuje styly a šablony pro <xref:System.Windows.Controls.DatePicker> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a4df7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DatePicker> control.</span></span> <span data-ttu-id="a4df7-104">Můžete upravit výchozí <xref:System.Windows.Controls.ControlTemplate> poskytnout jedinečný vzhledu ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a4df7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a4df7-105">Další informace najdete v tématu [přizpůsobení vzhledu existujícího ovládacího prvku tak, že vytvoříte ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a4df7-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="datepicker-parts"></a><span data-ttu-id="a4df7-106">Ovládací prvek DatePicker částí</span><span class="sxs-lookup"><span data-stu-id="a4df7-106">DatePicker Parts</span></span>  
 <span data-ttu-id="a4df7-107">V následující tabulce jsou uvedené části s názvem pro <xref:System.Windows.Controls.DatePicker> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a4df7-107">The following table lists the named parts for the <xref:System.Windows.Controls.DatePicker> control.</span></span>  
  
|<span data-ttu-id="a4df7-108">Část</span><span class="sxs-lookup"><span data-stu-id="a4df7-108">Part</span></span>|<span data-ttu-id="a4df7-109">Typ</span><span class="sxs-lookup"><span data-stu-id="a4df7-109">Type</span></span>|<span data-ttu-id="a4df7-110">Popis</span><span class="sxs-lookup"><span data-stu-id="a4df7-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a4df7-111">PART_Root</span><span class="sxs-lookup"><span data-stu-id="a4df7-111">PART_Root</span></span>|<xref:System.Windows.Controls.Grid>|<span data-ttu-id="a4df7-112">Kořen ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a4df7-112">The root of the control.</span></span>|  
|<span data-ttu-id="a4df7-113">PART_Button</span><span class="sxs-lookup"><span data-stu-id="a4df7-113">PART_Button</span></span>|<xref:System.Windows.Controls.Button>|<span data-ttu-id="a4df7-114">Tlačítko, které se otevře a zavření <xref:System.Windows.Controls.Calendar>.</span><span class="sxs-lookup"><span data-stu-id="a4df7-114">The button that opens and closes the <xref:System.Windows.Controls.Calendar>.</span></span>|  
|<span data-ttu-id="a4df7-115">PART_TextBox</span><span class="sxs-lookup"><span data-stu-id="a4df7-115">PART_TextBox</span></span>|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|<span data-ttu-id="a4df7-116">Textové pole, které umožňuje vstupní datum.</span><span class="sxs-lookup"><span data-stu-id="a4df7-116">The text box that allows you to input a date.</span></span>|  
|<span data-ttu-id="a4df7-117">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="a4df7-117">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="a4df7-118">Místní nabídka pro <xref:System.Windows.Controls.DatePicker> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a4df7-118">The popup for the <xref:System.Windows.Controls.DatePicker> control.</span></span>|  
  
## <a name="datepicker-states"></a><span data-ttu-id="a4df7-119">Ovládací prvek DatePicker stavy</span><span class="sxs-lookup"><span data-stu-id="a4df7-119">DatePicker States</span></span>  
 <span data-ttu-id="a4df7-120">Následující tabulka uvádí visual stavy pro <xref:System.Windows.Controls.DatePicker> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a4df7-120">The following table lists the visual states for the <xref:System.Windows.Controls.DatePicker> control.</span></span>  
  
|<span data-ttu-id="a4df7-121">Název VisualState</span><span class="sxs-lookup"><span data-stu-id="a4df7-121">VisualState Name</span></span>|<span data-ttu-id="a4df7-122">Název VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a4df7-122">VisualStateGroup Name</span></span>|<span data-ttu-id="a4df7-123">Popis</span><span class="sxs-lookup"><span data-stu-id="a4df7-123">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a4df7-124">Normální</span><span class="sxs-lookup"><span data-stu-id="a4df7-124">Normal</span></span>|<span data-ttu-id="a4df7-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-125">CommonStates</span></span>|<span data-ttu-id="a4df7-126">Ve výchozím stavu.</span><span class="sxs-lookup"><span data-stu-id="a4df7-126">The default state.</span></span>|  
|<span data-ttu-id="a4df7-127">zakázáno</span><span class="sxs-lookup"><span data-stu-id="a4df7-127">Disabled</span></span>|<span data-ttu-id="a4df7-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-128">CommonStates</span></span>|<span data-ttu-id="a4df7-129"><xref:System.Windows.Controls.DatePicker> Je zakázána.</span><span class="sxs-lookup"><span data-stu-id="a4df7-129">The <xref:System.Windows.Controls.DatePicker> is disabled.</span></span>|  
|<span data-ttu-id="a4df7-130">Platné</span><span class="sxs-lookup"><span data-stu-id="a4df7-130">Valid</span></span>|<span data-ttu-id="a4df7-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-131">ValidationStates</span></span>|<span data-ttu-id="a4df7-132">Ovládací prvek používá <xref:System.Windows.Controls.Validation> třídy a <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> je přidružená vlastnost `false`.</span><span class="sxs-lookup"><span data-stu-id="a4df7-132">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a4df7-133">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a4df7-133">InvalidFocused</span></span>|<span data-ttu-id="a4df7-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-134">ValidationStates</span></span>|<span data-ttu-id="a4df7-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Je přidružená vlastnost `true` má ovládací prvek má právě fokus.</span><span class="sxs-lookup"><span data-stu-id="a4df7-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a4df7-136">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a4df7-136">InvalidUnfocused</span></span>|<span data-ttu-id="a4df7-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-137">ValidationStates</span></span>|<span data-ttu-id="a4df7-138"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Je přidružená vlastnost `true` má ovládací prvek nemá fokus.</span><span class="sxs-lookup"><span data-stu-id="a4df7-138">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="datepickertextbox-parts"></a><span data-ttu-id="a4df7-139">DatePickerTextBox částí</span><span class="sxs-lookup"><span data-stu-id="a4df7-139">DatePickerTextBox Parts</span></span>  
 <span data-ttu-id="a4df7-140">V následující tabulce jsou uvedené části s názvem pro <xref:System.Windows.Controls.Primitives.DatePickerTextBox> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a4df7-140">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.DatePickerTextBox> control.</span></span>  
  
|<span data-ttu-id="a4df7-141">Část</span><span class="sxs-lookup"><span data-stu-id="a4df7-141">Part</span></span>|<span data-ttu-id="a4df7-142">Typ</span><span class="sxs-lookup"><span data-stu-id="a4df7-142">Type</span></span>|<span data-ttu-id="a4df7-143">Popis</span><span class="sxs-lookup"><span data-stu-id="a4df7-143">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a4df7-144">PART_Watermark</span><span class="sxs-lookup"><span data-stu-id="a4df7-144">PART_Watermark</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="a4df7-145">Element, který obsahuje počáteční text v <xref:System.Windows.Controls.DatePicker>.</span><span class="sxs-lookup"><span data-stu-id="a4df7-145">The element that contains the initial text in the <xref:System.Windows.Controls.DatePicker>.</span></span>|  
|<span data-ttu-id="a4df7-146">PART_ContentElement</span><span class="sxs-lookup"><span data-stu-id="a4df7-146">PART_ContentElement</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="a4df7-147">Vizuální prvek, který může obsahovat <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="a4df7-147">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="a4df7-148">Text <xref:System.Windows.Controls.TextBox> se zobrazí v tomto elementu.</span><span class="sxs-lookup"><span data-stu-id="a4df7-148">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="datepickertextbox-states"></a><span data-ttu-id="a4df7-149">DatePickerTextBox stavy</span><span class="sxs-lookup"><span data-stu-id="a4df7-149">DatePickerTextBox States</span></span>  
 <span data-ttu-id="a4df7-150">Následující tabulka uvádí visual stavy pro <xref:System.Windows.Controls.Primitives.DatePickerTextBox> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a4df7-150">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.DatePickerTextBox> control.</span></span>  
  
|<span data-ttu-id="a4df7-151">Název VisualState</span><span class="sxs-lookup"><span data-stu-id="a4df7-151">VisualState Name</span></span>|<span data-ttu-id="a4df7-152">Název VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a4df7-152">VisualStateGroup Name</span></span>|<span data-ttu-id="a4df7-153">Popis</span><span class="sxs-lookup"><span data-stu-id="a4df7-153">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a4df7-154">Normální</span><span class="sxs-lookup"><span data-stu-id="a4df7-154">Normal</span></span>|<span data-ttu-id="a4df7-155">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-155">CommonStates</span></span>|<span data-ttu-id="a4df7-156">Ve výchozím stavu.</span><span class="sxs-lookup"><span data-stu-id="a4df7-156">The default state.</span></span>|  
|<span data-ttu-id="a4df7-157">zakázáno</span><span class="sxs-lookup"><span data-stu-id="a4df7-157">Disabled</span></span>|<span data-ttu-id="a4df7-158">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-158">CommonStates</span></span>|<span data-ttu-id="a4df7-159"><xref:System.Windows.Controls.Primitives.DatePickerTextBox> Je zakázána.</span><span class="sxs-lookup"><span data-stu-id="a4df7-159">The <xref:System.Windows.Controls.Primitives.DatePickerTextBox> is disabled.</span></span>|  
|<span data-ttu-id="a4df7-160">Myš nad</span><span class="sxs-lookup"><span data-stu-id="a4df7-160">MouseOver</span></span>|<span data-ttu-id="a4df7-161">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-161">CommonStates</span></span>|<span data-ttu-id="a4df7-162">Umístění ukazatele myši nad <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.</span><span class="sxs-lookup"><span data-stu-id="a4df7-162">The mouse pointer is positioned over the <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.</span></span>|  
|<span data-ttu-id="a4df7-163">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="a4df7-163">ReadOnly</span></span>|<span data-ttu-id="a4df7-164">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-164">CommonStates</span></span>|<span data-ttu-id="a4df7-165">Uživatel nemůže změnit text v <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.</span><span class="sxs-lookup"><span data-stu-id="a4df7-165">The user cannot change the text in the <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.</span></span>|  
|<span data-ttu-id="a4df7-166">Zaměřuje</span><span class="sxs-lookup"><span data-stu-id="a4df7-166">Focused</span></span>|<span data-ttu-id="a4df7-167">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-167">FocusStates</span></span>|<span data-ttu-id="a4df7-168">Ovládací prvek má právě fokus.</span><span class="sxs-lookup"><span data-stu-id="a4df7-168">The control has focus.</span></span>|  
|<span data-ttu-id="a4df7-169">Nezaostřená</span><span class="sxs-lookup"><span data-stu-id="a4df7-169">Unfocused</span></span>|<span data-ttu-id="a4df7-170">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-170">FocusStates</span></span>|<span data-ttu-id="a4df7-171">Ovládací prvek nemá fokus.</span><span class="sxs-lookup"><span data-stu-id="a4df7-171">The control does not have focus.</span></span>|  
|<span data-ttu-id="a4df7-172">Mezí</span><span class="sxs-lookup"><span data-stu-id="a4df7-172">Watermarked</span></span>|<span data-ttu-id="a4df7-173">WatermarkStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-173">WatermarkStates</span></span>|<span data-ttu-id="a4df7-174">Ovládací prvek zobrazí jeho počáteční text.</span><span class="sxs-lookup"><span data-stu-id="a4df7-174">The control displays its initial text.</span></span>  <span data-ttu-id="a4df7-175"><xref:System.Windows.Controls.Primitives.DatePickerTextBox> Je ve stavu, pokud uživatel nebyl zadaný text nebo vybrané datum.</span><span class="sxs-lookup"><span data-stu-id="a4df7-175">The <xref:System.Windows.Controls.Primitives.DatePickerTextBox> is in the state when the user has not entered text or selected a date.</span></span>|  
|<span data-ttu-id="a4df7-176">Unwatermarked</span><span class="sxs-lookup"><span data-stu-id="a4df7-176">Unwatermarked</span></span>|<span data-ttu-id="a4df7-177">WatermarkStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-177">WatermarkStates</span></span>|<span data-ttu-id="a4df7-178">Uživatel zadal text do <xref:System.Windows.Controls.Primitives.DatePickerTextBox> nebo vybrat datum v <xref:System.Windows.Controls.DatePicker>.</span><span class="sxs-lookup"><span data-stu-id="a4df7-178">The user has entered text into the <xref:System.Windows.Controls.Primitives.DatePickerTextBox> or selected a date in the <xref:System.Windows.Controls.DatePicker>.</span></span>|  
|<span data-ttu-id="a4df7-179">Platné</span><span class="sxs-lookup"><span data-stu-id="a4df7-179">Valid</span></span>|<span data-ttu-id="a4df7-180">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-180">ValidationStates</span></span>|<span data-ttu-id="a4df7-181">Ovládací prvek používá <xref:System.Windows.Controls.Validation> třídy a <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> je přidružená vlastnost `false`.</span><span class="sxs-lookup"><span data-stu-id="a4df7-181">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a4df7-182">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a4df7-182">InvalidFocused</span></span>|<span data-ttu-id="a4df7-183">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-183">ValidationStates</span></span>|<span data-ttu-id="a4df7-184"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Je přidružená vlastnost `true` má ovládací prvek má právě fokus.</span><span class="sxs-lookup"><span data-stu-id="a4df7-184">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a4df7-185">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a4df7-185">InvalidUnfocused</span></span>|<span data-ttu-id="a4df7-186">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a4df7-186">ValidationStates</span></span>|<span data-ttu-id="a4df7-187"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Je přidružená vlastnost `true` má ovládací prvek nemá fokus.</span><span class="sxs-lookup"><span data-stu-id="a4df7-187">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="datepicker-controltemplate-example"></a><span data-ttu-id="a4df7-188">Ovládací prvek DatePicker ControlTemplate příklad</span><span class="sxs-lookup"><span data-stu-id="a4df7-188">DatePicker ControlTemplate Example</span></span>  
 <span data-ttu-id="a4df7-189">Následující příklad ukazuje, jak definovat <xref:System.Windows.Controls.ControlTemplate> pro <xref:System.Windows.Controls.DatePicker> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a4df7-189">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DatePicker> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
 <span data-ttu-id="a4df7-190">V předchozím příkladu používá jeden nebo více z následujících prostředků.</span><span class="sxs-lookup"><span data-stu-id="a4df7-190">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a4df7-191">Kompletní příklad, najdete v části [styly s ukázkou ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="a4df7-191">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4df7-192">Viz také</span><span class="sxs-lookup"><span data-stu-id="a4df7-192">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="a4df7-193">Styly ovládacího prvku a šablony</span><span class="sxs-lookup"><span data-stu-id="a4df7-193">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="a4df7-194">Přizpůsobení ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="a4df7-194">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="a4df7-195">Stylů a ukázka</span><span class="sxs-lookup"><span data-stu-id="a4df7-195">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="a4df7-196">Přizpůsobení vzhledu existujícího ovládacího prvku tak, že vytvoříte ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a4df7-196">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)