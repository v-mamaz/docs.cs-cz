---
title: ICLRRuntimeInfo::GetProcAddress – metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da9ae70056e3ef5d6d9e03fde1dcf8775e5d118e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498949"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a>ICLRRuntimeInfo::GetProcAddress – metoda
Získá adresu zadané funkce, která byla exportována z common language runtime (CLR) přidružené k tomuto rozhraní.  
  
 Tato metoda nahrazuje [getrealprocaddress –](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) funkce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a>Parametry  
 `pszProcName`  
 [in] Název exportované funkce.  
  
 `ppProc`  
 [out] Adresu exportované funkce.  
  
## <a name="return-value"></a>Návratová hodnota  
 Tato metoda vrátí následující konkrétní HRESULT, stejně jako hodnota HRESULT chyby, které označují selhání metoda.  
  
|HRESULT|Popis|  
|-------------|-----------------|  
|S_OK|Metoda byla úspěšně dokončena.|  
|E_POINTER|`pszProcName` nebo `ppProc` má hodnotu null.|  
|CLR_E_SHIM_RUNTIMEEXPORT|Zadaná funkce není exportované funkce.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda způsobí, že modul CLR do načtena, avšak nebyla inicializována.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** MetaHost.h  
  
 **Knihovna:** Zahrnuté jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICLRRuntimeInfo – rozhraní](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Rozhraní pro hostování](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hostování](../../../../docs/framework/unmanaged-api/hosting/index.md)
