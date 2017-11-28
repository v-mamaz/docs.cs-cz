---
title: "ICorProfilerInfo::GetModuleMetaData – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetModuleMetaData
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 540ed6f1f84f096563aa94798090c3511d6db5d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="d76dc-102">ICorProfilerInfo::GetModuleMetaData – metoda</span><span class="sxs-lookup"><span data-stu-id="d76dc-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="d76dc-103">Získá instanci rozhraní metadata, která se mapuje na zadaný modul.</span><span class="sxs-lookup"><span data-stu-id="d76dc-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d76dc-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d76dc-104">Syntax</span></span>  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d76dc-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d76dc-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="d76dc-106">[v] ID modulu, na kterou bude instance rozhraní namapovaná.</span><span class="sxs-lookup"><span data-stu-id="d76dc-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="d76dc-107">[v] Hodnota [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) výčet, který určuje režim pro otevírání souborů manifestu.</span><span class="sxs-lookup"><span data-stu-id="d76dc-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="d76dc-108">Pouze `ofRead`, `ofWrite` a `ofNoTransform` bits jsou platné.</span><span class="sxs-lookup"><span data-stu-id="d76dc-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="d76dc-109">[v] Odkaz na ID (GUID) metadat rozhraní, jejichž instance bude načten.</span><span class="sxs-lookup"><span data-stu-id="d76dc-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="d76dc-110">V tématu [rozhraní metadat](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) seznam rozhraní.</span><span class="sxs-lookup"><span data-stu-id="d76dc-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="d76dc-111">[out] Ukazatel na adresu instanci rozhraní metadat.</span><span class="sxs-lookup"><span data-stu-id="d76dc-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d76dc-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d76dc-112">Remarks</span></span>  
 <span data-ttu-id="d76dc-113">Může požádat o metadata otevřít v režimu pro čtení a zápis, ale tato akce způsobí pomalejší metadata spuštění programu, protože změn metadata nelze optimalizovat jako byly z kompilátoru.</span><span class="sxs-lookup"><span data-stu-id="d76dc-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="d76dc-114">Některé moduly (například moduly prostředků) mají žádná metadata.</span><span class="sxs-lookup"><span data-stu-id="d76dc-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="d76dc-115">V takových případech `GetModuleMetaData` vrátí hodnotu HRESULT S_FALSE a s hodnotou null v *`ppOut`.</span><span class="sxs-lookup"><span data-stu-id="d76dc-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in *`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d76dc-116">Požadavky</span><span class="sxs-lookup"><span data-stu-id="d76dc-116">Requirements</span></span>  
 <span data-ttu-id="d76dc-117">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d76dc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d76dc-118">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d76dc-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d76dc-119">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d76dc-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d76dc-120">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d76dc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76dc-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="d76dc-121">See Also</span></span>  
 [<span data-ttu-id="d76dc-122">Icorprofilerinfo – rozhraní</span><span class="sxs-lookup"><span data-stu-id="d76dc-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)