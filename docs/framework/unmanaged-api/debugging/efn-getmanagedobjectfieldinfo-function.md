---
title: "_EFN_GetManagedObjectFieldInfo – funkce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedObjectFieldInfo
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedObjectFieldInfo
helpviewer_keywords: _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3df09c9107b683381f21891a1001140c493a024
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="79811-102">_EFN_GetManagedObjectFieldInfo – funkce</span><span class="sxs-lookup"><span data-stu-id="79811-102">_EFN_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="79811-103">Získá posun od začátku objekt pole a hodnotu pole pomocí ukazatele zadaného objektu a název pole.</span><span class="sxs-lookup"><span data-stu-id="79811-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79811-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="79811-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79811-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="79811-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="79811-106">[v] Ukazatel na klientské ladění.</span><span class="sxs-lookup"><span data-stu-id="79811-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="79811-107">[v] Ukazatel spravovaného objektu.</span><span class="sxs-lookup"><span data-stu-id="79811-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="79811-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="79811-108">szFieldName</span></span>  
 <span data-ttu-id="79811-109">[v] Ukazatel spravovaného objektu na název pole.</span><span class="sxs-lookup"><span data-stu-id="79811-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="79811-110">[out] Hodnota pole.</span><span class="sxs-lookup"><span data-stu-id="79811-110">[out] The field value.</span></span> <span data-ttu-id="79811-111">Tento parametr může mít hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="79811-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="79811-112">[out] Posun od `objAddr` na pole.</span><span class="sxs-lookup"><span data-stu-id="79811-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="79811-113">Tento parametr může mít hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="79811-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79811-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="79811-114">Remarks</span></span>  
 <span data-ttu-id="79811-115">Pokud posun 0, je zapsán posunutí.</span><span class="sxs-lookup"><span data-stu-id="79811-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="79811-116">Pokud neexistuje žádný spravovaný kód ve vlákně aktuálně v kontextu, funkce vrátí HRESULT SOS_E_NOMANAGEDCODE s hodnotou zařízení 0xa0 a chybový kód 0x1000.</span><span class="sxs-lookup"><span data-stu-id="79811-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79811-117">Požadavky</span><span class="sxs-lookup"><span data-stu-id="79811-117">Requirements</span></span>  
 <span data-ttu-id="79811-118">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79811-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79811-119">**Záhlaví:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="79811-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="79811-120">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79811-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79811-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="79811-121">See Also</span></span>  
 [<span data-ttu-id="79811-122">Globální statické funkce ladění</span><span class="sxs-lookup"><span data-stu-id="79811-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)