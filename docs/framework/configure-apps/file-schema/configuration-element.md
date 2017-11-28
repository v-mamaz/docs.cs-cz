---
title: "&lt;konfigurace&gt; – element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2241f3e835defe308b94d0cbad96020518dfd19b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="configuration-element"></a><span data-ttu-id="6f84b-102">\<Konfigurace > elementu</span><span class="sxs-lookup"><span data-stu-id="6f84b-102">\<configuration> element</span></span>

<span data-ttu-id="6f84b-103">Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f84b-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="6f84b-104">**\<Konfigurace >**</span><span class="sxs-lookup"><span data-stu-id="6f84b-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6f84b-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6f84b-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="6f84b-106">Atributy</span><span class="sxs-lookup"><span data-stu-id="6f84b-106">Attributes</span></span>

<span data-ttu-id="6f84b-107">Žádné</span><span class="sxs-lookup"><span data-stu-id="6f84b-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="6f84b-108">Nadřazený element</span><span class="sxs-lookup"><span data-stu-id="6f84b-108">Parent element</span></span>

<span data-ttu-id="6f84b-109">Žádné</span><span class="sxs-lookup"><span data-stu-id="6f84b-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="6f84b-110">Podřízené prvky</span><span class="sxs-lookup"><span data-stu-id="6f84b-110">Child elements</span></span>

|     | <span data-ttu-id="6f84b-111">Popis</span><span class="sxs-lookup"><span data-stu-id="6f84b-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6f84b-112">**\<assemblybinding – >**</span><span class="sxs-lookup"><span data-stu-id="6f84b-112">**\<assemblyBinding>**</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="6f84b-113">Určuje sestavení vazby zásady na úrovni konfigurace.</span><span class="sxs-lookup"><span data-stu-id="6f84b-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="6f84b-114">**\<spuštění >** schéma nastavení</span><span class="sxs-lookup"><span data-stu-id="6f84b-114">**\<startup>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/startup/index.md) | <span data-ttu-id="6f84b-115">Všechny elementy ve schématu nastavení spuštění.</span><span class="sxs-lookup"><span data-stu-id="6f84b-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="6f84b-116">**\<modul runtime >** schéma nastavení</span><span class="sxs-lookup"><span data-stu-id="6f84b-116">**\<runtime>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/runtime/index.md) | <span data-ttu-id="6f84b-117">Všechny elementy ve schématu nastavení modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="6f84b-117">All elements in the runtime settings schema.</span></span> |
| [<span data-ttu-id="6f84b-118">**\<System.Runtime.Remoting >** schéma nastavení</span><span class="sxs-lookup"><span data-stu-id="6f84b-118">**\<system.runtime.remoting>** Settings Schema</span></span>](http://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | <span data-ttu-id="6f84b-119">Všechny elementy ve schématu nastavení vzdálené komunikace.</span><span class="sxs-lookup"><span data-stu-id="6f84b-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="6f84b-120">**\<system.Net >** schéma nastavení</span><span class="sxs-lookup"><span data-stu-id="6f84b-120">**\<system.Net>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/network/index.md) | <span data-ttu-id="6f84b-121">Všechny elementy ve schématu nastavení sítě.</span><span class="sxs-lookup"><span data-stu-id="6f84b-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="6f84b-122">**\<cryptographySettings – >** schéma nastavení</span><span class="sxs-lookup"><span data-stu-id="6f84b-122">**\<cryptographySettings>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | <span data-ttu-id="6f84b-123">Všechny elementy ve schématu kryptografických nastavení.</span><span class="sxs-lookup"><span data-stu-id="6f84b-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="6f84b-124">**\<Konfigurace >** schéma oddílů</span><span class="sxs-lookup"><span data-stu-id="6f84b-124">**\<configuration>** Sections Schema</span></span>](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | <span data-ttu-id="6f84b-125">Všechny elementy ve schématu oddílu nastavení konfigurace.</span><span class="sxs-lookup"><span data-stu-id="6f84b-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="6f84b-126">Trasování a ladění schématu nastavení</span><span class="sxs-lookup"><span data-stu-id="6f84b-126">Trace and Debug Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | <span data-ttu-id="6f84b-127">Všechny elementy ve schématu nastavení trasování a ladění.</span><span class="sxs-lookup"><span data-stu-id="6f84b-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="6f84b-128">[Schéma nastavení konfigurace technologie ASP.NET](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="6f84b-128">[ASP.NET Configuration Settings Schema](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span></span> | <span data-ttu-id="6f84b-129">Všechny elementy ve schématu konfigurace ASP.NET, který obsahuje prvky konfigurace ASP.NET – webové servery a aplikace.</span><span class="sxs-lookup"><span data-stu-id="6f84b-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="6f84b-130">Použít v *Web.config* soubory.</span><span class="sxs-lookup"><span data-stu-id="6f84b-130">Used in *Web.config* files.</span></span> |
| [<span data-ttu-id="6f84b-131">**\<webovým službám >** schéma nastavení</span><span class="sxs-lookup"><span data-stu-id="6f84b-131">**\<webServices>** Settings Schema</span></span>](http://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | <span data-ttu-id="6f84b-132">Všechny elementy ve schématu nastavení webových služeb.</span><span class="sxs-lookup"><span data-stu-id="6f84b-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="6f84b-133">Schéma nastavení webu</span><span class="sxs-lookup"><span data-stu-id="6f84b-133">Web Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/web/index.md) | <span data-ttu-id="6f84b-134">Všechny elementy ve schéma nastavení webu, který obsahuje prvky pro konfiguraci, jak funguje technologie ASP.NET s hostitelskou aplikaci, například služby IIS.</span><span class="sxs-lookup"><span data-stu-id="6f84b-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="6f84b-135">Použít v *soubor aspnet.config* soubory.</span><span class="sxs-lookup"><span data-stu-id="6f84b-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="6f84b-136">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6f84b-136">Remarks</span></span>

<span data-ttu-id="6f84b-137">Každý konfigurační soubor musí obsahovat přesně jeden  **\<konfigurace >** element.</span><span class="sxs-lookup"><span data-stu-id="6f84b-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f84b-138">Viz také</span><span class="sxs-lookup"><span data-stu-id="6f84b-138">See also</span></span>

[<span data-ttu-id="6f84b-139">Schéma konfiguračního souboru pro rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f84b-139">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)