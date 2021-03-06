---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions – metoda
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c9e3aa909c4eb674b166bfd14feb59e35df4cfd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488523"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a>ICLRDataEnumMemoryRegions::EnumMemoryRegions – metoda
Vytvoří výčet zadané oblasti paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `callback`  
 [in] Ukazatel [iclrdataenummemoryregionscallback –](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instanci, která volá tuto metodu pro každou oblast paměti výčtu oznámit ladicí program výsledku.  
  
 Výčet oblastí paměti bude pokračovat i v případě, že zpětné volání naznačuje chybu.  
  
 `miniDumpFlags`  
 [in] Nepoužívá se.  
  
 `clrFlags`  
 [in] Hodnota [clrdataenummemoryflags –](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) výčet, který určuje oblastí paměti pro provedení výčtu.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda používá zadaný [iclrdataenummemoryregionscallback –](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance oznámit volajícímu výsledky.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** ClrData.idl, ClrData.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ICLRDataEnumMemoryRegions – rozhraní](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
