---
title: <remove> – element pro element webRequestModules (nastavení sítě)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: af30fe15eab899f7a083e0feb1350fb67b1c32cd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267258"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a>\<Odebrat > – Element pro webRequestModules (nastavení sítě)
Vlastní modul požadavku webového odstraní z aplikace.  
  
 \<Konfigurace >  
\<system.net>  
\<webRequestModules>  
\<remove>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|**Atribut**|**Popis**|  
|-------------------|---------------------|  
|`prefix`|Předponu identifikátoru URI pro žádosti zpracovat tento modul webové žádosti.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|**Element**|**Popis**|  
|-----------------|---------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Určuje moduly, které použijte k vyžádání informace z hostitelů v síti.|  
  
## <a name="remarks"></a>Poznámky  
 `remove` Element odebere registrovaný modul požadavku webového pro zadaný identifikátor URI předponu.  
  
 Hodnota `prefix` atribut by měl mít počáteční znaky platný identifikátor URI – například "`http`", nebo "`http://www.contoso.com`".  
  
## <a name="configuration-files"></a>Konfigurační soubory  
 Tento element lze použít v konfiguračním souboru aplikace nebo konfiguračního souboru počítače (Machine.config).  
  
## <a name="example"></a>Příklad  

Následující příklad odebere existující webový modul požadavku pro protokol HTTP a poté registrů nový modul vlastní webového požadavku pro protokol HTTP žádostí o `www.contoso.com`.
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Net.WebRequest>
- [Schéma nastavení sítě](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
