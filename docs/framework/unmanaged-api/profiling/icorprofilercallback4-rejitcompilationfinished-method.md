---
title: "ICorProfilerCallback4::ReJITCompilationFinished – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 768c77a91c072cadc2975d9dde704c134e719220
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="97f83-102">ICorProfilerCallback4::ReJITCompilationFinished – metoda</span><span class="sxs-lookup"><span data-stu-id="97f83-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="97f83-103">Upozorní profileru, že nutnosti rekompilace funkce kompilátoru za běhu (JIT) byla dokončena.</span><span class="sxs-lookup"><span data-stu-id="97f83-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f83-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="97f83-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97f83-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="97f83-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="97f83-106">[v] ID funkce, která byla zopakovat.</span><span class="sxs-lookup"><span data-stu-id="97f83-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="97f83-107">[v] Identita překompilovat JIT funkce.</span><span class="sxs-lookup"><span data-stu-id="97f83-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="97f83-108">[v] Hodnota, která určuje, zda rekompilace JIT byla úspěšná.</span><span class="sxs-lookup"><span data-stu-id="97f83-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="97f83-109">[v] `true` k označení, že blokování může způsobit modulu runtime počkejte volající vlákno k návratu z této zpětného volání; `false` k označení, že blokování neovlivní operaci modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="97f83-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="97f83-110">Hodnota `true` nepříznivý vliv modul runtime, ale může ovlivnit profilování výsledky.</span><span class="sxs-lookup"><span data-stu-id="97f83-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97f83-111">Požadavky</span><span class="sxs-lookup"><span data-stu-id="97f83-111">Requirements</span></span>  
 <span data-ttu-id="97f83-112">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97f83-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97f83-113">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="97f83-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="97f83-114">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97f83-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97f83-115">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97f83-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f83-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="97f83-116">See Also</span></span>  
 [<span data-ttu-id="97f83-117">Icorprofilercallback – rozhraní</span><span class="sxs-lookup"><span data-stu-id="97f83-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="97f83-118">Icorprofilercallback4 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="97f83-118">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="97f83-119">Jitcompilationstarted – metoda</span><span class="sxs-lookup"><span data-stu-id="97f83-119">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [<span data-ttu-id="97f83-120">Rejitcompilationstarted – metoda</span><span class="sxs-lookup"><span data-stu-id="97f83-120">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)