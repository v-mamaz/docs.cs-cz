---
title: "ICorDebugType::GetStaticFieldValue – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetStaticFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34a37ef9a28dd0e6325db9bee61146f14d4638a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="86759-102">ICorDebugType::GetStaticFieldValue – metoda</span><span class="sxs-lookup"><span data-stu-id="86759-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="86759-103">Získá ukazatele rozhraní ICorDebugValue objektu, která obsahuje hodnotu statické pole odkazovaná v zadaném poli token v rámci zadaného zásobníku.</span><span class="sxs-lookup"><span data-stu-id="86759-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86759-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="86759-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86759-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="86759-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="86759-106">[v] `mdFieldDef` Token, který určuje statické pole.</span><span class="sxs-lookup"><span data-stu-id="86759-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="86759-107">[v] Ukazatel ICorDebugFrame, který představuje rámce zásobníku.</span><span class="sxs-lookup"><span data-stu-id="86759-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="86759-108">[out] Ukazatel na adresu `ICorDebugValue` obsahující hodnotu statické pole.</span><span class="sxs-lookup"><span data-stu-id="86759-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86759-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="86759-109">Remarks</span></span>  
 <span data-ttu-id="86759-110">`GetStaticFieldValue` Metoda může používat pouze v případě typ je ELEMENT_TYPE_CLASS nebo Typ ELEMENT_TYPE_VALUETYPE, který, jak [icordebugtype::gettype –](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="86759-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="86759-111">Pro typy neobecnou provádí operaci `GetStaticFieldValue` je stejný jako při volání [icordebugclass::getstaticfieldvalue –](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) ICorDebugClass objektu, který je vrácen [icordebugtype::getclass –](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="86759-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="86759-112">Pro obecné typy hodnotu statické pole bude relativně ke konkrétní vytváření instancí.</span><span class="sxs-lookup"><span data-stu-id="86759-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="86759-113">Navíc pokud statické pole může být může být relativní vzhledem k vlákno, kontextu nebo doménu aplikace, pak rámce zásobníku pomůže ladicího programu určit správnou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="86759-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86759-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="86759-114">Remarks</span></span>  
 <span data-ttu-id="86759-115">`GetStaticFieldValue`lze použít pouze při volání `ICorDebugType::GetType` vrací hodnotu ELEMENT_TYPE_CLASS nebo Typ ELEMENT_TYPE_VALUETYPE, který.</span><span class="sxs-lookup"><span data-stu-id="86759-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86759-116">Požadavky</span><span class="sxs-lookup"><span data-stu-id="86759-116">Requirements</span></span>  
 <span data-ttu-id="86759-117">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86759-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86759-118">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86759-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86759-119">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86759-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86759-120">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86759-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>