---
title: ICorDebugVariableSymbol::GetName Method
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d01f8c3956298daee9f11c912406079d98964225
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465295"
---
# <a name="icordebugvariablesymbolgetname-method"></a>ICorDebugVariableSymbol::GetName Method
Získá název proměnné.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `cchName`  
 [in] Počet znaků `szName` vyrovnávací paměti.  
  
 `pcchName`  
 [out] Ukazatel na počet aktuálně zapsaných do znaků `szName` vyrovnávací paměti.  
  
 `szName`  
 Ukazatel na pole znaků, který obsahuje název proměnné.  
  
## <a name="remarks"></a>Poznámky  
  
> [!NOTE]
>  Tato metoda je pouze k dispozici s .NET Native.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorDebugVariableSymbol – rozhraní](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [Rozhraní pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
