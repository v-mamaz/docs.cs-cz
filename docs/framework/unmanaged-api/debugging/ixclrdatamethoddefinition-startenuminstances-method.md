---
title: IXCLRDataMethodDefinition::StartEnumInstances – metoda
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e92eea9677731756bdbfcbdcfac1531861fb5dce
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361340"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a>IXCLRDataMethodDefinition::StartEnumInstances – metoda

Poskytuje popisovač pro výčet metodu instance danou `IXCLRDataAppDomain`.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntaxe

```
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a>Parametry

`appDomain`\
[in] Doména AppDomain pro výčet.

`handle`\
[out] Popisovač pro vytváření výčtu instancí.

## <a name="remarks"></a>Poznámky

Zadaná metoda je součástí `IXCLRDataMethodDefinition` rozhraní a odpovídá třetí slot v tabulce virtuální metody.

## <a name="requirements"></a>Požadavky

**Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
**Záhlaví:** Žádná  
**Knihovna:** Žádná  
**Verze rozhraní .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Viz také:

- [CLRDataSourceType Enumeration](clrdatasourcetype-enumeration.md)
- [Ladění](index.md)
- [IXCLRDataMethodDefinition rozhraní](ixclrdatamethoddefinition-interface.md)