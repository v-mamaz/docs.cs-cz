---
title: 'Postupy: Zjištění nainstalovaných verzí rozhraní .NET Framework'
ms.date: 03/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74c68aec535515803b9048aeed8395b53a4aaa4b
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411041"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Postupy: Zjištění nainstalovaných verzí rozhraní .NET Framework

Uživatelé můžou [nainstalovat](https://docs.microsoft.com/dotnet/framework/install) a spuštění několika verzí rozhraní .NET Framework na svých počítačích. Při vývoji nebo nasazení vaší aplikace, můžete potřebovat vědět, jaké verze rozhraní .NET Framework jsou nainstalovány v počítači uživatele. 

Rozhraní .NET Framework obsahuje dvě hlavní součásti, které mají samostatné verze:  
  
- Sadu sestavení, která jsou kolekce typů a prostředků, které poskytují funkce pro vaše aplikace. Rozhraní .NET Framework a sestavení sdílejí stejné číslo verze.  
  
- Modul CLR (CLR), jež spravuje a spouští kód vaší aplikace. CLR je identifikováno svým vlastním číslem verze (viz [verze a závislosti](~/docs/framework/migration-guide/versions-and-dependencies.md)).  

> [!NOTE]
> Každá nová verze rozhraní .NET Framework zachovává funkce předchozích verzí a přidává nové funkce. Více verzí rozhraní .NET Framework v jednom počítači můžete načíst ve stejnou dobu, což znamená, že můžete nainstalovat rozhraní .NET Framework bez odinstalování předchozích verzí. Obecně platí že byste neměli odinstalovávat předchozích verzích rozhraní .NET Framework, protože na konkrétní verzi může záviset aplikace, které používáte a mohou přestat fungovat, pokud je verze odebrána.
>
> Existuje rozdíl mezi verzí rozhraní .NET Framework a verzi modulu CLR: 
> - Verze rozhraní .NET Framework je založená na sadu sestavení, které tvoří knihovny tříd rozhraní .NET Framework. Například zahrnují verze rozhraní .NET Framework 4.5, 4.6.1 a 4.7.2. 
>- Verze CLR je založená na modulu runtime, na kterém aplikace rozhraní .NET Framework jsou spouštěny. Jedna verze modulu CLR obvykle podporuje více verzí rozhraní .NET Framework. Například verze modulu CLR 4.0.30319. *xxxxx* podporuje rozhraní .NET Framework verze 4 prostřednictvím 4.5.2 a 4.0.30319.42000 podporuje od verze rozhraní .NET Framework 4.6 verze rozhraní .NET Framework verze CLR. 
>
> Další informace o verzích, najdete v části [rozhraní .NET Framework verze a závislosti](versions-and-dependencies.md).


Pokud chcete získat seznam verzí rozhraní .NET Framework nainstalované na počítači, máte přístup k registru. Editor registru můžete použít buď k zobrazení registru nebo ji dotazovat s pomocí kódu:
 
- Najdete novější verze rozhraní .NET Framework (4.5 a novější): 
     - [Pomocí Editoru registru vyhledejte verze rozhraní .NET Framework](#net_b)  
     - [Použít kód k dotazování registru pro verze rozhraní .NET Framework](#net_d)  
     - [Použití Powershellu k dotazování registru pro verze rozhraní .NET Framework](#ps_a)
- Najít starší verze rozhraní .NET Framework (1&#8211;4):
     - [Pomocí Editoru registru vyhledejte verze rozhraní .NET Framework](#net_a)
     - [Použít kód k dotazování registru pro verze rozhraní .NET Framework](#net_c)   

Pokud chcete získat seznam verzí modulu CLR nainstalované v počítači, pomocí nástroje nebo kódu:  
  
- [Použití nástroje Clrver](#clr_a)  
- [Dotaz na třídu prostředí pomocí kódu](#clr_b)  

Informace o zjišťování nainstalovaných aktualizací pro každou verzi rozhraní .NET Framework najdete v tématu [jak: Zjištění nainstalovaných aktualizací rozhraní .NET Framework](how-to-determine-which-net-framework-updates-are-installed.md). 
  

## <a name="find-newer-net-framework-versions-45-and-later"></a>Najít novější verze rozhraní .NET Framework (4.5 a novější)

<a name="net_b"></a> 
### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a>Najít rozhraní .NET Framework verze 4.5 a vyšší v registru

1. Z **Start** nabídce zvolte **spustit**, zadejte *regedit*a pak vyberte **OK**.

     Musíte mít pověření správce, chcete-li spustit program regedit.

2. V editoru registru otevřete následující podklíč: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**. Pokud **úplné** podklíč není k dispozici a není k dispozici rozhraní .NET Framework 4.5 nebo novější.

    > [!NOTE]
    > **NET Framework Setup** složky v registru nezačíná tečkou.

3. Vyhledejte položku DWORD s názvem **vydání**. Pokud existuje, pak je nutné rozhraní .NET Framework 4.5 nebo novější. Jeho hodnota je verze klíče, který odpovídá konkrétní verzi rozhraní .NET Framework. Na následujícím obrázku, například hodnoty **Release** položka je *378389*, což je verze klíč pro rozhraní .NET Framework 4.5. 

     ![Položky registru pro rozhraní .NET Framework 4.5](media/clr-installdir.png "položky registru pro rozhraní .NET Framework 4.5")

V následující tabulce jsou uvedeny minimální hodnota **vydání** záznam pro každou verzi rozhraní .NET Framework. Tyto hodnoty můžete použít takto:

- Pokud chcete zjistit, zda je k dispozici minimální verze rozhraní .NET Framework, testování, zda **verze** v registru byla nalezena hodnota DWORD je *větší než nebo rovna hodnotě* hodnota uvedená v tabulce. Například pokud vaše aplikace vyžaduje rozhraní .NET Framework 4.7 nebo novější, je otestovat pro hodnotu minimální verze klíče z *460798*.

- Pokud chcete otestovat více verzí, začněte s nejnovější verzí rozhraní .NET Framework a pak test pro každou po sobě jdoucích starší verzi.

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|Verze rozhraní .NET Framework|Hodnota DWORD verze|
|--------------------------------|-------------|
|.NET Framework 4.5|378389|
|.NET Framework 4.5.1|378675|
|.NET Framework 4.5.2|379893|
|.NET Framework 4.6|393295|
|.NET Framework 4.6.1|394254|
|.NET Framework 4.6.2|394802|
|Rozhraní .NET framework 4.7|460798|
|.NET Framework 4.7.1|461308|
|.NET Framework 4.7.2|461808|

Kompletní tabulku verze klíče pro rozhraní .NET Framework pro konkrétní verze operačního systému Windows, naleznete v tématu [klíče rozhraní .NET Framework verze a verze operačního systému Windows](release-keys-and-os-versions.md).


<a name="net_d"></a> 
### <a name="find-net-framework-versions-45-and-later-with-code"></a>Najít rozhraní .NET Framework verze 4.5 a vyšší s kódem

1. Použití <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> a <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> metody pro přístup k **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** podklíčů v registru Windows.

    Existence **vydání** položku DWORD v **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** podklíč označuje, že je rozhraní .NET Framework 4.5 nebo novější verze počítači nainstalována. 

2. Zkontrolujte hodnotu **vydání** položku k určení Instalovatelné verze. Aby dopřednou vyhledejte hodnotu větší než nebo rovno hodnota uvedená ve [tabulku verzí rozhraní .NET Framework](#version_table).

Následující příklad zkontroluje hodnotu vlastnosti **vydání** záznam v registru najít rozhraní .NET Framework 4.5 a novější verze, které jsou nainstalovány:

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

V tomto příkladu následuje doporučený postup pro kontrolu verzí:

- Zkontroluje, zda hodnota **Release** položka je *větší než nebo rovna hodnotě* hodnotu klíče známé verze.

- Zkontroluje, aby nejstarší verzi z nejnovější verze.

<a name="ps_a"></a> 
### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a>Vyhledejte minimální požadovaná rozhraní .NET Framework verze (4.5 a novější) pomocí Powershellu

- Zkontrolovat hodnoty pomocí příkazů Powershellu **vydání** vstupu **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** podklíči.

Následující příklady kontrolu hodnoty **vydání** položku k určení, zda rozhraní .NET Framework 4.6.2 nebo novější nainstalován. Tento kód vrátí `True` je-li nainstalován a `False` jinak.

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
```

Vyhledat jinou verzi rozhraní .NET Framework minimální požadovaná, nahraďte *394802* v těchto příkladech se **vydání** hodnotu [tabulku verzí rozhraní .NET Framework](#version_table).

## <a name="find-older-net-framework-versions-182114"></a>Najít starší verze rozhraní .NET Framework (1&#8211;4)

<a name="net_a"></a>
### <a name="find-net-framework-versions-182114-in-the-registry"></a>Najít rozhraní .NET Framework verze 1&#8211;4 v registru 
  
1. Z **Start** nabídce zvolte **spustit**, zadejte *regedit*a pak vyberte **OK**.
  
    Musíte mít pověření správce, chcete-li spustit program regedit.  

2. V editoru registru otevřete následující podklíč: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:  

    - Pro rozhraní .NET Framework verze 1.1 až 3.5, každý nainstalovaná verze je uveden jako podklíč **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** podklíči. Například **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**. Číslo verze je uloženo jako hodnota v podklíči verze **verze** položka. 
     
    - Pro rozhraní .NET Framework 4 **verze** položka je v části **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** podklíči **HKEY_LOCAL_MACHINE\SOFTWARE\ Microsoft\NET Framework Setup\NDP\v4.0\Full** podklíče, nebo pod oběma podklíči.

    > [!NOTE]
    > **NET Framework Setup** složky v registru nezačíná tečkou.

    Následující obrázek znázorňuje podklíče a jeho **verze** položku pro rozhraní .NET Framework 3.5.

    ![Položky registru pro rozhraní .NET Framework 3.5. ](media/net-4-and-earlier.png "Rozhraní .NET framework 3.5 a starší")

<a name="net_c"></a> 
### <a name="find-net-framework-versions-182114-with-code"></a>Najít rozhraní .NET Framework verze 1&#8211;4 s kódem

- Použití <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> třídy k přístupu **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** podklíčů v registru Windows.

Následující příklad vyhledá rozhraní .NET Framework 1&#8211;4 verze, které jsou nainstalovány:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]


## <a name="find-clr-versions"></a>Najít verze CLR
  
<a name="clr_a"></a> 
### <a name="find-the-current-clr-version-with-clrverexe"></a>Vyhledání aktuální verze modulu CLR s Clrver.exe

Použití [nástroj CLR Version (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) k určení, jaké verze modulu CLR jsou nainstalovány v počítači:

- Z [Developer Command Prompt pro sadu Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), zadejte `clrver`.

    Ukázkový výstup:

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a> 
### <a name="find-the-current-clr-version-with-the-environment-class"></a>Vyhledání aktuální verze modulu CLR s třídou prostředí

> [!IMPORTANT]
> Pro rozhraní .NET Framework 4.5 a novější verze, nepoužívejte <xref:System.Environment.Version%2A?displayProperty=nameWithType> vlastnost zjistit verzi modulu CLR. Místo toho dotazu registru, jak je popsáno v [najít rozhraní .NET Framework verze 4.5 a vyšší s kódem](#net_d).

1. Dotaz <xref:System.Environment.Version?displayProperty=nameWithType> vlastnost pro načtení <xref:System.Version> objektu. 

    Vrácený `System.Version` objekt určuje verzi modulu runtime, který aktuálně spouští kód. Nevrací se verze sestavení ani jiné verze modulu runtime, který byl nainstalován v počítači.

    Pro rozhraní .NET Framework verze 4, 4.5, 4.5.1 a 4.5.2, řetězcovou reprezentaci vráceného <xref:System.Version> objektu má tvar 4.0.30319. *xxxxx*. Pro rozhraní .NET Framework 4.6 a novějším má formulář 4.0.30319.42000.    

2. Až budete mít `Version` objektu, dotaz následujícím způsobem:

   - Pro hlavní verzi identifikátor (například *4* pro verzi 4.0), použijte <xref:System.Version.Major%2A?displayProperty=nameWithType> vlastnost.

   - Nezletilý release identifikátor (například *0* pro verzi 4.0), použijte <xref:System.Version.Minor%2A?displayProperty=nameWithType> vlastnost.

   - Pro celého řetězci verze (například *4.0.30319.18010*), použijte <xref:System.Version.ToString%2A?displayProperty=nameWithType> metody. Tato metoda vrátí jednu hodnotu, která odpovídá verzi modulu runtime, který se spouští kód. Nevrací se verze sestavení ani jiné verze modulu runtime, které mohou být nainstalovány v počítači.



V následujícím příkladu <xref:System.Environment.Version%2A?displayProperty=nameWithType> vlastnost pro načtení informací o verzi modulu CLR:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>Viz také:

- [Postupy: Zjištění nainstalovaných aktualizací rozhraní .NET Framework](how-to-determine-which-net-framework-updates-are-installed.md)
- [Instalace rozhraní .NET Framework pro vývojáře](../install/guide-for-developers.md)
- [Rozhraní .NET framework verze a závislosti](versions-and-dependencies.md)
