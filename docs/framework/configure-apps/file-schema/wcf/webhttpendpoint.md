---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 9b4dd3a61a9b5ad1b35cce4025a50ac4220fd77e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256430"
---
# <a name="webhttpendpoint"></a>\<webHttpEndpoint>
Tento prvek konfigurace definuje standardní koncový bod s pevnou [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) vazby, která automaticky přidá [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) chování. Při zápisu služby REST, používejte tento koncový bod.  
  
\<system.ServiceModel>  
\<standardEndpoints>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String"
                        defaultOutgoingResponseFormat="Xml/Json"
                        helpEnabled="Boolean"
                        webEndpointType="String" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|automaticFormatSelectionEnabled|Logická hodnota, která určuje, zda je povolen automatický výběr formátu.<br /><br /> Pokud je povolen automatický výběr formátu, infrastruktura analyzuje `Accept` záhlaví zprávy s požadavkem a určí nejvhodnější formát odpovědi. Pokud `Accept` záhlaví neurčuje formát vhodný odpovědi, využívá infrastrukturu `Content-Type` zprávy s požadavkem nebo výchozí formát odpovědi z operace.|  
|defaultOutgoingResponseFormat|Atribut, který určuje výchozí formát pro odchozí odpovědi. Tento atribut je <xref:System.ServiceModel.Web.WebMessageFormat> typu|  
|helpEnabled|Logická hodnota určující, zda je povoleno na stránce nápovědy HTTP pro koncový bod.|  
|webEndpointType|Řetězec, který určuje typ koncového bodu.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<standardEndpoints>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Kolekce standardních koncových bodů, které jsou předem definované koncové body s jedním nebo více z jejich vlastností (adresu, vazbu, kontrakt) pevné.|  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
