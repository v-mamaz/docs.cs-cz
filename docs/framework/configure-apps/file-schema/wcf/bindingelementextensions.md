---
title: <bindingElementExtensions>
ms.date: 03/30/2017
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
ms.openlocfilehash: 9a2a3af093949c1d724fdea13655bbb80fe71048
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270459"
---
# <a name="bindingelementextensions"></a>\<bindingElementExtensions >
Tato část umožňuje používat vlastní prvek vazby z počítače nebo konfiguračního souboru aplikace. Vlastní prvek vazby můžete přidat do této kolekce pomocí `add` – klíčové slovo a nastavení `type` atribut elementu, který chcete rozšíření elementu vazby, stejně jako `name` atribut na prvek vlastní vazby.  
  
 Rozšíření vazby umožňují uživateli vytvořit uživatelem definované vazby prvky pro použití jako součást vlastní vazby. Prostřednictvím kódu programu, rozšíření vazby je typ, který implementuje abstraktní třídu <xref:System.ServiceModel.Channels.BindingElement>. V konfiguračním souboru `bindingElementExtensions` oddíl se používá k definování element rozšíření.  
  
 V následujícím příkladu `add` element, stejně jako `name` atribut můžete přidat příponu vazby na `bindingElementExtensions` oddílu konfiguračního souboru.  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingElementExtensions>
      <add name="udpTransport"
           type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingElementExtensions>
  </extensions>
</system.serviceModel>
```  
  
 Chcete-li přidat možnosti konfigurace na prvek, uživatel musí k zápisu a registrace `bindingElementExtensionSection` elementu. Další informace najdete v článku <xref:System.Configuration> dokumentaci.  
  
 Po definování elementu a jeho typ konfigurace rozšíření, je možné jako součást vlastní vazby, jak je znázorněno v následujícím příkladu.  
  
```xml  
<customBinding>
  <binding name="test2">
    <udpTransport />
    <binaryMessageEncoding maxReadPoolSize="211"
                           maxWritePoolSize="2132"
                           maxSessionSize="3141" />
  </binding>
</customBinding>
```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>
- [Rozšíření vazeb](../../../../../docs/framework/wcf/extending/extending-bindings.md)
