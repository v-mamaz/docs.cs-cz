---
title: <clear> z <claimTypeRequirements> – element
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: b20d5c1808bf41d1ecd6b3e3a61606ae45b0fbdd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270335"
---
# <a name="clear-of-claimtyperequirements-element"></a>\<Vymazat > z \<claimTypeRequirements > – element
Určuje, že všechny typy deklarací, jenž budou odebrány z federovaného pověření. Tím se zajistí, že začne prázdnou kolekci.  
  
 \<system.ServiceModel>  
\<vazby >  
\<wsFederatedBinding>  
\<Vytvoření vazby >  
\<security>  
\<Zpráva >  
\<claimTypeRequirements>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|Určuje kolekci požadovaných typů deklarací. Každý prvek je typu <xref:System.ServiceModel.Configuration.ClaimTypeElement>.<br /><br /> V případě federovaných stavu služby požadavky na příchozí přihlašovací údaje. Například příchozí přihlašovací údaje musí mít sadu typů deklarací identity. Každý prvek v této kolekci Určuje typy požadovaných a volitelných deklarací, očekává se objeví federovaného pověření.|  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
