---
title: "ICorDebugExceptionObjectValue::EnumerateExceptionCallStack – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 861d2ad5f9ce0fcc11ea7b1743cd369235cbd878
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a>ICorDebugExceptionObjectValue::EnumerateExceptionCallStack – metoda
Získá enumerátor do zásobníku volání vložených v objektu výjimky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 ppCallStackEnum  
 [out] Ukazatel na adresu [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) rozhraní objekt, který je enumerátor trasování zásobníku pro objekt spravované výjimky.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je k dispozici žádné informace zásobníku volání, vrátí metoda `S_OK`, a [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) je platný enumerátor s délkou 0. Pokud je metoda nelze načíst informace trasování zásobníku, je vrácenou hodnotu `E_FAIL` a je vrácena žádná enumerátor.  
  
 [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) objektu je zodpovědná za dekódování dat trasování zásobníku z `_stackTrace` pole objektu výjimky.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [ICorDebugExceptionObjectValue – rozhraní rozhraní](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 [Ladění v rozhraní](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)