---
title: "ICorProfilerCallback::RootReferences – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RootReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a12dec1ed0fecad235090592def9689f60e50193
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="2562c-102">ICorProfilerCallback::RootReferences – metoda</span><span class="sxs-lookup"><span data-stu-id="2562c-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="2562c-103">Upozorní profileru s informacemi o odkazů na kořenový po uvolnění paměti.</span><span class="sxs-lookup"><span data-stu-id="2562c-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2562c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2562c-104">Syntax</span></span>  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2562c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2562c-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="2562c-106">[v] Počet odkazů v `rootRefIds` pole.</span><span class="sxs-lookup"><span data-stu-id="2562c-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="2562c-107">[v] Pole ID objektů, které odkazují na statický objekt nebo objekt v zásobníku.</span><span class="sxs-lookup"><span data-stu-id="2562c-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2562c-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2562c-108">Remarks</span></span>  
 <span data-ttu-id="2562c-109">Obě `RootReferences` a [icorprofilercallback2::rootreferences2 –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) se nazývají oznámit profileru.</span><span class="sxs-lookup"><span data-stu-id="2562c-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="2562c-110">Profilery bude obvykle implementovat jednu nebo druhou, ale ne pomocí obou, protože předaná informace `RootReferences2` je nadmnožinou, je předaná `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="2562c-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="2562c-111">Je možné `rootRefIds` pole tak, aby obsahovala objekt s hodnotou null.</span><span class="sxs-lookup"><span data-stu-id="2562c-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="2562c-112">Například všechny odkazy na objekty deklarované v zásobníku se považují za kořeny modulem garbage collector a bude vždy hlášena.</span><span class="sxs-lookup"><span data-stu-id="2562c-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="2562c-113">Vrácený objekt ID `RootReferences` nejsou platné během zpětného volání sebe, protože kolekce paměti může být uprostřed přesun objektů z původní adresy na nové adresy.</span><span class="sxs-lookup"><span data-stu-id="2562c-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="2562c-114">Proto se profilery nesmíte pokoušet zkontrolovat objekty během `RootReferences` volání.</span><span class="sxs-lookup"><span data-stu-id="2562c-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="2562c-115">Když [icorprofilercallback2::garbagecollectionfinished –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) je volána, všechny objekty byly přesunuty do nového umístění a může být prověřovány bezpečně.</span><span class="sxs-lookup"><span data-stu-id="2562c-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2562c-116">Požadavky</span><span class="sxs-lookup"><span data-stu-id="2562c-116">Requirements</span></span>  
 <span data-ttu-id="2562c-117">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2562c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2562c-118">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2562c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2562c-119">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2562c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2562c-120">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2562c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2562c-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="2562c-121">See Also</span></span>  
 [<span data-ttu-id="2562c-122">Icorprofilercallback – rozhraní</span><span class="sxs-lookup"><span data-stu-id="2562c-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)