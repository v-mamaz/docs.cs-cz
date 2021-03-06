---
title: ICorDebugThread::EnumerateChains – metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e01f94e9574ebc032bc45490fd88ff92e9104aa3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482857"
---
# <a name="icordebugthreadenumeratechains-method"></a>ICorDebugThread::EnumerateChains – metoda
Získá enumerátor icordebugchainenum –, který obsahuje všechny řetězů zásobníku v tomto objektu ICorDebugThread ukazatel rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `ppChains`  
 [out] Ukazatel na adresu `ICorDebugChainEnum` zřetězí objekt, který umožňuje výčet všech zásobníku v tomto vláknu, začíná řetězec aktivní (to znamená, poslední).  
  
## <a name="remarks"></a>Poznámky  
 Řetěz zásobníku představuje fyzické volání zásobníku pro vlákno. V následujících případech vytvoření hranice řetěz zásobníku:  
  
-   Spravované na nespravované nebo nespravovaného do spravovaného přechodu.  
  
-   Přepnutí kontextu.  
  
-   A zneužití uživatelské vlákno ladicího programu.  
  
 V jednoduchém případě pro vlákno, na kterém běží v rámci jednoho čistě spravovaném kódu bude existovat shoda mezi vlákny a řetězů zásobníku.  
  
 Ladicí program může být vhodné ke změně uspořádání zásobníky fyzická volání všech vláken v logické zásobníky volání. To by vyžadovalo řazení řetězců všechna vlákna podle jejich vztahů volající/volaný a přerozdělit je.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
