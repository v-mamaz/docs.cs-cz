---
title: CreateICeeFileGen – funkce
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6931b03e087e963172cb72462327de185041563e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499066"
---
# <a name="createiceefilegen-function"></a>CreateICeeFileGen – funkce
Vytvoří [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objektu.  
  
 Tato funkce se již nepoužívá v [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `ceeFileGen`  
 [out] Ukazatel na novou adresu `ICeeFileGen` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Tato metoda vrací standardní kódy chyb COM.  
  
## <a name="remarks"></a>Poznámky  
 `ICeeFileGen` Objektu se používá k vytvoření common language runtime (CLR) souborů (PE portable executable).  
  
 Volání [destroyiceefilegen –](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) funkce zrušení `ICeeFileGen` objekt po dokončení.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** ICeeFileGen.h  
  
 **Knihovna:** MSCorPE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [Zastaralé funkce pro hostování CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
