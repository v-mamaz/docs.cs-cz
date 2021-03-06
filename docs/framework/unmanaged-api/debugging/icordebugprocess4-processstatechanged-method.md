---
title: ICorDebugProcess4::ProcessStateChanged Method
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: b77dd1277e7d23729f30d9d495c5417055a22759
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378987"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4::ProcessStateChanged Method

Upozorní ICorDebug kanálu, že je vzdálený ladicí program procesu pokračovat v provádění od laděného objektu.

## <a name="syntax"></a>Syntaxe

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Parametry

 `eChange`\
[in] Člen [výčet CorDebugStateChange](cordebugstatechange-enumeration.md) popisující změnu stavu spuštění procesu.

## <a name="remarks"></a>Poznámky

Zadaná metoda je součástí `ICorDebugProcess4` rozhraní a odpovídá čtvrtý pozice tabulce virtuální metody.

## <a name="requirements"></a>Požadavky

 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).

 **Záhlaví:** Žádná

 **Knihovna:** Žádná
 
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Viz také:

- [ICorDebugProcess4 Interface](icordebugprocess4-interface.md)
- [Rozhraní pro ladění](debugging-interfaces.md)
- [Ladění](index.md)