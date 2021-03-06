---
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: 3ffb18fbd410922df4311180ef7af5153ba5c0f5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379816"
---
# <a name="udpannouncementendpoint"></a>\<udpAnnouncementEndpoint>
Tento prvek konfigurace definuje standardní koncový bod služby používá k odeslání zpráv oznámení UDP vazby. Má pevnou kontrakt a podporuje dvě verze zjišťování. Kromě toho má pevnou vazbou UDP a adresu výchozí hodnotu podle specifikace WS-Discovery (WS-Discovery dubna 2005 nebo verze 1.1 WS-Discovery). Můžete zadat adresu vícesměrového vysílání pro odesílání a příjem zpráv s oznámením.  
  
\<system.ServiceModel>  
\<standardEndpoints>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|discoveryVersion|Řetězec, který určuje jeden ze dvou verzí protokolu WS-Discovery. Platné hodnoty jsou WSDiscovery11 a WSDiscoveryApril2005. Tato hodnota je typu <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.|  
|maxAnnouncementDelay|Časový interval hodnotu, která určuje maximální hodnotu zpoždění protokolu zjišťování bude čekat před odesláním uvítací zprávu. Náhodný čas hodnotu mezi 0 a hodnota tohoto atributu bude čekat zprávy před odesláním. Tento atribut slouží k nastavení malé náhodné zpoždění zabránil výstrahami sítě v případě, že se odesílá do sítě a všechny služby jsou zase online ve stejnou dobu.|  
|multicastAddress|Identifikátor URI určující adresu vícesměrového vysílání pro odesílání a přijímání zpráv zjišťování. Výchozí hodnota je jako vyhovující specifikace protokolu adresu vícesměrového vysílání.|  
|name|Řetězec, který určuje název konfigurace standardního koncového bodu. Název se používá v `endpointConfiguration` atribut koncového bodu služby propojit s jeho konfigurace je standardní koncový bod.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<udpTransportSettings>](udptransportsettings.md)|Kolekce nastavení, která vám umožní nakonfigurovat přenos UDP pro koncový bod protokolu UDP.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|Kolekce standardních koncových bodů, které jsou předem definované koncové body s jedním nebo více z jejich vlastností (adresu, vazbu, kontrakt) pevné.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje přes UDP naslouchání pro oznámení klienta vícesměrového vysílání přenos s výchozí adresy vícesměrového vysílání, UDP a vícesměrového vysílání přenosu pomocí zadané adresy vícesměrového vysílání.  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="udpAnnouncementEndpointStandard"
              kind="udpAnnouncementEndpoint"
              bindingConfiguration="..." />
    <endpoint name="udpAnnouncementEndpoint2"
              kind="udpAnnouncementEndpoint"
              endpointConfiguration="AnnouncementConfiguration3702"
              bindingConfiguration="..." />
    ...
  </service>
</services>
<standardEndpoints>
  <udpAnnouncementEndpoint>
    <standardEndpoint name="AnnouncementConfiguration2"
                      version="WSDiscoveryApril2005"
                      multicastAddress="soap.udp://239.255.255.250:3703"/>
  </udpAnnouncementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
