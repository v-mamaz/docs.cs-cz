---
title: "ASM_CACHE_FLAGS – výčet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASM_CACHE_FLAGS
api_location: fusion.dll
api_type: COM
f1_keywords: ASM_CACHE_FLAGS
helpviewer_keywords: ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 767cae15c37b8c62d47085533ea9fa3ce4957963
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="asmcacheflags-enumeration"></a>ASM_CACHE_FLAGS – výčet
Určuje zdroj sestavení, která je reprezentována [iassemblycacheitem –](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) v globální mezipaměti sestavení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Vytvoří výčet mezipaměti předkompilovaných sestavení pomocí Ngen.exe.|  
|`ASM_CACHE_GAC`|Vytvoří výčet globální mezipaměti sestavení.|  
|`ASM_CACHE_DOWNLOAD`|Vytvoří výčet sestavení, které byly staženy na vyžádání nebo která byla vytvořena stínová kopie.|  
|`ASM_CACHE_ROOT`|Určuje, že [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) funkce by měla vrátit cestu do globální mezipaměti sestavení pro modul CLR (CLR) verze 2.0. Smysl pouze v kontextu volání [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
|`ASM_CACHE_ROOT_EX`|Určuje, že [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) funkce by měla vrátit cestu do globální mezipaměti sestavení pro CLR verze 4. Smysl pouze v kontextu volání [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Fusion.h  
  
 **Knihovna:** zahrnuty jako prostředek v MsCorEE.dll  
  
 **Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [GetCachePath – funkce](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 [Iassemblycacheitem – rozhraní](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 [Výčty fúzí](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)