---
title: ImportFile – metoda
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16793cfd93ce296ba0e2bc70c59c22d598aacacd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500665"
---
# <a name="importfile-method"></a>ImportFile – metoda
Importuje nevázaného modulů a sestavení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  
 `pszFilename`  
 Plně kvalifikovaný název souboru k importu.  
  
 `pszTargetName`  
 Volitelné výstupní název souboru, který slouží k přejmenování souboru, jako je propojený do sestavení.  
  
 `fSmartImport`  
 Při hodnotě TRUE se používá importtypes –, jinak se import je nutné provést ručně.  
  
 `pImportToken`  
 Ukazatel na token, kam se budou ukládat jedinečný Identifikátor souboru. Soubor může být sestavení nebo souboru.  
  
 `ppAssemblyScope`  
 Přijímá ukazatel na [imetadataassemblyimport – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md). Může mít hodnotu NULL, pokud soubor není sestavení.  
  
 `pdwCountOfScopes`  
 Ukazatel na počet souborů a/nebo obory, které byly naimportovány.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud metoda uspěje, vrátí hodnotu S_OK.  
  
## <a name="requirements"></a>Požadavky  
 Vyžaduje alink.h  
  
## <a name="see-also"></a>Viz také:
- [IALink – rozhraní](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 – rozhraní](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Rozhraní API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
