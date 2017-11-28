---
title: "Představení aplikací spouštěných jako služby systému Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ServiceController
helpviewer_keywords:
- Windows Service applications, deploying
- OnStop method
- OnPause method
- services, about services
- Service class, Windows Service applications
- framework services, creating services
- ServiceController components, about Windows services
- Win32OwnProcess service type
- services, lifetime
- OnContinue method
- Windows Service applications, about Windows Service applications
- services, states
- service states
- WaitForStatus method
- Win32ShareProcess service type
- Windows Service applications, lifetime
ms.assetid: 1b1b5e67-3ff3-40c0-8154-322cfd6ef0ae
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: d24daf5520c7bfe74c09abc24a4260266e5b9c1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-windows-service-applications"></a><span data-ttu-id="58a8c-102">Představení aplikací spouštěných jako služby systému Windows</span><span class="sxs-lookup"><span data-stu-id="58a8c-102">Introduction to Windows Service Applications</span></span>
<span data-ttu-id="58a8c-103">Služby Microsoft Windows, dříve označovaná jako služba NT umožňují vytvářet dlouho běžící spustitelný soubor aplikace, které běží ve vlastní relací v systému Windows.</span><span class="sxs-lookup"><span data-stu-id="58a8c-103">Microsoft Windows services, formerly known as NT services, enable you to create long-running executable applications that run in their own Windows sessions.</span></span> <span data-ttu-id="58a8c-104">Tyto služby můžete být automaticky spustí při spuštění počítače, můžete pozastavit a restartování a nezobrazuje žádné uživatelské rozhraní.</span><span class="sxs-lookup"><span data-stu-id="58a8c-104">These services can be automatically started when the computer boots, can be paused and restarted, and do not show any user interface.</span></span> <span data-ttu-id="58a8c-105">Tyto funkce usnadnění služby ideální pro použití na serveru nebo kdykoli budete potřebovat dlouhodobé funkce, které nebudou v konfliktu s jinými uživateli, kteří pracují na stejném počítači.</span><span class="sxs-lookup"><span data-stu-id="58a8c-105">These features make services ideal for use on a server or whenever you need long-running functionality that does not interfere with other users who are working on the same computer.</span></span> <span data-ttu-id="58a8c-106">Služby můžete také spustit v kontextu zabezpečení konkrétní uživatelský účet, který se liší od přihlášeného uživatele nebo výchozího účtu.</span><span class="sxs-lookup"><span data-stu-id="58a8c-106">You can also run services in the security context of a specific user account that is different from the logged-on user or the default computer account.</span></span> <span data-ttu-id="58a8c-107">Další informace o službách a relace systému Windows naleznete v dokumentaci k Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="58a8c-107">For more information about services and Windows sessions, see the Windows SDK documentation.</span></span>  
  
 <span data-ttu-id="58a8c-108">Služby můžete snadno vytvořit tak, že vytvoříte aplikaci, která je nainstalován jako služba.</span><span class="sxs-lookup"><span data-stu-id="58a8c-108">You can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="58a8c-109">Předpokládejme například, že chcete monitorovat data čítače výkonu a reagovat na prahové hodnoty.</span><span class="sxs-lookup"><span data-stu-id="58a8c-109">For example, suppose you want to monitor performance counter data and react to threshold values.</span></span> <span data-ttu-id="58a8c-110">Můžete psát aplikace služby systému Windows, která naslouchá na data čítače výkonu, nasaďte aplikaci a zahájit shromažďování a analýza dat.</span><span class="sxs-lookup"><span data-stu-id="58a8c-110">You could write a Windows Service application that listens to the performance counter data, deploy the application, and begin collecting and analyzing data.</span></span>  
  
 <span data-ttu-id="58a8c-111">Vytvoření služby jako projekt sady Microsoft Visual Studio, definování kód v něm, který určuje, jaké příkazy lze odesílat a jaké akce by měla být provedena při přijetí těchto příkazů.</span><span class="sxs-lookup"><span data-stu-id="58a8c-111">You create your service as a Microsoft Visual Studio project, defining code within it that controls what commands can be sent to the service and what actions should be taken when those commands are received.</span></span> <span data-ttu-id="58a8c-112">Příkazy, které lze odeslat buď do služby zahrnují spuštění, pozastavení, obnovení a ukončení služby; Můžete také provést vlastní příkazy.</span><span class="sxs-lookup"><span data-stu-id="58a8c-112">Commands that can be sent to a service include starting, pausing, resuming, and stopping the service; you can also execute custom commands.</span></span>  
  
 <span data-ttu-id="58a8c-113">Po vytvoření a sestavení aplikace, můžete ho nainstalovat spuštěním nástroje příkazového řádku InstallUtil.exe a předání cesta ke spustitelnému souboru služby.</span><span class="sxs-lookup"><span data-stu-id="58a8c-113">After you create and build the application, you can install it by running the command-line utility InstallUtil.exe and passing the path to the service's executable file.</span></span> <span data-ttu-id="58a8c-114">Pak můžete použít **správci řízení služeb** pro spuštění, zastavení, pozastavení, obnovení a konfiguraci služby.</span><span class="sxs-lookup"><span data-stu-id="58a8c-114">You can then use the **Services Control Manager** to start, stop, pause, resume, and configure your service.</span></span> <span data-ttu-id="58a8c-115">Mohou také provádět mnoho z těchto úloh v **služby** uzlu v **Průzkumníka serveru** nebo pomocí <xref:System.ServiceProcess.ServiceController> – třída.</span><span class="sxs-lookup"><span data-stu-id="58a8c-115">You can also accomplish many of these same tasks in the **Services** node in **Server Explorer** or by using the <xref:System.ServiceProcess.ServiceController> class.</span></span>  
  
## <a name="service-applications-vs-other-visual-studio-applications"></a><span data-ttu-id="58a8c-116">Aplikace služby vs. Ostatní aplikace Visual Studio</span><span class="sxs-lookup"><span data-stu-id="58a8c-116">Service Applications vs. Other Visual Studio Applications</span></span>  
 <span data-ttu-id="58a8c-117">Funkce aplikace služby jinak než mnoho dalších typů projektu několika způsoby:</span><span class="sxs-lookup"><span data-stu-id="58a8c-117">Service applications function differently from many other project types in several ways:</span></span>  
  
-   <span data-ttu-id="58a8c-118">Kompilované spustitelný soubor, který vytvoří projekt aplikace služby musí na serveru nainstalovány, před projektu, můžou fungovat smysluplný způsobem.</span><span class="sxs-lookup"><span data-stu-id="58a8c-118">The compiled executable file that a service application project creates must be installed on the server before the project can function in a meaningful way.</span></span> <span data-ttu-id="58a8c-119">Nelze ladění a spusťte aplikaci služby stisknutím klávesy F5 nebo F11; nelze spustit okamžitě služby nebo krok do jeho kódu.</span><span class="sxs-lookup"><span data-stu-id="58a8c-119">You cannot debug or run a service application by pressing F5 or F11; you cannot immediately run a service or step into its code.</span></span> <span data-ttu-id="58a8c-120">Místo toho musíte nainstalovat a spustit služby a pak připojit ladicí program k procesu služby.</span><span class="sxs-lookup"><span data-stu-id="58a8c-120">Instead, you must install and start your service, and then attach a debugger to the service's process.</span></span> <span data-ttu-id="58a8c-121">Další informace najdete v tématu [postupy: ladění aplikace služby systému Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md).</span><span class="sxs-lookup"><span data-stu-id="58a8c-121">For more information, see [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md).</span></span>  
  
-   <span data-ttu-id="58a8c-122">Na rozdíl od některé typy projektů musíte vytvořit instalace součásti pro aplikace služby.</span><span class="sxs-lookup"><span data-stu-id="58a8c-122">Unlike some types of projects, you must create installation components for service applications.</span></span> <span data-ttu-id="58a8c-123">Součásti instalace nainstalujte a zaregistrujte službu na serveru a vytvořit položku pro vaši službu pomocí ovládacího prvku Windows **správci řízení služeb**.</span><span class="sxs-lookup"><span data-stu-id="58a8c-123">The installation components install and register the service on the server and create an entry for your service with the Windows **Services Control Manager**.</span></span> <span data-ttu-id="58a8c-124">Další informace najdete v tématu [postupy: Přidání instalačních programů pro vaše aplikace služby](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="58a8c-124">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
-   <span data-ttu-id="58a8c-125">`Main` Metoda pro aplikaci služby musíte vydat příkaz spustit pro služby projektu obsahuje.</span><span class="sxs-lookup"><span data-stu-id="58a8c-125">The `Main` method for your service application must issue the Run command for the services your project contains.</span></span> <span data-ttu-id="58a8c-126">`Run` Metoda načte služby do **správci řízení služeb** na příslušném serveru.</span><span class="sxs-lookup"><span data-stu-id="58a8c-126">The `Run` method loads the services into the **Services Control Manager** on the appropriate server.</span></span> <span data-ttu-id="58a8c-127">Pokud použijete **služby systému Windows** šablony projektu, tato metoda je napsán pro můžete automaticky.</span><span class="sxs-lookup"><span data-stu-id="58a8c-127">If you use the **Windows Services** project template, this method is written for you automatically.</span></span> <span data-ttu-id="58a8c-128">Všimněte si, že načítání služby není totéž jako službu spustit.</span><span class="sxs-lookup"><span data-stu-id="58a8c-128">Note that loading a service is not the same thing as starting the service.</span></span> <span data-ttu-id="58a8c-129">Najdete v části "Service doba trvání" následující další informace.</span><span class="sxs-lookup"><span data-stu-id="58a8c-129">See "Service Lifetime" below for more information.</span></span>  
  
-   <span data-ttu-id="58a8c-130">Aplikace služby systému Windows spustit v jiné časové období stanice než interaktivní stanice přihlášeného uživatele.</span><span class="sxs-lookup"><span data-stu-id="58a8c-130">Windows Service applications run in a different window station than the interactive station of the logged-on user.</span></span> <span data-ttu-id="58a8c-131">Okno stanice je objekt zabezpečení, který obsahuje schránky, sadu globální atomů a skupiny klientů objektů.</span><span class="sxs-lookup"><span data-stu-id="58a8c-131">A window station is a secure object that contains a Clipboard, a set of global atoms, and a group of desktop objects.</span></span> <span data-ttu-id="58a8c-132">Protože stanice služby systému Windows není interaktivní stanice, dialogová okna vyvolané z v rámci Windows aplikace služby nedostupné a může způsobit, že váš program přestal reagovat.</span><span class="sxs-lookup"><span data-stu-id="58a8c-132">Because the station of the Windows service is not an interactive station, dialog boxes raised from within a Windows service application will not be seen and may cause your program to stop responding.</span></span> <span data-ttu-id="58a8c-133">Podobně chybové zprávy by měl být zaznamenají do protokolu událostí systému Windows a nikoli vyvolána v uživatelském rozhraní.</span><span class="sxs-lookup"><span data-stu-id="58a8c-133">Similarly, error messages should be logged in the Windows event log rather than raised in the user interface.</span></span>  
  
     <span data-ttu-id="58a8c-134">Třídy služeb systému Windows nepodporuje rozhraní .NET Framework nepodporují interakci s interaktivní stanice, který je uživatel přihlášen.</span><span class="sxs-lookup"><span data-stu-id="58a8c-134">The Windows service classes supported by the .NET Framework do not support interaction with interactive stations, that is, the logged-on user.</span></span> <span data-ttu-id="58a8c-135">Rozhraní .NET Framework také nezahrnuje tříd, které představují stanic a stolní počítače.</span><span class="sxs-lookup"><span data-stu-id="58a8c-135">The .NET Framework also does not include classes that represent stations and desktops.</span></span> <span data-ttu-id="58a8c-136">Pokud vaše služba systému Windows musí spolupracovat s ostatních stanic, potřebujete pro přístup k nespravovaného rozhraní API systému Windows.</span><span class="sxs-lookup"><span data-stu-id="58a8c-136">If your Windows service must interact with other stations, you will need to access the unmanaged Windows API.</span></span> <span data-ttu-id="58a8c-137">Další informace najdete v dokumentaci k Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="58a8c-137">For more information, see the Windows SDK documentation.</span></span>  
  
     <span data-ttu-id="58a8c-138">Interakce služby s uživateli nebo jiné stanice musí být navrženy pečlivě zahrnout scénáře takové protože neexistuje žádný přihlášený uživatel nebo uživatel s neočekávanou sadu objektů plochy Windows.</span><span class="sxs-lookup"><span data-stu-id="58a8c-138">The interaction of the Windows service with the user or other stations must be carefully designed to include scenarios such as there being no logged on user, or the user having an unexpected set of desktop objects.</span></span> <span data-ttu-id="58a8c-139">V některých případech může být vhodnější pro zápis aplikace systému Windows, který spouští pod kontrolou uživatele.</span><span class="sxs-lookup"><span data-stu-id="58a8c-139">In some cases, it may be more appropriate to write a Windows application that runs under the control of the user.</span></span>  
  
-   <span data-ttu-id="58a8c-140">Aplikace služby systému Windows spusťte v jejich vlastním kontextu zabezpečení a jsou spuštěny před se uživatel přihlásí do Windows počítače, na kterém jsou nainstalované.</span><span class="sxs-lookup"><span data-stu-id="58a8c-140">Windows service applications run in their own security context and are started before the user logs into the Windows computer on which they are installed.</span></span> <span data-ttu-id="58a8c-141">Měli pečlivě naplánovat jaké uživatelský účet, ke spouštění služby v rámci; služby spuštěné pod účtem system má další oprávnění a oprávnění než uživatelský účet.</span><span class="sxs-lookup"><span data-stu-id="58a8c-141">You should plan carefully what user account to run the service within; a service running under the system account has more permissions and privileges than a user account.</span></span>  
  
## <a name="service-lifetime"></a><span data-ttu-id="58a8c-142">Doba platnosti služby</span><span class="sxs-lookup"><span data-stu-id="58a8c-142">Service Lifetime</span></span>  
 <span data-ttu-id="58a8c-143">Služba projde několik interní stavy v celé jeho životnosti.</span><span class="sxs-lookup"><span data-stu-id="58a8c-143">A service goes through several internal states in its lifetime.</span></span> <span data-ttu-id="58a8c-144">Nejprve je služba nainstalována systému, na kterém se spustí.</span><span class="sxs-lookup"><span data-stu-id="58a8c-144">First, the service is installed onto the system on which it will run.</span></span> <span data-ttu-id="58a8c-145">Tento proces se spustí instalační služby pro projekt služby a načte službu do **správci řízení služeb** pro tento počítač.</span><span class="sxs-lookup"><span data-stu-id="58a8c-145">This process executes the installers for the service project and loads the service into the **Services Control Manager** for that computer.</span></span> <span data-ttu-id="58a8c-146">**Správci řízení služeb** je centrální nástroj obsažené v systému Windows ke správě služeb.</span><span class="sxs-lookup"><span data-stu-id="58a8c-146">The **Services Control Manager** is the central utility provided by Windows to administer services.</span></span>  
  
 <span data-ttu-id="58a8c-147">Po zavedení služby je nutné spustit.</span><span class="sxs-lookup"><span data-stu-id="58a8c-147">After the service has been loaded, it must be started.</span></span> <span data-ttu-id="58a8c-148">Spouštění služby umožňuje, aby začal fungovat.</span><span class="sxs-lookup"><span data-stu-id="58a8c-148">Starting the service allows it to begin functioning.</span></span> <span data-ttu-id="58a8c-149">Můžete spustit služby z **správci řízení služeb**, z **Průzkumníka serveru**, nebo z kódu voláním <xref:System.ServiceProcess.ServiceController.Start%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="58a8c-149">You can start a service from the **Services Control Manager**, from **Server Explorer**, or from code by calling the <xref:System.ServiceProcess.ServiceController.Start%2A> method.</span></span> <span data-ttu-id="58a8c-150"><xref:System.ServiceProcess.ServiceController.Start%2A> Metoda předá zpracování aplikace <xref:System.ServiceProcess.ServiceBase.OnStart%2A> metoda a zpracuje žádný kód, který jste definovali existuje.</span><span class="sxs-lookup"><span data-stu-id="58a8c-150">The <xref:System.ServiceProcess.ServiceController.Start%2A> method passes processing to the application's <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and processes any code you have defined there.</span></span>  
  
 <span data-ttu-id="58a8c-151">Spuštěná služba může existovat v tomto stavu, bez omezení, dokud nebude buď zastavena nebo pozastavena, nebo dokud se počítač vypne.</span><span class="sxs-lookup"><span data-stu-id="58a8c-151">A running service can exist in this state indefinitely until it is either stopped or paused or until the computer shuts down.</span></span> <span data-ttu-id="58a8c-152">Služba může existovat v jednom ze tří stavů základní: <xref:System.ServiceProcess.ServiceControllerStatus.Running>, <xref:System.ServiceProcess.ServiceControllerStatus.Paused>, nebo <xref:System.ServiceProcess.ServiceControllerStatus.Stopped>.</span><span class="sxs-lookup"><span data-stu-id="58a8c-152">A service can exist in one of three basic states: <xref:System.ServiceProcess.ServiceControllerStatus.Running>, <xref:System.ServiceProcess.ServiceControllerStatus.Paused>, or <xref:System.ServiceProcess.ServiceControllerStatus.Stopped>.</span></span> <span data-ttu-id="58a8c-153">Službu můžete také sestavy stavu čekající příkazu: <xref:System.ServiceProcess.ServiceControllerStatus.ContinuePending>, <xref:System.ServiceProcess.ServiceControllerStatus.PausePending>, <xref:System.ServiceProcess.ServiceControllerStatus.StartPending>, nebo <xref:System.ServiceProcess.ServiceControllerStatus.StopPending>.</span><span class="sxs-lookup"><span data-stu-id="58a8c-153">The service can also report the state of a pending command: <xref:System.ServiceProcess.ServiceControllerStatus.ContinuePending>, <xref:System.ServiceProcess.ServiceControllerStatus.PausePending>, <xref:System.ServiceProcess.ServiceControllerStatus.StartPending>, or <xref:System.ServiceProcess.ServiceControllerStatus.StopPending>.</span></span> <span data-ttu-id="58a8c-154">Tyto stavy znamenat, že příkaz byl vydán, třeba příkaz pozastaví spuštěné služby, ale nebyla ještě provádějí.</span><span class="sxs-lookup"><span data-stu-id="58a8c-154">These statuses indicate that a command has been issued, such as a command to pause a running service, but has not been carried out yet.</span></span> <span data-ttu-id="58a8c-155">Můžete zadat dotaz <xref:System.ServiceProcess.ServiceController.Status%2A> k určení, co stav služby je v nebo pomocí <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A> proveďte akci, pokud některý z těchto stavů dojde k.</span><span class="sxs-lookup"><span data-stu-id="58a8c-155">You can query the <xref:System.ServiceProcess.ServiceController.Status%2A> to determine what state a service is in, or use the <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A> to carry out an action when any of these states occurs.</span></span>  
  
 <span data-ttu-id="58a8c-156">Můžete pozastavit, zastavit nebo obnovit služby z **správci řízení služeb**, z **Průzkumníka serveru**, nebo voláním metod v kódu.</span><span class="sxs-lookup"><span data-stu-id="58a8c-156">You can pause, stop, or resume a service from the **Services Control Manager**, from **Server Explorer**, or by calling methods in code.</span></span> <span data-ttu-id="58a8c-157">Každý z těchto akcí můžete volat s příslušným postupem v rámci služby (<xref:System.ServiceProcess.ServiceBase.OnStop%2A>, <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, nebo <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>), ve kterém můžete definovat další zpracování, které mají být provedeny, když se změní stav služby.</span><span class="sxs-lookup"><span data-stu-id="58a8c-157">Each of these actions can call an associated procedure in the service (<xref:System.ServiceProcess.ServiceBase.OnStop%2A>, <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, or <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>), in which you can define additional processing to be performed when the service changes state.</span></span>  
  
## <a name="types-of-services"></a><span data-ttu-id="58a8c-158">Typy služeb</span><span class="sxs-lookup"><span data-stu-id="58a8c-158">Types of Services</span></span>  
 <span data-ttu-id="58a8c-159">Existují dva typy služeb, které lze vytvořit v sadě Visual Studio pomocí rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="58a8c-159">There are two types of services you can create in Visual Studio using the .NET Framework.</span></span> <span data-ttu-id="58a8c-160">Služby, které jsou pouze služby v procesu přiřazené typ <xref:System.ServiceProcess.ServiceType.Win32OwnProcess>.</span><span class="sxs-lookup"><span data-stu-id="58a8c-160">Services that are the only service in a process are assigned the type <xref:System.ServiceProcess.ServiceType.Win32OwnProcess>.</span></span> <span data-ttu-id="58a8c-161">Služby, které proces sdílet s jinou službu přiřazené typ <xref:System.ServiceProcess.ServiceType.Win32ShareProcess>.</span><span class="sxs-lookup"><span data-stu-id="58a8c-161">Services that share a process with another service are assigned the type <xref:System.ServiceProcess.ServiceType.Win32ShareProcess>.</span></span> <span data-ttu-id="58a8c-162">Typ služby můžete načíst pomocí dotazu <xref:System.ServiceProcess.ServiceController.ServiceType%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="58a8c-162">You can retrieve the service type by querying the <xref:System.ServiceProcess.ServiceController.ServiceType%2A> property.</span></span>  
  
 <span data-ttu-id="58a8c-163">Jiné typy služeb může občas zobrazit, je-li dotaz stávající služby, které nebyly vytvořeny v sadě Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="58a8c-163">You might occasionally see other service types if you query existing services that were not created in Visual Studio.</span></span> <span data-ttu-id="58a8c-164">Další informace naleznete v tématu <xref:System.ServiceProcess.ServiceType>.</span><span class="sxs-lookup"><span data-stu-id="58a8c-164">For more information on these, see the <xref:System.ServiceProcess.ServiceType>.</span></span>  
  
## <a name="services-and-the-servicecontroller-component"></a><span data-ttu-id="58a8c-165">Služby a součást ServiceController</span><span class="sxs-lookup"><span data-stu-id="58a8c-165">Services and the ServiceController Component</span></span>  
 <span data-ttu-id="58a8c-166"><xref:System.ServiceProcess.ServiceController> Součást je použité pro připojení k instalované služby a pracovat s její stav; pomocí <xref:System.ServiceProcess.ServiceController> součásti, můžete spustit a zastavit službu, pozastavit a pokračovat v jeho fungování a odeslat vlastní příkazy ke službě.</span><span class="sxs-lookup"><span data-stu-id="58a8c-166">The <xref:System.ServiceProcess.ServiceController> component is used to connect to an installed service and manipulate its state; using a <xref:System.ServiceProcess.ServiceController> component, you can start and stop a service, pause and continue its functioning, and send custom commands to a service.</span></span> <span data-ttu-id="58a8c-167">Však není potřeba použít <xref:System.ServiceProcess.ServiceController> součást při vytváření aplikace služby.</span><span class="sxs-lookup"><span data-stu-id="58a8c-167">However, you do not need to use a <xref:System.ServiceProcess.ServiceController> component when you create a service application.</span></span> <span data-ttu-id="58a8c-168">Ve skutečnosti ve většině případů vaší <xref:System.ServiceProcess.ServiceController> komponenty by měly existovat v samostatných aplikací z aplikace služby systému Windows, která definuje služby.</span><span class="sxs-lookup"><span data-stu-id="58a8c-168">In fact, in most cases your <xref:System.ServiceProcess.ServiceController> component should exist in a separate application from the Windows service application that defines your service.</span></span>  
  
 <span data-ttu-id="58a8c-169">Další informace naleznete v tématu <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="58a8c-169">For more information, see <xref:System.ServiceProcess.ServiceController>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58a8c-170">Požadavky</span><span class="sxs-lookup"><span data-stu-id="58a8c-170">Requirements</span></span>  
  
-   <span data-ttu-id="58a8c-171">Služby musí být vytvořen v **služba systému Windows** projekt aplikace nebo jiného projektu podporující rozhraní .NET Framework, který vytvoří soubor .exe při sestavení a dědí z <xref:System.ServiceProcess.ServiceBase> třídy.</span><span class="sxs-lookup"><span data-stu-id="58a8c-171">Services must be created in a **Windows Service** application project or another .NET Framework–enabled project that creates an .exe file when built and inherits from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
-   <span data-ttu-id="58a8c-172">Projekty obsahující služby systému Windows musí být instalace součásti pro projekt a jeho služeb.</span><span class="sxs-lookup"><span data-stu-id="58a8c-172">Projects containing Windows services must have installation components for the project and its services.</span></span> <span data-ttu-id="58a8c-173">To se dá snadno udělat z **vlastnosti** okno.</span><span class="sxs-lookup"><span data-stu-id="58a8c-173">This can be easily accomplished from the **Properties** window.</span></span> <span data-ttu-id="58a8c-174">Další informace najdete v tématu [postupy: Přidání instalačních programů pro vaše aplikace služby](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="58a8c-174">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a8c-175">Viz také</span><span class="sxs-lookup"><span data-stu-id="58a8c-175">See Also</span></span>  
 [<span data-ttu-id="58a8c-176">Aplikace služby systému Windows</span><span class="sxs-lookup"><span data-stu-id="58a8c-176">Windows Service Applications</span></span>](../../../docs/framework/windows-services/index.md)  
 [<span data-ttu-id="58a8c-177">Architektura programování aplikace služby</span><span class="sxs-lookup"><span data-stu-id="58a8c-177">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 [<span data-ttu-id="58a8c-178">Postupy: vytváření služeb systému Windows</span><span class="sxs-lookup"><span data-stu-id="58a8c-178">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="58a8c-179">Postupy: instalace a odinstalace služeb</span><span class="sxs-lookup"><span data-stu-id="58a8c-179">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="58a8c-180">Postupy: spuštění služeb</span><span class="sxs-lookup"><span data-stu-id="58a8c-180">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="58a8c-181">Postupy: ladění aplikace služby systému Windows</span><span class="sxs-lookup"><span data-stu-id="58a8c-181">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="58a8c-182">Návod: Vytvoření aplikace služby systému Windows v Návrháři součástí</span><span class="sxs-lookup"><span data-stu-id="58a8c-182">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 [<span data-ttu-id="58a8c-183">Postupy: Přidání instalačních programů do aplikace služby</span><span class="sxs-lookup"><span data-stu-id="58a8c-183">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)