---
title: "Přehled událostí automatizace uživatelského rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, providers
- UI Automation, events
- clients, UI Automation
- events, UI Automation
- providers, UI Automation
- UI Automation, clients
ms.assetid: 69eebd8b-39ed-40e7-93cc-4457c4caf746
caps.latest.revision: "22"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 9634c686d23503dcb4deae171f0023055c41ce2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-events-overview"></a><span data-ttu-id="6711d-102">Přehled událostí automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="6711d-102">UI Automation Events Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="6711d-103">Tato dokumentace je určena pro rozhraní .NET Framework vývojáře, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] třídy definované v <xref:System.Windows.Automation> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="6711d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6711d-104">Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], najdete v části [rozhraní API systému Windows automatizace: automatizace uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="6711d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]<span data-ttu-id="6711d-105">oznámení o události je klíčovou funkcí pro usnadnění technologie, jako je například čtečky obrazovky a zvětšování zobrazení.</span><span class="sxs-lookup"><span data-stu-id="6711d-105"> event notification is a key feature for assistive technologies such as screen readers and screen magnifiers.</span></span> <span data-ttu-id="6711d-106">Tyto události sledování klientů automatizace uživatelského rozhraní, které jsou aktivovány zprostředkovatelé automatizace uživatelského rozhraní když v se stane něco [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] a využít tyto informace mají obdržet oznámení koncovým uživatelům.</span><span class="sxs-lookup"><span data-stu-id="6711d-106">These UI Automation clients track events that are raised by UI Automation providers when something happens in the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] and use the information to notify end users.</span></span>  
  
 <span data-ttu-id="6711d-107">Zlepšení efektivity tím, že poskytovatel aplikace umožňuje aktivovat události selektivně, v závislosti na tom, jestli všechny klienty přihlášeni k události, nebo vůbec, pokud jsou pro všechny události, naslouchá žádní klienti.</span><span class="sxs-lookup"><span data-stu-id="6711d-107">Efficiency is improved by allowing provider applications to raise events selectively, depending on whether any clients are subscribed to those events, or not at all, if no clients are listening for any events.</span></span>  
  
<a name="Types_of_Events"></a>   
## <a name="types-of-events"></a><span data-ttu-id="6711d-108">Typy událostí</span><span class="sxs-lookup"><span data-stu-id="6711d-108">Types of Events</span></span>  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="6711d-109">události spadají do následujících kategorií.</span><span class="sxs-lookup"><span data-stu-id="6711d-109"> events fall into the following categories.</span></span>  
  
|<span data-ttu-id="6711d-110">Událost</span><span class="sxs-lookup"><span data-stu-id="6711d-110">Event</span></span>|<span data-ttu-id="6711d-111">Popis</span><span class="sxs-lookup"><span data-stu-id="6711d-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6711d-112">Změna vlastnosti</span><span class="sxs-lookup"><span data-stu-id="6711d-112">Property change</span></span>|<span data-ttu-id="6711d-113">Vyvolá, když vlastnost [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element nebo ovládací prvek vzor změny.</span><span class="sxs-lookup"><span data-stu-id="6711d-113">Raised when a property on an [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element or control pattern changes.</span></span> <span data-ttu-id="6711d-114">Například pokud klient potřebuje ke sledování aplikace ovládací prvek zaškrtávací políčko, se můžete zaregistrovat pro naslouchání pro událost změny vlastnosti <xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="6711d-114">For example, if a client needs to monitor an application's check box control, it can register to listen for a property change event on the <xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> property.</span></span> <span data-ttu-id="6711d-115">Pokud ovládací prvek zaškrtávací políčko je zaškrtnuté nebo nezaškrtnuté, zprostředkovatele vyvolá událost, a klient může fungovat podle potřeby.</span><span class="sxs-lookup"><span data-stu-id="6711d-115">When the check box control is checked or unchecked, the provider raises the event and the client can act as necessary.</span></span>|  
|<span data-ttu-id="6711d-116">Element akce</span><span class="sxs-lookup"><span data-stu-id="6711d-116">Element action</span></span>|<span data-ttu-id="6711d-117">Vyvolá, když změnu [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] výsledky z koncového uživatele nebo programové aktivity, například pokud kliknutí na tlačítko nebo vyvolat prostřednictvím <xref:System.Windows.Automation.InvokePattern>.</span><span class="sxs-lookup"><span data-stu-id="6711d-117">Raised when a change in the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] results from end user or programmatic activity; for example, when a button is clicked or invoked through <xref:System.Windows.Automation.InvokePattern>.</span></span>|  
|<span data-ttu-id="6711d-118">Změnu struktury</span><span class="sxs-lookup"><span data-stu-id="6711d-118">Structure change</span></span>|<span data-ttu-id="6711d-119">Vyvolá, když strukturu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromu změny.</span><span class="sxs-lookup"><span data-stu-id="6711d-119">Raised when the structure of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree changes.</span></span> <span data-ttu-id="6711d-120">Struktura změny při vydání nových [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] položky stane viditelné, skrytá nebo odebraných na ploše.</span><span class="sxs-lookup"><span data-stu-id="6711d-120">The structure changes when new [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] items become visible, hidden, or removed on the desktop.</span></span>|  
|<span data-ttu-id="6711d-121">Globální plochy změn</span><span class="sxs-lookup"><span data-stu-id="6711d-121">Global desktop change</span></span>|<span data-ttu-id="6711d-122">Vyvolá, když dojde k akcí globální zájmu klientovi, například když dojde k deaktivaci od jednoho prvku na jiný, nebo při zavření okna.</span><span class="sxs-lookup"><span data-stu-id="6711d-122">Raised when actions of global interest to the client occur, such as when the focus shifts from one element to another, or when a window closes.</span></span>|  
  
 <span data-ttu-id="6711d-123">Některé události neznamenají, že došlo ke změně stavu rozhraní.</span><span class="sxs-lookup"><span data-stu-id="6711d-123">Some events do not necessarily mean that the state of the UI has changed.</span></span> <span data-ttu-id="6711d-124">Například pokud uživatel karty na textového pole a poté kliknutím na tlačítko Aktualizovat pole `TextChangedEvent` se vyvolá, i když uživatel ve skutečnosti nezměnila text.</span><span class="sxs-lookup"><span data-stu-id="6711d-124">For example, if the user tabs to a text entry field and then clicks a button to update the field, a `TextChangedEvent` is raised even if the user did not actually change the text.</span></span> <span data-ttu-id="6711d-125">Při zpracování události, může být nezbytné pro klientskou aplikaci, zkontrolujte, zda nic ve skutečnosti se změnila před provedením akce.</span><span class="sxs-lookup"><span data-stu-id="6711d-125">When processing an event, it may be necessary for a client application to check whether anything has actually changed before taking action.</span></span>  
  
 <span data-ttu-id="6711d-126">Tyto události může dosáhnout i v případě, že stav rozhraní nebylo změněno.</span><span class="sxs-lookup"><span data-stu-id="6711d-126">The following events may be raised even when the state of the UI has not changed.</span></span>  
  
-   <span data-ttu-id="6711d-127">`AutomationPropertyChangedEvent`(v závislosti na vlastnost, která se změnila)</span><span class="sxs-lookup"><span data-stu-id="6711d-127">`AutomationPropertyChangedEvent` (depending on the property that has changed)</span></span>  
  
-   `ElementSelectedEvent`  
  
-   `InvalidatedEvent`  
  
-   `TextChangedEvent`  
  
<a name="UI_Automation_Event_Identifiers"></a>   
## <a name="ui-automation-event-identifiers"></a><span data-ttu-id="6711d-128">Identifikátory událostí automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="6711d-128">UI Automation Event Identifiers</span></span>  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]<span data-ttu-id="6711d-129">události jsou identifikovány <xref:System.Windows.Automation.AutomationEvent> objekty.</span><span class="sxs-lookup"><span data-stu-id="6711d-129"> events are identified by <xref:System.Windows.Automation.AutomationEvent> objects.</span></span> <span data-ttu-id="6711d-130"><xref:System.Windows.Automation.AutomationIdentifier.Id%2A> Vlastnost obsahuje hodnotu, která jednoznačně identifikuje typ události.</span><span class="sxs-lookup"><span data-stu-id="6711d-130">The <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> property contains a value that uniquely identifies the kind of event.</span></span>  
  
 <span data-ttu-id="6711d-131">Možné hodnoty <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> jsou uvedeny v následující tabulce, společně s typu použitého pro argumenty událostí.</span><span class="sxs-lookup"><span data-stu-id="6711d-131">The possible values for <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> are given in the following table, along with the type used for event arguments.</span></span> <span data-ttu-id="6711d-132">Všimněte si, že identifikátory používané klienty a poskytovatelé stejně jako s názvem pole z různých tříd.</span><span class="sxs-lookup"><span data-stu-id="6711d-132">Note that the identifiers used by clients and providers are identically named fields from different classes.</span></span>  
  
|<span data-ttu-id="6711d-133">Identifikátor klienta</span><span class="sxs-lookup"><span data-stu-id="6711d-133">Client Identifier</span></span>|<span data-ttu-id="6711d-134">Identifikátor zprostředkovatele</span><span class="sxs-lookup"><span data-stu-id="6711d-134">Provider identifier</span></span>|<span data-ttu-id="6711d-135">Argumenty typu události</span><span class="sxs-lookup"><span data-stu-id="6711d-135">Event Arguments Type</span></span>|  
|-----------------------|-------------------------|--------------------------|  
|<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AsyncContentLoadedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AsyncContentLoadedEventArgs>|  
|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionPattern.InvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.InvokePattern.InvokedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.LayoutInvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.MenuClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPattern.TextChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPattern.TextSelectionChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.ToolTipClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.MenuClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.MenuOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.WindowPatternIdentifiers.WindowOpenedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationPropertyChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.StructureChangedEventArgs>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowClosedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.WindowClosedEventArgs>|  
  
<a name="UI_Automation_Event_Arguments"></a>   
## <a name="ui-automation-event-arguments"></a><span data-ttu-id="6711d-136">Argumenty událostí automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="6711d-136">UI Automation Event Arguments</span></span>  
 <span data-ttu-id="6711d-137">Následující třídy zapouzdřovat argumenty událostí.</span><span class="sxs-lookup"><span data-stu-id="6711d-137">The following classes encapsulate event arguments.</span></span>  
  
|<span data-ttu-id="6711d-138">Třída</span><span class="sxs-lookup"><span data-stu-id="6711d-138">Class</span></span>|<span data-ttu-id="6711d-139">Popis</span><span class="sxs-lookup"><span data-stu-id="6711d-139">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Automation.AsyncContentLoadedEventArgs>|<span data-ttu-id="6711d-140">Obsahuje informace o asynchronní načítání obsah, včetně Procento načítání byla dokončena.</span><span class="sxs-lookup"><span data-stu-id="6711d-140">Contains information about the asynchronous loading of content, including the percentage of loading completed.</span></span>|  
|<xref:System.Windows.Automation.AutomationEventArgs>|<span data-ttu-id="6711d-141">Obsahuje informace o jednoduchá událost, která vyžaduje žádná další data.</span><span class="sxs-lookup"><span data-stu-id="6711d-141">Contains information about a simple event that requires no extra data.</span></span>|  
|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<span data-ttu-id="6711d-142">Obsahuje informace o změně v zaměření pro vstup od jednoho prvku na jiný.</span><span class="sxs-lookup"><span data-stu-id="6711d-142">Contains information about a change in input focus from one element to another.</span></span> <span data-ttu-id="6711d-143">Události tohoto typu jsou vydané [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] systému není poskytovateli.</span><span class="sxs-lookup"><span data-stu-id="6711d-143">Events of this type are raised by the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] system, not by providers.</span></span>|  
|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<span data-ttu-id="6711d-144">Obsahuje informace o změnu v hodnotě vlastnosti vzorku element nebo ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="6711d-144">Contains information about a change in a property value of an element or control pattern.</span></span>|  
|<xref:System.Windows.Automation.StructureChangedEventArgs>|<span data-ttu-id="6711d-145">Obsahuje informace o změnu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromu.</span><span class="sxs-lookup"><span data-stu-id="6711d-145">Contains information about a change in the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree.</span></span>|  
|<xref:System.Windows.Automation.WindowClosedEventArgs>|<span data-ttu-id="6711d-146">Obsahuje informace o zavření okna.</span><span class="sxs-lookup"><span data-stu-id="6711d-146">Contains information about a window closing.</span></span>|  
  
 <span data-ttu-id="6711d-147">Všechny třídy událostí argument obsahovat <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A> člen.</span><span class="sxs-lookup"><span data-stu-id="6711d-147">All the event argument classes contain an <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A> member.</span></span> <span data-ttu-id="6711d-148">Tento identifikátor je zapouzdřené v <xref:System.Windows.Automation.AutomationEvent>.</span><span class="sxs-lookup"><span data-stu-id="6711d-148">This identifier is encapsulated in an <xref:System.Windows.Automation.AutomationEvent>.</span></span>  
  
 <span data-ttu-id="6711d-149"><xref:System.Windows.Automation.AutomationEvent> Objekty použité k identifikaci událostí jsou získány zprostředkovatelé z pole v <xref:System.Windows.Automation.AutomationElementIdentifiers> a řídit vzor identifikátor třídy, jako <xref:System.Windows.Automation.DockPatternIdentifiers>.</span><span class="sxs-lookup"><span data-stu-id="6711d-149">The <xref:System.Windows.Automation.AutomationEvent> objects used to identify events are obtained by providers from fields in <xref:System.Windows.Automation.AutomationElementIdentifiers> and control pattern identifier classes such as <xref:System.Windows.Automation.DockPatternIdentifiers>.</span></span> <span data-ttu-id="6711d-150">Ekvivalentní pole jsou získány pomocí klientských aplikací z pole v <xref:System.Windows.Automation.AutomationElement> a řídit vzor třídy, jako <xref:System.Windows.Automation.DockPattern>.</span><span class="sxs-lookup"><span data-stu-id="6711d-150">The equivalent fields are obtained by client applications from fields in <xref:System.Windows.Automation.AutomationElement> and control pattern classes such as <xref:System.Windows.Automation.DockPattern>.</span></span>  
  
 <span data-ttu-id="6711d-151">Seznam identifikátorů událostí najdete v tématu [událostí automatizace uživatelského rozhraní pro klienty](../../../docs/framework/ui-automation/ui-automation-events-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6711d-151">For a list of event identifiers, see [UI Automation Events for Clients](../../../docs/framework/ui-automation/ui-automation-events-for-clients.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6711d-152">Viz také</span><span class="sxs-lookup"><span data-stu-id="6711d-152">See Also</span></span>  
 [<span data-ttu-id="6711d-153">Události automatizace uživatelského rozhraní pro klienty</span><span class="sxs-lookup"><span data-stu-id="6711d-153">UI Automation Events for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-events-for-clients.md)  
 [<span data-ttu-id="6711d-154">Implementace zprostředkovatele automatizace uživatelského rozhraní na straně serveru</span><span class="sxs-lookup"><span data-stu-id="6711d-154">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)  
 [<span data-ttu-id="6711d-155">Přihlásit k odběru událostí automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="6711d-155">Subscribe to UI Automation Events</span></span>](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)