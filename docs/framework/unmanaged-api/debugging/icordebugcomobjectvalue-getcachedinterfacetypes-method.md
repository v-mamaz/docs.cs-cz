---
title: ICorDebugComObjectValue::GetCachedInterfaceTypes – metoda
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60a74b3c90c11f799f5b9738e84d33b603f0ef04
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485470"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a>ICorDebugComObjectValue::GetCachedInterfaceTypes – metoda
Poskytuje enumerátor pro typy rozhraní, že byl přetypován na nebo použít jako aktuální objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a>Parametry  
 `bIInspectableOnly`  
 [in] Hodnota, která určuje, zda metoda vrátí pouze [!INCLUDE[wrt](../../../../includes/wrt-md.md)] rozhraní (`IInspectable` rozhraní) nebo jen rozhraní modelu COM v mezipaměti obálka volatelná za běhu (RCW).  
  
 `ppInterfacesEnum`  
 [out] Ukazatel na adresu, která poskytuje přístup k objektům ICorDebugType, které představují typy z mezipaměti rozhraní čítače icordebugtypeenum – filtrovat podle `bIInspectableOnly`.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorDebugComObjectValue – rozhraní](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [Rozhraní pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
