---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 752b1188fccb6f09cdcab6a50653abf26e8e2a53
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288181"
---
# <a name="customcookiehandler"></a>\<customCookieHandler>
Nastaví typ obslužné rutiny vlastních souborů cookie. Tento element může být pouze přítomen, pokud `mode` atribut `<cookieHandler>` elementu je "Vlastní". Vlastní typ musí být odvozen od <xref:System.IdentityModel.Services.CookieHandler> třídy.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler>  
\<customCookieHandler>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|– typ|Určuje, která je odvozena z vlastního typu <xref:System.IdentityModel.Services.CookieHandler> třídy. Další informace o tom, jak zadat `type` atributu naleznete v tématu [odkazů na vlastní typy](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádná  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<cookieHandler>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Konfiguruje <xref:System.IdentityModel.Services.CookieHandler> , který <xref:System.IdentityModel.Services.SessionAuthenticationModule> používá ke čtení a zápis souborů cookie.|  
  
## <a name="remarks"></a>Poznámky  
 Při zadání obslužné rutiny vlastních souborů cookie pomocí nastavení `mode` atribut `<cookieHandler>` element "Vlastní", je třeba zadat typ obslužné rutiny vlastních souborů cookie zahrnutím `<customCookieHandler>` podřízený prvek, který odkazuje na typ obslužné rutiny souborů cookie. Tento element nemůže být zadán při `mode` atribut je nastaven na "Bloku dat" nebo "Výchozí". Vlastní soubor cookie obslužné rutiny musí být odvozen od <xref:System.IdentityModel.Services.CookieHandler> třídy.  
  
 `<customCookieHandler>` Prvek je reprezentován <xref:System.IdentityModel.Configuration.CustomTypeElement> třídy.  
  
## <a name="example"></a>Příklad  
 Následující příklad nastaví SAM použít vlastní soubor cookie obslužné rutiny typu `MyNamespace.MyCustomCookieHandler`.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.IdentityModel.Services.CookieHandler>
