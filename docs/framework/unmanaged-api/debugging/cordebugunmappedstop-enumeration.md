---
title: CorDebugUnmappedStop – výčet
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6f22c045be9af71644415ae3b6b5e64d3e399dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495432"
---
# <a name="cordebugunmappedstop-enumeration"></a>CorDebugUnmappedStop – výčet
Určuje typ nenamapované kód, který můžete aktivovat zastavení provádění kódu pomocí krokovače.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|`STOP_NONE`|Není zastavit v libovolný typ nenamapované kódu.|  
|`STOP_PROLOG`|Zastavte v kódu prologu.|  
|`STOP_EPILOG`|Zastavení Kód epilogu.|  
|`STOP_NO_MAPPING_INFO`|Zastavte v kódu, který neobsahuje žádné informace o mapování.|  
|`STOP_OTHER_UNMAPPED`|Zastavte v nenamapované kódu, který se nevejde do kódu prologu, epilogu, ne informace mapování nebo nespravované kategorie.|  
|`STOP_UNMANAGED`|Zastavte v nespravovaném kódu. Tato hodnota je platný pouze pro definiční ladění.|  
|`STOP_ALL`|Zastavte ve všech typech nenamapované kódu.|  
  
## <a name="remarks"></a>Poznámky  
 Použití [icordebugstepper::setunmappedstopmask –](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) metoda nastavit příznaky, které určují nenamapované kódu, ve kterém se zastaví krokovače.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [Výčty pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
