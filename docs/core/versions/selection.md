---
title: Výběr verze .NET core
description: Zjistěte, jak .NET Core vyhledá a vybere verze modulu runtime pro váš program.
author: billwagner
ms.author: wiwagn
ms.date: 06/27/2018
ms.openlocfilehash: d1b885ebbade4736d5f592d1dc1d4ba25a321a16
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874467"
---
# <a name="net-core-version-selection"></a>Výběr verze .NET core

[!INCLUDE [topic-appliesto-net-core-2plus](../../../includes/topic-appliesto-net-core-2plus.md)]

Tento článek vysvětluje zásady slouží k výběru verze nástroje .NET Core, sady SDK a modulu runtime. Tyto zásady umožňují rovnováhu mezi spuštěných aplikací, které usnadňují používání zadanou verzí a povolení upgradu počítače pro vývojáře a koncový uživatel. Tyto zásady postupujte takto:

- Snadné a efektivní nasazení .NET Core, včetně aktualizací zabezpečení a spolehlivost.
- Použijte nejnovější nástroje a příkazy, které jsou nezávislé na cílový modul runtime.

Nastane, výběr verze:

- Při spuštění příkazu k sadě SDK [používá nejnovější verze sady sdk](#the-sdk-uses-the-latest-installed-version).
- Při sestavování sestavení, [cílové rozhraní framework monikery definují čas sestavení rozhraní API](#target-framework-monikers-define-build-time-apis).
- Když spustíte aplikaci .NET Core, [cílové rozhraní framework závislé aplikace posunout vpřed](#framework-dependent-apps-roll-forward).
- Při publikování je samostatná aplikace, [samostatná nasazení zahrnovat vybraný modul runtime](#self-contained-deployments-include-the-selected-runtime).

Zbývající část tohoto dokumentu zkontroluje tyto čtyři scénáře.

## <a name="the-sdk-uses-the-latest-installed-version"></a>Sada SDK používá nejnovější verze

Zahrnuje následující příkazy SDK `dotnet new`, `dotnet build` nebo `dotnet run`. `dotnet` Rozhraní příkazového řádku, musíte zvolit verzi sady SDK pro kterýkoli příkaz. Rozhraní příkazového řádku .NET Core využívá nejnovější sadu SDK ve výchozím nastavení nainstalovaná na počítači. .NET Core SDK v2.1.301 budete používat při instalaci, i v případě, že projekt, že pracujete s cílí .NET Core Runtime 2.0. Všimněte si, že to platí pro verze preview, jakož i vydané verze. Při cílení na dřívější verze modulu runtime .NET Core můžete využít výhod nejnovějších funkcí sady SDK a vylepšení. Můžete cílit více verzí modulu runtime .NET Core v různých projektech pomocí stejných nástrojů sady SDK pro všechny projekty.

Ve výjimečných případech budete muset použít starší verzi sady SDK. Zadejte v této verzi [ *global.json* souboru](../tools/global-json.md). Zásady "použít nejnovější" znamená, že používejte pouze *global.json* k určení sady .NET Core SDK verze starší než nejnovější verze.

*Global.JSON* může být umístěna kdekoli v hierarchii souborů. Rozhraní příkazového řádku se vyhledá směrem nahoru z adresáře projektu pro první *global.json* , které nalezne. Můžete řídit projekty, které daném *global.json* se vztahuje na příslušné místo v systému souborů. Vyhledá v .NET CLI *global.json* souboru zavádět postupně navigace cestu nahoru z aktuálního pracovního adresáře. První *global.json* nebyl nalezen soubor Určuje verzi použít. Pokud je nainstalovaná tato verze, se používá tuto verzi. Pokud v zadané sadě SDK *global.json* nenajde, rozhraní příkazového řádku .NET posunete na nainstalovánu nejnovější sadu SDK. To je stejný jako výchozí chování, když ne *global.json* soubor se nenašel.

Následující příklad ukazuje *global.json* syntaxi:

``` json
{
  "sdk": {
    "version": "2.0.0"
  }
}
```

Proces pro výběr ze sady SDK verze je:

1. `dotnet` vyhledává *global.json* souboru zavádět postupně navigace cestu nahoru z aktuálního pracovního adresáře zpětného.
1. `dotnet` používá sadu SDK, zadané v prvním *global.json* nalezen.
1. `dotnet` využívá nejnovější nainstalované sady SDK, pokud žádné *global.json* nenajde.

Další informace o výběru verzi sady SDK v [pravidel](../tools/global-json.md) tématu na *global.json*.

## <a name="target-framework-monikers-define-build-time-apis"></a>Cílové rozhraní Framework Monikery definují čas sestavení rozhraní API

Sestavit projekt před definované v rozhraní API **Moniker cílového rozhraní** (TFM). Můžete zadat [Cílová architektura](../../standard/frameworks.md) v souboru projektu. Nastavte `TargetFramework` prvku v souboru projektu, jak je znázorněno v následujícím příkladu:

``` xml
<TargetFramework>netcoreapp2.0</TargetFramework>
```

Může sestavení projektu s více Tfm. Nastavení více cílových rozhraní je běžné knihovny ale můžete udělat s aplikacemi stejně. Můžete zadat `TargetFrameworks` vlastnosti (množném čísle z `TargetFramework`). Cílové architektury jsou oddělený středníkem jak je znázorněno v následujícím příkladu:

``` xml
<TargetFrameworks>netcoreapp2.0;net47</TargetFrameworks>
```

Daný sada SDK podporuje fixní sadu platforem, které budou omezené na modul runtime, který je dodáván s cílovou architekturu. Například, .NET Core 2.0 SDK zahrnuje modul runtime .NET Core 2.0, což je implementace z `netcoreapp2.0` cílovou architekturu. Sada .NET Core 2.0 SDK podporuje `netcoreapp1.0`, `netcoreapp1.1`, a `netcoreapp2.0` , ale ne `netcoreapp2.1` (nebo vyšší). Nainstalovat .NET Core SDK 2.1 k sestavení pro `netcoreapp2.1`.

Cílové rozhraní .NET standard jsou omezené i pro cílové prostředí modulu runtime, který se dodává se sadou SDK. Sada .NET Core 2.0 SDK je omezené na `netstandard2.0`.

## <a name="framework-dependent-apps-roll-forward"></a>Dopředné posunutí závisí na architektuře aplikací

Spuštění aplikace ze zdroje s [ `dotnet run` ](../tools/dotnet-run.md). `dotnet run` jak sestaví a spustí aplikaci. `dotnet` Spustitelný soubor je **hostitele** pro aplikaci ve vývojovém prostředí.

Hostitel vybere nejnovější verze opravy na počítači nainstalovaný. Například, pokud jste zadali `netcoreapp2.0` v souboru projektu a `2.0.4` nejnovější modul .NET runtime nainstalovaný, je `2.0.4` modul runtime se používá.

Pokud nejsou přípustné `2.0.*` nalezena verze nový `2.*` je použita verze. Například, pokud jste zadali `netcoreapp2.0` a pouze `2.1.0` je nainstalovaný, spuštění aplikace pomocí `2.1.0` modulu runtime. Toto chování se označuje jako "podverze vpřed." Nižší verze také nebude považovat za. Pokud je nainstalován žádný přijatelný modul runtime, aplikace se nespustí.

Několik příkladů použití ukazují chování:

- 2.0.4 je povinný. 2.0.5 je nejvyšší nainstalovaná verze opravy. 2.0.5 se používá.
- 2.0.4 je povinný. 2.0 č. * nainstalovaných verzí rozhraní. 1.1.1 je nejvyšší modul runtime nainstalovaný. Zobrazí se chybová zpráva.
- 2.0.4 je povinný. 2.0.0 je nejvyšší verze instalované. Zobrazí se chybová zpráva.
- 2.0.4 je povinný. 2.0 č. * nainstalovaných verzí rozhraní. 2.2.2 je nainstalovaná nejvyšší modul runtime verze 2.x. 2.2.2 se používá.
- 2.0.4 je povinný. Žádné verze 2.x nainstalují. 3.0.0 (je nainstalovaná není aktuálně dostupná verze). Zobrazí se chybová zpráva.

Podverze vpřed má jeden vedlejší efekt, který může mít vliv na koncové uživatele. Vezměte v úvahu následující scénář:

- 2.0.4 je povinný. 2.0 č. * nainstalovaných verzí rozhraní. 2.2.2 je nainstalovaný. 2.2.2 se používá.
- 2.0.5 je novější. pro následující aplikace spustí, ne 2.2.2 použije 2.0.5. Nejnovější opravy požadovaný dílčí verze je upřednostňována před vyšší podverze.
- Je možné, že 2.0.5 a 2.2.2 chovají odlišně, zejména pro scénáře, jako jsou serializace binární data.

## <a name="self-contained-deployments-include-the-selected-runtime"></a>Samostatná nasazení zahrnovat vybraný modul runtime

Můžete publikovat aplikaci jako [ **samostatná distribuce**](../deploying/index.md#self-contained-deployments-scd). Tento postup obsahuje ureitou modul runtime .NET Core a knihovny se zmírněními hrozeb vaší aplikace. Samostatná nasazení nemáte závislosti na prostředí runtime. Vyvolá se při publikování, nikoli čas spuštění výběr verze modulu runtime.

Proces publikování se vybrala nejnovější verze opravy řady daného modulu runtime. Například `dotnet publish` vybere .NET Core 2.0.4, pokud je nejnovější verzi opravy řady modulu runtime .NET Core 2.0. Cílová architektura (včetně nejnovějších oprav nainstalovaných zabezpečovacích) je součástí balíčku aplikace.

Jedná se o chybu, pokud není splněná minimální verze zadané pro aplikaci. `dotnet publish` vytvoří vazbu na nejnovější verzi opravy modulu runtime (v rámci dané vlastnosti major.minor verze rodiny). `dotnet publish` nepodporuje sémantika vpřed `dotnet run`. Další informace o opravy a samostatná nasazení, najdete v článku na [výběr opravy modulu runtime](../deploying/runtime-patch-selection.md) při nasazování aplikací .NET Core.

Samostatná nasazení může vyžadovat oprav konkrétní verze. Runtime minimální verzi opravy (na vyšší nebo nižší verze) v souboru projektu, můžete přepsat, jak je znázorněno v následujícím příkladu:

``` xml
<RuntimeFrameworkVersion>2.0.4</RuntimeFrameworkVersion>
```

`RuntimeFrameworkVersion` Elementu přepíše výchozí zásada verze. Pro samostatné nasazení `RuntimeFrameworkVersion` Určuje *přesné* framework verze modulu runtime. Pro závislé aplikace rozhraní framework `RuntimeFrameworkVersion` Určuje *minimální* požadovaná verze rozhraní framework.