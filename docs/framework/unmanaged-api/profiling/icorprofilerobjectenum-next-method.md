---
title: ICorProfilerObjectEnum::Next – metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc5d36267dcadcfafd4b715127ebbe2bcb9832b2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487879"
---
# <a name="icorprofilerobjectenumnext-method"></a>ICorProfilerObjectEnum::Next – metoda
Získá zadaný počet souvislých objekty z sekvenční kolekcí objektů, od aktuální pozice čítače výčtu v sekvenci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `celt`  
 [in] Počet objektů, které se mají načíst.  
  
 `objects`  
 [out] Pole `ObjectID` hodnot, z nichž každý představuje načtený objekt.  
  
 `pceltFetched`  
 [out] Ukazatel na počet skutečně vrácených v prvků `objects` pole.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorProf.idl, CorProf.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorProfilerObjectEnum – rozhraní](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
