---
title: Protokoly transakce verze 1.0
ms.date: 03/30/2017
ms.assetid: 034679af-0002-402e-98a8-ef73dcd71bb6
ms.openlocfilehash: c28c013bc791b5358a2282dc21446d5f2129aa2c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258016"
---
# <a name="transaction-protocols-version-10"></a>Protokoly transakce verze 1.0
Windows Communication Foundation (WCF) verze 1 implementuje protokol WS-koordinaci a WS-Atomic Transactions verze 1.0. Další informace o verzi 1.1 naleznete v tématu [protokoly transakcí](../../../../docs/framework/wcf/feature-details/transaction-protocols.md).  
  
|Specifikace/dokumentu|Odkaz|  
|-----------------------------|----------|  
|Koordinace WS|<http://specs.xmlsoap.org/ws/2004/10/wscoor/wscoor.pdf>|  
|WS-AtomicTransaction|<http://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf>|  
  
 Vzájemná funkční spolupráce na této specifikaci protokolu vyžádáním ve dvou úrovních: mezi aplikacemi a mezi správci transakcí (viz následující obrázek). Specifikace podrobnému popisu, skvělé formáty zpráv a zpráv exchange pro obě úrovně interoperability. Některé zabezpečení, spolehlivost a kódování aplikace aplikace exchange platí, jako je tomu u aplikace regulární systému exchange. Úspěšné vzájemná funkční spolupráce mezi správci transakcí však vyžaduje smlouvou pro konkrétní vazbu, protože není obvykle nakonfigurovaná uživatelem.  
  
 Toto téma popisuje složení specifikaci WS-Atomic Transactions (WS-AT) se zabezpečením a popisuje zabezpečené vazby používaný ke komunikace mezi správci transakcí. Postup popsaný v tomto dokumentu se úspěšně testoval se systémem jiným implementacím WS-AT a WS-koordinace včetně IBM, IONA, Sun Microsystems a dalších.  
  
 Následující obrázek znázorňuje interoperabilitu mezi dvěma vedoucími transakce, transakce Manager 1 a 2 správce transakcí a dvě aplikace, aplikace 1 a 2 aplikace.  
  
 ![Protokoly transakcí](../../../../docs/framework/wcf/feature-details/media/transactionmanagers.gif "TransactionManagers")  
  
 Vezměte v úvahu Typický scénář WS-koordinace/WS-Atomic Transactions jednoho iniciátoru (I) a jeden účastník (P). Iniciátor i účastníka mají správci transakcí (ITM a druh, v uvedeném pořadí). Dvoufázového potvrzení se označuje jako 2PC v tomto tématu.  
  
|||  
|-|-|  
|1. CreateCoordinationContext|12. Zpráva odpovědi aplikace|  
|2. CreateCoordinationContextResponse|13. Potvrzení změn (dokončení)|  
|3. Registr (dokončení)|14. Příprava (2PC)|  
|4. RegisterResponse|15. Příprava (2PC)|  
|5. Zprávy aplikace.|16. Připravené (2PC)|  
|6. CreateCoordinationContext s kontextem|17. Připravené (2PC)|  
|7. Registr (trvale)|18. Potvrdit (dokončení)|  
|8. RegisterResponse|19. Potvrzení (2PC)|  
|9. CreateCoordinationContextResponse|20. Potvrzení (2PC)|  
|10. Registr (trvale)|21. Potvrdit (2PC)|  
|11. RegisterResponse|22. Potvrdit (2PC)|  
  
 Tento dokument popisuje složení specifikaci WS-AtomicTransaction se zabezpečením a zabezpečené vazby používaný ke komunikace mezi správci transakcí. Postup popsaný v tomto dokumentu bylo úspěšně otestovat s jinými implementacemi WS-AT a WS-koordinace.  
  
 Obrázek a tabulka ukazuje čtyři třídy zpráv z hlediska zabezpečení:  
  
-   Aktivace zprávy (CreateCoordinationContext a CreateCoordinationContextResponse).  
  
-   Registrační zprávy (registr a RegisterResponse)  
  
-   Protokol zprávy (připravit, vrácení změn, potvrzení, přerušeno a tak dále).  
  
-   Zprávy aplikace.  
  
 První tři zpráva třídy jsou považovány za správce transakcí zpráv a jejich vazbu konfigurace je popsaná v "Aplikace zpráv Exchange" dále v tomto tématu. Čtvrtý třída zprávy zprávy do aplikací a je popsaný v části "Zpráva příklady" dále v tomto tématu. Tato část popisuje protokol vazby používá pro každou z těchto tříd WCF.  
  
 V tomto dokumentu se používá následující obory názvů XML a přidružené předpony.  
  
|Předpona|Identifikátor URI Namespace|  
|------------|-------------------|  
|s11|http://schemas.xmlsoap.org/soap/envelope|  
|wsa|http://www.w3.org/2004/08/addressing|  
|wscoor|http://schemas.xmlsoap.org/ws/2004/10/wscoor|  
|WSAT|http://schemas.xmlsoap.org/ws/2004/10/wsat|  
|t|http://schemas.xmlsoap.org/ws/2005/02/trust|  
|o|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd|  
|XSD|http://www.w3.org/2001/XMLSchema|  
  
## <a name="transaction-manager-bindings"></a>Správce transakcí vazby  
 R1001: Správci transakcí musí používat protokol SOAP 1.1 a WS-Addressing 2004/08 protokolu WS-AtomicTransaction a výměny zpráv WS-koordinace.  
  
 Zprávy aplikace nejsou omezeny na těchto vazeb a jsou popsané dále.  
  
### <a name="transaction-manager-https-binding"></a>Vazba HTTPS správce transakcí  
 Vazba HTTPS správce transakcí spoléhá výhradně na zabezpečení přenosu k zajištění zabezpečení a navázání vztahu důvěryhodnosti mezi každý pár odesílatele příjemce ve stromové struktuře transakce.  
  
#### <a name="https-transport-configuration"></a>Konfigurace protokolu HTTPS přenosu  
 Zřízení správce transakcí Identity se používají certifikáty X.509. Je požadováno ověření klient/server a klient/server autorizace je ponechané jako podrobnost implementace:  
  
-   R1111: Certifikáty X.509 zobrazí přenosu musí mít název subjektu, který odpovídá plně kvalifikovaný název domény (FQDN) počítači původce.  
  
-   B1112: DNS musí být funkční mezi každý pár odesílatele příjemce v systému pro kontroly název subjektu X.509 proběhla úspěšně.  
  
#### <a name="activation-and-registration-binding-configuration"></a>Aktivace a konfigurace vazby registrace  
 WCF vyžaduje požadavek nebo odpověď duplexní vazby s korelací přes protokol HTTPS. (Další informace o korelaci a popisy vzorů exchange zpráv žádost odpověď, najdete v protokolu WS-AtomicTransaction, část 8.)  
  
#### <a name="2pc-protocol-binding-configuration"></a>Konfigurace vazeb protokolu 2PC  
 WCF podporuje zprávy jednosměrné (datagram) přes protokol HTTPS. Korelace mezi zprávy je ponechané jako podrobnost implementace.  
  
 B2131: Implementace musí podporovat `wsa:ReferenceParameters` jak je popsáno v WS-Addressing k dosažení korelace zpráv WCF vaší 2PC.  
  
### <a name="transaction-manager-mixed-security-binding"></a>Správce transakcí ve smíšeném vazby zabezpečení  
 Toto je alternativní (ve smíšeném režimu) vazby zabezpečení přenosu používá v kombinaci s modelem WS-koordinace vystavený Token pro účely identity zařízení.  Aktivace a registrace jsou pouze prvky, které se liší mezi dvě vazby.  
  
#### <a name="https-transport-configuration"></a>Konfigurace protokolu HTTPS přenosu  
 Zřízení správce transakcí Identity se používají certifikáty X.509. Vyžaduje se klientem a serverem ověřování a autorizace klienta nebo serveru je ponecháno jako podrobnost implementace.  
  
#### <a name="activation-message-binding-configuration"></a>Konfigurace vazby zprávy aktivace  
 Aktivace zprávy obvykle nejsou součástí interoperability vzhledem k tomu obvykle dochází mezi aplikací a její místní správce transakcí.  
  
 B1221: WCF používá duplexní vazbu HTTPS (popsané v [protokoly zasílání zpráv](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) pro aktivaci zprávy. Žádost a odpověď zprávy se korelují pomocí WS-Addressing 2004/08.  
  
 Specifikace WS-Atomic Transactions, 8 část popisuje další podrobnosti o korelaci a vzory zpráv exchange.  
  
-   R1222: Po přijetí `CreateCoordinationContext`, musíte vydat koordinátor `SecurityContextToken` s tajným klíčem přidružené `STx`. Tento token se vrátí uvnitř `t:IssuedTokens` záhlaví podle specifikace WS-Trust.  
  
-   R1223: Pokud dojde k aktivaci v rámci existující kontext koordinace `t:IssuedTokens` záhlaví s `SecurityContextToken` spojené s existujícím kontextu toku na `CreateCoordinationContext` zprávy.  
  
 Nový `t:IssuedTokens` záhlaví by měl být vygenerován pro připojení k odchozích dat `wscoor:CreateCoordinationContextResponse` zprávy.  
  
#### <a name="registration-message-binding-configuration"></a>Konfigurace vazby zpráva registrace  
 B1231: WCF používá duplexní vazbu HTTPS (popsané v [protokoly zasílání zpráv](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)). Žádost a odpověď zprávy se korelují pomocí WS-Addressing 2004/08.  
  
 WS-AtomicTransaction, část 8, popisuje další podrobnosti o korelaci a popisy vzorů zprávy exchange.  
  
 R1232: Odchozí `wscoor:Register` musí používat zprávy `IssuedTokenOverTransport` režim ověřování je popsáno v [protokoly zabezpečení](../../../../docs/framework/wcf/feature-details/security-protocols.md).  
  
 `wsse:Timestamp` Elementu musí být podepsané pomocí `SecurityContextToken STx` vydané. Tento podpis je doklad o vlastnictví tokenu přidružený k konkrétní transakce a slouží k ověřování účastníka uvedení v transakci. RegistrationResponse zpráva se pošle zpět prostřednictvím protokolu HTTPS.  
  
#### <a name="2pc-protocol-binding-configuration"></a>Konfigurace vazeb protokolu 2PC  
 WCF podporuje zprávy jednosměrné (datagram) přes protokol HTTPS. Korelace mezi zprávy je ponechané jako podrobnost implementace.  
  
 B2131: Implementace musí podporovat `wsa:ReferenceParameters` jak je popsáno v WS-Addressing k dosažení korelace zpráv WCF vaší 2PC.  
  
## <a name="application-message-exchange"></a>Aplikace zprávy Exchange  
 Aplikace se můžete používat konkrétní vazbu pro zprávy aplikace do aplikace, tak dlouho, dokud vazbu splňuje následující požadavky na zabezpečení:  
  
-   R2001: Toku aplikace aplikace zprávy `t:IssuedTokens` záhlaví spolu s `CoordinationContext` v záhlaví zprávy.  
  
-   R2002: Integritu a důvěrnost `t:IssuedToken` musí být zadaná.  
  
 `CoordinationContext` Obsahuje záhlaví `wscoor:Identifier`. Při definici `xsd:AnyURI` umožňuje použít absolutní a relativní identifikátory URI, WCF podporuje pouze `wscoor:Identifiers`, které jsou absolutní URI.  
  
 Pokud `wscoor:Identifier` z `wscoor:CoordinationContext` je relativní identifikátor URI, vrátí se chyby z transakční služeb WCF.  
  
## <a name="message-examples"></a>Příklady zprávy  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a>Zprávy požadavků/odpovědí CreateCoordinationContext  
 Tyto zprávy se řídí vzorem žádostí a odpovědí.  
  
#### <a name="createcoordinationcontext"></a>CreateCoordinationContext  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse"></a>CreateCoordinationContextResponse  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse     
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>   
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>    
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference   
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference   
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret   
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="registration-messages"></a>Registrační zprávy  
 Tyto zprávy jsou zprávy registrace.  
  
#### <a name="register"></a>Registr  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>        
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference   
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response"></a>Registrovat odpovědi  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e        
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a>Dvě fáze potvrzení protokolu zpráv  
 Tato zpráva má vztah k protokol dvoufázového potvrzení (2PC).  
  
#### <a name="commit"></a>Potvrzení změn  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="application-messages"></a>Aplikace zprávy  
 Tyto zprávy jsou zprávy aplikace.  
  
#### <a name="application-message-request"></a>Zpráva žádosti  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">   
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken   
          wssu:Id="IA_Certificate"   
          ValueType="...#X509v3"   
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->    
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader >  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader   
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->      
    <e:EncryptedData Id="encrypted_body"   
           Type="http://www.w3.org/2001/04/xmlenc#Content"   
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
