---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: ef3d92e07aaf4d4ba9d90e381017db104f2cc8fe
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356582"
---
# <a name="transactionflow"></a>\<transactionFlow>
Určuje podporu toku transakcí vlastní vazby.  
  
 \<system.serviceModel>  
\<vazby >  
\<customBinding>  
\<Vytvoření vazby >  
\<transactionFlow>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|transactionProtocol|Určuje protokol transakce, který se má použít. Platné hodnoty patří:<br /><br /> -OleTransactions<br />-WSAtomicTransactionOctober2004<br /><br /> Výchozí hodnota je OleTransactions.<br /><br /> Tento atribut je typu <xref:System.ServiceModel.TransactionProtocol>.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<Vytvoření vazby >](../../../../../docs/framework/misc/binding.md)|Definuje všechny možnosti vázání pro vlastní vazbu.|  
  
## <a name="remarks"></a>Poznámky  
 Tento element slouží k povolení nebo zakázání tok příchozích transakcí v nastavení vazby koncového bodu, jakož i k určení formátu požadovaný protokol pro příchozí transakce. Další informace o použití tento prvek konfigurace, najdete v části [konfigurace transakcí ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) a [povolení toku transakcí](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
> [!CAUTION]
>  Při použití `OleTransactions` protokol k toku transakce z koncového bodu endpoint, časový limit transakce může dojít ke ztrátě, pokud se pokusí tok znovu pomocí libovolného protokolu pro jiné než cílový koncový bod `OleTransactions`. To může způsobit všechny uzly nižší úrovně po směrování OleTransactions vypršení časového limitu později, než se očekávalo.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Konfigurace transakcí ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)
- [Povolení toku transakcí](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
- [Vazby](../../../../../docs/framework/wcf/bindings.md)
- [Rozšíření vazeb](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Vlastní vazby](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
