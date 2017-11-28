---
title: "Základní programování WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- basic programming [WCF]
- WCF [WCF], basic programming
- WCF [WCF], programming
- Windows Communication Foundation [WCF], basic programming
- Windows Communication Foundation [WCF], programming
ms.assetid: 3ae3d498-f43c-4ecc-8cc0-6cbe36b62593
caps.latest.revision: "31"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fa43705fd20a60512ca4c460bb3048220aa1e193
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="basic-wcf-programming"></a><span data-ttu-id="f81c3-102">Základní programování WCF</span><span class="sxs-lookup"><span data-stu-id="f81c3-102">Basic WCF Programming</span></span>
<span data-ttu-id="f81c3-103">Tato část představuje základy pro vytvoření [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="f81c3-103">This section presents the fundamentals for creating [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f81c3-104">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="f81c3-104">In This Section</span></span>  
 [<span data-ttu-id="f81c3-105">Základní programovací životní cyklus</span><span class="sxs-lookup"><span data-stu-id="f81c3-105">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 <span data-ttu-id="f81c3-106">Popisuje životní cyklus návrhu, vytváření a nasazování [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] služby a klientské aplikace.</span><span class="sxs-lookup"><span data-stu-id="f81c3-106">Describes the lifecycle of designing, building, and deploying [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service and client applications.</span></span>  
  
 [<span data-ttu-id="f81c3-107">Navrhování a implementace služeb</span><span class="sxs-lookup"><span data-stu-id="f81c3-107">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
 <span data-ttu-id="f81c3-108">Popisuje postup návrhu a implementace kontraktu služby, zvolte vzorce výměny zpráv, zadejte chyba – kontrakt a další základní aspekty služby.</span><span class="sxs-lookup"><span data-stu-id="f81c3-108">Describes how to design and implement a service contract, choose a message exchange pattern, specify a fault contract, and other basic aspects of services.</span></span>  
  
 [<span data-ttu-id="f81c3-109">Konfigurace služeb</span><span class="sxs-lookup"><span data-stu-id="f81c3-109">Configuring Services</span></span>](../../../docs/framework/wcf/configuring-services.md)  
 <span data-ttu-id="f81c3-110">Popisuje postup konfigurace [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] službě pro podporu požadavků kontrakt, přizpůsobení chování místní runtime a označuje adresu k publikování služby.</span><span class="sxs-lookup"><span data-stu-id="f81c3-110">Describes how to configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service to support the contract requirements, customize local runtime behavior, and indicate the address to publish the service.</span></span>  
  
 [<span data-ttu-id="f81c3-111">Služby hostování</span><span class="sxs-lookup"><span data-stu-id="f81c3-111">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
 <span data-ttu-id="f81c3-112">Popisuje základní informace o hostování služeb v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="f81c3-112">Describes the basics of hosting services in an application.</span></span>  
  
 [<span data-ttu-id="f81c3-113">Sestavování klientů</span><span class="sxs-lookup"><span data-stu-id="f81c3-113">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
 <span data-ttu-id="f81c3-114">Popisuje, jak získat metadata ze služeb, která na převod [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kód klienta, popisovač problémy se zabezpečením a sestavení, konfiguraci a hostitele [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klienta.</span><span class="sxs-lookup"><span data-stu-id="f81c3-114">Describes how to obtain metadata from services, convert that into [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client code, handle security issues, and build, configure, and host an [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client.</span></span>  
  
 [<span data-ttu-id="f81c3-115">Úvod do rozšíření</span><span class="sxs-lookup"><span data-stu-id="f81c3-115">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
 <span data-ttu-id="f81c3-116">Popisuje, jak rozšířit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] při vytváření vlastních řešení.</span><span class="sxs-lookup"><span data-stu-id="f81c3-116">Describes how to extend [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] to create custom solutions.</span></span>  
  
 [<span data-ttu-id="f81c3-117">Rychlý start řešení potíží s WCF</span><span class="sxs-lookup"><span data-stu-id="f81c3-117">WCF Troubleshooting Quickstart</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 <span data-ttu-id="f81c3-118">Popisuje některé z nejběžnějších problémů, ke kterým došlo, co můžete dělat je můžete vyřešit a kde najít další informace o problému.</span><span class="sxs-lookup"><span data-stu-id="f81c3-118">Describes some of the most common issues that occur, what you can do to solve them, and where to locate more information about the issue.</span></span>  
  
 [<span data-ttu-id="f81c3-119">WCF a ASP.NET Web API</span><span class="sxs-lookup"><span data-stu-id="f81c3-119">WCF and ASP.NET Web API</span></span>](../../../docs/framework/wcf/wcf-and-aspnet-web-api.md)  
 <span data-ttu-id="f81c3-120">Popisuje dvě technologie, jak se vztahují k vzájemně a jejich použití.</span><span class="sxs-lookup"><span data-stu-id="f81c3-120">Discusses the two technologies, how they relate to each other, and when to use them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f81c3-121">Odkaz</span><span class="sxs-lookup"><span data-stu-id="f81c3-121">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="f81c3-122">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="f81c3-122">Related Sections</span></span>  
 [<span data-ttu-id="f81c3-123">Požadavky na systém</span><span class="sxs-lookup"><span data-stu-id="f81c3-123">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)  
  
 [<span data-ttu-id="f81c3-124">Koncepční přehled</span><span class="sxs-lookup"><span data-stu-id="f81c3-124">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
  
 [<span data-ttu-id="f81c3-125">Kurz Začínáme</span><span class="sxs-lookup"><span data-stu-id="f81c3-125">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="f81c3-126">Pokyny a osvědčené postupy</span><span class="sxs-lookup"><span data-stu-id="f81c3-126">Guidelines and Best Practices</span></span>](../../../docs/framework/wcf/guidelines-and-best-practices.md)  
  
 [<span data-ttu-id="f81c3-127">Nástroje služby Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f81c3-127">Windows Communication Foundation Tools</span></span>](../../../docs/framework/wcf/tools.md)  
  
 [<span data-ttu-id="f81c3-128">Ukázky Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f81c3-128">Windows Communication Foundation Samples</span></span>](http://msdn.microsoft.com/en-us/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [<span data-ttu-id="f81c3-129">Začínáme</span><span class="sxs-lookup"><span data-stu-id="f81c3-129">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
  
 [<span data-ttu-id="f81c3-130">Hostování IIS pomocí vloženého kódu</span><span class="sxs-lookup"><span data-stu-id="f81c3-130">IIS Hosting Using Inline Code</span></span>](../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)  
  
 [<span data-ttu-id="f81c3-131">Vlastní hostování</span><span class="sxs-lookup"><span data-stu-id="f81c3-131">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)