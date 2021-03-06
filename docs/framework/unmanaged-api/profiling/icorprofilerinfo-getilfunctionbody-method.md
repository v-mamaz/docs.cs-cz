---
title: ICorProfilerInfo::GetILFunctionBody – metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8e98ee26da2d78278435d90d6d04ef9771f41104
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489446"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody – metoda
Získá ukazatel do těla metody v kódu Microsoft intermediate language (MSIL) začínající na jeho záhlaví.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a>Parametry  
 `moduleId`  
 [in] ID modulu, ve kterém se funkce nachází.  
  
 `methodId`  
 [in] Token metadat pro metodu.  
  
 `ppMethodHeader`  
 [out] Ukazatel na záhlaví metody.  
  
 `pcbMethodSize`  
 [out] Celé číslo, které určuje velikost metody.  
  
## <a name="remarks"></a>Poznámky  
 Metoda je určeno v modulu, ve kterém se nachází. Vzhledem k tomu, `GetILFunctionBody` metoda je určena poskytnout přístup k nástroji pro kód jazyka MSIL, předtím, než byl načten modulem common language runtime (CLR), použije token metadat metody k vyhledání požadovaného instance.  
  
 `GetILFunctionBody` může vrátit hodnotu HRESULT CORPROF_E_FUNCTION_NOT_IL, pokud `methodId` odkazuje na metodu, bez jakékoli MSIL kód (jako abstraktní metody nebo platformu vyvolání metody (PInvoke)).  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorProf.idl, CorProf.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorProfilerInfo – rozhraní](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
