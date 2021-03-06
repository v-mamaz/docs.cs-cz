---
title: ICLRRuntimeInfo::GetDefaultStartupFlags – metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7ef61c8ae1d8c2e5cf1fee80d8900a0e0e7f73b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493424"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>ICLRRuntimeInfo::GetDefaultStartupFlags – metoda
Získá příznaky spuštění a konfiguračním souboru hostitele, který se použije ke spuštění modulu runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a>Parametry  
 `pdwStartupFlags`  
 [out] Ukazatel na příznaky spuštění hostitele, které jsou aktuálně nastaveny.  
  
 `pwzHostConfigFile`  
 [out] Ukazatel na cestu k adresáři aktuálního konfiguračního souboru hostitele.  
  
 `pcchHostConfigFile`  
 [out v] Na vstupní velikost `pwzHostConfigFile`předešli přetečení vyrovnávací paměti. Pokud `pwzHostConfigFile` je null, vrátí metoda požadovaná velikost `pwzHostConfigFile` pro předběžné přidělení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Tato metoda vrátí následující konkrétní HRESULT a také HRESULT chyby, které označují selhání metoda.  
  
|HRESULT|Popis|  
|-------------|-----------------|  
|S_OK|Metoda byla úspěšně dokončena.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí výchozí hodnoty příznak (`STARTUP_CONCURRENT_GC` a `NULL`), nebo hodnoty poskytnuté předchozí volání [iclrruntimeinfo::setdefaultstartupflags – metoda](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), nebo hodnoty nastavené podle těchto sloupců `CorBind*` metody, pokud jsou vázány na tento modul runtime.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** MetaHost.h  
  
 **Knihovna:** Zahrnuté jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICLRRuntimeInfo – rozhraní](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Rozhraní pro hostování](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hostování](../../../../docs/framework/unmanaged-api/hosting/index.md)
