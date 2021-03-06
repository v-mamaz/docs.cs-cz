---
title: Element <appDomainManagerAssembly>
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66b2e6a3ef73b70a7ce78e3d6f32ba48f8cba980
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269702"
---
# <a name="appdomainmanagerassembly-element"></a>\<appDomainManagerAssembly> Element
Určuje sestavení, které poskytuje správce domény aplikace ve výchozí doméně aplikace v procesu.  
  
 \<Konfigurace >  
\<modul runtime >  
\<appDomainManagerAssembly>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`value`|Požadovaný atribut. Určuje zobrazovaný název sestavení, které poskytuje správce domény aplikace ve výchozí doméně aplikace v procesu.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|`configuration`|Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.|  
|`runtime`|Obsahuje informace o vazbách sestavení a uvolnění paměti.|  
  
## <a name="remarks"></a>Poznámky  
 Chcete-li určit typ správce domény aplikace, je nutné zadat obě tento element a [ \<appdomainmanagertype – >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) elementu. Pokud některý z těchto prvků není zadán, druhý se ignoruje.  
  
 Při načítání výchozí domény aplikace <xref:System.TypeLoadException> je vyvolána, pokud zadané sestavení neexistuje, nebo pokud sestavení neobsahuje typ zadaný [ \<appdomainmanagertype – >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element; a proces se nedaří spustit. Pokud je sestavení nalezeno, ale informace o verzi neodpovídá, <xref:System.IO.FileLoadException> je vyvolána výjimka.  
  
 Když zadáte typ správce domény aplikace výchozí aplikační domény, dědí jiných domén aplikace vytvořené z výchozí domény aplikace typ správce domény aplikace. Použití <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> a <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> vlastnosti zadat typ správce různých aplikační domény pro novou doménu aplikace.  
  
 Určení typu správce domény aplikace vyžaduje, aby aplikace mít plnou důvěryhodnost. (Například aplikace běžící v desktopovém má úplný vztah důvěryhodnosti.) Pokud aplikace nemá plnou důvěryhodnost <xref:System.TypeLoadException> je vyvolána výjimka.  
  
 Formát zobrazovaný název sestavení, najdete v článku <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> vlastnost.  
  
 Tento prvek konfigurace je k dispozici pouze v [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] a novější.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak určit, že je aplikace správce domény pro doménu aplikace výchozí procesu `MyMgr` zadejte `AdMgrExample` sestavení.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [\<appDomainManagerType> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)
- [Schéma nastavení běhového prostředí](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schéma konfiguračního souboru](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [SetAppDomainManagerType – metoda](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
