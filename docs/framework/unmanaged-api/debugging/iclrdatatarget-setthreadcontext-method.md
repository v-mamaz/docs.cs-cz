---
title: ICLRDataTarget::SetThreadContext – metoda
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4ab183bbe82c8e64b833c8fcdbc1e05ceb18e1f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482246"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a>ICLRDataTarget::SetThreadContext – metoda
Nastaví aktuální kontext ze zadaného vlákna v cílovém procesu. Tato metoda je volána službami common language runtime (CLR) přístup k datům.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `threadID`  
 [in] Operační systém identifikátor vlákna v cílovém procesu.  
  
 `contextSize`  
 [in] Velikost kontext.  
  
 `context`  
 [in] Ukazatel do vyrovnávací paměti, který obsahuje kontext.  
  
 Data v `context` vyrovnávací paměť bude ve formátu Win32 `CONTEXT` struktury. Kontext určuje data registru specifické pro procesor, takže definice Win32 `CONTEXT` struktura závisí na architektuře procesoru. Najdete v souboru WinNT.h hlavičkový soubor pro definici Win32 `CONTEXT` struktury.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je implementováno tvůrci ladění aplikace.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** ClrData.idl, ClrData.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICLRDataTarget – rozhraní](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
