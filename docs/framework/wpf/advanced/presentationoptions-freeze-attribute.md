---
title: "PresentationOptions:Freeze – atribut"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d8f1a876f65941afb159d4c3d8904ab4426d9177
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="4ce1c-102">PresentationOptions:Freeze – atribut</span><span class="sxs-lookup"><span data-stu-id="4ce1c-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="4ce1c-103">Nastaví <xref:System.Windows.Freezable.IsFrozen%2A> stavu na `true` na obsahující <xref:System.Windows.Freezable> elementu.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="4ce1c-104">Výchozí chování <xref:System.Windows.Freezable> bez `PresentationOptions:Freeze` zadaný atribut je, že <xref:System.Windows.Freezable.IsFrozen%2A> je `false` v doba načítání a závisí na Obecné <xref:System.Windows.Freezable> chování za běhu.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="4ce1c-105">Použití atributu XAML</span><span class="sxs-lookup"><span data-stu-id="4ce1c-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="4ce1c-106">Hodnoty XAML</span><span class="sxs-lookup"><span data-stu-id="4ce1c-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="4ce1c-107">Předpony oboru názvů XML, který může být jakýkoli platnou předponu řetězec podle specifikace XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="4ce1c-108">Předpona `PresentationOptions` se používá pro potřeby identifikace v této dokumentaci.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="4ce1c-109">Element, který vytvoří všechny odvozené třídy z <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ce1c-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4ce1c-110">Remarks</span></span>  
 <span data-ttu-id="4ce1c-111">`Freeze` Se pouze atribut, nebo jiné programovací element definovaný v `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` obor názvů XML.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="4ce1c-112">`Freeze` Atribut existuje v tomto oboru názvů speciální konkrétně tak, aby ho lze označit jako Ignorovatelná pomocí [mc: Ignorovatelná atribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) jako součást deklarací kořenový element.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="4ce1c-113">Z důvodu, `Freeze` musí být schopen být Ignorovatelná není protože všechny [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementace zpracovatelů dokážou zmrazení <xref:System.Windows.Freezable> v okamžiku načtení; tato funkce není součástí [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specifikace.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="4ce1c-114">Možnost zpracování `Freeze` atribut je konkrétně založená na [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesor, který zpracovává [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pro kompilované aplikace.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="4ce1c-115">Jakákoli třída nepodporuje atribut a atribut syntaxe není rozšiřitelné nebo změn.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="4ce1c-116">Při implementaci vlastní [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesor můžete paralelní zmrazení chování [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesoru při zpracování `Freeze` atributu u <xref:System.Windows.Freezable> elementy v okamžiku načtení.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="4ce1c-117">Žádnou hodnotu pro `Freeze` atribut jiné než `true` (ne velká a malá písmena) generuje chybu v době zatížení.</span><span class="sxs-lookup"><span data-stu-id="4ce1c-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="4ce1c-118">(Určení `Freeze` atribut jako `false` není chybu, ale který je už výchozí, takže nastavení `false` se nic nestane.).</span><span class="sxs-lookup"><span data-stu-id="4ce1c-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce1c-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="4ce1c-119">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 [<span data-ttu-id="4ce1c-120">Zmrazitelné objekty – přehled</span><span class="sxs-lookup"><span data-stu-id="4ce1c-120">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="4ce1c-121">MC: Ignorovatelná atribut</span><span class="sxs-lookup"><span data-stu-id="4ce1c-121">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)