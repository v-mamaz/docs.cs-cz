---
title: <transport> z <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: ea025751020d6d98292f6bc3ecfe9421af0cb793
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372318"
---
# <a name="transport-of-wshttpbinding"></a>\<přenos > z \<wsHttpBinding >

Definuje nastavení ověřování pro přenos pomocí protokolu HTTP.

\<system.serviceModel>\
\<vazby > \
\<wsHttpBinding>\
\<binding>\
\<security>\
\<přenos >

## <a name="syntax"></a>Syntaxe

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
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
|`realm`|Řetězec určující sféru ověřování hodnotou hash nebo základní ověřování. Výchozí hodnota je prázdný řetězec.<br /><br /> Sféra ověření určuje nejméně název hostitele, který provádí ověřování. Můžete také určit kolekci uživatelů, který má přístup. Sféra ověření pro ověření, který z nich několik možných uživatelská jména a hesla je možné dotazovat uživatele.|
|`policyEnforcement`|Tento výčet Určuje, kdy <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> by se měly vynucovat.<br /><br /> 1.  Nikdy – zásady se vynucují nikdy (rozšířené ochrany je zakázáno).<br />2.  WhenSupported – zásady se vynucuje jenom v případě, že klient podporuje rozšířenou ochranu.<br />3.  Vždy – je vždy zásady vynucují. K ověření se nezdaří klientů, kteří nepodporují rozšířenou ochranu.|

## <a name="clientcredentialtype-attribute"></a>clientCredentialType Attribute

|Hodnota|Popis|
|-----------|-----------------|
|`None`|Zabezpečení je zakázaná.|
|`Basic`|Používá základní ověřování.|
|`Digest`|Použití ověřování algoritmem digest.|
|`Ntlm`|Ověřování protokolem NTLM se používá jako nouzové řešení pomocí domény Windows.|
|`Windows`|Používá integrované ověřování Windows.|
|`Certificate`|Certifikáty X.509 používá k ověření klienta.|

## <a name="proxycredentialtype-attribute"></a>proxyCredentialType Attribute

|Hodnota|Popis|
|-----------|-----------------|
|`None`|Zabezpečení je zakázaná.|
|`Basic`|Používá základní ověřování.|
|`Digest`|Použití ověřování algoritmem digest.|
|`Ntlm`|Používá NTLM jako nouzové řešení pomocí domény Windows.|
|`Windows`|Používá integrované ověřování Windows.|
|`Certificate`|Certifikáty X.509 používá k ověření klienta.|

### <a name="child-elements"></a>Podřízené elementy

Žádné

### <a name="parent-elements"></a>Nadřazené elementy

|Prvek|Popis|
|-------------|-----------------|
|[\<zabezpečení >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|Představuje možnosti zabezpečení [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).|

## <a name="see-also"></a>Viz také:

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [Zabezpečení služeb a klientů](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Vazby](../../../../../docs/framework/wcf/bindings.md)
- [Konfigurace vazeb poskytovaných systémem](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Používání vazeb ke konfiguraci služeb a klientů](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Vytvoření vazby >](../../../../../docs/framework/misc/binding.md)
