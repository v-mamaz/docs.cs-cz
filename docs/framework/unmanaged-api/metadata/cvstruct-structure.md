---
title: CVStruct – struktura
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fb73980faa64464c572945fe5ad04e015dc8805b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720649"
---
# <a name="cvstruct-structure"></a>CVStruct – struktura
Obsahuje informace, které se použijí při instalaci modulu nebo složený bitové kopie.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|Hlavní|Číslo hlavní verze sestavení.|  
|Vedlejší|Číslo podverze sestavení.|  
|Sub|Dílčí číslo sestavení.|  
|Sestavení|Číslo sestavení.|  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Cor.h  
  
 **Knihovna:** Použít jako prostředek v MsCorEE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [Struktury pro metadata](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
