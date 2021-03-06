---
title: ICorDebugNativeFrame::SetIP – metoda
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33a4315d8908906e9ae1511aa9501969752d4af6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484859"
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP – metoda
Nastaví ukazatele na instrukci do zadaného umístění posunu v nativním kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `nOffset`  
 [in] Umístění posunu v nativním kódu.  
  
## <a name="remarks"></a>Poznámky  
 Volání `SetIP` okamžitě zneplatnit všechny rámce a řetězce pro aktuální vlákno. Pokud ladicí program potřebuje informace o snímcích po volání `SetIP`, je nutné provést nové trasování zásobníku.  
  
 [Icordebug –](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) se pokusí uchovat rámce zásobníku v platném stavu. Ale i v případě, že rámec je v platném stavu, co se týče modul runtime, stále může existovat problémy, jako je například neinicializovaných místních proměnných a tak dále. Volající zodpovídá za pojištění integrita spuštěný program.  
  
 Na 64bitových platformách, ukazatele na instrukci nelze přesunout z celkového počtu `catch` nebo `finally` bloku. Pokud `SetIP` nazývá provést přesun na 64bitové platformě, vrátí HRESULT označující selhání.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:

