---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: 424bc0f223dbdc6dbfc69a6623f86bcc2c71fa88
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758856"
---
# <a name="peerauthentication"></a>\<peerAuthentication>
Určuje nastavení ověřování pro sdílené certifikát používaný službou partnerský uzel.  
  
 \<system.ServiceModel>  
\<chování >  
\<serviceBehaviors>  
\<chování >  
\<serviceCredentials>  
\<peer>  
\<peerAuthentication>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`certificateValidationMode`|Volitelný výčet. Určuje jeden ze tří režimů používaných pro ověření pověření. Tento atribut je typu <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Pokud hodnotu `Custom`, o `customCertificateValidator` musí být rovněž dodán.|  
|`customCertificateValidatorType`|Volitelný řetězec. Určuje typ a sestavení používané pro ověření vlastního typu. Tento atribut musí být nastaven při `certificateValidationMode` je nastavena na `Custom`. Tento atribut je typu <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Windows Communication Foundation (WCF) poskytuje sdílené výchozí validátor certifikátu, který ověřuje certifikát peer proti úložišti důvěryhodných osob. Také ověřuje, že certifikát zřetězený platného kořenového. Můžete implementovat vlastní validátor určit různá chování a používání tohoto atributu na vlastní validátor.|  
|`revocationMode`|Volitelný výčet. Určuje režim odvolání certifikátu. Tento atribut je typu <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. Systém ověří, že peer certifikát nebyl odvolaný ve vyhledávání v seznamu odvolaných certifikátů. Tato kontrola lze provést tak, že zkontrolujete online nebo seznam odvolaných certifikátů uložené v mezipaměti. Kontrola odvolání můžete vypnout pomocí nastavení tohoto atributu na NoCheck.|  
|`trustedStoreLocation`|Volitelný výčet. Určuje umístění úložiště pro důvěryhodného kde ověření certifikátu druhé strany systém zabezpečení WCF. Tento atribut je typu <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Určuje aktuální pověření pro partnerský uzel.|  
  
## <a name="remarks"></a>Poznámky  
 `<authentication>` Odpovídá elementu <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> třídy. Tento prvek určuje ověřování, které se vyvolá při ověřování sousední souseda v mřížce. Nový partnerský uzel pokusí navázat připojení k sousedovi, předá odpovídá peer své vlastní přihlašovací údaje. Validátor odpovídajícího objektu je vyvolán k ověření přihlašovacích údajů vzdálené strany. Při každém navázání připojení partnera v mřížce, jak partnerské uzly jsou vzájemně se ověřují, jsou vyvolány význam validátory na obou koncích.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [Práce s certifikáty](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Síť rovnocenných počítačů](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [Ověřování zpráv protokolu peer Channel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Vlastní ověřování protokolu peer Channel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Zabezpečení aplikací protokolu Peer Channel](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
