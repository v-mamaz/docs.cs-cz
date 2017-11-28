---
title: "Podpora automatizace uživatelského rozhraní pro typ ovládacího prvku oddělovač"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, Separator control type
- Separator control type
- control types, Separator
ms.assetid: 89f42247-c699-4afa-91e1-2baaf0d86c9d
caps.latest.revision: "20"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 33cf6631e34a36a6a751993385f942d7cfde8e23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-support-for-the-separator-control-type"></a><span data-ttu-id="d3759-102">Podpora automatizace uživatelského rozhraní pro typ ovládacího prvku oddělovač</span><span class="sxs-lookup"><span data-stu-id="d3759-102">UI Automation Support for the Separator Control Type</span></span>
> [!NOTE]
>  <span data-ttu-id="d3759-103">Tato dokumentace je určena pro rozhraní .NET Framework vývojáře, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] třídy definované v <xref:System.Windows.Automation> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="d3759-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d3759-104">Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], najdete v části [rozhraní API systému Windows automatizace: automatizace uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="d3759-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d3759-105">Toto téma obsahuje informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] podporu pro typ ovládacího prvku oddělovač.</span><span class="sxs-lookup"><span data-stu-id="d3759-105">This topic provides information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] support for the Separator control type.</span></span> <span data-ttu-id="d3759-106">V [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], typ ovládacího prvku je sadu podmínek, které ovládacího prvku musí splnit, aby bylo možné používat <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="d3759-106">In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a control type is a set of conditions that a control must meet in order to use the <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> property.</span></span> <span data-ttu-id="d3759-107">Podmínky zahrnují konkrétní pokyny pro [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromové struktury, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] hodnoty vlastností a vzory ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="d3759-107">The conditions include specific guidelines for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values, and control patterns.</span></span>  
  
 <span data-ttu-id="d3759-108">Ovládací prvky oddělovače se používají k vizuálně mezeru rozdělit do dvou oblastí.</span><span class="sxs-lookup"><span data-stu-id="d3759-108">Separator controls are used to visually divide a space into two regions.</span></span> <span data-ttu-id="d3759-109">Ovládací prvek oddělovače může být například panel, který definuje dvě podokna v okně.</span><span class="sxs-lookup"><span data-stu-id="d3759-109">For example, a separator control can be a bar that defines two panes in a window.</span></span> <span data-ttu-id="d3759-110">Pokud lze přesunout oddělovač, by měly být vystaveny ovládacího prvku jako Flash v – typ ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="d3759-110">If the separator can be moved, the control should be exposed as Thumb in control type.</span></span>  
  
 <span data-ttu-id="d3759-111">Následující části zadejte požadované [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromové struktury, vlastností, vzory ovládacích prvků a události pro typ ovládacího prvku oddělovač.</span><span class="sxs-lookup"><span data-stu-id="d3759-111">The following sections define the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, properties, control patterns, and events for the Separator control type.</span></span> <span data-ttu-id="d3759-112">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Požadavky platí pro všechny ovládací prvky seznamu, zda [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], nebo [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3759-112">The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requirements apply to all list controls, whether [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], or [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a><span data-ttu-id="d3759-113">Struktura stromu automatizace požadované uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="d3759-113">Required UI Automation Tree Structure</span></span>  
 <span data-ttu-id="d3759-114">Následující tabulka znázorňuje zobrazení ovládacího prvku a zobrazení obsahu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromové struktury, která se vztahují na oddělovače ovládací prvky a popisuje, co může být obsažený v každém zobrazení.</span><span class="sxs-lookup"><span data-stu-id="d3759-114">The following table depicts the Control View and the Content View of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree that pertains to separator controls and describes what can be contained in each view.</span></span> <span data-ttu-id="d3759-115">Další informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromu najdete v tématu [Přehled stromu automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d3759-115">For more information on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span></span>  
  
|<span data-ttu-id="d3759-116">Zobrazení ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="d3759-116">Control View</span></span>|<span data-ttu-id="d3759-117">Zobrazení obsahu</span><span class="sxs-lookup"><span data-stu-id="d3759-117">Content View</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="d3759-118">Oddělovač</span><span class="sxs-lookup"><span data-stu-id="d3759-118">Separator</span></span>|<span data-ttu-id="d3759-119">– Ovládací prvek oddělovače nikdy obsah.</span><span class="sxs-lookup"><span data-stu-id="d3759-119">-   The Separator control never has content.</span></span>|  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a><span data-ttu-id="d3759-120">Vlastnosti automatizace požadované uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="d3759-120">Required UI Automation Properties</span></span>  
 <span data-ttu-id="d3759-121">Následující tabulka uvádí [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] vlastnosti, jehož hodnota nebo definice je obzvláště důležité pro ovládací prvky oddělovače.</span><span class="sxs-lookup"><span data-stu-id="d3759-121">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties whose value or definition is especially relevant to separator controls.</span></span> <span data-ttu-id="d3759-122">Další informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] najdete v části vlastnosti, [vlastnosti automatizace uživatelského rozhraní pro klienty](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="d3759-122">For more information on [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="d3759-123">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="d3759-123"> Property</span></span>|<span data-ttu-id="d3759-124">Hodnota</span><span class="sxs-lookup"><span data-stu-id="d3759-124">Value</span></span>|<span data-ttu-id="d3759-125">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d3759-125">Notes</span></span>|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|<span data-ttu-id="d3759-126">V části poznámky</span><span class="sxs-lookup"><span data-stu-id="d3759-126">See notes</span></span>|<span data-ttu-id="d3759-127">Hodnota této vlastnosti musí být jedinečný v rámci všech ovládacích prvků v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="d3759-127">The value of this property needs to be unique across all controls in an application.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|<span data-ttu-id="d3759-128">V části poznámky</span><span class="sxs-lookup"><span data-stu-id="d3759-128">See notes</span></span>|<span data-ttu-id="d3759-129">Nejkrajnější obdélníku, který obsahuje celý ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="d3759-129">The outermost rectangle that contains the whole control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|<span data-ttu-id="d3759-130">V části poznámky</span><span class="sxs-lookup"><span data-stu-id="d3759-130">See notes</span></span>|<span data-ttu-id="d3759-131">Podporováno, pokud je ohraničující obdélník.</span><span class="sxs-lookup"><span data-stu-id="d3759-131">Supported if there is a bounding rectangle.</span></span> <span data-ttu-id="d3759-132">Není-li každého bodu v rámci ohraničující obdélník je můžete kliknout a provést specializované přístupů testování, přepsání a nabízí bod můžete kliknout.</span><span class="sxs-lookup"><span data-stu-id="d3759-132">If not every point within the bounding rectangle is clickable, and you perform specialized hit testing, then override and provide a clickable point.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|<span data-ttu-id="d3759-133">V části poznámky</span><span class="sxs-lookup"><span data-stu-id="d3759-133">See notes</span></span>|<span data-ttu-id="d3759-134">Pokud ovládací prvek může přijímat fokus klávesnice, musí podporovat tuto vlastnost.</span><span class="sxs-lookup"><span data-stu-id="d3759-134">If the control can receive keyboard focus, it must support this property.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|<span data-ttu-id="d3759-135">""</span><span class="sxs-lookup"><span data-stu-id="d3759-135">""</span></span>|<span data-ttu-id="d3759-136">Ovládací prvek oddělovače nevyžaduje NameProperty.</span><span class="sxs-lookup"><span data-stu-id="d3759-136">The separator control does not require a NameProperty.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`null`|<span data-ttu-id="d3759-137">Ovládací prvek oddělovače nemá statické štítek.</span><span class="sxs-lookup"><span data-stu-id="d3759-137">The separator control does not have a static label.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|<span data-ttu-id="d3759-138">Oddělovač</span><span class="sxs-lookup"><span data-stu-id="d3759-138">Separator</span></span>|<span data-ttu-id="d3759-139">Tato hodnota je stejný pro všechny rozhraní uživatelského rozhraní.</span><span class="sxs-lookup"><span data-stu-id="d3759-139">This value is the same for all UI frameworks.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|<span data-ttu-id="d3759-140">"Oddělovač"</span><span class="sxs-lookup"><span data-stu-id="d3759-140">"Separator"</span></span>|<span data-ttu-id="d3759-141">Lokalizovaný řetězec odpovídající typ ovládacího prvku oddělovač.</span><span class="sxs-lookup"><span data-stu-id="d3759-141">Localized string corresponding to the Separator control type.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|<span data-ttu-id="d3759-142">False</span><span class="sxs-lookup"><span data-stu-id="d3759-142">False</span></span>|<span data-ttu-id="d3759-143">Ovládací prvek oddělovače se nikdy obsahu.</span><span class="sxs-lookup"><span data-stu-id="d3759-143">The separator control is never content.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|<span data-ttu-id="d3759-144">Hodnota TRUE</span><span class="sxs-lookup"><span data-stu-id="d3759-144">True</span></span>|<span data-ttu-id="d3759-145">Ovládací prvek oddělovače musí být vždy ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="d3759-145">The separator control must always be a control.</span></span>|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a><span data-ttu-id="d3759-146">Vzory ovládacích prvků automatizace uživatelského rozhraní požadované</span><span class="sxs-lookup"><span data-stu-id="d3759-146">Required UI Automation Control Patterns</span></span>  
 <span data-ttu-id="d3759-147">Ovládací prvek oddělovače nemusí podporovat všechny vzory ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="d3759-147">The separator control is not required to support any control patterns.</span></span>  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a><span data-ttu-id="d3759-148">Události automatizace požadované uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="d3759-148">Required UI Automation Events</span></span>  
 <span data-ttu-id="d3759-149">Následující tabulka uvádí [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] události potřeba podporovat všechny ovládací prvky oddělovače.</span><span class="sxs-lookup"><span data-stu-id="d3759-149">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events required to be supported by all separator controls.</span></span> <span data-ttu-id="d3759-150">Další informace o událostech najdete v tématu [Přehled událostí automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d3759-150">For more information about events, see [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="d3759-151">Události</span><span class="sxs-lookup"><span data-stu-id="d3759-151"> Event</span></span>|<span data-ttu-id="d3759-152">Podpora</span><span class="sxs-lookup"><span data-stu-id="d3759-152">Support</span></span>|<span data-ttu-id="d3759-153">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d3759-153">Notes</span></span>|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<span data-ttu-id="d3759-154"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>událost změny vlastnosti</span><span class="sxs-lookup"><span data-stu-id="d3759-154"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> property-changed event</span></span>|<span data-ttu-id="d3759-155">Požadováno</span><span class="sxs-lookup"><span data-stu-id="d3759-155">Required</span></span>|<span data-ttu-id="d3759-156">Žádné</span><span class="sxs-lookup"><span data-stu-id="d3759-156">None</span></span>|  
|<span data-ttu-id="d3759-157"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>událost změny vlastnosti</span><span class="sxs-lookup"><span data-stu-id="d3759-157"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> property-changed event</span></span>|<span data-ttu-id="d3759-158">Požadováno</span><span class="sxs-lookup"><span data-stu-id="d3759-158">Required</span></span>|<span data-ttu-id="d3759-159">Žádné</span><span class="sxs-lookup"><span data-stu-id="d3759-159">None</span></span>|  
|<span data-ttu-id="d3759-160"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>událost změny vlastnosti</span><span class="sxs-lookup"><span data-stu-id="d3759-160"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> property-changed event</span></span>|<span data-ttu-id="d3759-161">Požadováno</span><span class="sxs-lookup"><span data-stu-id="d3759-161">Required</span></span>|<span data-ttu-id="d3759-162">Žádné</span><span class="sxs-lookup"><span data-stu-id="d3759-162">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|<span data-ttu-id="d3759-163">Požadováno</span><span class="sxs-lookup"><span data-stu-id="d3759-163">Required</span></span>|<span data-ttu-id="d3759-164">Žádné</span><span class="sxs-lookup"><span data-stu-id="d3759-164">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|<span data-ttu-id="d3759-165">Požadováno</span><span class="sxs-lookup"><span data-stu-id="d3759-165">Required</span></span>|<span data-ttu-id="d3759-166">Žádné</span><span class="sxs-lookup"><span data-stu-id="d3759-166">None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3759-167">Viz také</span><span class="sxs-lookup"><span data-stu-id="d3759-167">See Also</span></span>  
 <xref:System.Windows.Automation.ControlType.Separator>  
 [<span data-ttu-id="d3759-168">Přehled typů ovládacích prvků automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="d3759-168">UI Automation Control Types Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [<span data-ttu-id="d3759-169">Přehled automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="d3759-169">UI Automation Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-overview.md)