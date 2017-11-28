---
title: ".NET core rozhraní příkazového řádku (CLI) nástroje"
description: "Přehled funkcí a nástrojů .NET Core rozhraní příkazového řádku (CLI)."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: d66738593a1542affc956e08bbc38a3b2b1841b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="c691e-103">.NET core nástrojů rozhraní příkazového řádku (CLI)</span><span class="sxs-lookup"><span data-stu-id="c691e-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="c691e-104">Rozhraní .NET Core příkazového řádku (CLI) je nová sada nástrojů a platformy pro vývoj aplikací .NET.</span><span class="sxs-lookup"><span data-stu-id="c691e-104">The .NET Core command-line interface (CLI) is a new cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="c691e-105">Rozhraní příkazového řádku je foundation, při které vyšší úrovně nástroje, jako je, přesuňte integrované vývojové prostředí (integrovaného vývojového prostředí), editory a orchestrators sestavení.</span><span class="sxs-lookup"><span data-stu-id="c691e-105">The CLI is a foundation upon which higher-level tools, such as Integrated Development Environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="c691e-106">Instalace</span><span class="sxs-lookup"><span data-stu-id="c691e-106">Installation</span></span>

<span data-ttu-id="c691e-107">Buď použijte nativní instalační programy nebo použít skripty prostředí instalace:</span><span class="sxs-lookup"><span data-stu-id="c691e-107">Either use the native installers or use the installation shell scripts:</span></span>

* <span data-ttu-id="c691e-108">Nativní instalační programy se primárně používají na počítačích pro vývojáře a použití každé podporované platformy nativní nainstalujte mechanismus, například bázi DEB balíčků na Ubuntu nebo MSI sady v systému Windows.</span><span class="sxs-lookup"><span data-stu-id="c691e-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="c691e-109">Tyto instalační programy instalace a konfigurace prostředí pro okamžitou používá vývojář ale vyžadují oprávnění správce na počítači.</span><span class="sxs-lookup"><span data-stu-id="c691e-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="c691e-110">Můžete zobrazit v pokynech k instalaci v [Průvodce instalací .NET Core](https://aka.ms/dotnetcoregs).</span><span class="sxs-lookup"><span data-stu-id="c691e-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
* <span data-ttu-id="c691e-111">Skripty prostředí se primárně používají pro nastavení servery sestavení nebo pokud chcete nainstalovat nástroje bez oprávnění správce.</span><span class="sxs-lookup"><span data-stu-id="c691e-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="c691e-112">Nainstalujte skripty neinstalujte požadavky na počítač, který musí být nainstalován ručně.</span><span class="sxs-lookup"><span data-stu-id="c691e-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="c691e-113">Další informace najdete v tématu [instalaci skriptu referenční téma](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="c691e-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="c691e-114">Informace o tom, jak nastavit rozhraní příkazového řádku na vašem serveru sestavení průběžnou integraci (CI) najdete v tématu [pomocí rozhraní .NET Core SDK a nástrojů v nepřetržité integrace konfigurace](using-ci-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="c691e-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="c691e-115">Ve výchozím nastavení nainstaluje rozhraní příkazového řádku (SxS) způsobem vedle sebe, tak mohou existovat vedle sebe více verzí nástrojů příkazového řádku na jednom počítači.</span><span class="sxs-lookup"><span data-stu-id="c691e-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="c691e-116">Určení, které verze se má použít na počítači, kde je nainstalováno více verzí je vysvětlené podrobněji v [ovladač](#driver) části.</span><span class="sxs-lookup"><span data-stu-id="c691e-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="c691e-117">Rozhraní příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="c691e-117">CLI commands</span></span>

<span data-ttu-id="c691e-118">Ve výchozím nastavení instalují se následující příkazy:</span><span class="sxs-lookup"><span data-stu-id="c691e-118">The following commands are installed by default:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c691e-119">.NET pro základní 2.x</span><span class="sxs-lookup"><span data-stu-id="c691e-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="c691e-120">**Základní příkazy**</span><span class="sxs-lookup"><span data-stu-id="c691e-120">**Basic commands**</span></span>

* [<span data-ttu-id="c691e-121">Nový</span><span class="sxs-lookup"><span data-stu-id="c691e-121">new</span></span>](dotnet-new.md)
* [<span data-ttu-id="c691e-122">obnovení</span><span class="sxs-lookup"><span data-stu-id="c691e-122">restore</span></span>](dotnet-restore.md)
* [<span data-ttu-id="c691e-123">sestavení</span><span class="sxs-lookup"><span data-stu-id="c691e-123">build</span></span>](dotnet-build.md)
* [<span data-ttu-id="c691e-124">publikování</span><span class="sxs-lookup"><span data-stu-id="c691e-124">publish</span></span>](dotnet-publish.md)
* [<span data-ttu-id="c691e-125">Spustit</span><span class="sxs-lookup"><span data-stu-id="c691e-125">run</span></span>](dotnet-run.md)
* [<span data-ttu-id="c691e-126">Test</span><span class="sxs-lookup"><span data-stu-id="c691e-126">test</span></span>](dotnet-test.md)
* [<span data-ttu-id="c691e-127">vstest</span><span class="sxs-lookup"><span data-stu-id="c691e-127">vstest</span></span>](dotnet-vstest.md)
* [<span data-ttu-id="c691e-128">Pack</span><span class="sxs-lookup"><span data-stu-id="c691e-128">pack</span></span>](dotnet-pack.md)
* [<span data-ttu-id="c691e-129">migrace</span><span class="sxs-lookup"><span data-stu-id="c691e-129">migrate</span></span>](dotnet-migrate.md)
* [<span data-ttu-id="c691e-130">Vyčištění</span><span class="sxs-lookup"><span data-stu-id="c691e-130">clean</span></span>](dotnet-clean.md)
* [<span data-ttu-id="c691e-131">SLN –</span><span class="sxs-lookup"><span data-stu-id="c691e-131">sln</span></span>](dotnet-sln.md)
* [<span data-ttu-id="c691e-132">Pomoc</span><span class="sxs-lookup"><span data-stu-id="c691e-132">help</span></span>](dotnet-help.md)
* [<span data-ttu-id="c691e-133">úložiště</span><span class="sxs-lookup"><span data-stu-id="c691e-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="c691e-134">**Příkazy Úpravy projektu**</span><span class="sxs-lookup"><span data-stu-id="c691e-134">**Project modification commands**</span></span>

* [<span data-ttu-id="c691e-135">Přidání balíčku</span><span class="sxs-lookup"><span data-stu-id="c691e-135">add package</span></span>](dotnet-add-package.md)
* [<span data-ttu-id="c691e-136">Přidání odkazu</span><span class="sxs-lookup"><span data-stu-id="c691e-136">add reference</span></span>](dotnet-add-reference.md)
* [<span data-ttu-id="c691e-137">Odebrání balíčku</span><span class="sxs-lookup"><span data-stu-id="c691e-137">remove package</span></span>](dotnet-remove-package.md)
* [<span data-ttu-id="c691e-138">Odebrat odkaz</span><span class="sxs-lookup"><span data-stu-id="c691e-138">remove reference</span></span>](dotnet-remove-reference.md)
* [<span data-ttu-id="c691e-139">odkaz na seznamu</span><span class="sxs-lookup"><span data-stu-id="c691e-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="c691e-140">**Pokročilé příkazy**</span><span class="sxs-lookup"><span data-stu-id="c691e-140">**Advanced commands**</span></span>

* [<span data-ttu-id="c691e-141">odstranění nuget</span><span class="sxs-lookup"><span data-stu-id="c691e-141">nuget delete</span></span>](dotnet-nuget-delete.md)
* [<span data-ttu-id="c691e-142">místní hodnoty – nuget</span><span class="sxs-lookup"><span data-stu-id="c691e-142">nuget locals</span></span>](dotnet-nuget-locals.md)
* [<span data-ttu-id="c691e-143">nabízená nuget</span><span class="sxs-lookup"><span data-stu-id="c691e-143">nuget push</span></span>](dotnet-nuget-push.md)
* [<span data-ttu-id="c691e-144">nástroje MSBuild</span><span class="sxs-lookup"><span data-stu-id="c691e-144">msbuild</span></span>](dotnet-msbuild.md)
* [<span data-ttu-id="c691e-145">Instalační skript pro DotNet.</span><span class="sxs-lookup"><span data-stu-id="c691e-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c691e-146">.NET pro základní 1.x</span><span class="sxs-lookup"><span data-stu-id="c691e-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c691e-147">**Základní příkazy**</span><span class="sxs-lookup"><span data-stu-id="c691e-147">**Basic commands**</span></span>

* [<span data-ttu-id="c691e-148">Nový</span><span class="sxs-lookup"><span data-stu-id="c691e-148">new</span></span>](dotnet-new.md)
* [<span data-ttu-id="c691e-149">obnovení</span><span class="sxs-lookup"><span data-stu-id="c691e-149">restore</span></span>](dotnet-restore.md)
* [<span data-ttu-id="c691e-150">sestavení</span><span class="sxs-lookup"><span data-stu-id="c691e-150">build</span></span>](dotnet-build.md)
* [<span data-ttu-id="c691e-151">publikování</span><span class="sxs-lookup"><span data-stu-id="c691e-151">publish</span></span>](dotnet-publish.md)
* [<span data-ttu-id="c691e-152">Spustit</span><span class="sxs-lookup"><span data-stu-id="c691e-152">run</span></span>](dotnet-run.md)
* [<span data-ttu-id="c691e-153">Test</span><span class="sxs-lookup"><span data-stu-id="c691e-153">test</span></span>](dotnet-test.md)
* [<span data-ttu-id="c691e-154">vstest</span><span class="sxs-lookup"><span data-stu-id="c691e-154">vstest</span></span>](dotnet-vstest.md)
* [<span data-ttu-id="c691e-155">Pack</span><span class="sxs-lookup"><span data-stu-id="c691e-155">pack</span></span>](dotnet-pack.md)
* [<span data-ttu-id="c691e-156">migrace</span><span class="sxs-lookup"><span data-stu-id="c691e-156">migrate</span></span>](dotnet-migrate.md)
* [<span data-ttu-id="c691e-157">Vyčištění</span><span class="sxs-lookup"><span data-stu-id="c691e-157">clean</span></span>](dotnet-clean.md)
* [<span data-ttu-id="c691e-158">SLN –</span><span class="sxs-lookup"><span data-stu-id="c691e-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="c691e-159">**Příkazy Úpravy projektu**</span><span class="sxs-lookup"><span data-stu-id="c691e-159">**Project modification commands**</span></span>

* [<span data-ttu-id="c691e-160">Přidání balíčku</span><span class="sxs-lookup"><span data-stu-id="c691e-160">add package</span></span>](dotnet-add-package.md)
* [<span data-ttu-id="c691e-161">Přidání odkazu</span><span class="sxs-lookup"><span data-stu-id="c691e-161">add reference</span></span>](dotnet-add-reference.md)
* [<span data-ttu-id="c691e-162">Odebrání balíčku</span><span class="sxs-lookup"><span data-stu-id="c691e-162">remove package</span></span>](dotnet-remove-package.md)
* [<span data-ttu-id="c691e-163">Odebrat odkaz</span><span class="sxs-lookup"><span data-stu-id="c691e-163">remove reference</span></span>](dotnet-remove-reference.md)
* [<span data-ttu-id="c691e-164">odkaz na seznamu</span><span class="sxs-lookup"><span data-stu-id="c691e-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="c691e-165">**Pokročilé příkazy**</span><span class="sxs-lookup"><span data-stu-id="c691e-165">**Advanced commands**</span></span>

* [<span data-ttu-id="c691e-166">odstranění nuget</span><span class="sxs-lookup"><span data-stu-id="c691e-166">nuget delete</span></span>](dotnet-nuget-delete.md)
* [<span data-ttu-id="c691e-167">místní hodnoty – nuget</span><span class="sxs-lookup"><span data-stu-id="c691e-167">nuget locals</span></span>](dotnet-nuget-locals.md)
* [<span data-ttu-id="c691e-168">nabízená nuget</span><span class="sxs-lookup"><span data-stu-id="c691e-168">nuget push</span></span>](dotnet-nuget-push.md)
* [<span data-ttu-id="c691e-169">nástroje MSBuild</span><span class="sxs-lookup"><span data-stu-id="c691e-169">msbuild</span></span>](dotnet-msbuild.md)
* [<span data-ttu-id="c691e-170">Instalační skript pro DotNet.</span><span class="sxs-lookup"><span data-stu-id="c691e-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="c691e-171">Rozhraní příkazového řádku přijme model rozšiřitelnosti, které vám umožní určit dalších nástrojů pro projekty.</span><span class="sxs-lookup"><span data-stu-id="c691e-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="c691e-172">Další informace najdete v tématu [model rozšiřitelnosti .NET Core rozhraní příkazového řádku](extensibility.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="c691e-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="c691e-173">Příkaz struktura</span><span class="sxs-lookup"><span data-stu-id="c691e-173">Command structure</span></span>

<span data-ttu-id="c691e-174">Struktura rozhraní příkazového řádku příkaz se skládá z [ovladače ("dotnet")](#driver), [příkazu (nebo "akce")](#command-verb)a případně příkaz [argumenty](#arguments) a [možnosti](#options).</span><span class="sxs-lookup"><span data-stu-id="c691e-174">CLI command structure consists of the [the driver ("dotnet")](#driver), [the command (or "verb")](#command-verb), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="c691e-175">Zobrazí tento vzor většinu operací rozhraní příkazového řádku, jako je například vytváření novou konzolovou aplikaci a spuštění z příkazového řádku jako následující příkazy, zobrazit, když je proveden z adresáře, s názvem *my_app*:</span><span class="sxs-lookup"><span data-stu-id="c691e-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c691e-176">.NET pro základní 2.x</span><span class="sxs-lookup"><span data-stu-id="c691e-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```console
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c691e-177">.NET pro základní 1.x</span><span class="sxs-lookup"><span data-stu-id="c691e-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```


---

### <a name="driver"></a><span data-ttu-id="c691e-178">Ovladače</span><span class="sxs-lookup"><span data-stu-id="c691e-178">Driver</span></span>

<span data-ttu-id="c691e-179">Ovladač jmenuje [dotnet](dotnet.md) a má dva odpovědnosti, buď spuštěná [framework závislé aplikace](../deploying/index.md) nebo spuštěním příkazu.</span><span class="sxs-lookup"><span data-stu-id="c691e-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> <span data-ttu-id="c691e-180">Pouze `dotnet` se používá bez příkaz se, pokud se používá ke spuštění aplikace.</span><span class="sxs-lookup"><span data-stu-id="c691e-180">The only time `dotnet` is used without a command is when it's used to start an application.</span></span>

<span data-ttu-id="c691e-181">Chcete spustit framework závislé aplikace, zadejte aplikaci po ovladače, například `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="c691e-181">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="c691e-182">Při provádění příkazu ze složky, které se nachází aplikace DLL, stačí spustit `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="c691e-182">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span>

<span data-ttu-id="c691e-183">Když zadáte příkaz, který má ovladače, `dotnet.exe` spustí se proces spuštění příkazu rozhraní příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="c691e-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="c691e-184">Nejprve ovladač Určuje verzi sady SDK k použití.</span><span class="sxs-lookup"><span data-stu-id="c691e-184">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="c691e-185">Pokud verze není zadané v příkazu Možnosti, používá ovladač na nejnovější dostupnou verzi.</span><span class="sxs-lookup"><span data-stu-id="c691e-185">If the version isn't specified in the command options, the driver uses the latest version available.</span></span> <span data-ttu-id="c691e-186">K určení verze než poslední instalované verzi, použijte `--fx-version <VERSION>` možnost (najdete v článku [dotnet. příkaz](dotnet.md) odkaz).</span><span class="sxs-lookup"><span data-stu-id="c691e-186">To specify a version other than the latest installed version, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span> <span data-ttu-id="c691e-187">Jakmile je určena verze sady SDK, ovladač provede příkaz.</span><span class="sxs-lookup"><span data-stu-id="c691e-187">Once the SDK version is determined, the driver executes the command.</span></span>

### <a name="command-verb"></a><span data-ttu-id="c691e-188">Příkaz ("akce")</span><span class="sxs-lookup"><span data-stu-id="c691e-188">Command ("verb")</span></span>

<span data-ttu-id="c691e-189">Příkaz (nebo "akce") je jednoduše příkaz, který provádí akce.</span><span class="sxs-lookup"><span data-stu-id="c691e-189">The command (or "verb") is simply a command that performs an action.</span></span> <span data-ttu-id="c691e-190">Například `dotnet build` sestavení vašeho kódu.</span><span class="sxs-lookup"><span data-stu-id="c691e-190">For example, `dotnet build` builds your code.</span></span> <span data-ttu-id="c691e-191">`dotnet publish`publikuje vašeho kódu.</span><span class="sxs-lookup"><span data-stu-id="c691e-191">`dotnet publish` publishes your code.</span></span> <span data-ttu-id="c691e-192">Příkazy jsou implementované jako aplikace konzoly pomocí `dotnet {verb}` konvence.</span><span class="sxs-lookup"><span data-stu-id="c691e-192">The commands are implemented as a console application using a `dotnet {verb}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="c691e-193">Arguments</span><span class="sxs-lookup"><span data-stu-id="c691e-193">Arguments</span></span>

<span data-ttu-id="c691e-194">Argumenty, které můžete předat na příkazovém řádku jsou argumenty pro příkaz vyvolat.</span><span class="sxs-lookup"><span data-stu-id="c691e-194">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="c691e-195">Například při spuštění `dotnet publish my_app.csproj`, `my_app.csproj` argument určuje projekt, který má publikovat a je předána `publish` příkaz.</span><span class="sxs-lookup"><span data-stu-id="c691e-195">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="c691e-196">Možnosti</span><span class="sxs-lookup"><span data-stu-id="c691e-196">Options</span></span>

<span data-ttu-id="c691e-197">Možnosti, které můžete předat na příkazovém řádku jsou možnosti k vyvolání příkazu.</span><span class="sxs-lookup"><span data-stu-id="c691e-197">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="c691e-198">Například při spuštění `dotnet publish --output /build_output`, `--output` možnost a jeho hodnota se budou předávat `publish` příkaz.</span><span class="sxs-lookup"><span data-stu-id="c691e-198">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span> 

## <a name="migration-from-projectjson"></a><span data-ttu-id="c691e-199">Migrace ze souboru project.json</span><span class="sxs-lookup"><span data-stu-id="c691e-199">Migration from project.json</span></span>

<span data-ttu-id="c691e-200">Pokud jste použili Preview 2 nástrojů k vytvoření *project.json*– na základě projekty, najdete [dotnet migrovat](dotnet-migrate.md) tématu informace o migraci projektu nástroje MSBuild /*.csproj*pro použití s verzí nástroje.</span><span class="sxs-lookup"><span data-stu-id="c691e-200">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="c691e-201">Pro .NET Core projekty vytvořené před vydáním nástrojů Preview 2, buď ručně aktualizovat projektu následující pokyny v [migrace z DNX na .NET Core rozhraní příkazového řádku (project.json)](../migration/from-dnx.md) a pak použijte `dotnet migrate` nebo přímo upgrade vašich projektů.</span><span class="sxs-lookup"><span data-stu-id="c691e-201">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="c691e-202">Viz také</span><span class="sxs-lookup"><span data-stu-id="c691e-202">See also</span></span>

 [<span data-ttu-id="c691e-203">DotNet nebo rozhraní příkazového řádku úložiště GitHub</span><span class="sxs-lookup"><span data-stu-id="c691e-203">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)  
 [<span data-ttu-id="c691e-204">Průvodce instalací .NET core</span><span class="sxs-lookup"><span data-stu-id="c691e-204">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)  