---
title: Struktura AXL_AUTHENTICODE_TIMESTAMPER_INFO
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8060e95f06fd53ca985f84666cc81cfe49394fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659654"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a>Struktura AXL_AUTHENTICODE_TIMESTAMPER_INFO
Definuje informace o čase stamper Authenticode.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|`cbSize`|Velikost struktury.|  
|`dwError`|Kód chyby|  
|`algHash`|Hashovací algoritmus.|  
|`ftTimestamp`|Doba časového razítka.|  
|`pChainContext`|Čas stamper kontextu řetězu.  Zobrazit [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) struktury.|  
  
## <a name="see-also"></a>Viz také:
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
