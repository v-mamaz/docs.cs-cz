---
title: GetCachePath – funkce
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc29c5f975424e3dbe91e206f6a05f830d760398
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472648"
---
# <a name="getcachepath-function"></a>GetCachePath – funkce
Získá cestu k sestavení v mezipaměti, pomocí zadané příznaky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>Parametry  
 `dwCacheFlags`  
 [in] [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) hodnotu, která určuje zdroj sestavení v mezipaměti.  
  
 `pwzCachePath`  
 [out] Vrácený ukazatel na cestu.  
  
 `pcchPath`  
 [out v] Požadovaná maximální délce `pwzCachePath`a po návratu, skutečná délka `pwzCachePath`.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Fusion.h  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [ASM_CACHE_FLAGS – výčet](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [Globální statické funkce pro fúze](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
