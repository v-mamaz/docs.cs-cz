---
title: ICorDebugInternalFrame2::IsCloserToLeaf – metoda
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96deee943f6a4c636a52b41c8f4c2fda86c6bd18
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493716"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>ICorDebugInternalFrame2::IsCloserToLeaf – metoda
Kontroluje, zda `this` vnitřní rámec je blíže než zadaný objekt ICorDebugFrame listu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>Parametry  
 `pFrameToCompare`  
 [in] Ukazatel na porovnání `ICorDebugFrame` objektu.  
  
 `pIsCloser`  
 [out] `true` Pokud `this` vnitřní rámec je blíž ke listu než rámce určené `pFrameToCompare`; v opačném případě `false`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Tato metoda vrátí následující konkrétní HRESULT, stejně jako hodnota HRESULT chyby, které označují selhání metoda.  
  
|HRESULT|Popis|  
|-------------|-----------------|  
|S_OK|Porovnání se úspěšně provedla.|  
|E_FAIL|Porovnání nelze provést.|  
|E_INVALIDARG|`pFrameToCompare` nebo `pIsCloser` má hodnotu null.|  
  
## <a name="remarks"></a>Poznámky  
 `IsCloserToLeaf` je možné implementovat zásady pro prokládání vnitřních rámcích pomocí jiné rámce v zásobníku.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorDebugInternalFrame2 – rozhraní](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [Rozhraní pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Ladění](../../../../docs/framework/unmanaged-api/debugging/index.md)
