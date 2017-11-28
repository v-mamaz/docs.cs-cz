---
title: "ICorProfilerCallback3::ProfilerAttachComplete – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3.ProfilerAttachComplete Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0bf1e535c6270660797554c38a0b031df82f0925
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="cc0e9-102">ICorProfilerCallback3::ProfilerAttachComplete – metoda</span><span class="sxs-lookup"><span data-stu-id="cc0e9-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="cc0e9-103">Modul CLR (CLR) k označení, že můžete nyní volat profileru je voláno [icorprofilerinfo3::enumjitedfunctions –](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) a [icorprofilerinfo3::enummodules –](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) opravný metody.</span><span class="sxs-lookup"><span data-stu-id="cc0e9-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc0e9-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cc0e9-104">Syntax</span></span>  
  
```  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cc0e9-105">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cc0e9-105">Remarks</span></span>  
 <span data-ttu-id="cc0e9-106">`ProfilerAttachComplete` Zpětné volání se objeví po [icorprofilercallback3::initializeforattach –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) metoda je volána.</span><span class="sxs-lookup"><span data-stu-id="cc0e9-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="cc0e9-107">Znamená to následující:</span><span class="sxs-lookup"><span data-stu-id="cc0e9-107">It indicates the following:</span></span>  
  
-   <span data-ttu-id="cc0e9-108">Zpětná volání, které byly požadoval profileru v `InitializeForAttach` aktivoval.</span><span class="sxs-lookup"><span data-stu-id="cc0e9-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
-   <span data-ttu-id="cc0e9-109">Profileru teď můžete dělat zjištěná v přidružené ID aniž by musel být zajímá chybějící oznámení.</span><span class="sxs-lookup"><span data-stu-id="cc0e9-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="cc0e9-110">Modul CLR ignoruje návratovou hodnotou z této zpětného volání.</span><span class="sxs-lookup"><span data-stu-id="cc0e9-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc0e9-111">Požadavky</span><span class="sxs-lookup"><span data-stu-id="cc0e9-111">Requirements</span></span>  
 <span data-ttu-id="cc0e9-112">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc0e9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc0e9-113">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cc0e9-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cc0e9-114">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc0e9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc0e9-115">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc0e9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0e9-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="cc0e9-116">See Also</span></span>  
 [<span data-ttu-id="cc0e9-117">Icorprofilercallback – rozhraní</span><span class="sxs-lookup"><span data-stu-id="cc0e9-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="cc0e9-118">Icorprofilerinfo3 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="cc0e9-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="cc0e9-119">Rozhraní pro profilaci</span><span class="sxs-lookup"><span data-stu-id="cc0e9-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="cc0e9-120">Profilace</span><span class="sxs-lookup"><span data-stu-id="cc0e9-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)