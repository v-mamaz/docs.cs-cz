---
title: IHostTaskManager – rozhraní
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d7b85a30a5abd9186f039aa21cbe7790325e4f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545644"
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager – rozhraní
Poskytuje metody, které umožňují common language runtime (CLR) pro práci s úkoly prostřednictvím hostitele namísto použití funkce dělení na vlákna nebo vlákénka standardním operačním systému.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[BeginDelayAbort – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Upozorní, že na hostitele, spravovaný kód je zadání období, ve kterém nesmí být aktuální úloha přerušena.|  
|[BeginThreadAffinity – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Upozorní, že na hostitele, spravovaný kód je zadání období, ve kterém nesmí aktuální úlohy přesunout do jiného vlákna operačního systému.|  
|[CallNeedsHostHook – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Umožňuje hostiteli k určení, zda modul common language runtime můžete vložené určené volání nespravované funkci.|  
|[CreateTask – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Požadavky, že hostitel vytvoří nový úkol.|  
|[EndDelayAbort – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Upozorní na hostitele, spravovaný kód se ukončuje období, ve kterém nesmí být aktuální úloha přerušena, po dřívějším volání `BeginDelayAbort`.|  
|[EndThreadAffinity – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Upozorní na hostitele, spravovaný kód se ukončuje období, ve kterém nesmí být aktuálního úkolu přesunuty do jinému vláknu operačního systému po dřívějším volání `BeginThreadAffinity`.|  
|[EnterRuntime – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Upozorňuje hostitele, že volání nespravované metody, například platformu vyvolat metodu, vrací řízení provádění modulu CLR.|  
|[GetCurrentTask – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Získá ukazatel rozhraní k úkolu, který aktuálně spouští ve vlákně operačního systému, ze kterého je provedeno toto volání.|  
|[GetStackGuarantee – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Získá velikost místa zásobníku, které je zaručeno, že bude k dispozici po dokončení operace zásobníku, ale před ukončením procesu.|  
|[LeaveRuntime – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Upozorní, že na hostitele, spravovaný kód se chystá provést volání nespravované funkci.|  
|[ReverseEnterRuntime – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Upozorňuje hostitele, že je se k volání do common language runtime (CLR) z nespravovaného kódu.|  
|[ReverseLeaveRuntime – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Upozorňuje hostitele, že je ovládací prvek CLR opuštění a zadáním nespravované funkci, která byla, pak volá ze spravovaného kódu.|  
|[SetCLRTaskManager – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Poskytuje ukazatel rozhraní k hostiteli [iclrtaskmanager –](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implementován modulem CLR.|  
|[SetLocale – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Upozorňuje hostitele, CLR se změnila národní prostředí na aktuálního úkolu.|  
|[SetStackGuarantee – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Vyhrazeno pouze pro interní použití.|  
|[SetUILocale – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Upozorňuje hostitele, že národní prostředí uživatelského rozhraní se změnil na aktuální úlohu.|  
|[Sleep – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Upozorňuje hostitele, že aktuální úloha přechází do režimu spánku.|  
|[SwitchToTask – metoda](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Upozorňuje hostitele, že by měla přepnutí aktuálního úkolu.|  
  
## <a name="remarks"></a>Poznámky  
 `IHostTaskManager` CLR k vytváření a správě úloh, umožňuje poskytovat háky hostitele provést akci při předání řízení ze spravovaného do nespravovaného kódu a naopak a určit, určité akce hostitele lze a nelze provést během provádění kódu.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** MSCorEE.h  
  
 **Knihovna:** Zahrnuté jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICLRTask – rozhraní](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager – rozhraní](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask – rozhraní](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Rozhraní pro hostování](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
