---
title: IAssemblyCache::CreateAssemblyCacheItem – metoda
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 476f28b37efef483b31ad548d3db62c820d536c5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489056"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a>IAssemblyCache::CreateAssemblyCacheItem – metoda
Získá odkaz na novou [iassemblycacheitem –](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `dwFlags`  
 [in] Příznaky definované v Fusion.idl. Podporovány jsou následující hodnoty:  
  
-   IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)  
  
-   IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0X00000002)  
  
 `pvReserved`  
 [in] Vyhrazeno pro budoucí rozšíření. `pvReserved` musí být referencí s hodnotou null.  
  
 `ppAsmItem`  
 [out] Vrácený `IAssemblyCacheItem` ukazatele.  
  
 `pszAssemblyName`  
 [in, volitelné] Uncanonicalized, oddělené čárkami `name=value` dvojice.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Fusion.h  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [IAssemblyCache – rozhraní](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [IAssemblyCacheItem – rozhraní](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
