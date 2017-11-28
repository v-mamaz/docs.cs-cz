---
title: '&lt;standardEndpoints&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d62153d7-a6e6-462a-a784-cca61e9c2ba1
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cd4de65da3dcce6360fef6e404b0951dbbd26336
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="ltstandardendpointsgt"></a><span data-ttu-id="a2387-102">&lt;standardEndpoints&gt;</span><span class="sxs-lookup"><span data-stu-id="a2387-102">&lt;standardEndpoints&gt;</span></span>
<span data-ttu-id="a2387-103">Tento konfigurační oddíl umožňuje definovat kolekce standardních koncových bodů, které jsou opakovaně použitelné předem nakonfigurované koncové body.</span><span class="sxs-lookup"><span data-stu-id="a2387-103">This configuration section allows you to define a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="a2387-104">Koncový bod standardní bude mít jeden nebo více adresy, vazby a atributy kontrakt nastavte na pevnou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="a2387-104">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="a2387-105">Například v koncový bod zjišťování vyřešen kontrakt.</span><span class="sxs-lookup"><span data-stu-id="a2387-105">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="a2387-106">Standardní koncové body můžete taky rozšířit koncový bod služby s nové vlastnosti podobná definování vlastní vazby.</span><span class="sxs-lookup"><span data-stu-id="a2387-106">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>  
  
 <span data-ttu-id="a2387-107">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a2387-107">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2387-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a2387-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>  
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2387-109">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="a2387-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a2387-110">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="a2387-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2387-111">Atributy</span><span class="sxs-lookup"><span data-stu-id="a2387-111">Attributes</span></span>  
 <span data-ttu-id="a2387-112">Žádné</span><span class="sxs-lookup"><span data-stu-id="a2387-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a2387-113">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="a2387-113">Child Elements</span></span>  
  
|<span data-ttu-id="a2387-114">Prvek</span><span class="sxs-lookup"><span data-stu-id="a2387-114">Element</span></span>|<span data-ttu-id="a2387-115">Popis</span><span class="sxs-lookup"><span data-stu-id="a2387-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2387-116">\<announcementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="a2387-116">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="a2387-117">Definuje standardní koncový bod s pevnou oznámení kontrakt.</span><span class="sxs-lookup"><span data-stu-id="a2387-117">Defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="a2387-118">Služba může volitelně informovat jeho dostupnost zaslat e online a offline oznámení, pokud je otevřen nebo uzavřený v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="a2387-118">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="a2387-119">A [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] služby určuje koncových bodů oznámení v [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) elementu a používá AnnouncementClient k provedení hlášení.</span><span class="sxs-lookup"><span data-stu-id="a2387-119">A [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="a2387-120">Chtějí naslouchat pro oznámení z jiné služby skutečně funguje jako klient [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] služba; proto budete muset nakonfigurovat koncových bodů oznámení pro daného klienta v [ \<služby >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) části.</span><span class="sxs-lookup"><span data-stu-id="a2387-120">A client wishing to listen for the announcement from other service is actually acting as a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>|  
|[<span data-ttu-id="a2387-121">\<discoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="a2387-121">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="a2387-122">Definuje standardní koncový bod s pevnou zjišťování kontrakt.</span><span class="sxs-lookup"><span data-stu-id="a2387-122">Defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="a2387-123">Při přidání konfigurace služby, určuje, kde přijímat zprávy zjišťování.</span><span class="sxs-lookup"><span data-stu-id="a2387-123">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="a2387-124">Po přidání do konfigurace klienta Určuje, kam má posílat dotazy zjišťování.</span><span class="sxs-lookup"><span data-stu-id="a2387-124">When added to the client configuration it specifies where to send the discovery queries.</span></span>|  
|[<span data-ttu-id="a2387-125">\<dynamicEndpoint ></span><span class="sxs-lookup"><span data-stu-id="a2387-125">\<dynamicEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/dynamicendpoint.md)|<span data-ttu-id="a2387-126">Tento element konfigurace definuje standardní koncový bod, který obsahuje informace o povolení aplikace fungovat jako klient programu, můžete najít adresa koncového bodu dynamicky za běhu.</span><span class="sxs-lookup"><span data-stu-id="a2387-126">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
|[<span data-ttu-id="a2387-127">\<mexEndpoint ></span><span class="sxs-lookup"><span data-stu-id="a2387-127">\<mexEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/mexendpoint.md)|<span data-ttu-id="a2387-128">Definuje standardní koncový bod s pevnou IMetadataExchange kontrakt.</span><span class="sxs-lookup"><span data-stu-id="a2387-128">Defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="a2387-129">Vzhledem k tomu, že všechny koncové body metadat serveru exchange zadejte IMetadataExchange jako jejich kontrakt, můžete použít tento standardní bod místo definování jeden pro sami.</span><span class="sxs-lookup"><span data-stu-id="a2387-129">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>|  
|[<span data-ttu-id="a2387-130">\<udpAnnoucementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="a2387-130">\<udpAnnoucementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)|<span data-ttu-id="a2387-131">Definuje standardní koncový bod, který je používán služby pro odeslání zpráv oznámení vazbu UDP.</span><span class="sxs-lookup"><span data-stu-id="a2387-131">Defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="a2387-132">Má pevnou kontraktu a podporuje dvě verze zjišťování.</span><span class="sxs-lookup"><span data-stu-id="a2387-132">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="a2387-133">Kromě toho má vazbu pevné UDP a adresu výchozí hodnotu podle specifikace WS-Discovery (WS-Discovery. dubna 2005 nebo WS-Discovery verze 1.1).</span><span class="sxs-lookup"><span data-stu-id="a2387-133">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="a2387-134">Můžete zadat adresu vícesměrového vysílání pro odesílání a přijímání zpráv oznámení.</span><span class="sxs-lookup"><span data-stu-id="a2387-134">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>|  
|[<span data-ttu-id="a2387-135">\<udpDiscoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="a2387-135">\<udpDiscoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md)|<span data-ttu-id="a2387-136">Definuje standardní koncový bod, který je předem nakonfigurovaný pro operace zjišťování přes UDP vícesměrového vysílání vazby.</span><span class="sxs-lookup"><span data-stu-id="a2387-136">Defines a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="a2387-137">Tento koncový bod má pevnou kontraktu a podporuje dvě verze protokolu WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="a2387-137">This endpoint has a fixed contract and supports two WS-Discovery protocol versions.</span></span> <span data-ttu-id="a2387-138">Kromě toho má pevnou vazba UDP a výchozí adresu podle specifikace WS-Discovery (WS-Discovery. dubna 2005 nebo V1.1 WS-Discovery).</span><span class="sxs-lookup"><span data-stu-id="a2387-138">In addition, it has a fixed UDP binding and a default address as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery V1.1).</span></span>|  
|[<span data-ttu-id="a2387-139">\<webHttpEndpoint ></span><span class="sxs-lookup"><span data-stu-id="a2387-139">\<webHttpEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpendpoint.md)|<span data-ttu-id="a2387-140">Definuje standardní koncový bod s pevným [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) vazby, který automaticky přidá [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) chování.</span><span class="sxs-lookup"><span data-stu-id="a2387-140">Defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="a2387-141">Při zápisu služby REST, použijte tento koncový bod.</span><span class="sxs-lookup"><span data-stu-id="a2387-141">Use this endpoint when writing a REST service.</span></span>|  
|[<span data-ttu-id="a2387-142">\<webScriptEndpoint ></span><span class="sxs-lookup"><span data-stu-id="a2387-142">\<webScriptEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webscriptendpoint.md)|<span data-ttu-id="a2387-143">Definuje standardní koncový bod s pevným [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) vazby, který automaticky přidá [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) chování.</span><span class="sxs-lookup"><span data-stu-id="a2387-143">Defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="a2387-144">Když vytváříte službu, která je volána z aplikace ASP.NET AJAX, použijte tento koncový bod.</span><span class="sxs-lookup"><span data-stu-id="a2387-144">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>|  
|[<span data-ttu-id="a2387-145">\<workflowControlEndpoint ></span><span class="sxs-lookup"><span data-stu-id="a2387-145">\<workflowControlEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowcontrolendpoint.md)|<span data-ttu-id="a2387-146">Definuje standardní koncový bod pro řízení provádění instancí pracovního postupu (vytvoření, spuštění, pozastavení, ukončit, atd).</span><span class="sxs-lookup"><span data-stu-id="a2387-146">Defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2387-147">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="a2387-147">Parent Elements</span></span>  
  
|<span data-ttu-id="a2387-148">Prvek</span><span class="sxs-lookup"><span data-stu-id="a2387-148">Element</span></span>|<span data-ttu-id="a2387-149">Popis</span><span class="sxs-lookup"><span data-stu-id="a2387-149">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2387-150">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a2387-150">\<system.ServiceModel></span></span>|<span data-ttu-id="a2387-151">Kořenový element všechny konfigurační prvky WCF.</span><span class="sxs-lookup"><span data-stu-id="a2387-151">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2387-152">Viz také</span><span class="sxs-lookup"><span data-stu-id="a2387-152">See Also</span></span>  
 [<span data-ttu-id="a2387-153">Standardní koncové body</span><span class="sxs-lookup"><span data-stu-id="a2387-153">Standard Endpoints</span></span>](../../../../../docs/framework/wcf/feature-details/standard-endpoints.md)