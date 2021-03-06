---
title: ICorDebugBreakpoint – rozhraní
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7e454c15ddfa977a6d06921a5d80a6c05dca92f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973571"
---
# <a name="icordebugbreakpoint-interface"></a>ICorDebugBreakpoint – rozhraní

Představuje zarážku ve funkci nebo bod sledování na hodnotě.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Activate – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|Nastaví aktivní stav `ICorDebugBreakpoint`.|  
|[IsActive – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|Získá hodnotu, která určuje, jestli to `ICorDebugBreakpoint` je aktivní.|  
  
## <a name="remarks"></a>Poznámky  
 Zarážky přímo nepodporuje podmíněné výrazy. Pokud se tato funkce požaduje, ladicí program musí implementovat ji nad `ICorDebugBreakpoint`.  
  
 Icordebugfunctionbreakpoint – rozhraní rozšiřuje `ICorDebugBreakpoint` pro podporu zarážek v rámci funkcí.  
  
> [!NOTE]
>  Toto rozhraní nepodporuje vzdálené volání, mezi počítači nebo procesy.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [Rozhraní pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
