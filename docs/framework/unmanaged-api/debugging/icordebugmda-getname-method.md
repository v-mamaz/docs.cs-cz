---
title: ICorDebugMDA::GetName – metoda
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f0ed1aa0d095b13a90ed5b036719e71ccc8e272
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468192"
---
# <a name="icordebugmdagetname-method"></a>ICorDebugMDA::GetName – metoda
Získá řetězec obsahující název pomocníka spravovaného ladění (MDA) reprezentována [icordebugmda –](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `cchName`  
 [in] Velikost `szName` pole.  
  
 `pcchName`  
 [out] Ukazatel na délka názvu.  
  
 `szName`  
 [out] Pole pro uložení názvu.  
  
## <a name="remarks"></a>Poznámky  
 MDA názvy jsou jedinečné hodnoty. `GetName` Metody je vhodné výkonu alternativou k získání datový proud XML a extrahování název z datového proudu na základě schématu.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorDebugMDA – rozhraní](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [Diagnostikování chyb pomocí asistentů spravovaného ladění](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
