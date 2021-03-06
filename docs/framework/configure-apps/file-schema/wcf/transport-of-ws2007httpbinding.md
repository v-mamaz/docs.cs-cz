---
title: <transport> z <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: b8f84d0ed6c6248e72e3353675c9da96a0678ae6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273303"
---
# <a name="transport-of-ws2007httpbinding"></a>\<přenos > z \<ws2007HttpBinding >
Definuje nastavení ověřování pro přenos pomocí protokolu HTTP.  
  
 \<system.serviceModel>  
\<vazby >  
\<ws2007HttpBinding>  
\<Vytvoření vazby >  
\<security>  
\<přenos >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a>Typ  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`clientCredentialType`|Určuje přihlašovací údaje pro ověření klienta ke službě. Tento atribut je typu <xref:System.ServiceModel.HttpClientCredentialType>.|  
|`proxyCredentialType`|Určuje přihlašovací údaje pro ověření klienta pro proxy server domény. Tento atribut je typu <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|`realm`|Sféra ověřování hodnotou hash nebo základní ověřování. Výchozí hodnota je prázdný řetězec.<br /><br /> Sféra ověření určuje nejméně název hostitele, který provádí ověřování. Můžete také určit kolekci uživatelů, kteří mají přístup. Sféra ověření k určení, která z nich několik možných uživatelská jména a hesla je možné dotazovat uživatele.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType Attribute  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|Žádná|Zabezpečení je zakázaná.|  
|Základní|Používá základní ověřování.|  
|ověřování algoritmem Digest|Použití ověřování algoritmem digest.|  
|Ntlm|Ověřování protokolem NTLM se používá jako nouzové řešení pomocí domény Windows.|  
|Windows|Používá integrované ověřování Windows.|  
|Certifikát|Certifikáty X.509 používá k ověření klienta.|  
  
## <a name="proxycredentialtype-attribute"></a>proxyCredentialType Attribute  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|Žádná|Zabezpečení je zakázaná.|  
|Základní|Používá základní ověřování.|  
|ověřování algoritmem Digest|Použití ověřování algoritmem digest.|  
|Ntlm|Používá NTLM jako nouzové řešení pomocí domény Windows.|  
|Windows|Používá integrované ověřování Windows.|  
|Certifikát|Certifikáty X.509 používá k ověření klienta.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádná  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<zabezpečení >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|Představuje možnosti zabezpečení [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elementu.|  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [Zabezpečení služeb a klientů](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Vazby](../../../../../docs/framework/wcf/bindings.md)
- [Konfigurace vazeb poskytovaných systémem](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Používání vazeb ke konfiguraci služeb a klientů](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Vytvoření vazby >](../../../../../docs/framework/misc/binding.md)
