---
title: <remove> – element pro element connectionManagement (nastavení sítě)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: 62f7793c8f25f4803e881e2f183c99c62000ca23
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270507"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a>\<Odebrat > – Element pro connectionManagement (nastavení sítě)
Odebere ze seznamu pro správu připojení IP adresu nebo název DNS.  
  
 \<Konfigurace >  
\<system.net>  
\<connectionManagement>  
\<remove>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|**Atribut**|**Popis**|  
|-------------------|---------------------|  
|`address`|IP adresa nebo název DNS.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|**Element**|**Popis**|  
|-----------------|---------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Určuje maximální počet připojení k síti hostitele.|  
  
## <a name="remarks"></a>Poznámky  
 `remove` Element odstraní položku seznamu správy připojení na určeném serveru.  
  
 Hodnota `address` atribut by měl mít platnou IP adresu nebo název hostitele.  
  
## <a name="configuration-files"></a>Konfigurační soubory  
 Tento element lze použít v konfiguračním souboru aplikace nebo konfiguračního souboru počítače (Machine.config).  
  
## <a name="example"></a>Příklad  
 Následující příklad odebere všechny položky seznamu správu připojení pro server `www.adventure-works.com` a pak nakonfiguruje aplikaci pro použití čtyř připojení k serveru `www.contoso.com` a dvě spojení na všechny ostatní servery.  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [Schéma nastavení sítě](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
