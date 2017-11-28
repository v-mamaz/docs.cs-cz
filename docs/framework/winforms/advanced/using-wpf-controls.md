---
title: "Používání ovládacích prvků WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6fe8fb972f8080bbffeed5db2063d8c0484aec4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="using-wpf-controls"></a><span data-ttu-id="c803d-102">Používání ovládacích prvků WPF</span><span class="sxs-lookup"><span data-stu-id="c803d-102">Using WPF Controls</span></span>
<span data-ttu-id="c803d-103">Ovládací prvky Windows Presentation Foundation (WPF) můžete použít ve svých aplikacích pomocí formulářů Windows.</span><span class="sxs-lookup"><span data-stu-id="c803d-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="c803d-104">I když jsou tyto dvě technologie jiné zobrazení, budou spolupracovat bez problémů.</span><span class="sxs-lookup"><span data-stu-id="c803d-104">Although these are two different view technologies, they interoperate smoothly.</span></span>  
  
 <span data-ttu-id="c803d-105">Návrhář formulářů Windows poskytuje prostředí visual návrhu pro hostování ovládacích prvků Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="c803d-105">The Windows Forms Designer provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="c803d-106">Ovládací prvek WPF hostován ve speciální ovládacího prvku Windows Forms, který je pojmenován <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="c803d-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="c803d-107">Tento ovládací prvek umožňuje ovládací prvek WPF zapojit se do rozvržení a aby se zprávy klávesnici a myš.</span><span class="sxs-lookup"><span data-stu-id="c803d-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="c803d-108">V době návrhu, můžete uspořádat <xref:System.Windows.Forms.Integration.ElementHost> řízení stejně jako libovolný ovládací prvek Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c803d-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>  
  
 <span data-ttu-id="c803d-109">Windows Forms – ovládací prvky můžete použít také v aplikacích grafického subsystému WPF.</span><span class="sxs-lookup"><span data-stu-id="c803d-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="c803d-110">Další informace najdete v tématu [WPF Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26).</span><span class="sxs-lookup"><span data-stu-id="c803d-110">For more information, see [WPF Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c803d-111">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="c803d-111">In This Section</span></span>  
 [<span data-ttu-id="c803d-112">Postupy: kopírování a vložení ovládacího prvku ElementHost během návrhu</span><span class="sxs-lookup"><span data-stu-id="c803d-112">How to: Copy and Paste an ElementHost Control at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 <span data-ttu-id="c803d-113">Ukazuje, jak zkopírovat Windows Presentation Foundation ovládací prvek na formuláři Windows.</span><span class="sxs-lookup"><span data-stu-id="c803d-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>  
  
 [<span data-ttu-id="c803d-114">Návod: Uspořádání obsahu WPF ve Windows Forms v době návrhu</span><span class="sxs-lookup"><span data-stu-id="c803d-114">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="c803d-115">Ukazuje, jak funkce rozložení Windows Forms, jako je například ukotvení a zarovnávací čáry, používat k uspořádání ovládacích prvků Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="c803d-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>  
  
 [<span data-ttu-id="c803d-116">Návod: Změna vlastností hostovaného prvku WPF během návrhu</span><span class="sxs-lookup"><span data-stu-id="c803d-116">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 <span data-ttu-id="c803d-117">Ukazuje pracovní postup mezi Návrhář formulářů Windows a [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] pro změnu vlastností ovládacích prvků WPF.</span><span class="sxs-lookup"><span data-stu-id="c803d-117">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] for changing properties on WPF controls.</span></span>  
  
 [<span data-ttu-id="c803d-118">Návod: Vytvoření nového obsahu WPF v rozhraní Windows Forms v době návrhu</span><span class="sxs-lookup"><span data-stu-id="c803d-118">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="c803d-119">Ukazuje postup vytvoření ovládacího prvku Windows Presentation Foundation pro použití v aplikacích Windows formulářů.</span><span class="sxs-lookup"><span data-stu-id="c803d-119">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>  
  
 [<span data-ttu-id="c803d-120">Návod: Zkopírování a vložení ovládacího prvku ElementHost do samostatného formuláře Windows</span><span class="sxs-lookup"><span data-stu-id="c803d-120">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 <span data-ttu-id="c803d-121">Ukazuje, jak kopírovat ovládacího prvku Windows Presentation Foundation z jednoho formuláře Windows do jiného.</span><span class="sxs-lookup"><span data-stu-id="c803d-121">Shows how to copy a Windows Presentation Foundation control from one Windows Form to another.</span></span>  
  
 [<span data-ttu-id="c803d-122">Návod: Přiřazování obsahu WPF ve Windows Forms v době návrhu</span><span class="sxs-lookup"><span data-stu-id="c803d-122">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="c803d-123">Ukazuje, jak vybrat typy ovládacích prvků Windows Presentation Foundation, které chcete zobrazit ve formuláři.</span><span class="sxs-lookup"><span data-stu-id="c803d-123">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>  
  
 [<span data-ttu-id="c803d-124">Návod: Určení stylu obsahu WPF</span><span class="sxs-lookup"><span data-stu-id="c803d-124">Walkthrough: Styling WPF Content</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 <span data-ttu-id="c803d-125">Ukazuje pracovní postup mezi Návrhář formulářů Windows a [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] použití styly pro ovládací prvky Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="c803d-125">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c803d-126">Odkaz</span><span class="sxs-lookup"><span data-stu-id="c803d-126">Reference</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <span data-ttu-id="c803d-127">Popisuje třídu, která vám pomůže Windows Presentation Foundation hostitelské ovládací prvky v aplikacích Windows formulářů.</span><span class="sxs-lookup"><span data-stu-id="c803d-127">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 <span data-ttu-id="c803d-128">Popisuje třídy, který můžete použít k hostitelské ovládací prvky Windows Forms v aplikaci na základě Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="c803d-128">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c803d-129">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="c803d-129">Related Sections</span></span>  
 [<span data-ttu-id="c803d-130">Migrace a vzájemná funkční spolupráce</span><span class="sxs-lookup"><span data-stu-id="c803d-130">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 <span data-ttu-id="c803d-131">Popisuje vzájemná spolupráce mezi technologie Windows Presentation Foundation a systém Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c803d-131">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>  
  
 [<span data-ttu-id="c803d-132">Návrhář WPF</span><span class="sxs-lookup"><span data-stu-id="c803d-132">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 <span data-ttu-id="c803d-133">Popisuje postup návrhu Windows Presentation Foundation ovládacích prvků v [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c803d-133">Describes how to design Windows Presentation Foundation controls in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>