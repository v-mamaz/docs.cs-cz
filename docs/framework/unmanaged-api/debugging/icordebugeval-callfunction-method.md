---
title: "ICorDebugEval::CallFunction – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.CallFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72713d81931b53e8d61fb39cee146fd30a59bfcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="4ee8d-102">ICorDebugEval::CallFunction – metoda</span><span class="sxs-lookup"><span data-stu-id="4ee8d-102">ICorDebugEval::CallFunction Method</span></span>
<span data-ttu-id="4ee8d-103">Nastaví volání zadanou funkci.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-103">Sets up a call to the specified function.</span></span>  
  
 <span data-ttu-id="4ee8d-104">Tato metoda je zastaralé v rozhraní .NET Framework verze 2.0.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="4ee8d-105">Použití [icordebugeval2::callparameterizedfunction –](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) místo.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-105">Use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ee8d-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4ee8d-106">Syntax</span></span>  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ee8d-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="4ee8d-107">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="4ee8d-108">[v] Ukazatel na ICorDebugFunction objekt, který určuje funkce, která má být volána.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="4ee8d-109">[v] Počet argumentů pro funkci.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-109">[in] The number of arguments for the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="4ee8d-110">[v] Pole ukazatele, každý z nich odkazuje na objekt ICorDebugValue, který určuje argument mají být předány funkce.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ee8d-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4ee8d-111">Remarks</span></span>  
 <span data-ttu-id="4ee8d-112">Pokud je virtuální, funkce `CallFunction` provede virtuální odesílání.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="4ee8d-113">Pokud je v doméně jinou aplikaci, přechod dojde, pokud jsou všechny argumenty také v této doméně.</span><span class="sxs-lookup"><span data-stu-id="4ee8d-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ee8d-114">Požadavky</span><span class="sxs-lookup"><span data-stu-id="4ee8d-114">Requirements</span></span>  
 <span data-ttu-id="4ee8d-115">**Platformy:** WindowSee [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ee8d-115">**Platforms:** WindowSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ee8d-116">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ee8d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ee8d-117">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ee8d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ee8d-118">**Verze rozhraní .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="4ee8d-118">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee8d-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="4ee8d-119">See Also</span></span>  
 [<span data-ttu-id="4ee8d-120">Callparameterizedfunction – metoda</span><span class="sxs-lookup"><span data-stu-id="4ee8d-120">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)