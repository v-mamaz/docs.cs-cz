---
title: ICorDebugDataTarget::GetPlatform – metoda
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab4cdaf87b6fd65eecbe62f2e3b927eee6094e72
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496167"
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform – metoda
Poskytuje informace o platformě, včetně architektury procesoru a operačního systému, na kterém je spuštěný Cílový proces.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Parametry  
 `pTargetPlatform`  
 [out] Ukazatel [cordebugplatformenum –](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) výčet, který popisuje cílovou platformu.  
  
## <a name="remarks"></a>Poznámky  
 `CorDebugPlatformEnum` Návratová hodnota výčtu je používán [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) rozhraní zjistěte podrobnosti cílového procesu, jako je například velikost ukazatele, rozložení prostoru adres, nastavení registru, formát instrukce, kontext rozložení a konvence volání.  
  
 `pTargetPlatform` Může hodnota odkazovat na platformu, která je emulovaných pro cílové místo určení skutečné hardwarové používá. Například by měl použít proces, který běží ve Windows v prostředí Windows (WOW) na 64-bit edition operačního systému Windows `CORDB_PLATFORM_WINDOWS_X86` hodnotu [cordebugplatformenum –](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) výčtu.  
  
 Tato metoda musí být úspěšný. Pokud selže, nepoužitelný cílovou platformu. Metoda může selhat z následujících důvodů:  
  
-   Platforma, která je emulovaných pro cíl nepoužitelné.  
  
-   Skutečné hardwarové na cílové platformě není použitelná.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorDebugDataTarget – rozhraní](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Rozhraní pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Ladění](../../../../docs/framework/unmanaged-api/debugging/index.md)
