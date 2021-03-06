---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: aff415bb75cf719ce19fb2189cc69c2c159af6cf
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281005"
---
# <a name="windowsstreamsecurity"></a>\<windowsStreamSecurity>
Zadejte nastavení zabezpečení datového proudu Windows pro vlastní vazbu.  
  
 \<system.serviceModel>  
\<vazby >  
\<customBinding>  
\<Vytvoření vazby >  
\<windowsStreamSecurity>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Třída protectionLevel|Definuje zabezpečení na úrovni zprávy. Podepisování zpráv snižuje riziko manipulace s zprávy při jejich přenosu od jiných dodavatelů. Šifrování poskytuje data úrovně ochrany osobních údajů při přenosu. Platné hodnoty patří:<br /><br /> -Žádný: Žádná ochrana.<br />– Přihlášení: Zprávy jsou podepsané.<br />-EncryptAndSign: Zprávy jsou podepsaný a zašifrovaný.<br /><br /> Výchozí hodnota je EncryptAndSign.<br /><br /> Tento atribut je typu <xref:System.Net.Security.ProtectionLevel>.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádná  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<Vytvoření vazby >](../../../../../docs/framework/misc/binding.md)|Definuje všechny možnosti vázání pro vlastní vazbu.|  
  
## <a name="remarks"></a>Poznámky  
 Na základě datového proudu přenosu inovace podporují přenosy, které používají protokol orientovaný na stream jako je například TCP a pojmenované kanály. Konkrétně WCF poskytuje upgradů zabezpečení. Konfigurace tohoto zabezpečení přenosu jsou zapouzdřena objektem tento prvek konfigurace a také zobrazením [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), které se konfigurují a přidat do vlastní vazby  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [Vazby](../../../../../docs/framework/wcf/bindings.md)
- [Rozšíření vazeb](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Vlastní vazby](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
