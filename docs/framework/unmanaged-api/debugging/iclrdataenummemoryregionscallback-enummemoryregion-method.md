---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion – metoda
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d744c74676695ca48a6d3607732fc70dca55bcaf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495257"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion – metoda
Volané [iclrdataenummemoryregions::enummemoryregions –](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) k poskytnutí zprávy ladicímu programu výsledek pokusu o výčet určité oblasti paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `address`  
 [in] Počáteční adresa, která byla pro provedení výčtu oblasti paměti.  
  
 `size`  
 [in] Velikost v bajtech, oblasti paměti.  
  
## <a name="remarks"></a>Poznámky  
 `ICLRDataEnumMemoryRegions::EnumMemoryRegions` Metoda zavolá tato metoda zpětného volání po každém pokusu o výčet oblasti paměti. Výčet pokračovat i v případě, že tato metoda vrátí hodnotu HRESULT označující selhání.  
  
 Oblasti hlášených toto zpětné volání může být duplicitní nebo překrývající se oblasti.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** ClrData.idl, ClrData.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICLRDataEnumMemoryRegionsCallback – rozhraní](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
