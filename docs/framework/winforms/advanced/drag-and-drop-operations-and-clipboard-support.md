---
title: "Operace přetažení a podpora schránky"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drag and drop [Windows Forms]
- drag and drop [Windows Forms], Windows Forms
- Clipboard [Windows Forms], Windows Forms
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 722c37645d95009ce03bbbf813bc9f9fb2418e60
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="drag-and-drop-operations-and-clipboard-support"></a><span data-ttu-id="14447-102">Operace přetažení a podpora schránky</span><span class="sxs-lookup"><span data-stu-id="14447-102">Drag-and-Drop Operations and Clipboard Support</span></span>
<span data-ttu-id="14447-103">Operace přetažení myší uživatele v rámci aplikace systému Windows můžete povolit zpracování řadu událostí, zejména <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, a <xref:System.Windows.Forms.Control.DragDrop> události.</span><span class="sxs-lookup"><span data-stu-id="14447-103">You can enable user drag-and-drop operations within a Windows-based application by handling a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
 <span data-ttu-id="14447-104">Můžete taky implementovat podporu vyjímání, kopírování a vkládání uživatele a dat uživatele přenést do schránky v rámci vaší aplikace pro systém Windows pomocí jednoduchý způsob volání.</span><span class="sxs-lookup"><span data-stu-id="14447-104">You can also implement user cut/copy/paste support and user data transfer to the Clipboard within your Windows-based applications by using simple method calls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14447-105">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="14447-105">In This Section</span></span>  
 [<span data-ttu-id="14447-106">Návod: Provádění operace přetažení myší v systému Windows Forms</span><span class="sxs-lookup"><span data-stu-id="14447-106">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 <span data-ttu-id="14447-107">Vysvětluje, jak spustit operaci přetažení myší.</span><span class="sxs-lookup"><span data-stu-id="14447-107">Explains how to start a drag-and-drop operation.</span></span>  
  
 [<span data-ttu-id="14447-108">Postupy: provádění operací přetažení myší mezi aplikacemi</span><span class="sxs-lookup"><span data-stu-id="14447-108">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)  
 <span data-ttu-id="14447-109">Ukazuje, jak k provádění operací přetažení myší napříč aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="14447-109">Illustrates how to accomplish drag-and-drop operations across applications.</span></span>  
  
 [<span data-ttu-id="14447-110">Postupy: přidání dat do schránky.</span><span class="sxs-lookup"><span data-stu-id="14447-110">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 <span data-ttu-id="14447-111">Popisuje způsob, jak programově vložení informací do schránky.</span><span class="sxs-lookup"><span data-stu-id="14447-111">Describes a way to programmatically insert information on the Clipboard.</span></span>  
  
 [<span data-ttu-id="14447-112">Postupy: načtení dat ze schránky</span><span class="sxs-lookup"><span data-stu-id="14447-112">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 <span data-ttu-id="14447-113">Popisuje postup přístup k datům uloženým do schránky.</span><span class="sxs-lookup"><span data-stu-id="14447-113">Describes how to access the data stored on the Clipboard.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="14447-114">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="14447-114">Related Sections</span></span>  
 [<span data-ttu-id="14447-115">A přetažení funkce ve Windows Forms</span><span class="sxs-lookup"><span data-stu-id="14447-115">Drag-and-Drop Functionality in Windows Forms</span></span>](../../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)  
 <span data-ttu-id="14447-116">Popisuje metody, události a třídy používané k implementaci chování přetažení myší.</span><span class="sxs-lookup"><span data-stu-id="14447-116">Describes the methods, events, and classes used to implement drag-and-drop behavior.</span></span>  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 <span data-ttu-id="14447-117">Popisuje rozbor všech události, která požaduje oprávnění k pokračovat v provádění operace přetažení.</span><span class="sxs-lookup"><span data-stu-id="14447-117">Describes the intricacies of the event that asks permission to continue the drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 <span data-ttu-id="14447-118">Popisuje rozbor všech metody, která je základem od operaci přetažení.</span><span class="sxs-lookup"><span data-stu-id="14447-118">Describes the intricacies of the method that is central to beginning a drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Clipboard>  
 <span data-ttu-id="14447-119">Viz také [postupy: odesílání dat do aktivního podřízeného MDI](http://msdn.microsoft.com/library/y0hkh2c8\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="14447-119">Also see [How to: Send Data to the Active MDI Child](http://msdn.microsoft.com/library/y0hkh2c8\(v=vs.110\)).</span></span>