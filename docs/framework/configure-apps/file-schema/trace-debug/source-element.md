---
title: Element <source>
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: a528e0f77efea6df7379a0f01495bc09d2ed0b24
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254480"
---
# <a name="source-element"></a>\<zdroj > – Element
Určuje zdroj trasování, který iniciuje trasovací zprávy.  
  
 \<Konfigurace >  
\<system.diagnostics>  
\<zdroje >  
\<zdroj >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Nepovinný atribut.<br /><br /> Určuje název zdroje trasování.|  
|`switchName`|Nepovinný atribut.<br /><br /> Určuje název instance přepínače trasování v aplikaci. Pokud přepínač není identifikované v `<switches>` elementu, hodnota určuje úroveň pro přepínač.|  
|`switchType`|Nepovinný atribut.<br /><br /> Určuje typ přepínače trasování. Pokud jsou k dispozici, typ musí být platný název třídy a nemůže být prázdný řetězec.|  
|`extraAttribute`|Nepovinný atribut.<br /><br /> Určuje hodnotu pro atribut specifická pro zdroj trasování identifikován <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> metoda u tohoto zdroje trasování.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|Obsahuje moduly pro naslouchání, které shromažďování, ukládání a směrovat zprávy.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|`configuration`|Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.|  
|`system.diagnostics`|Určuje, kteří shromažďování, ukládání a směrovat zprávy a úroveň, kde je nastaven přepínač trasování.|  
|`sources`|Obsahuje zdrojů trasování, které se zahájí trasovací zprávy.|  
  
## <a name="remarks"></a>Poznámky  
 Tento element lze použít v konfiguračním souboru počítače (Machine.config) a konfigurační soubor aplikace.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `<source>` prvek a přidat zdroj trasování `mySource` a nastavit úroveň pro přepínač zdroje s názvem `sourceSwitch`. Naslouchacího procesu trasování konzoly je přidat informace o trasování, která zapisuje do konzoly.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a>Viz také:
- [Trasování a ladění schématu nastavení](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [Přepínače trasování](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
