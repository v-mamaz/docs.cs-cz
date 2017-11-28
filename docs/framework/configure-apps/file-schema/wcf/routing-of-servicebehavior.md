---
title: "&lt;routing&gt; – &lt;serviceBehavior&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4e5c27b2b276e6659680dabfd9460c6d072bad3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="ltroutinggt-of-ltservicebehaviorgt"></a><span data-ttu-id="0d012-102">&lt;routing&gt; – &lt;serviceBehavior&gt;</span><span class="sxs-lookup"><span data-stu-id="0d012-102">&lt;routing&gt; of &lt;serviceBehavior&gt;</span></span>
<span data-ttu-id="0d012-103">Poskytuje běhové přístup ke službě Směrování a povolit dynamické změnu konfigurace směrování.</span><span class="sxs-lookup"><span data-stu-id="0d012-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="0d012-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0d012-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0d012-105">\<chování ></span><span class="sxs-lookup"><span data-stu-id="0d012-105">\<behaviors></span></span>  
<span data-ttu-id="0d012-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0d012-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0d012-107">\<chování ></span><span class="sxs-lookup"><span data-stu-id="0d012-107">\<behavior></span></span>  
<span data-ttu-id="0d012-108">\<směrování ></span><span class="sxs-lookup"><span data-stu-id="0d012-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d012-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0d012-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String" 
               routeOnHeadersOnly="Boolean" 
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d012-110">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="0d012-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0d012-111">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="0d012-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d012-112">Atributy</span><span class="sxs-lookup"><span data-stu-id="0d012-112">Attributes</span></span>  
  
|<span data-ttu-id="0d012-113">Atribut</span><span class="sxs-lookup"><span data-stu-id="0d012-113">Attribute</span></span>|<span data-ttu-id="0d012-114">Popis</span><span class="sxs-lookup"><span data-stu-id="0d012-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d012-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="0d012-115">filterTable</span></span>|<span data-ttu-id="0d012-116">Řetězec, který určuje název směrovací tabulka, která obsahuje filtry k vyhodnocení pomocí služby směrování.</span><span class="sxs-lookup"><span data-stu-id="0d012-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="0d012-117">Tato hodnota musí odpovídat `name` atribut [ \<filterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) element v [ \<filterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) části.</span><span class="sxs-lookup"><span data-stu-id="0d012-117">This value must match the `name` attribute of a [\<filterTable>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) element in the [\<filterTables>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) section.</span></span>|  
|<span data-ttu-id="0d012-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="0d012-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="0d012-119">Logická hodnota, která určuje, zda bude text zprávy a záhlaví nebo pouze záhlaví zkontrolujte filtru.</span><span class="sxs-lookup"><span data-stu-id="0d012-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="0d012-120">Výchozí hodnota je `true`.</span><span class="sxs-lookup"><span data-stu-id="0d012-120">The default is `true`.</span></span>|  
|<span data-ttu-id="0d012-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="0d012-121">soapProcessingEnabled</span></span>|<span data-ttu-id="0d012-122">Logická hodnota, která určuje, zda má vzniknout zpracování protokolu SOAP.</span><span class="sxs-lookup"><span data-stu-id="0d012-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d012-123">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="0d012-123">Child Elements</span></span>  
 <span data-ttu-id="0d012-124">Žádné</span><span class="sxs-lookup"><span data-stu-id="0d012-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d012-125">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="0d012-125">Parent Elements</span></span>  
  
|<span data-ttu-id="0d012-126">Prvek</span><span class="sxs-lookup"><span data-stu-id="0d012-126">Element</span></span>|<span data-ttu-id="0d012-127">Popis</span><span class="sxs-lookup"><span data-stu-id="0d012-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d012-128">\<chování ></span><span class="sxs-lookup"><span data-stu-id="0d012-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="0d012-129">Určuje chování element.</span><span class="sxs-lookup"><span data-stu-id="0d012-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d012-130">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0d012-130">Remarks</span></span>  
 <span data-ttu-id="0d012-131">Při přidání do konfigurace chování služby, tento element konfigurace umožňuje směrování pro službu.</span><span class="sxs-lookup"><span data-stu-id="0d012-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="0d012-132">Můžete zadat skutečný směrovací tabulky pro použití službou v tomto elementu.</span><span class="sxs-lookup"><span data-stu-id="0d012-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="0d012-133">Pomocí tento konfigurační oddíl, můžete změnit nastavení směrování za chodu při změně vzor vaše nasazení.</span><span class="sxs-lookup"><span data-stu-id="0d012-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="0d012-134">V době běhu směrování rozšíření můžete zaregistrovat pomocí nového nastavení směrování a služba Směrování začne, pomocí informací o aktualizovanou konfiguraci nových zpráv a relace, a nechat neukládají zprávy nebo relací pomocí ať pravidla byly v místní při jejich spuštění.</span><span class="sxs-lookup"><span data-stu-id="0d012-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="0d012-135">To vám umožňuje provést bezpečné relace, recyklaci bez změny konfigurace služby směrování za běhu.</span><span class="sxs-lookup"><span data-stu-id="0d012-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
  