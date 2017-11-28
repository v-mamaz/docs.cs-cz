---
title: "Správa a diagnostika"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, diagnostics
- Windows Communication Foundation, administration
- diagnostics [WCF]
- WCF, diagnostics
- administration [WCF]
- WCF, administration
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2f103570cf7d94a9ac6256f3db991c44767fa7c4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="administration-and-diagnostics"></a><span data-ttu-id="89e24-102">Správa a diagnostika</span><span class="sxs-lookup"><span data-stu-id="89e24-102">Administration and Diagnostics</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="89e24-103">poskytuje bohatou sadu funkcí, které umožňují monitorovat různých fázích životního aplikace.</span><span class="sxs-lookup"><span data-stu-id="89e24-103"> provides a rich set of functionalities that can help you monitor the different stages of an application’s life.</span></span> <span data-ttu-id="89e24-104">Například můžete použít konfiguraci nastavení služeb a klientů v nasazení.</span><span class="sxs-lookup"><span data-stu-id="89e24-104">For example, you can use configuration to set up services and clients at deployment.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="89e24-105">obsahuje velké sady čítačů výkonu můžete měřit výkon vaší aplikace.</span><span class="sxs-lookup"><span data-stu-id="89e24-105"> includes a large set of performance counters to help you gauge your application's performance.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="89e24-106">taky zpřístupňuje dat kontroly služby za běhu prostřednictvím [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zprostředkovatele Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="89e24-106"> also exposes inspection data of a service at runtime through a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Windows Management Instrumentation (WMI) provider.</span></span> <span data-ttu-id="89e24-107">Při vyskytne chyba nebo spustí funguje nesprávně aplikace, můžete zobrazit, pokud nic významné došlo k chybě v protokolu událostí.</span><span class="sxs-lookup"><span data-stu-id="89e24-107">When the application experiences a failure or starts acting improperly, you can use the Event Log to see if anything significant has occurred.</span></span> <span data-ttu-id="89e24-108">Můžete také použít protokolování zpráv a trasování a zjistěte, jaké události jsou situaci klient server ve vaší aplikaci.</span><span class="sxs-lookup"><span data-stu-id="89e24-108">You can also use Message Logging and Tracing to see what events are happening end-to-end in your application.</span></span> <span data-ttu-id="89e24-109">Tyto funkce pomůže vývojáře a IT odborníky řešení potíží [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikace při nepracuje správně.</span><span class="sxs-lookup"><span data-stu-id="89e24-109">These features assist both developers and IT professionals to troubleshoot an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application when it is not behaving correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89e24-110">Pokud se vám chyb s nejsou žádné konkrétní podrobné informace, měli byste povolit `includeExceptionDetailInFaults` atribut [ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) konfigurační prvek.</span><span class="sxs-lookup"><span data-stu-id="89e24-110">If you are receiving faults with no specific detail information, you should enable the `includeExceptionDetailInFaults` attribute of the [\<serviceDebug>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) configuration element.</span></span> <span data-ttu-id="89e24-111">Tím se nastaví [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Odeslat podrobnosti výjimky pro klienty, které umožňuje detekovat mnoho běžných problémů bez nutnosti pokročilejší diagnostiku.</span><span class="sxs-lookup"><span data-stu-id="89e24-111">This instructs [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to send exception detail to clients, which enables you to detect many common problems without requiring more advanced diagnosis.</span></span> <span data-ttu-id="89e24-112">Další informace najdete v tématu [odesílání a přijímání chyb](../../../../docs/framework/wcf/sending-and-receiving-faults.md).</span><span class="sxs-lookup"><span data-stu-id="89e24-112">For more information, see [Sending and Receiving Faults](../../../../docs/framework/wcf/sending-and-receiving-faults.md).</span></span>  
  
## <a name="diagnostics-features-provided-by-wcf"></a><span data-ttu-id="89e24-113">Diagnostické funkce poskytované službou WCF</span><span class="sxs-lookup"><span data-stu-id="89e24-113">Diagnostics Features Provided by WCF</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="89e24-114">poskytuje následující funkce diagnostics:</span><span class="sxs-lookup"><span data-stu-id="89e24-114"> provides the following diagnostics functionalities:</span></span>  
  
-   <span data-ttu-id="89e24-115">Trasování začátku do konce poskytuje data instrumentace pro řešení potíží s aplikace bez použití ladicí program.</span><span class="sxs-lookup"><span data-stu-id="89e24-115">End-To-End tracing provides instrumentation data for troubleshooting an application without using a debugger.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="89e24-116">výstupy trasování pro proces milníky, jakož i chybové zprávy.</span><span class="sxs-lookup"><span data-stu-id="89e24-116"> outputs traces for process milestones, as well as error messages.</span></span> <span data-ttu-id="89e24-117">To může zahrnovat otevření kanálu nebo odesílání a přijímání zpráv pomocí hostitele služby.</span><span class="sxs-lookup"><span data-stu-id="89e24-117">This can include opening a channel factory or sending and receiving messages by a service host.</span></span> <span data-ttu-id="89e24-118">Trasování je možné zapnout pro běžící aplikaci monitorovat její postup.</span><span class="sxs-lookup"><span data-stu-id="89e24-118">Tracing can be enabled for a running application to monitor its progress.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="89e24-119">[trasování](../../../../docs/framework/wcf/diagnostics/tracing/index.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="89e24-119"> the [Tracing](../../../../docs/framework/wcf/diagnostics/tracing/index.md) topic.</span></span> <span data-ttu-id="89e24-120">Abyste pochopili, jak můžete trasování ladění aplikace, najdete v článku [pomocí trasování řešení vaše aplikace](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="89e24-120">To understand how you can use tracing to debug your application, see the [Using Tracing to Troubleshoot Your Application](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) topic.</span></span>  
  
-   <span data-ttu-id="89e24-121">Protokolování zpráv umožňuje zobrazit vzhled zprávy před a po přenosu.</span><span class="sxs-lookup"><span data-stu-id="89e24-121">Message logging allows you to see how messages look both before and after transmission.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="89e24-122">[protokolování zpráv](../../../../docs/framework/wcf/diagnostics/message-logging.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="89e24-122"> the [Message Logging](../../../../docs/framework/wcf/diagnostics/message-logging.md) topic.</span></span>  
  
-   <span data-ttu-id="89e24-123">Události trasování událostí se zapisují do protokolu událostí pro potíže hlavní.</span><span class="sxs-lookup"><span data-stu-id="89e24-123">Event tracing writes events in the Event Log for any major issues.</span></span> <span data-ttu-id="89e24-124">Potom můžete v prohlížeči událostí k prozkoumání abnormality.</span><span class="sxs-lookup"><span data-stu-id="89e24-124">You can then use the Event Viewer to examine any abnormalities.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="89e24-125">[protokolování událostí](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="89e24-125"> the [Event Logging](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) topic.</span></span>  
  
-   <span data-ttu-id="89e24-126">Čítače výkonu, které jsou k dispozici prostřednictvím nástroje Sledování výkonu umožňují sledovat vaše aplikace a stavu systému.</span><span class="sxs-lookup"><span data-stu-id="89e24-126">Performance counters exposed through Performance Monitor enable you to monitor your application and system's health.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="89e24-127">[čítače výkonu](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="89e24-127"> the [Performance Counters](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) topic.</span></span>  
  
-   <span data-ttu-id="89e24-128"><xref:System.ServiceModel.Configuration> Obor názvů umožňuje načíst konfigurační soubory a nastavit koncový bod služby nebo klienta.</span><span class="sxs-lookup"><span data-stu-id="89e24-128">The <xref:System.ServiceModel.Configuration> namespace allows you to load configuration files and set up a service or client endpoint.</span></span> <span data-ttu-id="89e24-129">Model objektu do skriptu změny mnoho aplikací můžete použít při aktualizace musí být nasazený na mnoha počítačích.</span><span class="sxs-lookup"><span data-stu-id="89e24-129">You can use the object model to script changes to many applications when updates must be deployed to many computers.</span></span> <span data-ttu-id="89e24-130">Alternativně můžete použít [nástroj Configuration Editor (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) upravit konfigurační nastavení pomocí průvodce s grafickým uživatelským rozhraním.</span><span class="sxs-lookup"><span data-stu-id="89e24-130">Alternatively, you can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) to edit the configuration settings using a GUI wizard.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="89e24-131">[konfigurace vaše aplikace](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="89e24-131"> the [Configuring Your Application](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) topic.</span></span>  
  
-   <span data-ttu-id="89e24-132">Rozhraní WMI umožňuje zjistit, jaké služby jsou naslouchá na počítači a vazby, které jsou používány.</span><span class="sxs-lookup"><span data-stu-id="89e24-132">WMI enables you to find out what services are listening on a machine and the bindings that are in use.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="89e24-133">[pomocí rozhraní Windows Management Instrumentation pro diagnostiku](../../../../docs/framework/wcf/diagnostics/wmi/index.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="89e24-133"> the [Using Windows Management Instrumentation for Diagnostics](../../../../docs/framework/wcf/diagnostics/wmi/index.md) topic.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="89e24-134">také poskytuje několik grafického uživatelského rozhraní a nástroje příkazového řádku snadno vytvářet, nasazovat a spravovat [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="89e24-134"> also provides several GUI and command line tools to make it easier for you to create, deploy, and manage [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="89e24-135">[Nástroje služby Windows Communication Foundation](../../../../docs/framework/wcf/tools.md).</span><span class="sxs-lookup"><span data-stu-id="89e24-135"> [Windows Communication Foundation Tools](../../../../docs/framework/wcf/tools.md).</span></span> <span data-ttu-id="89e24-136">Například můžete použít [nástroj Configuration Editor (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) můžete vytvářet a upravovat [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] konfigurační nastavení pomocí průvodce, místo přímou úpravou kódu XML.</span><span class="sxs-lookup"><span data-stu-id="89e24-136">For example, you can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and edit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration settings using a wizard, instead of editing XML directly.</span></span> <span data-ttu-id="89e24-137">Můžete také [nástroj Prohlížeč trasování služeb (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) Pokud chcete zobrazit, skupiny a filtrovat zprávy trasování tak, aby lze diagnostikovat, opravte a zkontrolujte problémy s [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] služby.</span><span class="sxs-lookup"><span data-stu-id="89e24-137">You can also use the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) to view, group, and filter trace messages so that you can diagnose, repair, and verify issues with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e24-138">Viz také</span><span class="sxs-lookup"><span data-stu-id="89e24-138">See Also</span></span>  
 [<span data-ttu-id="89e24-139">Konfigurace aplikace</span><span class="sxs-lookup"><span data-stu-id="89e24-139">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)  
 [<span data-ttu-id="89e24-140">Nasazení služeb</span><span class="sxs-lookup"><span data-stu-id="89e24-140">Deploying Services</span></span>](../../../../docs/framework/wcf/diagnostics/deploying-services.md)  
 [<span data-ttu-id="89e24-141">Přehled výjimek</span><span class="sxs-lookup"><span data-stu-id="89e24-141">Exceptions Reference</span></span>](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)  
 [<span data-ttu-id="89e24-142">Protokolování událostí</span><span class="sxs-lookup"><span data-stu-id="89e24-142">Event Logging</span></span>](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="89e24-143">Protokolování zpráv</span><span class="sxs-lookup"><span data-stu-id="89e24-143">Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/message-logging.md)  
 [<span data-ttu-id="89e24-144">Nástroj Configuration Editor (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="89e24-144">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [<span data-ttu-id="89e24-145">Nástroj Prohlížeč trasování služeb (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="89e24-145">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [<span data-ttu-id="89e24-146">Nástroj ServiceModelReg.exe</span><span class="sxs-lookup"><span data-stu-id="89e24-146">ServiceModel Registration Tool</span></span>](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)  
 [<span data-ttu-id="89e24-147">Trasování</span><span class="sxs-lookup"><span data-stu-id="89e24-147">Tracing</span></span>](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="89e24-148">Pomocí rozhraní Windows Management Instrumentation pro diagnostiku</span><span class="sxs-lookup"><span data-stu-id="89e24-148">Using Windows Management Instrumentation for Diagnostics</span></span>](../../../../docs/framework/wcf/diagnostics/wmi/index.md)  
 [<span data-ttu-id="89e24-149">Čítače výkonu</span><span class="sxs-lookup"><span data-stu-id="89e24-149">Performance Counters</span></span>](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)  
 [<span data-ttu-id="89e24-150">Nástroje služby Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="89e24-150">Windows Communication Foundation Tools</span></span>](../../../../docs/framework/wcf/tools.md)