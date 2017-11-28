---
title: "COR_PRF_FUNCTION_ARGUMENT_INFO – struktura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION_ARGUMENT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4e791bdc41707133fb787a511a39d3ec3d7453a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="corprffunctionargumentinfo-structure"></a><span data-ttu-id="4192c-102">COR_PRF_FUNCTION_ARGUMENT_INFO – struktura</span><span class="sxs-lookup"><span data-stu-id="4192c-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="4192c-103">Představuje argumenty funkcí v pořadí zleva doprava.</span><span class="sxs-lookup"><span data-stu-id="4192c-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4192c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4192c-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="4192c-105">Členové</span><span class="sxs-lookup"><span data-stu-id="4192c-105">Members</span></span>  
  
|<span data-ttu-id="4192c-106">Člen</span><span class="sxs-lookup"><span data-stu-id="4192c-106">Member</span></span>|<span data-ttu-id="4192c-107">Popis</span><span class="sxs-lookup"><span data-stu-id="4192c-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="4192c-108">Počet bloků argumentů.</span><span class="sxs-lookup"><span data-stu-id="4192c-108">The number of blocks of arguments.</span></span> <span data-ttu-id="4192c-109">Tato hodnota je počet [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) struktury v `ranges` pole.</span><span class="sxs-lookup"><span data-stu-id="4192c-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="4192c-110">Celková velikost všech argumentů.</span><span class="sxs-lookup"><span data-stu-id="4192c-110">The total size of all arguments.</span></span> <span data-ttu-id="4192c-111">Jinými slovy tato hodnota je součtem argument délek.</span><span class="sxs-lookup"><span data-stu-id="4192c-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="4192c-112">Pole `COR_PRF_FUNCTION_ARGUMENT_RANGE` struktury, z nichž každý představuje jeden blok argumenty funkce.</span><span class="sxs-lookup"><span data-stu-id="4192c-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4192c-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4192c-113">Remarks</span></span>  
 <span data-ttu-id="4192c-114">Funkce může mít mnoho argumentů.</span><span class="sxs-lookup"><span data-stu-id="4192c-114">A function may have many arguments.</span></span> <span data-ttu-id="4192c-115">Tyto argumenty nemusí být souvisle uložené v paměti.</span><span class="sxs-lookup"><span data-stu-id="4192c-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="4192c-116">Můžete mít blok tři argumenty na jednom místě, blok dva argumenty na jiném místě a poslední blok jeden argument na jiné místo.</span><span class="sxs-lookup"><span data-stu-id="4192c-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="4192c-117">Jsou všechny tyto argumenty pro stejnou funkci; právě byly uloženy do různých místech.</span><span class="sxs-lookup"><span data-stu-id="4192c-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="4192c-118">`COR_PRF_FUNCTION_ARGUMENT_INFO` Struktura představuje všechny argumenty jedné funkce.</span><span class="sxs-lookup"><span data-stu-id="4192c-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="4192c-119">Chcete-li všechny bloky argumenty funkce používá pole.</span><span class="sxs-lookup"><span data-stu-id="4192c-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="4192c-120">Ano, pro jednu funkci, máte jediný `COR_PRF_FUNCTION_ARGUMENT_INFO` strukturu, která odkazuje na více `COR_PRF_FUNCTION_ARGUMENT_RANGE` struktury, každý z nich odkazuje na jeden nebo více argumenty funkce.</span><span class="sxs-lookup"><span data-stu-id="4192c-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="4192c-121">Argumenty, které jsou uložené v registrech jsou uniknout do paměti k vytvoření struktury.</span><span class="sxs-lookup"><span data-stu-id="4192c-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4192c-122">Požadavky</span><span class="sxs-lookup"><span data-stu-id="4192c-122">Requirements</span></span>  
 <span data-ttu-id="4192c-123">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4192c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4192c-124">**Záhlaví:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="4192c-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4192c-125">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4192c-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4192c-126">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4192c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4192c-127">Viz také</span><span class="sxs-lookup"><span data-stu-id="4192c-127">See Also</span></span>  
 [<span data-ttu-id="4192c-128">Struktury pro profilaci</span><span class="sxs-lookup"><span data-stu-id="4192c-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)