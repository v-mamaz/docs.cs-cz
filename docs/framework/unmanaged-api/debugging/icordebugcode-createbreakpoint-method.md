---
title: ICorDebugCode::CreateBreakpoint – metoda
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df27d2ab609551bb7a7f6f4b0ff8c7118c9f93f8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478671"
---
# <a name="icordebugcodecreatebreakpoint-method"></a>ICorDebugCode::CreateBreakpoint – metoda
Vytvoří zarážku v tomto segmentu kódu v zadaném posunu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `offset`  
 [in] Posun, na kterém chcete vytvořit zarážku.  
  
 `ppBreakpoint`  
 [out] Ukazatel na adresu objektu "icordebugfunctionbreakpoint –", který představuje zarážku.  
  
## <a name="remarks"></a>Poznámky  
 Předtím, než je zarážky aktivní, je nutné přidat do objektu process.  
  
 Pokud tento kód je kód Microsoft intermediate language (MSIL) a je just-in-time (JIT)-kompilované, nativní verzi kódu, zarážka se použijí v kompilaci JIT kódu. (Stejný je hodnota true, pokud kód je zkompilován JIT Kompilátorem později.)  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také:

