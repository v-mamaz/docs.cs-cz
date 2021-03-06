---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime – metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c85888e9d29e7b3ae6ad76d1e534e08a4603ed2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499022"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>ICLRRuntimeInfo::BindAsLegacyV2Runtime – metoda
Vytvoří vazbu aktuální modul runtime pro všechny starší verze common language runtime (CLR) verze 2 aktivace rozhodnutí o zásadách.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Tato metoda vrátí následující konkrétní HRESULT:  
  
|HRESULT|Popis|  
|-------------|-----------------|  
|S_OK|Byla vazba úspěšná, nebo tento modul runtime již byl vázaný jako starší verze runtime 2 Aktivace zásady CLR verze.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Jiný modul runtime je již vázán na starší verze 2 Aktivace zásady CLR verze.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud aktuální modul runtime je již vázán pro všechny starší verze CLR verze 2 aktivace rozhodnutí o zásadách (například pomocí `useLegacyV2RuntimeActivationPolicy` atribut na [ \<spuštění > element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) v konfiguračním souboru), tato metoda nevrátí chybného výsledku; Výsledkem je místo toho S_OK, stejně jako by bylo, pokud metoda bylo úspěšně navázán Zásady aktivace starší verze.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** MetaHost.h  
  
 **Knihovna:** Zahrnuté jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICLRRuntimeInfo – rozhraní](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Rozhraní pro hostování](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hostování](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [\<Po spuštění > – Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
