---
title: ICorProfilerCallback::AppDomainCreationFinished – metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08a0ed8303804df1889973fe3ffab6db93249d5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481440"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>ICorProfilerCallback::AppDomainCreationFinished – metoda
Upozornění profileru vytvoření domény aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a>Parametry  
 `appDomainId`  
 [in] Určuje doménu, která byla vytvořena.  
  
 `hrStatus`  
 [in] HRESULT, která určuje, zda vytváření domény aplikace byla úspěšně dokončena.  
  
## <a name="remarks"></a>Poznámky  
 ID aplikace není platná pro všechny žádost o informace, dokud `AppDomainCreationFinished` metoda je volána.  
  
 Některé části načtení domény aplikace může pokračovat po `AppDomainCreationFinished` zpětného volání. Selhání hodnoty HRESULT v `hrStatus` naznačuje chybu. Ale úspěch HRESULT v `hrStatus` značí pouze, že první část vytváření domény aplikace proběhla úspěšně.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorProf.idl, CorProf.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorProfilerCallback – rozhraní](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
