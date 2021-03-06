---
title: IEnumReferenceIdentity – rozhraní
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f2ea9d0e20cb67cc36d0b5883e483ce98941b2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743215"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity – rozhraní
Slouží jako enumerátor pro kolekci `IReferenceIdentity` objekty.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Získá ukazatel rozhraní na nový `IEnumReferenceIdentity` , která obsahuje stejné členy jako to `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Next`|Získá zadaný počet `IReferenceIdentity` objektů, počínaje na aktuální pozici.|  
|`IEnumReferenceIdentity::Reset`|Přesune ukazatel na instrukci na začátek `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Přesune ukazatele na instrukci vpřed o zadaný počet prvků počínaje od aktuální pozice.|  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Isolation.h  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [Rozhraní pro fúze](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IReferenceIdentity – rozhraní](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
