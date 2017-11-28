---
title: "ICorProfilerCallback::AssemblyUnloadFinished – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyUnloadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 144f7af59afbb403d9ec1894f06c5c028b767416
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="99558-102">ICorProfilerCallback::AssemblyUnloadFinished – metoda</span><span class="sxs-lookup"><span data-stu-id="99558-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="99558-103">Upozorní profileru sestavení byl odpojen.</span><span class="sxs-lookup"><span data-stu-id="99558-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99558-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="99558-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99558-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="99558-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="99558-106">[v] Identifikuje sestavení, které odpojení.</span><span class="sxs-lookup"><span data-stu-id="99558-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="99558-107">[v] HRESULT, která určuje, zda byla sestavení úspěšně odpojen.</span><span class="sxs-lookup"><span data-stu-id="99558-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99558-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="99558-108">Remarks</span></span>  
 <span data-ttu-id="99558-109">Hodnota `assemblyId` není platná pro požadavek informace po [icorprofilercallback::assemblyunloadstarted –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) metoda vrátí.</span><span class="sxs-lookup"><span data-stu-id="99558-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="99558-110">Některé části uvolnění sestavení může pokračovat po `AssemblyUnloadFinished` zpětného volání.</span><span class="sxs-lookup"><span data-stu-id="99558-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="99558-111">Selhání HRESULT v `hrStatus` znamená chybu.</span><span class="sxs-lookup"><span data-stu-id="99558-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="99558-112">Ale úspěšné HRESULT v `hrStatus` pouze označuje, že první část uvolnění sestavení proběhl úspěšně.</span><span class="sxs-lookup"><span data-stu-id="99558-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99558-113">Požadavky</span><span class="sxs-lookup"><span data-stu-id="99558-113">Requirements</span></span>  
 <span data-ttu-id="99558-114">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99558-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99558-115">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99558-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99558-116">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99558-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99558-117">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99558-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99558-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="99558-118">See Also</span></span>  
 [<span data-ttu-id="99558-119">Icorprofilercallback – rozhraní</span><span class="sxs-lookup"><span data-stu-id="99558-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)