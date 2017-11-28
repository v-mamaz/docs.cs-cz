---
title: "Postupy: Povolení znaků tabulátoru v ovládacím prvku TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TextBox control [WPF], enabling tab characters
- tab characters [WPF], enabling
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc77668d9544cb37a8c9d1fcbdc3ed0351bc9eef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-tab-characters-in-a-textbox-control"></a><span data-ttu-id="34451-102">Postupy: Povolení znaků tabulátoru v ovládacím prvku TextBox</span><span class="sxs-lookup"><span data-stu-id="34451-102">How to: Enable Tab Characters in a TextBox Control</span></span>
<span data-ttu-id="34451-103">Tento příklad ukazuje, jak povolit přijetí karta znaků jako normální vstup v <xref:System.Windows.Controls.TextBox> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="34451-103">This example shows how to enable the acceptance of tab characters as normal input in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34451-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="34451-104">Example</span></span>  
 <span data-ttu-id="34451-105">K povolení přijetí karta znaků jako vstup ve <xref:System.Windows.Controls.TextBox> , nastavte <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> atribut **true**.</span><span class="sxs-lookup"><span data-stu-id="34451-105">To enable the acceptance of tab characters as input in a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_EnablingTab#_AcceptsTab](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## <a name="see-also"></a><span data-ttu-id="34451-106">Viz také</span><span class="sxs-lookup"><span data-stu-id="34451-106">See Also</span></span>  
 [<span data-ttu-id="34451-107">TextBox – přehled</span><span class="sxs-lookup"><span data-stu-id="34451-107">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="34451-108">RichTextBox – přehled</span><span class="sxs-lookup"><span data-stu-id="34451-108">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)