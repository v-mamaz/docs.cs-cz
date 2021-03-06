---
title: Co je nového v usnadnění přístupu v rozhraní .NET Framework
ms.custom: updateeachrelease
ms.date: 04/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bdb1bf5d7e32c2e05eb779eed16c311cbd3eae7
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212505"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Co je nového v usnadnění přístupu v rozhraní .NET Framework

Rozhraní .NET Framework, zaměřuje na zpřístupnění aplikace více uživatelům. Funkce usnadnění umožnit aplikaci pro zajištění odpovídající prostředí pro uživatele technologie pro usnadnění. Od verze rozhraní .NET Framework 4.7.1, rozhraní .NET Framework obsahuje velké množství vylepšení přístupnosti, které umožňují vývojářům vytvářet aplikace přístupné.

## <a name="accessibility-switches"></a>Usnadnění přepínače

Můžete nakonfigurovat aplikaci tak, aby přihlašují funkce pro usnadnění přístupu, pokud cílí na rozhraní .NET Framework 4.7 nebo starší verzi, ale běží na rozhraní .NET Framework 4.7.1 nebo novější. Můžete také konfigurovat aplikace pro použití funkce starší verze (a ne Využijte výhod funkce pro usnadnění přístupu), pokud je zaměřena rozhraní .NET Framework 4.7.1 nebo novější. Každá verze rozhraní .NET Framework, která zahrnuje funkce pro usnadnění přístupu má specifické pro verzi usnadnění přepínač, který přidáte do [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) prvek [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) oddílu konfiguračního souboru aplikace. Tady jsou podporované přepínače:

|Version|Přepínač|
|---|---|
|.NET Framework 4.7.1|"Switch.UseLegacyAccessibilityFeatures"|
|.NET Framework 4.7.2|"Switch.UseLegacyAccessibilityFeatures.2"|

### <a name="taking-advantage-of-accessibility-enhancements"></a>Využití výhod vylepšení přístupnosti

Nové funkce pro usnadnění přístupu se ve výchozím nastavení pro aplikace, které jsou cíleny rozhraní .NET Framework 4.7.1 povolená nebo novější. Kromě toho aplikace, které cílí na starší verzi rozhraní .NET Framework, ale jsou spuštěny v rozhraní .NET Framework 4.7.1 nebo později se můžou rozhodnout ze starší verze usnadnění chování (a tím využít výhod vylepšení přístupnosti) přidáním přepínače [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) prvek [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) oddílu konfiguračního souboru aplikace a nastavení jejich hodnoty na `false`. Následující ukazuje, jak můžete vyjádřit výslovný souhlas vylepšení přístupnosti představena v rozhraní .NET Framework 4.7.1:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Pokud budete chtít povolit funkce usnadnění v novější verzi rozhraní .NET Framework, musíte také explicitně připojíte k funkcím z předchozích verzí rozhraní .NET Framework. Konfigurace aplikace využít k vylepšení přístupnosti v obou rozhraní .NET Framework 4.7.1 a 4.7.2 vyžaduje následující [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a>Obnovit starší chování

Aplikací s cílovou verzí rozhraní .NET Framework 4.7.1 počínaje může zakázat funkce pro usnadnění přístupu přidáním přepínače [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) prvek [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) část konfigurační soubor aplikace a nastavení jejich hodnoty na `true`. Například následující konfigurace výslovný představena v rozhraní .NET Framework 4.7.2 funkce pro usnadnění přístupu:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-472"></a>Co je nového v usnadnění přístupu v rozhraní .NET Framework 4.7.2

Rozhraní .NET Framework 4.7.2 obsahuje nové funkce pro usnadnění přístupu v následujících oblastech:

- [Windows Forms](#winforms472)

- [Windows Presentation Foundation (WPF)](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a>Windows Forms

**Operační systém definovaných barev v Vysokokontrastních motivech**

Počínaje rozhraním .NET Framework 4.7.2, Windows Forms používá barvám definovaným v Vysokokontrastních motivech v operačním systému. Tato akce ovlivní následující ovládací prvky:

- Na šipku rozevíracího seznamu <xref:System.Windows.Forms.ToolStripDropDownButton> ovládacího prvku.

- <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> a <xref:System.Windows.Forms.CheckBox> ovládací prvky s <xref:System.Windows.Forms.ButtonBase.FlatStyle> nastavena na <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> nebo <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>. Dříve vybrané barvy textu a pozadí nebyly kontrastní a bylo obtížné číst.

- Ovládací prvky obsažené v rámci <xref:System.Windows.Forms.GroupBox> , který má jeho <xref:System.Windows.Forms.Control.Enabled> nastavenou na `false`.

- <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, A <xref:System.Windows.Forms.ToolStripDropDownButton> ovládací prvky, které mají zvýšené světelnost kontrastní poměr v režimu s vysokým kontrastem.

- <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> Vlastnost <xref:System.Windows.Forms.DataGridViewLinkCell>.

**Vylepšení programu Předčítání**

Počínaje rozhraním .NET Framework 4.7.2, je program Předčítání podpory rozšířeného následujícím způsobem:

- Představuje hodnotu <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> při uvedení text <xref:System.Windows.Forms.ToolStripMenuItem>.

- Označuje, kdy <xref:System.Windows.Forms.ToolStripMenuItem> má jeho <xref:System.Windows.Forms.Control.Enabled> nastavenou na `false`.

- Poskytuje zpětnou vazbu týkající se stavu zaškrtávacího políčka při <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> je nastavena na `true`.

- Program Předčítání na režim kontroly fokus pořadí je konzistentní s visual pořadí ovládacích prvků v dialogovém okně stahování ClickOnce.

**Vylepšení ovládacího prvku DataGridView**

Počínaje rozhraním .NET Framework 4.7.2, <xref:System.Windows.Forms.DataGridView> ovládací prvek přináší následující vylepšení přístupnosti:

- Lze seřadit řádky pomocí klávesnice. Uživatele můžete použít klávesy F3 k řazení podle aktuální sloupce.

- Když <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> je nastavena na <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, záhlaví sloupce se změní barvu označující aktuální sloupec jako karty uživatele mezi buňkami v aktuálním řádku.

- <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> Vlastnost <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> vrátí správné nadřazený ovládací prvek.

**Vylepšené vizuální prvky**

- <xref:System.Windows.Forms.RadioButton> a <xref:System.Windows.Forms.CheckBox> ovládací prvky s prázdnou <xref:System.Windows.Forms.ButtonBase.Text> vlastnost zobrazit indikátor fokus, když obdrží fokus.

**Podpora vylepšené vlastnost mřížky**

- <xref:System.Windows.Forms.PropertyGrid> Ovládací prvek nyní návratový podřízené prvky `true` pro <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> vlastnost, jenom když je povolený prvku PropertyGrid.

- <xref:System.Windows.Forms.PropertyGrid> Ovládacích prvků podřízené návratový `false` pro <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> vlastnost pouze v případě, že uživatel může změnit prvku PropertyGrid.

**Navigace pomocí kláves vylepšené**

- <xref:System.Windows.Forms.ToolStripButton> Ovládací prvek umožňuje fokus, pokud je obsažen v <xref:System.Windows.Forms.ToolStripPanel> , který má <xref:System.Windows.Forms.ToolStripPanel.TabStop> vlastnost nastavena na hodnotu `true`

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Změny ovládacích prvků CheckBox a ovládacího prvku RadioButton**

V rozhraní .NET Framework 4.7.1 a předchozími verzemi, WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> a <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> ovládací prvky mají nekonzistentní a v modelu Classic a Vysoký kontrast motivy, nesprávné fokus vizuály.  Těmto problémům dochází v případech, ve kterém ovládací prvky nemají žádné sadu obsahu.  Přechod mezi motivy matoucí a vizuál se fokus může být špatně vidět.

V rozhraní .NET Framework 4.7.2 tyto vizuály jsou teď víc konzistentní v rámci celého motivy a snadněji viditelné v modelu Classic a Vysoký kontrast – motivy.

**Ovládacích prvků WinForms hostované v aplikaci WPF**

Pro ovládací prvek WinForms je hostován v aplikaci WPF v rozhraní .NET Framework 4.7.1 a dřívějších verzích, uživatelé nelze kartu z vrstvy WinForms Pokud je první nebo poslední ovládací prvek v této vrstvě WPF <xref:System.Windows.Forms.Integration.ElementHost> ovládacího prvku. V rozhraní .NET Framework 4.7.2 uživatelé mohou nyní na kartě mimo vrstvě WinForms.

Automatizované aplikace, které spoléhají na fokus nikdy uvození WinForms vrstvy, ale už nemusí fungovat podle očekávání.

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>Co je nového v usnadnění přístupu v rozhraní .NET Framework 4.7.1

Rozhraní .NET Framework 4.7.1 obsahuje nové funkce pro usnadnění přístupu v následujících oblastech:

- [Windows Presentation Foundation (WPF)](#wpf471)

- [Windows Forms](#winforms471)

- [Webové ovládací prvky ASP.NET](#aspnet471)

- [.NET SDK Tools](#tools471)

- [Windows Workflow Foundation (WF), návrháře postupu provádění](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Vylepšení čtečky obrazovky**

Pokud jsou povolené vylepšení přístupnosti, rozhraní .NET Framework 4.7.1 zahrnuje následující vylepšení, které ovlivňují čtečky obrazovky:

- V rozhraní .NET Framework 4.7 a předchozími verzemi <xref:System.Windows.Controls.Expander> ovládací prvky byly oznamovaný čtečkami obrazovky jako tlačítka. Od verze rozhraní .NET Framework 4.7.1, jejich správně oznámení jako rozšíření/sbalitelné skupiny.

- V rozhraní .NET Framework 4.7 a předchozími verzemi <xref:System.Windows.Controls.DataGridCell> ovládací prvky byly oznamovaný čtečkami obrazovky jako "vlastní". Od verze rozhraní .NET Framework 4.7.1, jejich nyní správně oznámení jako buňka datové mřížky (lokalizované).

- Od verze rozhraní .NET Framework 4.7.1, čtečky obrazovky oznamujeme název upravitelné <xref:System.Windows.Controls.ComboBox>.

- V rozhraní .NET Framework 4.7 a předchozími verzemi <xref:System.Windows.Controls.PasswordBox> ovládací prvky byly uvolněné jako "žádné položky v zobrazení" nebo měl jinak nesprávné chování. Tento problém vyřešen, od verze rozhraní .NET Framework 4.7.1.

**Vlastnosti UIAutomation LiveRegion podpory**

Čtečky obrazovky, jako jsou například lidé pomoc programu Předčítání číst obsah uživatelského rozhraní aplikace, obvykle převod textu na řeč výstupní obsah uživatelského rozhraní, který má fokus. Pokud ale prvku uživatelského rozhraní se změní a nemá fokus, uživatel nemusí být upozorněni a přijít o důležité informace. Živé oblastech zaměřené na řešení tohoto problému. Vývojář můžete využít k informování čtečky obrazovky nebo jakéhokoli klienta vlastnosti UIAutomation, který byl proveden důležité změny prvku uživatelského rozhraní. Čtečka obrazovky se můžete rozhodnout používat jak a kdy informovat uživatele o této změně.

Pro podporu živé oblastí, jsme přidali následující rozhraní API k použití WPF:

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> a <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> pole, které identifikovat **LiveSetting** vlastnost a **LiveRegionChanged** událostí. Můžete třeba nastavit pomocí XAML.

- **AutomationProperties.LiveSetting** přidružená vlastnost, která informuje o čtečka obrazovky významné změny uživatelského rozhraní pro uživatele.

- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> Vlastnost, která identifikuje **AutomationProperties.LiveSetting** přidružená vlastnost.

- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> Metodu, která může být potlačena za účelem poskytují **LiveSetting** hodnotu.

- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> a <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> metody, které get a set **LiveSetting** hodnotu.

- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> Výčet, který definuje následující možné **LiveSetting** hodnoty:

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>. Element neodešle oznámení, pokud došlo ke změně obsahu aktivní oblast.
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>. Element odešle-interruptive oznámení, pokud došlo ke změně obsahu aktivní oblast.

   - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>. Element odešle interruptive oznámení, pokud došlo ke změně obsahu aktivní oblast.

Můžete vytvořit LiveRegion nastavením **AutomationProperties.LiveSetting** vlastnosti prvku, která vás zajímá, jak je znázorněno v následujícím příkladu:

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

Při změně dat v živé oblasti a je potřeba informovat čtečky obrazovky, můžete explicitně vyvolat událost, jak je znázorněno v následujícím příkladu.

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**Vysoký kontrast**

Od verze rozhraní .NET Framework 4.7.1, vylepšení ve vysokém kontrastu byly provedeny na různé ovládací prvky WPF. Jsou nyní viditelné při <xref:System.Windows.SystemParameters.HighContrast%2A> je nastavený. Zde jsou některé z nich:

- <xref:System.Windows.Controls.Expander> Ovládací prvek

    Visual pro zaměření <xref:System.Windows.Controls.Expander> je nyní ovládací prvek viditelný. Vizuály klávesnice pro <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, a <xref:System.Windows.Controls.RadioButton> ovládací prvky jsou také viditelné. Příklad:

    Před: 

    ![Rozšíření – ovládací prvek s fokusem před vylepšení přístupnosti](media/expander-before.png)

    Po: 

    ![Rozšíření – ovládací prvek s fokusem po vylepšení přístupnosti](media/expander-after.png)

- <xref:System.Windows.Controls.CheckBox> a <xref:System.Windows.Controls.RadioButton> ovládacích prvků

    Text <xref:System.Windows.Controls.CheckBox> a <xref:System.Windows.Controls.RadioButton> ovládacích prvků je teď snazší zjistit při výběru v vysokokontrastních motivech. Příklad:

    Před: 

    ![Vysoký kontrast – přepínač s fokusem před vylepšení přístupnosti](media/radio-button-before.png)

    Po: 

    ![Vysoký kontrast – přepínač s fokusem po vylepšení přístupnosti](media/radio-button-after.png)

- <xref:System.Windows.Controls.ComboBox> Ovládací prvek

    Od verze rozhraní .NET Framework 4.7.1, ohraničení zakázané <xref:System.Windows.Controls.ComboBox> ovládací prvek se stejnou barvu jako neaktivního textu. Příklad:

    Před: 

     ![Pole se seznamem zakázané ohraničení a text před vylepšení přístupnosti](media/combo-disabled-before.png)

    Po:   

     ![Pole se seznamem zakázané ohraničení a text po vylepšení přístupnosti](media/combo-disabled-after.png)

    Kromě toho tlačítka zakázáno a zaměřují se používají Barva motivu správné.

    Před:

    ![Tlačítko barvy motivu před vylepšení přístupnosti](media/button-themes-before.png) 

    Po: 

    ![Tlačítko barvy motivu po vylepšení přístupnosti](media/button-themes-after.png) 

    Nakonec v rozhraní .NET Framework 4.7 a předchozími verzemi, nastavení <xref:System.Windows.Controls.ComboBox> stylu ovládacího prvku na `Toolbar.ComboBoxStyleKey` způsobila na šipku rozevíracího seznamu byla neviditelná. Tento problém vyřešen, od verze rozhraní .NET Framework 4.7.1. Příklad:

    Před: 

    ![Toolbar.ComboBoxStyleKey před vylepšení přístupnosti](media/comboboxstylekey-before.png) 

    Po: 

    ![Toolbar.ComboBoxStyleKey po vylepšení přístupnosti](media/comboboxstylekey-after.png) 

- <xref:System.Windows.Controls.DataGrid> Ovládací prvek

    Od verze rozhraní .NET Framework 4.7.1, šipku indikátor řazení v <xref:System.Windows.Controls.DataGrid> řídí teď používá opravte barvy motivu. Příklad:

    Před: 

    ![Šipka řazení před vylepšení přístupnosti](media/sort-indicator-before.png) 

    Po:   

    ![Řazení šipka po vylepšení přístupnosti](media/sort-indicator-after.png) 

    Kromě toho v rozhraní .NET Framework 4.7 a dřívějších verzích výchozí styl odkaz změnit k nesprávné barvě po pozastavení ukazatele myši v režimu vysokého kontrastu. Tento problém nevyřeší, od verze rozhraní .NET Framework 4.7.1. Obdobně <xref:System.Windows.Controls.DataGrid> sloupce zaškrtávací políčko používá očekávané barvy pro zpětnou vazbu fokus klávesnice, která je od verze rozhraní .NET Framework 4.7.1.

    Před: 

    ![DataGrid – výchozí odkaz styl před vylepšení přístupnosti](media/default-link-style-before.png) 

    Po:    

    ![DataGrid – výchozí odkaz styl po vylepšení přístupnosti](media/default-link-style-after.png) 

Další informace o vylepšení přístupnosti WPF v rozhraní .NET Framework 4.7.1 najdete v tématu [vylepšení přístupnosti v subsystému WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a>Vylepšení přístupnosti Windows Forms

V rozhraní .NET Framework 4.7.1 Windows Forms (WinForms) zahrnuje usnadnění změny v následujících oblastech.

**Vylepšené zobrazení v režim s vysokým kontrastem**

Od verze rozhraní .NET Framework 4.7.1, různých ovládacích prvků WinForms nabízí vylepšené vykreslování v režimech funkce Vysoký kontrast v operačním systému. Windows 10 došlo ke změně hodnoty pro některé vysoký kontrast – barvy system a Windows Forms je založená na platformě Windows 10 Win32. Pro dosažení co nejlepších výsledků spusťte na nejnovější verzi Windows a vyjádřit výslovný souhlas s nejnovějšími změnami operačního systému tak, že přidáte soubor app.manifest v aplikaci test a zrušení comment Windows 10 nepodporují řádku operačního systému tak, aby následující:

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```

Mezi příklady vysoký kontrast – změny patří:

- Značek zaškrtnutí v <xref:System.Windows.Forms.MenuStrip> položky jsou usnadňuje zobrazení.

- Pokud je vybráno, zakázané <xref:System.Windows.Forms.MenuStrip> položky jsou usnadňuje zobrazení.

- Text ve vybrané <xref:System.Windows.Forms.Button> řídit liší od tradičnější barvu výběru.

- Neaktivní text je lépe čitelný. Příklad:

    Před:

    ![Neaktivní text před vylepšení přístupnosti](media/wf-disabled-before.png) 

    Po:

    ![Neaktivní text po vylepšení přístupnosti](media/wf-disabled-after.png) 

- Vysoký kontrast – vylepšení v dialogovém okně výjimky vlákna.

**Vylepšená podpora Předčítání**

Windows Forms v rozhraní .NET Framework 4.7.1 zahrnuje následující vylepšení přístupnosti Narrator:

- <xref:System.Windows.Forms.MonthCalendar> Ovládací prvek je přístupný podle program Předčítání, a další nástroje pro automatizaci uživatelského rozhraní.

- <xref:System.Windows.Forms.CheckedListBox> Ovládací prvek upozorní Předčítání při změně stavu zaškrtnutí položky tak, že se uživatel dozví, že jste se změnil hodnotu ovládacího prvku položky seznamu.

- <xref:System.Windows.Forms.DataGridViewCell> Ovládací prvek sestavy Předčítání správný stav jen pro čtení.

- Program Předčítání teď dokáže číst zakázáno <xref:System.Windows.Forms.ToolStripMenuItem> text, zatímco dříve by přeskočit prostřednictvím položky nabídky zakázané.

**Vylepšená podpora pro vlastnosti UIAutomation usnadnění vzory**

Od verze rozhraní .NET Framework 4.7.1, můžou využívat technologie usnadnění vývoje sofwaru bez běžných vzorů pro usnadnění rozhraní API a vlastnosti pro několik ovládacích prvků WinForms. Vylepšení usnadnění přístupu patří:

- <xref:System.Windows.Forms.ComboBox> a <xref:System.Windows.Forms.ToolStripSplitButton> teď podporují [Rozbalit/sbalit vzor](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- <xref:System.Windows.Forms.DataGridViewCheckBoxCell> Teď podporuje [vzoru přepínání](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).

- <xref:System.Windows.Forms.ToolStripItem> Podporuje ovládací prvek <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> vlastnost a [Rozbalit/sbalit vzor](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- <xref:System.Windows.Forms.NumericUpDown> a <xref:System.Windows.Forms.DomainUpDown> řídí podporu <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> vlastnost.

**Vylepšené vlastnost prohlížeče prostředí**

Od verze rozhraní .NET Framework 4.7.1, Windows Forms obsahuje:

- Lepší navigaci pomocí klávesnice prostřednictvím různých windows rozevíracího seznamu výběru.
- Snížení zbytečné tabulátoru.
- Lepší vytváření sestav, typů ovládacích prvků.
- Vylepšené Předčítání chování.

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a>Webové ovládací prvky ASP.NET

Od verze rozhraní .NET Framework 4.7.1 a Visual Studio 2017 15.3, ASP.NET zlepšuje, jak fungují ovládací prvky technologie ASP.NET webové technologie usnadnění v sadě Visual Studio. Změny patří:

- Změny pro implementaci chybějící vzory usnadnění přístupu uživatelského rozhraní v ovládacích prvcích, jako je třeba **přidat pole** dialogového okna v **zobrazení podrobností o** průvodce, nebo **konfigurace ListView** dialogové okno **ListView** průvodce.

- Změny s cílem zobrazit v režimu vysokého kontrastu, jako je třeba **Editor pole stránkování dat**.

- Změny pro zlepšení navigace klávesnice, prostředí pro ovládací prvky, jako je třeba **pole** dialogového okna v **úpravy polí stránkování** průvodce ovládací prvek DataPager **Konfigurovat ObjectContext**  dialogového okna, nebo **Konfigurovat výběr dat** dialogové okno **konfigurace zdroje dat** průvodce.

<a name="tools471"></a>

### <a name="net-sdk-tools"></a>.NET SDK Tools

[Nástroj Configuration Editor (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) a [nástroj Prohlížeč trasování služeb (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) byly vylepšeny opravou různých usnadnění. Většina z nich byly malé problémy, jako je název nedefinují nebo určité vzory pro automatizaci uživatelského rozhraní nebyl správně implementována. Přestože mnoho uživatelů nebude vědět o těchto nesprávné hodnoty, zákazníci, kteří používají podpůrnou technologií, jako je čtečky obrazovky najdete tyto sady SDK nástroje přístupnější.

Tato vylepšení změnit některé předchozí chování, jako je například pořadí fokus klávesnice.

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a>Windows Workflow Foundation (WF), návrháře postupu provádění

Usnadnění změny v Návrháři postupu provádění, patří:

- Změní pořadí zleva doprava a shora dolů v některé ovládací prvky:

  - Okno Inicializace korelace pro korelaci dat pro nastavení <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity.

  - V okně Definice obsahu <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity.

- Další funkce jsou k dispozici prostřednictvím klávesnice:

  - Při úpravě vlastností aktivity, skupiny vlastností můžete sbalit pomocí klávesnice, zaměřuje prvním.

  - Varovné ikony jsou přístupné pomocí klávesnice.

  - **Více vlastností** tlačítko **vlastnosti** okno přístupný pomocí klávesnice.

  - Uživatelé klávesnice můžete přistupovat k položky hlavičky v **argumenty** a **proměnné** podoken návrháře postupu provádění.

- Vylepšená viditelnost položek s fokusem, jako např. kdy:

  - Přidání řádků do datových mřížek používají návrháři návrháře pracovních postupů a aktivit.

  - Procházíte polí <xref:System.ServiceModel.Activities.ReceiveReply> a <xref:System.ServiceModel.Activities.SendReply> aktivity.

  - Nastavení výchozích hodnot proměnných nebo argumentů

- Čtečky obrazovky nyní správně rozpozná:

  - Zarážky nastavené v Návrháři pracovních postupů.

  - <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, A <xref:System.ServiceModel.Activities.CorrelationScope> aktivity.
  - Obsah <xref:System.ServiceModel.Activities.Receive> aktivity.

  - Cílový typ pro <xref:System.Activities.Statements.InvokeMethod> aktivity.

  - Pole se seznamem výjimek a nakonec v části <xref:System.Activities.Statements.TryCatch> aktivity.

  - Pole se seznamem typ zprávy, rozdělovač v okně Přidat inicializátory korelace, okno Definice obsahu a okno definice vlastnosti CorrelatesOn v zasílání zpráv aktivity (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, a <xref:System.ServiceModel.Activities.ReceiveReply>).

  - Stavový stroj přechody a přechody cíle.

  - Poznámky a konektory na <xref:System.Activities.Statements.FlowDecision> aktivity.

  - (Klikněte pravým tlačítkem) kontextové nabídky pro aktivity.

  - Do editorů hodnot vlastnost, tlačítko Vymazat hledání, podle kategorie a tlačítka abecední řazení a dialogové okno Editor výrazů v mřížce vlastnosti.

  - Procento zvětšení v Návrháři pracovních postupů.

  - Oddělovač v <xref:System.Activities.Statements.Parallel> a <xref:System.Activities.Statements.Pick> aktivity.

  - <xref:System.Activities.Statements.InvokeDelegate> Aktivity.

  - V okně vyberte typy aktivit slovník (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`atd.).

  - Okno Procházet a vybrat typ .NET.

  - V Návrháři pracovních postupů s popisem cesty.

- Uživatelé, kteří se rozhodnou vysoký kontrast – motivy uvidí řady vylepšení v zobrazení návrháře pracovních postupů a jeho ovládacích prvků, jako je lepší kontrastní poměr mezi elementy a snadněji postřehnutelné zaškrtávacími políčky použitých pro elementy fokus.

## <a name="see-also"></a>Viz také:

- [Co je nového v rozhraní .NET Framework](whats-new.md)
