---
title: Atributy nastavení aplikace
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: cfbaac8ad9a8576d076ed34059fb62e9e0a91ebc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714655"
---
# <a name="application-settings-attributes"></a>Atributy nastavení aplikace
Architektura nastavení aplikace poskytuje mnoho atributů, které lze použít buď pro obálkovou třídu nastavení aplikace nebo jeho jednotlivé vlastnosti. Tyto atributy jsou zkoumány za běhu aplikace nastavení infrastruktury, často konkrétně poskytovatel nastavení, aby bylo možné přizpůsobit jejich fungování stanovených potřebám vlastní obálku.  
  
 V následující tabulce jsou uvedeny atributy, které můžete použít pro obálkovou třídu nastavení aplikace nebo jednotlivé vlastnosti této třídy. Podle definice pouze jeden atribut –**UserScopedSettingAttribute** nebo **atribut ApplicationScopedSettingAttribute**– musí použít u každého nastavení vlastnosti.  
  
> [!NOTE]
>  Vlastní nastavení poskytovatele, odvozený z <xref:System.Configuration.SettingsProvider> třídy, je potřeba jenom k rozpoznání následující tři atributy: **Atribut ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, a **DefaultSettingValueAttribute**.  
  
|Atribut|Target|Popis|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Obojí|Určuje krátký název nastavení zprostředkovatele má být použit pro trvalost.<br /><br /> Pokud tento atribut není zadán, výchozí zprostředkovatel <xref:System.Configuration.LocalFileSettingsProvider>, předpokládá se.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Obojí|Definuje vlastnost jako nastavení rozsahu uživatele aplikace.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Obojí|Definuje vlastnost jako nastavení aplikace s rozsahem aplikace.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Vlastnost|Určuje řetězec, který lze deserializovat zprostředkovatelem do pevně zakódované výchozí hodnoty pro tuto vlastnost.<br /><br /> <xref:System.Configuration.LocalFileSettingsProvider> Nevyžaduje, aby tento atribut a přepíše libovolnou hodnotu, pokud tento atribut dojde-li hodnotu již trvale uložena.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Vlastnost|Poskytuje popisný testu pro individuální nastavení, primárně používá za běhu a návrhových nástrojů.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Třída|Poskytuje explicitní název pro skupinu nastavení. Pokud tento atribut chybí, <xref:System.Configuration.ApplicationSettingsBase> používá název obálkové třídy.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Třída|Poskytuje popisný testu pro skupinu nastavení, který se primárně používá za běhu a návrhových nástrojů.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Obojí|Určuje nula nebo více možností správy služeb, které by měla být k dispozici nastavení skupiny nebo vlastnost. Dostupné služby jsou popsané <xref:System.Configuration.SettingsManageability> výčtu.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Vlastnost|Označuje, že nastavení patří do speciální, předdefinované kategorie, jako je například připojovací řetězec, která navrhuje, speciální zpracování nastavení poskytovatele. Předdefinované kategorie pro tento atribut jsou definovány <xref:System.Configuration.SpecialSetting> výčtu.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Obojí|Určuje upřednostňovaný serializace mechanismus pro nastavení skupina nebo vlastnost. Mechanismus serializace k dispozici jsou definovány <xref:System.Configuration.SettingsSerializeAs> výčtu.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Vlastnost|Určuje, že poskytovatel nastavení zakažte všechny funkce upgradu aplikace pro vlastnost označené.|  
  
 *Třída* označuje, že atribut lze použít pouze pro třídu obálky nastavení aplikace. *Vlastnost* znamená, že atribut může být použitý jenom nastavení vlastnosti. *Obě* označuje, že atribut je možné použít na obou úrovní.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- [Architektura nastavení aplikace](application-settings-architecture.md)
- [Postupy: Vytvořit nastavení aplikace](how-to-create-application-settings.md)
