---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: f3d4b049afe55fb9fb80cbad56c49e8ec13e60db
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758739"
---
# <a name="resolver"></a>\<resolver>
Určuje mechanismus rozpoznávání partnera, který se používá pro partnerské sítě ID k sadě adres partnerských uzlů, jenž jsou součástí sítě.  
  
 \<system.ServiceModel>  
\<vazby >  
\<netPeerBinding>  
\<Vytvoření vazby >  
\<resolver>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`mode`|Řetězec, který určuje, jestli instance služby mechanismu rozpoznávání partnera přidružený k této službě je buď PNRP specifická, vlastní mechanismus rozpoznávání nebo je automaticky zjišťovaná. Tento atribut je typu <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.|  
|`referralPolicy`|Řetězec určující způsob odkazů jsou sdíleny mezi partnery. Tento atribut je typu <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<headers>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|Určuje nastavení pro službu překladače vlastní sdílené.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<Vytvoření vazby >](../../../../../docs/framework/misc/binding.md)|Definuje všechny vazby funkce [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## <a name="remarks"></a>Poznámky  
 Mechanismus rozpoznávání partnera název je služba zjišťování používají kanály peer najít partnerské uzly, které jsou součástí sdílené sítě. Používá se také "zaregistrovat" uzlu sítě peer, mechanismus, pomocí kterého bude rovnocenný uzel stane známé a dostupné ze sítě peer. Další informace o překladače partnerských uzlů najdete v tématu [překladače partnerských uzlů](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [Překladače partnerských uzlů](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- [Přidání vlastní mechanismus rozpoznávání pro kanál PeerChannel aplikaci](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))
