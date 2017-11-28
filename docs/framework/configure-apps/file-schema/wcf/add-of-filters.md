---
title: "&lt;add&gt; – &lt;filters&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7143216b6b195c59077b004f8aaa1b17a249fbc3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltfiltersgt"></a><span data-ttu-id="cdc80-102">&lt;add&gt; – &lt;filters&gt;</span><span class="sxs-lookup"><span data-stu-id="cdc80-102">&lt;add&gt; of &lt;filters&gt;</span></span>
<span data-ttu-id="cdc80-103">Filtr XPath, který určuje typ zprávy do protokolu.</span><span class="sxs-lookup"><span data-stu-id="cdc80-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
 <span data-ttu-id="cdc80-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cdc80-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cdc80-105">\<diagnostické ></span><span class="sxs-lookup"><span data-stu-id="cdc80-105">\<diagnostic></span></span>  
<span data-ttu-id="cdc80-106">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="cdc80-106">\<messageLogging></span></span>  
<span data-ttu-id="cdc80-107">\<Filtry ></span><span class="sxs-lookup"><span data-stu-id="cdc80-107">\<filters></span></span>  
<span data-ttu-id="cdc80-108">\<Přidat ></span><span class="sxs-lookup"><span data-stu-id="cdc80-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdc80-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cdc80-109">Syntax</span></span>  
  
```xml  
<filters>  
   <add filter="String"/>  
</filters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cdc80-110">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="cdc80-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cdc80-111">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="cdc80-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cdc80-112">Atributy</span><span class="sxs-lookup"><span data-stu-id="cdc80-112">Attributes</span></span>  
  
|<span data-ttu-id="cdc80-113">Atribut</span><span class="sxs-lookup"><span data-stu-id="cdc80-113">Attribute</span></span>|<span data-ttu-id="cdc80-114">Popis</span><span class="sxs-lookup"><span data-stu-id="cdc80-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cdc80-115">filtrování</span><span class="sxs-lookup"><span data-stu-id="cdc80-115">filter</span></span>|<span data-ttu-id="cdc80-116">Řetězec, který určuje dotazu v dokumentu XML definované výraz XPath 1.0.</span><span class="sxs-lookup"><span data-stu-id="cdc80-116">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="cdc80-117">Další informace naleznete v tématu <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="cdc80-117">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cdc80-118">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="cdc80-118">Child Elements</span></span>  
 <span data-ttu-id="cdc80-119">Žádné</span><span class="sxs-lookup"><span data-stu-id="cdc80-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cdc80-120">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="cdc80-120">Parent Elements</span></span>  
  
|<span data-ttu-id="cdc80-121">Prvek</span><span class="sxs-lookup"><span data-stu-id="cdc80-121">Element</span></span>|<span data-ttu-id="cdc80-122">Popis</span><span class="sxs-lookup"><span data-stu-id="cdc80-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cdc80-123">\<Filtry ></span><span class="sxs-lookup"><span data-stu-id="cdc80-123">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|<span data-ttu-id="cdc80-124">Obsahuje kolekci filtrů XPath použít k řízení, jaký typ zprávy přihlášen.</span><span class="sxs-lookup"><span data-stu-id="cdc80-124">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdc80-125">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cdc80-125">Remarks</span></span>  
 <span data-ttu-id="cdc80-126">Filtry se použijí jenom v přenosové vrstvě určeného `logMessagesAtTransportLevel` je `true`.</span><span class="sxs-lookup"><span data-stu-id="cdc80-126">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="cdc80-127">Protokolování úrovně a poškozených zpráv služby nemá vliv filtry.</span><span class="sxs-lookup"><span data-stu-id="cdc80-127">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="cdc80-128">Chcete-li přidat filtr do kolekce, použijte `add` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="cdc80-128">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="cdc80-129">Když jsou definovány jeden nebo více filtrů, jsou protokolovány pouze zprávy, které odpovídají alespoň jeden z filtrů.</span><span class="sxs-lookup"><span data-stu-id="cdc80-129">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="cdc80-130">Pokud je definován žádný filtr, všechny zprávy předávat.</span><span class="sxs-lookup"><span data-stu-id="cdc80-130">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="cdc80-131">Filtry podporovat úplnou syntaxí XPath a aplikují v pořadí, ve kterém se zobrazují v konfiguračním souboru.</span><span class="sxs-lookup"><span data-stu-id="cdc80-131">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="cdc80-132">Správnou syntaxi filtr výsledkem výjimka v konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="cdc80-132">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="cdc80-133">Následuje příklad, jak nakonfigurovat filtr, který zaznamenává jen zprávy, které máte oddíl hlavičky SOAP.</span><span class="sxs-lookup"><span data-stu-id="cdc80-133">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdc80-134">Příklad</span><span class="sxs-lookup"><span data-stu-id="cdc80-134">Example</span></span>  
 <span data-ttu-id="cdc80-135">Následuje příklad, jak nakonfigurovat filtr, který zaznamenává jen zprávy, které máte oddíl hlavičky SOAP.</span><span class="sxs-lookup"><span data-stu-id="cdc80-135">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"  
     logMalformedMessages="true" logMessagesAtServiceLevel="true"  
     logMessagesAtTransportLevel="true" maxMessagesToLog="420">  
     <filters>  
        <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
                        /soap:Envelope/soap:Headers  
        </add>  
     </filters>  
</messageLogging>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdc80-136">Viz také</span><span class="sxs-lookup"><span data-stu-id="cdc80-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>  
 <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>  
 [<span data-ttu-id="cdc80-137">Konfigurace protokolování zpráv</span><span class="sxs-lookup"><span data-stu-id="cdc80-137">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [<span data-ttu-id="cdc80-138">Konfigurace protokolování zpráv</span><span class="sxs-lookup"><span data-stu-id="cdc80-138">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [<span data-ttu-id="cdc80-139">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="cdc80-139">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)