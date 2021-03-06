---
title: ICorDebugAppDomain::GetName – metoda
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7939f7b1c0c725bb4e8c642bc38121dd755da5e2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471049"
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName – metoda
Získá název domény aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `cchName`  
 [in] Velikost `szName` pole. Tuto hodnotu nastavte na hodnotu nula, tato metoda uvést do režimu dotazu.  
  
 `pcchName`  
 [out] Ukazatel na velikost název nebo počet znaků ve skutečnosti vrátí v `szName`. V režimu dotazu, tato hodnota umožňuje volajícímu vědět, jak velkou vyrovnávací paměti k přidělení pro název.  
  
 `szName`  
 [out] Pole uchovávající název domény aplikace.  
  
## <a name="remarks"></a>Poznámky  
 Ladicí program volá `GetName` jednou metodu k získání velikost vyrovnávací paměti, třeba název. Ladicí program přiděluje vyrovnávací paměti a potom volá metodu podruhé tak, aby vyplnil vyrovnávací paměti. První volání, získat její velikost názvu, se označuje jako *režim dotazů*.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
