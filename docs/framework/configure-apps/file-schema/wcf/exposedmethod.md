---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 151929cd99df08b705bee94eb6fd6f10c254a660
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259849"
---
# <a name="exposedmethod"></a>\<exposedMethod >
Představuje metodu COM +, která je vystavena při vystavení rozhraní komponenty COM + jako webovou službu.  
  
 \<system.ServiceModel>  
\<comContracts>  
\<comContract>  
\<metody >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|name|Řetězec, který obsahuje metodu COM +, která je vystavena při vystavení rozhraní komponenty COM + jako webovou službu.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<exposedMethods >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|Kolekce [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementy.|  
  
## <a name="remarks"></a>Poznámky  
 COM + integration nástroj pro konfiguraci (ComSvcConfig.exe) slouží k přidání specifických metod z rozhraní modelu COM, který se zobrazí na kontrakt generovaný služby.  
  
 Například slouží následující příkaz k přidání tří pojmenované metody ze `IFinances` rozhraní modelu COM na `ItemOrders`. Finanční součásti pro kontrakt generovaný služby.  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 Při spuštění také ComSvcConfig.exe, poté vygeneruje následující kontrakt služby výpis výše uvedených metod jako [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementy.  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 Během inicializace služby, modul runtime pokusí vygenerovat kontraktu služby znázorňující v a přidáním pouze metody uvedené v seznamu [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementy. Trasování je vytvořen pro každou metodu rozhraní, který není součástí kontraktu služby.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [Integrace s aplikacemi modelu COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Postupy: Konfigurace nastavení služby modelu COM +](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
