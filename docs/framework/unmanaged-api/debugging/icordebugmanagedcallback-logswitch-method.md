---
title: ICorDebugManagedCallback::LogSwitch – metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 040c7dea7f751accb801f8fda190e9387c7aede1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466164"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>ICorDebugManagedCallback::LogSwitch – metoda
Ladicí program upozorní, že společným pojítkem language runtime (CLR) spravované volal metodu <xref:System.Diagnostics.Switch> třídy k vytvoření, úpravě nebo odstranění přepínače ladění a trasování.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a>Parametry  
 `PAppDomain`  
 [in] Ukazatel na objekt ICorDebugAppDomain, který představuje doménu aplikace obsahující spravované vlákna, které vytvořili, změněn nebo odstraněn přepínač ladění a trasování.  
  
 `pThread`  
 [in] Ukazatel na objekt ICorDebugThread, která představuje spravované vlákno.  
  
 `lLevel`  
 [in] Hodnota, která určuje úroveň závažnosti popisné zprávy, která byla zapsána do protokolu událostí.  
  
 `ulReason`  
 [in] Hodnota [logswitchcallreason –](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) výčet, který označuje, operace provedené na přepínač ladění a trasování.  
  
 `pLogSwitchName`  
 [in] Ukazatel na název přepínače, ladění a trasování.  
  
 `pParentName`  
 [in] Ukazatel na název nadřazeného přepínače, ladění a trasování.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorDebugManagedCallback – rozhraní](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
