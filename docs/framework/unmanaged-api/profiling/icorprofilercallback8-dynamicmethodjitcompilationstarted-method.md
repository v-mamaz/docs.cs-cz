---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 170d0b20069724a4e1845be0250b2897daa10dee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501237"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method
[Podporované v rozhraní .NET Framework 4.7 a novějších verzích]  
  
Profiler upozorní při každém spuštění kompilace JIT dynamické metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a>Parametry  
[in] `functionId`  
Identifikátor funkce v paměti, pro které JIT kompilace spuštění.   

[in] `fIsSafeToBlock`   
`true` k označení, že blokování může způsobit, že modul runtime počká pro volajícího vlákna má vrátit z této zpětné volání; `false` k označení, že blokování nebude mít vliv na operace modulu runtime.  

[in] `pILHeader`    
Ukazatel na první bajt záhlaví úrovně Důvěryhodnosti metody.   

[in] `cbILHeader`    
Počet bajtů v záhlaví úrovně Důvěryhodnosti. 

## <a name="remarks"></a>Poznámky  

Toto zpětné volání se aktivuje vždy, když je dynamická metoda kompilována JIT. To zahrnuje různé zástupné procedury IL a LCG metody. Jeho cílem je poskytnout dostatek informací k identifikaci metody kompilované pro uživatele autoři profileru.

> [!NOTE]
> `functionId` hodnoty nelze přeložit na jejich tokeny metadat použít, protože dynamické metody mají žádná metadata.

`pILHeader` Ukazatel je platný pouze během zpětného volání.

## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorProf.idl, CorProf.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Viz také:
- [DynamicMethodJITCompilationFinished – metoda](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [ICorProfilerCallback8 – rozhraní](icorprofilercallback8-interface.md)
