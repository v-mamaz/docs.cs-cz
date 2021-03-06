---
title: PFN_CLRDataCreateInstance – ukazatel na funkci
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19d7284399719dd848af43765a392802a589fc33
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492527"
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a>PFN_CLRDataCreateInstance – ukazatel na funkci
Odkazuje na funkci, která vytvoří objekt rozhraní pro zadanou cílovou položku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `iid`  
 [in] Identifikátor rozhraní má být vytvořena.  
  
 `target`  
 [in] Ukazatel na uživatelské implementované [iclrdatatarget –](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) objekt, který představuje cílovou položku, pro který chcete vytvořit objekt rozhraní.  
  
 `iface`  
 [out] Ukazatel na adresu objektu vrácené rozhraní.  
  
## <a name="remarks"></a>Poznámky  
 `ICLRDataTarget` Objektu je implementováno tvůrci ladění aplikace. Implementace závisí na typu představované cílovou položku. Cílová položka může být proces, výpis paměti, vzdálený počítač a tak dále.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** ClrData.idl  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [Globální statické funkce pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
