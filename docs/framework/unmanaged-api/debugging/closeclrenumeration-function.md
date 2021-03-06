---
title: CloseCLREnumeration – funkce
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60b6d9c302cd3af9f41e5a8dce62d7eb268c4198
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491874"
---
# <a name="closeclrenumeration-function"></a>CloseCLREnumeration – funkce
Zavře žádné platný common language runtime (CLR) pokračovat po spuštění události nachází v poli popisovačů vrácený [enumerateclrs – funkce](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)a uvolní paměť pro cestu pole popisovač a řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a>Parametry  
 `pHandleArray`  
 [in] Ukazatel na pole obslužné rutiny událostí vrácených [enumerateclrs – funkce](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).  
  
 `pStringArray`  
 [in] Ukazatel na pole vrácená z cesty řetězce CLR [enumerateclrs – funkce](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).  
  
 `dwArrayLength`  
 [in] DWORD, který obsahuje velikost (délka) buď `pHandleArray` nebo `pStringArray` (jsou stejné).  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK  
 Popisovače otevírány [enumerateclrs – funkce](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) zavřou, a je uvolněna paměť přidělená pro řetězec a popisovače pole.  
  
 E_INVALIDARG  
 Délka `pHandleArray` neodpovídá délce, které je předáno `dwArrayLength`.  
  
 E_FAIL (nebo jiné E_ návratové kódy)  
 Nelze uvolnit paměť pro funkci `pHandleArray` a `pStringArray`.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** dbgshim.h  
  
 **Knihovna:** dbgshim.dll  
  
 **Verze rozhraní .NET framework:** 3.5 SP1
