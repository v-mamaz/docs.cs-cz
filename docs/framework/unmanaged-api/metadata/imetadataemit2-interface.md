---
title: IMetaDataEmit2 – rozhraní
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e0477adb4958a53289cd0a64f39259403fa7dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656931"
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2 – rozhraní
Rozšiřuje [imetadataemit –](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) rozhraní především k umožňují pracovat s obecných typů.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[DefineGenericParam – metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|Vytvoří definici pro parametr obecného typu a získá token pro tento parametr obecného typu.|  
|[DefineMethodSpec – metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|Vytvoří instanci obecné metody a získá token pro definici.|  
|[GetDeltaSaveSize – metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|Získá hodnotu, která rozdíl ve velikosti dat, který je potřeba express změny pro aktuální relaci edit-and-continue.|  
|[ResetENCLog – metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|Obnoví protokolu edit-and-continue a spustí novou relaci.|  
|[SaveDelta – metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|Uloží změny z aktuální relace edit-and-continue do zadaného souboru.|  
|[SaveDeltaToMemory – metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|Uloží změny z aktuální relace edit-and-continue do paměti.|  
|[SaveDeltaToStream – metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|Uloží změny z aktuální relace edit-and-continue do zadaného datového proudu.|  
|[SetGenericParamProps – metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|Nastavuje hodnoty vlastností pro obecný parametr definice odkazuje zadaný token.|  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Cor.h  
  
 **Knihovna:** Použít jako prostředek v MsCorEE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [Rozhraní pro metadata](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataEmit – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
