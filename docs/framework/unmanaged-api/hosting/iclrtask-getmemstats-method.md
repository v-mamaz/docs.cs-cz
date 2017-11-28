---
title: "ICLRTask::GetMemStats – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.GetMemStats
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11537989765d721830c33cb137d1814327b02e14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="c524e-102">ICLRTask::GetMemStats – metoda</span><span class="sxs-lookup"><span data-stu-id="c524e-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="c524e-103">Získá informace o využití paměti statistické související s úlohou, aktuální [iclrtask –](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance představuje.</span><span class="sxs-lookup"><span data-stu-id="c524e-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c524e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c524e-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c524e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c524e-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="c524e-106">[out] Ukazatel [cor_gc_thread_stats –](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance, který obsahuje podrobnosti o využití paměti úlohy, včetně počet bajtů přidělených.</span><span class="sxs-lookup"><span data-stu-id="c524e-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c524e-107">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="c524e-107">Return Value</span></span>  
  
|<span data-ttu-id="c524e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c524e-108">HRESULT</span></span>|<span data-ttu-id="c524e-109">Popis</span><span class="sxs-lookup"><span data-stu-id="c524e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c524e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c524e-110">S_OK</span></span>|<span data-ttu-id="c524e-111">`GetMemStats`úspěšně vrácena.</span><span class="sxs-lookup"><span data-stu-id="c524e-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="c524e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c524e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c524e-113">Modul CLR (CLR) nebyla načtena do procesu nebo CLR je ve stavu, ve kterém nemůže běžet spravovaného kódu nebo úspěšně zpracovat volání.</span><span class="sxs-lookup"><span data-stu-id="c524e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c524e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c524e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c524e-115">Vypršel časový limit volání.</span><span class="sxs-lookup"><span data-stu-id="c524e-115">The call timed out.</span></span>|  
|<span data-ttu-id="c524e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c524e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c524e-117">Volající není vlastníkem zámek.</span><span class="sxs-lookup"><span data-stu-id="c524e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c524e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c524e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c524e-119">Událost byla zrušena při blokované vlákna nebo fiber čekal na něm.</span><span class="sxs-lookup"><span data-stu-id="c524e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c524e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c524e-120">E_FAIL</span></span>|<span data-ttu-id="c524e-121">Došlo k neznámému závažné selhání.</span><span class="sxs-lookup"><span data-stu-id="c524e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c524e-122">Po návratu metody E_FAIL modulu CLR již není použitelné v rámci procesu.</span><span class="sxs-lookup"><span data-stu-id="c524e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c524e-123">Následující volání hostování metody vrací HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c524e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c524e-124">Požadavky</span><span class="sxs-lookup"><span data-stu-id="c524e-124">Requirements</span></span>  
 <span data-ttu-id="c524e-125">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c524e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c524e-126">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c524e-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c524e-127">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c524e-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c524e-128">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c524e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c524e-129">Viz také</span><span class="sxs-lookup"><span data-stu-id="c524e-129">See Also</span></span>  
 [<span data-ttu-id="c524e-130">Iclrtask – rozhraní</span><span class="sxs-lookup"><span data-stu-id="c524e-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="c524e-131">Iclrtaskmanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="c524e-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="c524e-132">Ihosttask – rozhraní</span><span class="sxs-lookup"><span data-stu-id="c524e-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="c524e-133">Ihosttaskmanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="c524e-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)