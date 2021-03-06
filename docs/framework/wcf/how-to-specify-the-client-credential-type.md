---
title: 'Postupy: Určení typu pověření klienta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: 9fe999c4ee27d4a78bfad185fa3bcc065d74708a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643375"
---
# <a name="how-to-specify-the-client-credential-type"></a>Postupy: Určení typu pověření klienta
Po nastavení režimu zabezpečení (přenos nebo zpráva), máte možnost nastavit typ pověření klienta. Tato vlastnost určuje, jaký typ přihlašovacích údajů klient musí poskytnout službě pro ověřování. Další informace o nastavení režimu zabezpečení rozhraní (nezbytným krokem před nastavením typ přihlašovacích údajů klienta), najdete v části [jak: Nastavení režimu zabezpečení rozhraní](../../../docs/framework/wcf/how-to-set-the-security-mode.md).  
  
### <a name="to-set-the-client-credential-type-in-code"></a>Chcete-li nastavit typ přihlašovacích údajů klienta v kódu  
  
1.  Vytvoření instance vazby, který bude služba používat. V tomto příkladu <xref:System.ServiceModel.WSHttpBinding> vazby.  
  
2.  Nastavte <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> vlastnost na odpovídající hodnotu. Tento příklad používá režim zprávy.  
  
3.  Nastavte <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> vlastnost na odpovídající hodnotu. V tomto příkladu nastaví ho na použití ověřování Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a>Chcete-li nastavit typ přihlašovacích údajů klienta v konfiguraci  
  
1.  Přidat [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) prvku do konfiguračního souboru.  
  
2.  Jako podřízený prvek, přidejte [ \<vazby >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elementu.  
  
3.  Přidáte příslušnou datovou vazbu. V tomto příkladu [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elementu.  
  
4.  Přidat [ \<vazby >](../../../docs/framework/misc/binding.md) elementu a nastavte `name` atribut na odpovídající hodnotu. Tento příklad používá název "SecureBinding".  
  
5.  Přidat `<security>` vazby. Nastavte `mode` atribut na odpovídající hodnotu. V tomto příkladu nastaví na `"Message"`.  
  
6.  Přidat buď `<message>` nebo `<transport>` elementu, počítáno od režim zabezpečení. Nastavte `clientCredentialType` atribut na odpovídající hodnotu. Tento příklad používá `"Windows"`.  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a>Viz také:
- [Zabezpečení služeb](../../../docs/framework/wcf/securing-services.md)
- [Postupy: Nastavení režimu zabezpečení](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
