---
title: <dataContractSerializer> of <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: 488b0754194c1fa7896a168daac0a3a497076e56
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265932"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a>\<dataContractSerializer> of \<system.runtime.serialization>
Obsahuje konfigurační data pro <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 \<system.runtime.serialization>  
\<dataContractSerializer>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|ignoreExtensionDataObject|Logická hodnota, která určuje, jestli se má ignorovat data dodaná nástrojem koncový bod, když je serializován nebo deserializován. Tento atribut je nastavit pouze v `<dataContractSerializer>` pod `<behavior>` elementu.|  
|maxItemsInObjectGraph|Celé číslo, které určuje maximální počet položek k serializaci nebo deserializaci. Tento atribut je 65536.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<declaredTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|Obsahuje známé typy, které <xref:System.Runtime.Serialization.DataContractSerializer> používá při deserializaci.<br /><br /> Další informace o kontraktech dat a známých typech najdete v tématu [známé typy kontraktů dat](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|Představuje kořenový element <xref:System.Runtime.Serialization> části obor názvů a obsahuje prvky pro nastavení voleb <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Poznámky  
 Další informace o známých typů najdete v tématu <xref:System.Runtime.Serialization.DataContractSerializer> a [známé typy kontraktů dat](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [Známé typy kontraktů dat](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
