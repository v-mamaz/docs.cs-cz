---
title: "ICorDebugNativeFrame2 – rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2
helpviewer_keywords: ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c33eaa36313f0cf6aae904761fb40bb2dbf9d753
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="48ddd-102">ICorDebugNativeFrame2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="48ddd-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="48ddd-103">Poskytuje metody, které testují podřízené a nadřazené vztahy rámce.</span><span class="sxs-lookup"><span data-stu-id="48ddd-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48ddd-104">Metody</span><span class="sxs-lookup"><span data-stu-id="48ddd-104">Methods</span></span>  
  
|<span data-ttu-id="48ddd-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="48ddd-105">Method</span></span>|<span data-ttu-id="48ddd-106">Popis</span><span class="sxs-lookup"><span data-stu-id="48ddd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48ddd-107">Ischild – metoda</span><span class="sxs-lookup"><span data-stu-id="48ddd-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="48ddd-108">Určuje, zda je aktuální snímek podřízeného rámce.</span><span class="sxs-lookup"><span data-stu-id="48ddd-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="48ddd-109">Ismatchingparentframe – metoda</span><span class="sxs-lookup"><span data-stu-id="48ddd-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="48ddd-110">Určuje, zda je zadaný rámečku nadřazeného aktuální snímek.</span><span class="sxs-lookup"><span data-stu-id="48ddd-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="48ddd-111">Getstackparametersize – metoda</span><span class="sxs-lookup"><span data-stu-id="48ddd-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="48ddd-112">Vrátí celková velikost všech parametrů v zásobníku na x86 operační systémy.</span><span class="sxs-lookup"><span data-stu-id="48ddd-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48ddd-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="48ddd-113">Remarks</span></span>  
 <span data-ttu-id="48ddd-114">Toto rozhraní logicky rozšiřuje rozhraní "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="48ddd-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48ddd-115">Toto rozhraní nepodporuje volané vzdáleně, mezi počítači nebo mezi procesy.</span><span class="sxs-lookup"><span data-stu-id="48ddd-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48ddd-116">Požadavky</span><span class="sxs-lookup"><span data-stu-id="48ddd-116">Requirements</span></span>  
 <span data-ttu-id="48ddd-117">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48ddd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48ddd-118">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48ddd-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48ddd-119">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48ddd-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48ddd-120">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48ddd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ddd-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="48ddd-121">See Also</span></span>  
    
 [<span data-ttu-id="48ddd-122">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="48ddd-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="48ddd-123">Ladění</span><span class="sxs-lookup"><span data-stu-id="48ddd-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)