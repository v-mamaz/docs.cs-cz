---
title: ICorProfilerCallback::RuntimeSuspendFinished – metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f69c39938384c7feca28ae40aba3e80a0ba28ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706651"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>ICorProfilerCallback::RuntimeSuspendFinished – metoda
Oznámí profileru, že modul runtime dokončil pozastavení všechna vlákna modulu runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>Poznámky  
 Všechna vlákna modulu runtime, které jsou v nespravovaném kódu se může pokračovat, spuštění, dokud se pokusí znovu zadat modul runtime. V tomto okamžiku se bude také být pozastaveno, dokud modul runtime bude pokračovat. To platí i pro nová vlákna, které zadejte modul runtime. Všechna vlákna v modulu runtime jsou že buď pozastaveno okamžitě, pokud jsou již v paralelní kód, nebo mu zobrazit výzva k pozastavení, když dosáhnou paralelní kód.  
  
 `RuntimeSuspendFinished` Zpětného volání je zaručeno, ke kterým dochází ve stejném vlákně jako [icorprofilercallback::runtimesuspendstarted –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) zpětného volání.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorProf.idl, CorProf.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorProfilerCallback – rozhraní](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [RuntimeSuspendAborted – metoda](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
