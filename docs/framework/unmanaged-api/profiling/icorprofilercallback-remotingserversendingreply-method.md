---
title: ICorProfilerCallback::RemotingServerSendingReply – metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 655b2af2efcaba82af46e92ae94abf3a4adc349c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500405"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a>ICorProfilerCallback::RemotingServerSendingReply – metoda
Profiler upozorní, že procesu bylo dokončeno zpracování požadavku volání vzdálené metody a je přenášet odpovědi prostřednictvím kanálu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Parametry  
 `pCookie`  
 [in] Ukazatel na identifikátor GUID, který bude odpovídat hodnotu podle [icorprofilercallback::remotingclientreceivingreply –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) za těchto podmínek:  
  
-   Vzdálená komunikace GUID soubory cookie jsou aktivní.  
  
-   Kanál úspěšně odesílá zprávu.  
  
-   Identifikátor GUID soubory cookie jsou aktivní na straně klienta procesu.  
  
 To umožňuje snadno párování tvorby logické volání zásobníku a Vzdálená volání.  
  
 `fIsAsync`  
 [in] Hodnotu, která je `true` Pokud je volání asynchronní; v opačném případě `false`.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorProf.idl, CorProf.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICorProfilerCallback – rozhraní](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
