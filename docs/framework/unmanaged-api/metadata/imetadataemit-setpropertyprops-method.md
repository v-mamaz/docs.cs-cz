---
title: IMetaDataEmit::SetPropertyProps – metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d836abb63aec0ffd72fb54d342e36bae7191a533
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489030"
---
# <a name="imetadataemitsetpropertyprops-method"></a>IMetaDataEmit::SetPropertyProps – metoda
Nastaví uložená v metadatech pro vlastnosti určené předchozím volání funkce [DefineProperty – metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
## <a name="parameters"></a>Parametry  
 `pr`  
 [in] Token pro vlastnost, která má být změněn  
  
 `dwPropFlags`  
 [in] Vlastnost příznaky.  
  
 `dwCPlusTypeFlag`  
 [in] Typ vlastnosti na výchozí hodnotu.  
  
 `pValue`  
 [in] Výchozí hodnota pro vlastnost.  
  
 `cchValue`  
 [in] Počet (Unicode) znaky v `pValue`.  
  
 `mdSetter`  
 [in] Metoda, která nastaví hodnotu vlastnosti.  
  
 `mdGetter`  
 [in] Metoda, která vrací hodnotu vlastnosti.  
  
 `rmdOtherMethods[]`  
 [in] Pole jiné metody přidružený k vlastnosti. Toto pole se ukončí `mdTokenNil` token.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Cor.h  
  
 **Knihovna:** Použít jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [IMetaDataEmit – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
