---
title: "Postupy: Ovládací prvky stylu na objektu ToolBar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ce090ace11262e4809dbecadd5fe89d7dfaf62e5
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-style-controls-on-a-toolbar"></a><span data-ttu-id="b7531-102">Postupy: Ovládací prvky stylu na objektu ToolBar</span><span class="sxs-lookup"><span data-stu-id="b7531-102">How to: Style Controls on a ToolBar</span></span>
<span data-ttu-id="b7531-103"><xref:System.Windows.Controls.ToolBar> Definuje <xref:System.Windows.ResourceKey> objekty, které chcete určit styl ovládacích prvků v rámci <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="b7531-103">The <xref:System.Windows.Controls.ToolBar> defines <xref:System.Windows.ResourceKey> objects to specify the style of controls within the <xref:System.Windows.Controls.ToolBar>.</span></span>  <span data-ttu-id="b7531-104">K formátování v ovládacím prvku <xref:System.Windows.Controls.ToolBar>, nastavte `x:key` styl do atribut <xref:System.Windows.ResourceKey> definované v <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="b7531-104">To style a control in a <xref:System.Windows.Controls.ToolBar>, set the `x:key` attribute of the style to a <xref:System.Windows.ResourceKey> defined in <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 <span data-ttu-id="b7531-105"><xref:System.Windows.Controls.ToolBar> Definuje následující <xref:System.Windows.ResourceKey> objekty:</span><span class="sxs-lookup"><span data-stu-id="b7531-105">The <xref:System.Windows.Controls.ToolBar> defines the following <xref:System.Windows.ResourceKey> objects:</span></span>  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a><span data-ttu-id="b7531-106">Příklad</span><span class="sxs-lookup"><span data-stu-id="b7531-106">Example</span></span>  
 <span data-ttu-id="b7531-107">V následujícím příkladu definuje styly pro ovládací prvky v rámci <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="b7531-107">The following example defines styles for the controls within a <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a><span data-ttu-id="b7531-108">Viz také</span><span class="sxs-lookup"><span data-stu-id="b7531-108">See Also</span></span>  
 [<span data-ttu-id="b7531-109">Stylů a ukázka</span><span class="sxs-lookup"><span data-stu-id="b7531-109">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)