---
title: "&lt;Assert –&gt; – Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 520dfec180157c9a05c5fc3beb51b5fc17f9088b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltassertgt-element"></a><span data-ttu-id="b5496-102">&lt;Assert –&gt; – Element</span><span class="sxs-lookup"><span data-stu-id="b5496-102">&lt;assert&gt; Element</span></span>
<span data-ttu-id="b5496-103">Určuje, jestli se má zobrazit okno se zprávou při volání <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> metoda; také určuje název souboru pro zápis zprávy.</span><span class="sxs-lookup"><span data-stu-id="b5496-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
 <span data-ttu-id="b5496-104">\<Konfigurace ></span><span class="sxs-lookup"><span data-stu-id="b5496-104">\<configuration></span></span>  
<span data-ttu-id="b5496-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="b5496-105">\<system.diagnostics></span></span>  
<span data-ttu-id="b5496-106">\<Assert – ></span><span class="sxs-lookup"><span data-stu-id="b5496-106">\<assert></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5496-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b5496-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5496-108">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="b5496-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b5496-109">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="b5496-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5496-110">Atributy</span><span class="sxs-lookup"><span data-stu-id="b5496-110">Attributes</span></span>  
  
|<span data-ttu-id="b5496-111">Atribut</span><span class="sxs-lookup"><span data-stu-id="b5496-111">Attribute</span></span>|<span data-ttu-id="b5496-112">Popis</span><span class="sxs-lookup"><span data-stu-id="b5496-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="b5496-113">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="b5496-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b5496-114">Určuje, zda Pokud chcete zobrazit zprávu pole při **Debug.Assert –** vyhodnocen jako metoda **false**.</span><span class="sxs-lookup"><span data-stu-id="b5496-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="b5496-115">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="b5496-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b5496-116">Určuje název souboru pro zápis zprávy, když se **Debug.Assert –** vyhodnotí jako **false**.</span><span class="sxs-lookup"><span data-stu-id="b5496-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="b5496-117">assertuienabled atribut</span><span class="sxs-lookup"><span data-stu-id="b5496-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="b5496-118">Hodnota</span><span class="sxs-lookup"><span data-stu-id="b5496-118">Value</span></span>|<span data-ttu-id="b5496-119">Popis</span><span class="sxs-lookup"><span data-stu-id="b5496-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="b5496-120">Zobrazí okno se zprávou.</span><span class="sxs-lookup"><span data-stu-id="b5496-120">Displays the message box.</span></span> <span data-ttu-id="b5496-121">Toto nastavení je výchozí.</span><span class="sxs-lookup"><span data-stu-id="b5496-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="b5496-122">Do pole zpráva nezobrazí.</span><span class="sxs-lookup"><span data-stu-id="b5496-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5496-123">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="b5496-123">Child Elements</span></span>  
 <span data-ttu-id="b5496-124">Žádné</span><span class="sxs-lookup"><span data-stu-id="b5496-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b5496-125">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="b5496-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b5496-126">Prvek</span><span class="sxs-lookup"><span data-stu-id="b5496-126">Element</span></span>|<span data-ttu-id="b5496-127">Popis</span><span class="sxs-lookup"><span data-stu-id="b5496-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b5496-128">Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b5496-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b5496-129">Určuje naslouchací procesy trasování, které shromažďování, ukládání a směrování zpráv a úroveň, kde je nastaven na přepínač trasování.</span><span class="sxs-lookup"><span data-stu-id="b5496-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5496-130">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b5496-130">Remarks</span></span>  
 <span data-ttu-id="b5496-131">Oba atributy v  **\<assert >** element jsou volitelné.</span><span class="sxs-lookup"><span data-stu-id="b5496-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="b5496-132">Okna zpráv můžete zakázat bez zadání souboru pro zápis zprávy, které mají, nebo můžete zadat soubor k zápisu zprávy do při opuštění zprávy polí povoleno.</span><span class="sxs-lookup"><span data-stu-id="b5496-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5496-133">Příklad</span><span class="sxs-lookup"><span data-stu-id="b5496-133">Example</span></span>  
 <span data-ttu-id="b5496-134">Následující příklad ukazuje, jak zakázat zobrazování okna zpráv při volání **Debug.Assert –** a zápis zpráv do `c:\log.txt`.</span><span class="sxs-lookup"><span data-stu-id="b5496-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5496-135">Viz také</span><span class="sxs-lookup"><span data-stu-id="b5496-135">See Also</span></span>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="b5496-136">Trasování a ladění schématu nastavení</span><span class="sxs-lookup"><span data-stu-id="b5496-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)