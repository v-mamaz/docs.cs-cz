---
title: <bypasslist> – element (nastavení sítě)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: db975d44db96f605767d7320737ff3c162bbc8a5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282955"
---
# <a name="bypasslist-element-network-settings"></a>\<bypasslist – > – Element (nastavení sítě)
Poskytuje sadu regulární výrazy, které popisují adresy, které nepoužívají proxy server.  
  
 \<Konfigurace >  
\<system.net>  
\<defaultProxy>  
\<bypasslist – >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|**Element**|**Popis**|  
|-----------------|---------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|Přidá do seznamu obcházení proxy IP adresu nebo název DNS.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|Seznam obcházení vymaže.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|Odebere ze seznamu obcházení proxy IP adresu nebo název DNS.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|**Element**|**Popis**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Konfiguruje server proxy protokolu HTTP (Hypertext Transfer).|  
  
## <a name="remarks"></a>Poznámky  
 Seznam obcházení obsahuje regulárních výrazů, které popisují identifikátory URI, který <xref:System.Net.WebRequest> instancí k datům přímo namísto prostřednictvím proxy serveru.  
  
 Buďte opatrní při zadávání regulární výraz pro tento element. Regulární výraz "[-z] +\\.contoso\\.com" odpovídá některé hostovat v doméně contoso.com, ale také odpovídající libovolného hostitele v doméně contoso.com.cpandl.com. Tak, aby odpovídaly pouze na hostiteli v doméně contoso.com, použijte ukotvení ("$"): "[-z] +\\.contoso\\.com$".  
  
 Další informace o formátování regulárních výrazů naleznete v tématu. [Regulárních výrazech .NET Frameworku](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Konfigurační soubory  
 Tento element lze použít v konfiguračním souboru aplikace nebo konfiguračního souboru počítače (Machine.config).  
  
## <a name="example"></a>Příklad  
 Následující příklad přidá do seznamu obcházení dvě adresy. První obcházejí proxy serveru pro všechny servery v doméně contoso.com; druhý vynechá proxy serveru pro všechny servery jehož IP adres začít s 192.168.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Schéma nastavení sítě](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
