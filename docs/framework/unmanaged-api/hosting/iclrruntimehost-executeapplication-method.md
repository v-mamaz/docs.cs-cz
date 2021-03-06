---
title: ICLRRuntimeHost::ExecuteApplication – metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c2a56d153fcd7238f58c9650b8db08b3f39edaa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496271"
---
# <a name="iclrruntimehostexecuteapplication-method"></a>ICLRRuntimeHost::ExecuteApplication – metoda
Použít ve scénářích nasazení na bázi manifest ClickOnce k určení aktivovat v nové doméně aplikace. Další informace o těchto scénářích najdete v tématu [ClickOnce – zabezpečení a nasazení](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `pwzAppFullName`  
 [in] Úplný název aplikace, jak jsou definovány pro <xref:System.ApplicationIdentity>.  
  
 `dwManifestPaths`  
 [in] Počet součástí řetězce `ppwzManifestPaths` pole.  
  
 `ppwzManifestPaths`  
 [in] Volitelné. Pole řetězců obsahující cesty k manifestu aplikace.  
  
 `dwActivationData`  
 [in] Počet součástí řetězce `ppwzActivationData` pole.  
  
 `ppwzActivationData`  
 [in] Volitelné. Pole řetězců obsahující data aktivace aplikace, jako je například část řetězec dotazu adresy URL pro aplikace nasazené prostřednictvím webu.  
  
 `pReturnValue`  
 [out] Hodnota vrácená ze vstupního bodu aplikace.  
  
## <a name="return-value"></a>Návratová hodnota  
  
|HRESULT|Popis|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication` bylo úspěšně vráceno.|  
|HOST_E_CLRNOTAVAILABLE|Modul CLR (CLR) se nenačetl do procesu nebo modul CLR je ve stavu, ve kterém nelze spouštět spravovaný kód nebo úspěšně zpracovat volání.|  
|HOST_E_TIMEOUT|Vypršel časový limit volání.|  
|HOST_E_NOT_OWNER|Volající není vlastníkem zámku.|  
|HOST_E_ABANDONED|Událost byla zrušena při zablokování vlákna nebo vlákénka čekal na něj.|  
|E_FAIL|Došlo k neznámé katastrofických selhání. Pokud metoda vrátí E_FAIL, modul CLR už nejsou použitelné v rámci procesu. Následující volání metody hostování vrací HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Poznámky  
 `ExecuteApplication` slouží k aktivaci aplikací ClickOnce v doméně se nově vytvořená aplikace.  
  
 `pReturnValue` Výstupní parametr je nastaven na hodnotu vrácenou příkazem aplikace. Pokud zadáte hodnotu null pro `pReturnValue`, `ExecuteApplication` není selže, ale nevrací hodnotu.  
  
> [!IMPORTANT]
>  Nevolejte [metoda Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) před voláním metody `ExecuteApplication` metodu aktivace manifest aplikace. Pokud `Start` metoda je volána nejprve `ExecuteApplication` volání metody se nezdaří.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** MSCorEE.h  
  
 **Knihovna:** Zahrnuté jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [ICLRRuntimeHost – rozhraní](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [SetAppDomainManager – metoda](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [Návod: Stahování sestavení na vyžádání rozhraním API pro nasazení ClickOnce pomocí Návrháře](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
