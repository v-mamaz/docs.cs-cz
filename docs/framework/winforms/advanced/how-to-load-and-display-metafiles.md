---
title: "Postupy: Zavedení a zobrazení metasouborů"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 722b6d36801c69e500535a32e952ef8f45634d03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="7c2d0-102">Postupy: Zavedení a zobrazení metasouborů</span><span class="sxs-lookup"><span data-stu-id="7c2d0-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="7c2d0-103"><xref:System.Drawing.Imaging.Metafile> Třídy, která dědí z <xref:System.Drawing.Image> třídy, poskytuje metody pro záznam, zobrazení a zkoumání vektoru bitové kopie.</span><span class="sxs-lookup"><span data-stu-id="7c2d0-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c2d0-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="7c2d0-104">Example</span></span>  
 <span data-ttu-id="7c2d0-105">Chcete-li zobrazit bitovou kopii vektoru (metafile) na obrazovce, je třeba <xref:System.Drawing.Imaging.Metafile> objektu a <xref:System.Drawing.Graphics> objektu.</span><span class="sxs-lookup"><span data-stu-id="7c2d0-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="7c2d0-106">Předat název souboru (nebo datový proud) <xref:System.Drawing.Imaging.Metafile> konstruktor.</span><span class="sxs-lookup"><span data-stu-id="7c2d0-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="7c2d0-107">Po vytvoření <xref:System.Drawing.Imaging.Metafile> objektu, který předat <xref:System.Drawing.Imaging.Metafile> do objektu <xref:System.Drawing.Graphics.DrawImage%2A> metodu <xref:System.Drawing.Graphics> objektu.</span><span class="sxs-lookup"><span data-stu-id="7c2d0-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="7c2d0-108">V příkladu se vytváří <xref:System.Drawing.Imaging.Metafile> objekt ze souboru EMF (EMF) a pak nakreslí obrázek s jeho levého horního rohu v (60, 10).</span><span class="sxs-lookup"><span data-stu-id="7c2d0-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="7c2d0-109">Následující obrázek znázorňuje metafile vykreslovat v zadaném umístění.</span><span class="sxs-lookup"><span data-stu-id="7c2d0-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="7c2d0-110">![Obrázek pozice](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="7c2d0-110">![Image Position](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7c2d0-111">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="7c2d0-111">Compiling the Code</span></span>  
 <span data-ttu-id="7c2d0-112">V předchozím příkladu je určen k použití s modelem Windows Forms a vyžaduje <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.Control.Paint> obslužné rutiny události.</span><span class="sxs-lookup"><span data-stu-id="7c2d0-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c2d0-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="7c2d0-113">See Also</span></span>  
 [<span data-ttu-id="7c2d0-114">Práce s obrázky, rastrové obrázky, ikony a metasoubory</span><span class="sxs-lookup"><span data-stu-id="7c2d0-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)