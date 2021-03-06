---
title: Funkce SetSecurity (referenční dokumentace nespravovaného rozhraní API)
description: Funkce SetSecurity získá token zosobnění aktuální vlákno.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7200e3a19fcadabb5e149c38b620b3f60907c392
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377414"
---
# <a name="setsecurity-function"></a>SetSecurity – funkce

Získá token zosobnění spojený s aktuálním vláknem. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntaxe

```
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a>Parametry

`pNeedToReset`\
[out] Když funkce vrátí, obsahuje ukazatel na `boolean` , která označuje, zda tento token by se měla obnovit voláním [ResetSecurity](resetsecurity.md) funkce.

`token`\
[out] Když funkce vrátí, obsahuje ukazatel na popisovač token zosobnění spojený s aktuálním vláknem. Jeho hodnota může být `null` Pokud neexistuje žádný token spojené s aktuálním vláknem. 

## <a name="return-value"></a>Návratová hodnota

Pokud funkce uspěje, vrácená hodnota je `S_OK` (0).

Pokud funkce selže, vrácená hodnota je kód chyby. Chcete-li získat rozšířené informace o chybě, zavolejte [GetErrorInfo –](geterrorinfo.md) funkce.

## <a name="requirements"></a>Požadavky

 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).

 **Záhlaví:** WMINet_Utils.idl

 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Viz také:

- [WMI a čítače výkonu (referenční dokumentace nespravovaného rozhraní API)](index.md)