---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 126a6923469580d2d9481ab4b999560d9beda398
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273566"
---
# <a name="rsa"></a>\<rsa>
Zabezpečené klienta WCF, která se připojuje k koncový bod s tuto identitu ověří, deklarací identity předkládaných server obsahovat deklaraci identity, který obsahuje veřejný klíč RSA použitý k vytvoření této identity.  
  
 \<identity>  
\<rsa>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené elementy  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|value|Volitelný řetězec. RSA veřejné hodnota klíče, která bude porovnána na straně klienta.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádná  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Určuje identitu služby k ověření klienta.|  
  
## <a name="remarks"></a>Poznámky  
 Kontrolu RSA umožňuje konkrétně omezit ověřování do jednoho certifikátu na základě jeho klíč RSA nebo vygenerovat vlastní hodnotu klíče RSA. Toto umožňuje přísnější ověřování konkrétního klíče RSA za cenu služba již práce s existující klienti při změně hodnoty klíče RSA.  
  
 Další informace o používání identity k ověření služby ke klientovi naleznete v tématu [identita a ověřování služby](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="example"></a>Příklad  
 Následující kód konfigurace určuje hodnota veřejného klíče certifikátu X.509, který se používá k ověření serveru.  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [Identita a ověřování služby](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
