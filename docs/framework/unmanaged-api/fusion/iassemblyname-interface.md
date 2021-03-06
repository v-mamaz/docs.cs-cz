---
title: IAssemblyName – rozhraní
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22276e543e8eeb9c6cf9aeee7a9af92c503d3a7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549012"
---
# <a name="iassemblyname-interface"></a>IAssemblyName – rozhraní
Poskytuje metody pro popisující a práci s jedinečnou identitu sestavení.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Clone – metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|Vytvoří Mělkou kopii to `IAssemblyName` objektu.|  
|[Finalize – metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|To umožňuje `IAssemblyName` objektu k uvolnění prostředků a provádět jiné operace čištění před jeho destruktoru je volána.|  
|[GetDisplayName – metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|Získá popisný název sestavení odkazuje situace `IAssemblyName` objektu.|  
|[GetName – metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|Získá název jednoduchý a nešifrované sestavení odkazuje situace `IAssemblyName` objektu.|  
|[GetProperty – metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|Získá ukazatel na vlastnost odkazuje zadanou `PropertyId`.|  
|[GetVersion – metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|Získá informace o verzi pro sestavení odkazuje situace `IAssemblyName` objektu.|  
|[IsEqual – metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|Určuje, zda zadané `IAssemblyName` objekt rovná tomuto `IAssemblyName`podle zadané porovnávací příznaky.|  
|[SetProperty – metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|Nastaví hodnotu vlastnosti odkazuje zadaný `PropertyId`.|  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Fusion.h  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [Rozhraní pro fúze](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IAssemblyEnum – rozhraní](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
