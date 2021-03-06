---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 7506cce61966a4a4650ff591cd6106dfd4a33b67
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2019
ms.locfileid: "57680409"
---
# <a name="serviceactivations"></a>\<serviceActivations>

Konfigurace element, který slouží k přidání nastavení, jenž definuje nastavení aktivace virtuální služby, která je namapována na daný typ služby Windows Communication Foundation (WCF). To umožňuje aktivovat službám hostovaným ve WAS / IIS bez souboru .svc.

\<system.ServiceModel>\
\<serviceHostingEnvironment>\
\<serviceActivations>

## <a name="syntax"></a>Syntaxe

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a>Atributy a elementy

Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

Žádné

### <a name="child-elements"></a>Podřízené elementy

|Prvek|Popis|
|-------------|-----------------|
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|Přidá prvek konfigurace, který určuje aktivace aplikace služby.|

### <a name="parent-elements"></a>Nadřazené elementy

|Prvek|Popis|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Definuje typ, který vytvoří instanci hostitelským prostředím služby pro konkrétní přenos.|

## <a name="remarks"></a>Poznámky

Následující příklad ukazuje, jak nakonfigurovat nastavení aktivace v souboru web.config.

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

Pomocí této konfigurace, můžete aktivovat GreetingService bez použití souboru .svc.

Všimněte si, že `<serviceHostingEnvironment>` je konfigurace na úrovni aplikace. Je nutné umístit `web.config` obsahující konfiguraci v kořenu virtuální aplikace. Kromě toho `serviceHostingEnvironment` machineToApplication odvoditelný oddíl. Když si zaregistrujete jedinou službou v kořenové složce na počítači, každá služba aplikace zdědí tuto službu.

Aktivace podle konfigurace podporuje aktivaci přes protokol http a jiným protokolem než http. Vyžaduje adresu relativeAddress, tj. .svc, XOML nebo .xamlx s rozšířeními. Vlastní rozšíření můžete namapovat buildProviders ví, která vám pak umožní k aktivaci služby přes jakékoli rozšíření. Při konfliktu `<serviceActivations>` části přepíše .svc registrace.

## <a name="see-also"></a>Viz také:

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
