---
title: ICorProfilerInfo7::GetInMemorySymbolsLength Method
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 550acc8d696cbd9e82d05e09c48a8c929af23673
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487471"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>ICorProfilerInfo7::GetInMemorySymbolsLength Method
[Podporované v rozhraní .NET Framework 4.6.1 a novějších verzích]  
  
 Vrátí délku datového proudu symbolu v paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `moduleId`  
 [in] Identifikátor modulu, který obsahuje datový proud v paměti.  
  
 pCountSymbolBytes  
 [out] Ukazatel `DWORD` hodnotu, která po návratu metody obsahuje délku datového proudu v bajtech.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `S_OK` Pokud nelze určit délka datového proudu paměti, i když je nula (0).  
  
 Metoda vrátí `CORPROF_E_MODULE_IS_DYNAMIC` Pokud metoda byl vytvořen pomocí <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="remarks"></a>Poznámky  
 Pokud ho modul obsahuje symboly v paměti, délku datového proudu je umístěn v `pCountSymbolBytes`. Pokud modul nemá symboly v paměti `*pCountSymbolBytes = 0`.  
  
> [!NOTE]
>  Aktuální implementace nepodporuje Reflection.Emit. Pokud modul byl vytvořen pomocí třídy Reflection.Emit, metoda vrátí `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorProf.idl, CorProf.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorProfilerInfo7 – rozhraní](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
