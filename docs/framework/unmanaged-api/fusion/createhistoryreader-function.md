---
title: CreateHistoryReader – funkce
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e9c9866ee5ee3076d144dc732286ee008cd78c4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487246"
---
# <a name="createhistoryreader-function"></a>CreateHistoryReader – funkce
Vytvoří čtečku historie pro zadaný soubor.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a>Parametry  
 `wzFilePath`  
 [in] Cesta k souboru.  
  
 `ppHistoryReader`  
 [out] Při úspěšném dokončení obsahuje ukazatel na historie čtečky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Tato metoda vrátí standardní kódy chyb modelu COM, jak je definovaný ve WinError.h, kromě hodnotami popsanými v následující tabulce.  
  
|Návratový kód|Popis|  
|-----------------|-----------------|  
|S_OK|Označuje, že metoda byla úspěšně dokončena.|  
|E_INVALIDARG|Označuje, že `wzFilePath` nebo `ppHistoryReader` jsou nastaveny na hodnotu Null.|  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Knihovna:** Fusion.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [Globální statické funkce pro fúze](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
