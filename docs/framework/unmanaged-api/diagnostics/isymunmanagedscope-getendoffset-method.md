---
title: ISymUnmanagedScope::GetEndOffset – metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 47db4313354b00514084ec1110710cbd174a3788
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492618"
---
# <a name="isymunmanagedscopegetendoffset-method"></a>ISymUnmanagedScope::GetEndOffset – metoda
Získá koncové odsazení pro tento obor.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Ukazatel `ULONG32` , která obdrží koncové odsazení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud metoda uspěje; S_OK v opačném případě E_FAIL nebo jiný kód chyby.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Viz také:
- [ISymUnmanagedScope – rozhraní](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [GetStartOffset – metoda](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
