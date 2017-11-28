---
title: "ICorDebugMDA::GetOSThreadId – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetOSThreadId
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6cc53eecadd982d7cea045424de52d8e6f64107b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="88f3a-102">ICorDebugMDA::GetOSThreadId – metoda</span><span class="sxs-lookup"><span data-stu-id="88f3a-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="88f3a-103">Získá identifikátor operační systém (OS) přístup z více vláken, na kterém reprezentována Pomocník spravovaného ladění (MDA) [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) spouští.</span><span class="sxs-lookup"><span data-stu-id="88f3a-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88f3a-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="88f3a-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88f3a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="88f3a-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="88f3a-106">[out] Ukazatel na identifikátor operačního systému.</span><span class="sxs-lookup"><span data-stu-id="88f3a-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88f3a-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="88f3a-107">Remarks</span></span>  
 <span data-ttu-id="88f3a-108">Vlákno operačního systému se používá namísto ICorDebugThread pro situace, ve kterých je spouštěna MDA nativní vlákno buď spravovaných vláken, který ještě nebyl zadán spravovaného kódu.</span><span class="sxs-lookup"><span data-stu-id="88f3a-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88f3a-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="88f3a-109">Requirements</span></span>  
 <span data-ttu-id="88f3a-110">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88f3a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88f3a-111">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88f3a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88f3a-112">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88f3a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88f3a-113">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88f3a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88f3a-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="88f3a-114">See Also</span></span>  
 [<span data-ttu-id="88f3a-115">ICorDebugMDA – rozhraní rozhraní</span><span class="sxs-lookup"><span data-stu-id="88f3a-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="88f3a-116">Diagnostikování chyb pomocí asistentů spravovaného ladění</span><span class="sxs-lookup"><span data-stu-id="88f3a-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)