---
title: GetHashFromBlob – funkce
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d9e7b52c9061a1a7b470f9d4abf735e605087dc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352071"
---
# <a name="gethashfromblob-function"></a>GetHashFromBlob – funkce

Získá hodnotu hash sestavení na adrese zadaná paměťová, pomocí zadané hashovacího algoritmu.

Tato funkce je zastaralá. Použití [iclrstrongname::gethashfromblob –](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) metoda místo.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a>Parametry

`pbBlob`\
[in] Ukazatel na adresu blok paměti určený k hashovat.

`cchBlob`\
[in] Délka v bajtech, bloku paměti.

`piHashAlg`\
[out v] Konstanta, která určuje algoritmus hash. Použít nulu pro výchozí algoritmus.

`pbHash`\
[out] Vrácená hodnota hash vyrovnávací paměti.

`cchHash`\
[in] Požadovaná maximální velikost `pbHash`.

`pchHash`\
[out] Velikost v bajtech, vráceného `pbHash`.

## <a name="requirements"></a>Požadavky

**Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).

**Záhlaví:** StrongName.h

**Knihovna:** Zahrnuté jako prostředek v MsCorEE.dll

**Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Viz také:

- [GetHashFromBlob – metoda](../hosting/iclrstrongname-gethashfromblob-method.md)
- [ICLRStrongName – rozhraní](../hosting/iclrstrongname-interface.md)