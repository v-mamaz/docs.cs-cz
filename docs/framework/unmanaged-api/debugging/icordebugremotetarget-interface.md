---
title: ICorDebugRemoteTarget – rozhraní
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eb57295b72dade0bb396b3caa724b21722b26db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743501"
---
# <a name="icordebugremotetarget-interface"></a>ICorDebugRemoteTarget – rozhraní
Poskytuje metody, které umožňují vývojářům ladit aplikace programu Silverlight v prostředí common language runtime (CLR).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[ICorDebugRemoteTarget::GetHostName – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|Vrátí název hostitele nebo IP adresu vzdáleného počítače.|  
  
## <a name="remarks"></a>Poznámky  
 Ladění ve smíšeném režimu (tj. spravovaný a nativní kód) není podporováno ve Windows 95, Windows 98 nebo Windows ME, nebo na platformách x x86 (například IA-64 a AMD64).  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl  
  
 **Knihovna:** : CorGuids.lib  
  
 **Verze rozhraní .NET framework:** 3.5 SP1  
  
## <a name="see-also"></a>Viz také:
- [ICorDebugRemote – rozhraní](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [ICorDebug – rozhraní](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Rozhraní pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
