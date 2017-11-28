---
title: "Postupy: Sestavení standardního dialogového okna uživatelského rozhraní pomocí mřížky"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 641e74d8c9f8db1afde19c008de08f0029b0bf90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="fbddb-102">Postupy: Sestavení standardního dialogového okna uživatelského rozhraní pomocí mřížky</span><span class="sxs-lookup"><span data-stu-id="fbddb-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="fbddb-103">Tento příklad ukazuje, jak vytvořit standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialogové okno pomocí <xref:System.Windows.Controls.Grid> elementu.</span><span class="sxs-lookup"><span data-stu-id="fbddb-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbddb-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="fbddb-104">Example</span></span>  
 <span data-ttu-id="fbddb-105">Následující příklad vytvoří dialogové okno podobné **spustit** dialogovém okně [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operačního systému.</span><span class="sxs-lookup"><span data-stu-id="fbddb-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="fbddb-106">V příkladu se vytváří <xref:System.Windows.Controls.Grid> a používá <xref:System.Windows.Controls.ColumnDefinition> a <xref:System.Windows.Controls.RowDefinition> třídy k definování pět sloupců a řádků čtyři.</span><span class="sxs-lookup"><span data-stu-id="fbddb-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="fbddb-107">V příkladu se pak přidá a umisťuje <xref:System.Windows.Controls.Image>, `RunIcon.png`, účelem zastoupení obrázku, která se nachází v dialogovém okně.</span><span class="sxs-lookup"><span data-stu-id="fbddb-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="fbddb-108">Obrázek je umístěn v první sloupec a řádek <xref:System.Windows.Controls.Grid> (levého horního rohu).</span><span class="sxs-lookup"><span data-stu-id="fbddb-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="fbddb-109">V dalším kroku v příkladu přidáme <xref:System.Windows.Controls.TextBlock> element první sloupec, který zahrnuje zbývající sloupce prvního řádku.</span><span class="sxs-lookup"><span data-stu-id="fbddb-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="fbddb-110">Přidá další <xref:System.Windows.Controls.TextBlock> element na druhý řádek v první sloupec, aby reprezentoval **otevřete** textové pole.</span><span class="sxs-lookup"><span data-stu-id="fbddb-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="fbddb-111">A <xref:System.Windows.Controls.TextBlock> způsobem, která představuje vstupní data oblast.</span><span class="sxs-lookup"><span data-stu-id="fbddb-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="fbddb-112">Nakonec v příkladu přidáme tři <xref:System.Windows.Controls.Button> elementy poslední řádek, které představují **OK**, **zrušit**, a **Procházet** události.</span><span class="sxs-lookup"><span data-stu-id="fbddb-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fbddb-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="fbddb-113">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.GridUnitType>  
 [<span data-ttu-id="fbddb-114">Přehled panelů</span><span class="sxs-lookup"><span data-stu-id="fbddb-114">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="fbddb-115">Postupy: témata</span><span class="sxs-lookup"><span data-stu-id="fbddb-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)