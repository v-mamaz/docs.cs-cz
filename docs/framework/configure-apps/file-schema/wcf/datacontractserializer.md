---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 933d49092c392fa293468d546e521bf7ed858376
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539841"
---
# <a name="datacontractserializer"></a>dataContractSerializer
Obsahuje konfigurační data pro <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 \<system.ServiceModel>  
\<chování >  
\<endpointBehaviors>  
\<chování >  
\<dataContractSerializer>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|ignoreExtensionDataObject|Logická hodnota, která určuje, jestli se má ignorovat data dodaná nástrojem koncový bod, když je serializován nebo deserializován.|  
|maxItemsInObjectGraph|Celé číslo, které určuje maximální počet položek k serializaci nebo deserializaci.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Určuje chování koncového bodu.|  
  
## <a name="remarks"></a>Poznámky  
 Zobrazit <xref:System.Runtime.Serialization.DataContractSerializer> dokumentaci pro další informace o známých typů.  
  
> [!CAUTION]
>  `<dataContractSerializer>` Chování – element (pokud existuje) by měla vždy předcházet `<enableWebScript>` prvek chování v konfiguračním souboru. V opačném případě výsledné chování není definováno.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [Známé typy kontraktů dat](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [Přenos a serializace dat](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
