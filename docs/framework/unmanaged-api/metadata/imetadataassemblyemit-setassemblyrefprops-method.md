---
title: IMetaDataAssemblyEmit::SetAssemblyRefProps – metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b6c29861faa469f03ca5f2d3cb18e95b3e78f52
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489901"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyRefProps – metoda
Upraví zadaný `AssemblyRef` struktury metadat.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `ar`  
 [in] Token metadat, který určuje `AssemblyRef` struktury metadat má být upraven.  
  
 `pbPublicKeyOrToken`  
 [in] Veřejný klíč vydavatele odkazovaných sestavení.  
  
 `cbPublicKeyOrToken`  
 [in] Velikost v bajtech `pbPublicKeyOrToken`.  
  
 `szName`  
 [in] Uživatelsky čitelná textová název sestavení.  
  
 `pMetaData`  
 [in] Ukazatel na instanci assemblymetadata –, který obsahuje informace o verzi, platformy a národní prostředí pro sestavení.  
  
 `pbHashValue`  
 [in] Ukazatel na hodnotu hash dat přidružené k sestavení.  
  
 `cbHashValue`  
 [in] Velikost v bajtech `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 [in] Bitová kombinace hodnot [assemblyrefflags –](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) hodnoty, které určují atributy odkazovaného sestavení.  
  
## <a name="remarks"></a>Poznámky  
 K vytvoření `AssemblyRef` struktury metadat, použijte [imetadataassemblyemit::defineassemblyref –](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Cor.h  
  
 **Knihovna:** Použít jako prostředek v MsCorEE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [IMetaDataAssemblyEmit – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
