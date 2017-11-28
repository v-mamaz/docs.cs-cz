---
title: "Síťové programování v rozhraní .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
caps.latest.revision: "24"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 76b747624a22212fb7b9ba1a6353956a99ed1559
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="network-programming-in-the-net-framework"></a><span data-ttu-id="1c885-102">Síťové programování v rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1c885-102">Network Programming in the .NET Framework</span></span>
<span data-ttu-id="1c885-103">Rozhraní Microsoft .NET Framework poskytuje vícevrstvou rozšiřitelnou a spravovatelnou implementaci internetových služeb, kterou můžete rychle a snadno integrovat do své aplikace.</span><span class="sxs-lookup"><span data-stu-id="1c885-103">The Microsoft .NET Framework provides a layered, extensible, and managed implementation of Internet services that can be quickly and easily integrated into your applications.</span></span> <span data-ttu-id="1c885-104">Síťové aplikace mohou stavět na připojitelných protokolech a díky tomu automaticky využívat nové internetové protokoly nebo mohou používat spravovanou implementaci rozhraní soketů systému Windows pro práci se sítí na úrovni soketu.</span><span class="sxs-lookup"><span data-stu-id="1c885-104">Your network applications can build on pluggable protocols to automatically take advantage of new Internet protocols, or they can use a managed implementation of the Windows socket interface to work with the network on the socket level.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c885-105">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="1c885-105">In This Section</span></span>  
 [<span data-ttu-id="1c885-106">Představení modulární protokoly</span><span class="sxs-lookup"><span data-stu-id="1c885-106">Introducing Pluggable Protocols</span></span>](../../../docs/framework/network-programming/introducing-pluggable-protocols.md)  
 <span data-ttu-id="1c885-107">Popisuje, jak získat přístup ke zdroji v Internetu bez ohledu na přístupový protokol, který vyžaduje.</span><span class="sxs-lookup"><span data-stu-id="1c885-107">Describes how to access an Internet resource without regard to the access protocol that it requires.</span></span>  
  
 [<span data-ttu-id="1c885-108">Požadavek na Data</span><span class="sxs-lookup"><span data-stu-id="1c885-108">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 <span data-ttu-id="1c885-109">Vysvětluje, jak pomocí připojitelných protokolů odesílat a stahovat data ze zdrojů v Internetu.</span><span class="sxs-lookup"><span data-stu-id="1c885-109">Explains how to use pluggable protocols to upload and download data from Internet resources.</span></span>  
  
 [<span data-ttu-id="1c885-110">Modulární protokoly programování</span><span class="sxs-lookup"><span data-stu-id="1c885-110">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)  
 <span data-ttu-id="1c885-111">Vysvětluje, jak odvodit třídy pro konkrétní protokoly za účelem implementace připojitelných protokolů.</span><span class="sxs-lookup"><span data-stu-id="1c885-111">Explains how to derive protocol-specific classes to implement pluggable protocols.</span></span>  
  
 [<span data-ttu-id="1c885-112">Pomocí protokolů aplikací</span><span class="sxs-lookup"><span data-stu-id="1c885-112">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 <span data-ttu-id="1c885-113">Popisuje programování aplikací, které využívají síťové protokoly, například TCP, UDP nebo HTTP.</span><span class="sxs-lookup"><span data-stu-id="1c885-113">Describes programming applications that take advantage of network protocols such as TCP, UDP, and HTTP.</span></span>  
  
 [<span data-ttu-id="1c885-114">Protokol IP verze 6</span><span class="sxs-lookup"><span data-stu-id="1c885-114">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 <span data-ttu-id="1c885-115">Popisuje výhody verze 6 protokolu Internet Protocol (IPv6) oproti aktuální verzi sady protokolů Internet Protocol (IPv4). Dále popisuje adresování, směrování a automatickou konfiguraci protokolu IPv6 a postup, jak povolit nebo zakázat protokol IPv6.</span><span class="sxs-lookup"><span data-stu-id="1c885-115">Describes the advantages of Internet Protocol version 6 (IPv6) over the current version of the Internet Protocol suite (IPv4), describes IPv6 addressing, routing and auto-configuration, and how to enable and disable IPv6.</span></span>  
  
 [<span data-ttu-id="1c885-116">Konfigurace Internetové aplikace</span><span class="sxs-lookup"><span data-stu-id="1c885-116">Configuring Internet Applications</span></span>](../../../docs/framework/network-programming/configuring-internet-applications.md)  
 <span data-ttu-id="1c885-117">Vysvětluje, jak nakonfigurovat internetové aplikace pomocí konfiguračních souborů rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1c885-117">Explains how to use the .NET Framework configuration files to configure Internet applications.</span></span>  
  
 [<span data-ttu-id="1c885-118">Trasování sítě v rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1c885-118">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)  
 <span data-ttu-id="1c885-119">Vysvětluje, jak pomocí trasování sítě získat informace o vyvoláních metody a přenosech v síti generovaných spravovanou aplikací.</span><span class="sxs-lookup"><span data-stu-id="1c885-119">Explains how to use network tracing to get information about method invocations and network traffic generated by a managed application.</span></span>  
  
 [<span data-ttu-id="1c885-120">Správa mezipaměti pro síťové aplikace</span><span class="sxs-lookup"><span data-stu-id="1c885-120">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 <span data-ttu-id="1c885-121">Popisuje, jak používat ukládání do mezipaměti pro aplikace, které používají <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>, a <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="1c885-121">Describes how to use caching for applications that use the <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>, and <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> classes.</span></span>  
  
 [<span data-ttu-id="1c885-122">Zabezpečení v síťové programování</span><span class="sxs-lookup"><span data-stu-id="1c885-122">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)  
 <span data-ttu-id="1c885-123">Popisuje, jak používat standardní techniky ověřování a zabezpečení v Internetu.</span><span class="sxs-lookup"><span data-stu-id="1c885-123">Describes how to use standard Internet security and authentication techniques.</span></span>  
  
 [<span data-ttu-id="1c885-124">Osvědčené postupy pro System.NET – třídy</span><span class="sxs-lookup"><span data-stu-id="1c885-124">Best Practices for System.Net Classes</span></span>](../../../docs/framework/network-programming/best-practices-for-system-net-classes.md)  
 <span data-ttu-id="1c885-125">Nabízí tipy a triky pro maximální využití internetových aplikací.</span><span class="sxs-lookup"><span data-stu-id="1c885-125">Provides tips and tricks for getting the most out of your Internet applications.</span></span>  
  
 [<span data-ttu-id="1c885-126">Přístup k Internetu prostřednictvím proxy serveru</span><span class="sxs-lookup"><span data-stu-id="1c885-126">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 <span data-ttu-id="1c885-127">Popisuje postup konfigurace proxy serverů.</span><span class="sxs-lookup"><span data-stu-id="1c885-127">Describes how to configure proxies.</span></span>  
  
 [<span data-ttu-id="1c885-128">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="1c885-128">NetworkInformation</span></span>](../../../docs/framework/network-programming/networkinformation.md)  
 <span data-ttu-id="1c885-129">Popisuje, jak získat informace o události sítě, změny, statistiky a vlastnosti a také vysvětluje, jak určit, zda je vzdálený hostitel dosažitelný pomocí <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="1c885-129">Describes how to gather information about network events, changes, statistics, and properties and also explains how to determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
 [<span data-ttu-id="1c885-130">Změny v oboru názvů System.Uri v verze 2.0</span><span class="sxs-lookup"><span data-stu-id="1c885-130">Changes to the System.Uri namespace in Version 2.0</span></span>](../../../docs/framework/network-programming/changes-to-the-system-uri-namespace-in-version-2-0.md)  
 <span data-ttu-id="1c885-131">Popisuje několik změny provedené <xref:System.Uri?displayProperty=nameWithType> třídy ve verzi 2.0 pevné nesprávné chování, zlepšují použitelnost a zvýšit zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="1c885-131">Describes several changes made to the <xref:System.Uri?displayProperty=nameWithType> class in Version 2.0 to fixed incorrect behavior, enhance usability, and enhance security.</span></span>  
  
 [<span data-ttu-id="1c885-132">Podpora identifikátor mezinárodní prostředků v System.Uri</span><span class="sxs-lookup"><span data-stu-id="1c885-132">International Resource Identifier Support in System.Uri</span></span>](../../../docs/framework/network-programming/international-resource-identifier-support-in-system-uri.md)  
 <span data-ttu-id="1c885-133">Popisuje vylepšení <xref:System.Uri?displayProperty=nameWithType> podporu třídy v verze 3.5, 3.0 s aktualizací SP1 a 2.0 SP1 pro mezinárodní prostředků identifikátor (IRI) a mezinárodní název domény (IDN).</span><span class="sxs-lookup"><span data-stu-id="1c885-133">Describes enhancements to the <xref:System.Uri?displayProperty=nameWithType> class in Version 3.5, 3.0 SP1, and 2.0 SP1 for International Resource Identifier (IRI) and Internationalized Domain Name (IDN) support.</span></span>  
  
 [<span data-ttu-id="1c885-134">Vylepšení výkonu soketu v verze 3.5</span><span class="sxs-lookup"><span data-stu-id="1c885-134">Socket Performance Enhancements in Version 3.5</span></span>](../../../docs/framework/network-programming/socket-performance-enhancements-in-version-3-5.md)  
 <span data-ttu-id="1c885-135">Popisuje sadu vylepšení <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> třídy v verze 3.5, 3.0 s aktualizací SP1 a 2.0 SP1, které poskytují alternativní asynchronní vzor, který lze použít speciální soketu vysoce výkonné aplikace.</span><span class="sxs-lookup"><span data-stu-id="1c885-135">Describes a set of enhancements to the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> class in Version 3.5, 3.0 SP1, and 2.0 SP1 that provide an alternative asynchronous pattern that can be used by specialized high-performance socket applications.</span></span>  
  
 [<span data-ttu-id="1c885-136">Protokol PNRP</span><span class="sxs-lookup"><span data-stu-id="1c885-136">Peer Name Resolution Protocol</span></span>](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)  
 <span data-ttu-id="1c885-137">Popisuje funkce přidané ve verzi 3.5 pro podporu protokolu PNRP (Peer Name Resolution Protocol), registrace názvů bez použití serverů, dynamické registrace názvů a protokolu překladu IP adres.</span><span class="sxs-lookup"><span data-stu-id="1c885-137">Describes support added in Version 3.5 to support the Peer Name Resolution Protocol (PNRP), a serverless and dynamic name registration and name resolution protocol.</span></span> <span data-ttu-id="1c885-138">Tyto nové funkce jsou podporovány <xref:System.Net.PeerToPeer?displayProperty=nameWithType> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="1c885-138">These new features are supported by the <xref:System.Net.PeerToPeer?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="1c885-139">Spolupráce peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="1c885-139">Peer-to-Peer Collaboration</span></span>](../../../docs/framework/network-programming/peer-to-peer-collaboration.md)  
 <span data-ttu-id="1c885-140">Popisuje funkce přidané ve verzi 3.5 pro podporu spolupráce Peer-to-Peer založené na protokolu PNRP.</span><span class="sxs-lookup"><span data-stu-id="1c885-140">Describes support added in Version 3.5 to support the Peer-to-Peer Collaboration that builds on PNRP.</span></span> <span data-ttu-id="1c885-141">Tyto nové funkce jsou podporovány <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="1c885-141">These new features are supported by the <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="1c885-142">Změny v ověřování protokolem NTLM pro HttpWebRequest v verze 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="1c885-142">Changes to NTLM authentication for HttpWebRequest in Version 3.5 SP1</span></span>](../../../docs/framework/network-programming/changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 <span data-ttu-id="1c885-143">Popisuje zabezpečení změny provedené v verze 3.5 SP1, které mají vliv jak integrované ověřování systému Windows, které se provádí ověřování <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, a související třídy v oboru názvů System.Net.</span><span class="sxs-lookup"><span data-stu-id="1c885-143">Describes security changes made in Version 3.5 SP1 that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, and related classes in the System.Net namespace.</span></span>  
  
 [<span data-ttu-id="1c885-144">Integrované ověřování systému Windows s rozšířené ochrany</span><span class="sxs-lookup"><span data-stu-id="1c885-144">Integrated Windows Authentication with Extended Protection</span></span>](../../../docs/framework/network-programming/integrated-windows-authentication-with-extended-protection.md)  
 <span data-ttu-id="1c885-145">Popisuje vylepšení pro rozšířené ochrany, které by ovlivnily jak integrované ověřování systému Windows jsou zpracována <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, a související třídy v <xref:System.Net?displayProperty=nameWithType> a související obory názvů.</span><span class="sxs-lookup"><span data-stu-id="1c885-145">Describes enhancements for extended protection that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, and related classes in the <xref:System.Net?displayProperty=nameWithType> and related namespaces.</span></span>  
  
 [<span data-ttu-id="1c885-146">NAT Traversal používající protokoly IPv6 a Teredo</span><span class="sxs-lookup"><span data-stu-id="1c885-146">NAT Traversal using IPv6 and Teredo</span></span>](../../../docs/framework/network-programming/nat-traversal-using-ipv6-and-teredo.md)  
 <span data-ttu-id="1c885-147">Popisuje vylepšení přidaných do <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>, a <xref:System.Net.Sockets?displayProperty=nameWithType> obory názvů pro podporu NAT traversal používající protokoly IPv6 a Teredo.</span><span class="sxs-lookup"><span data-stu-id="1c885-147">Describes enhancements added to the <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>, and <xref:System.Net.Sockets?displayProperty=nameWithType> namespaces to support NAT traversal using IPv6 and Teredo.</span></span>  
  
 [<span data-ttu-id="1c885-148">Izolace sítě pro aplikace Windows Store</span><span class="sxs-lookup"><span data-stu-id="1c885-148">Network Isolation for Windows Store Apps</span></span>](../../../docs/framework/network-programming/network-isolation-for-windows-store-apps.md)  
 <span data-ttu-id="1c885-149">Popisuje dopady izolace sítě při třídy v <xref:System.Net>, <xref:System.Net.Http>, a <xref:System.Net.Http.Headers> obory názvů, které se používají v [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="1c885-149">Describes the impact of network isolation when classes in the <xref:System.Net>, <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces are used in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [<span data-ttu-id="1c885-150">Síťové programování ukázky</span><span class="sxs-lookup"><span data-stu-id="1c885-150">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 <span data-ttu-id="1c885-151">Odkazy na stažení sítě programovací vzorků, které používají třídy v <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> obory názvů.</span><span class="sxs-lookup"><span data-stu-id="1c885-151">Links to downloadable network programming samples that use classes in the <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> namespaces.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1c885-152">Odkaz</span><span class="sxs-lookup"><span data-stu-id="1c885-152">Reference</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-153">Poskytuje jednoduché programovací rozhraní pro celou řadu protokolů, které se v současnosti v sítích používají.</span><span class="sxs-lookup"><span data-stu-id="1c885-153">Provides a simple programming interface for many of the protocols used on networks today.</span></span> <span data-ttu-id="1c885-154"><xref:System.Net.WebRequest?displayProperty=nameWithType> a <xref:System.Net.WebResponse?displayProperty=nameWithType> třídy v tomto oboru názvů slouží jako základ pro připojitelné protokoly.</span><span class="sxs-lookup"><span data-stu-id="1c885-154">The <xref:System.Net.WebRequest?displayProperty=nameWithType> and <xref:System.Net.WebResponse?displayProperty=nameWithType> classes in this namespace are the basis for pluggable protocols.</span></span>  
  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-155">Definuje typy a výčty používaný k definování zásady mezipaměti pro prostředků získaných pomocí <xref:System.Net.WebRequest?displayProperty=nameWithType> a <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="1c885-155">Defines the types and enumerations used to define cache policies for resources obtained using the <xref:System.Net.WebRequest?displayProperty=nameWithType> and <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> classes.</span></span>  
  
 <xref:System.Net.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-156">Třídy, pomocí nichž aplikace přistupují v kódu programu k nastavením konfigurace pro obory názvů System.Net a aktualizují tato nastavení</span><span class="sxs-lookup"><span data-stu-id="1c885-156">Classes that applications use to programmatically access and update configuration settings for the System.Net namespaces.</span></span>  
  
 <xref:System.Net.Http?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-157">Třídy, které poskytují programovací rozhraní pro moderní aplikace využívající protokol HTTP</span><span class="sxs-lookup"><span data-stu-id="1c885-157">Classes that provides a programming interface for modern HTTP applications.</span></span>  
  
 <xref:System.Net.Http.Headers?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-158">Poskytuje podporu pro kolekce hlaviček HTTP používaný <xref:System.Net.Http?displayProperty=nameWithType> obor názvů</span><span class="sxs-lookup"><span data-stu-id="1c885-158">Provides support for collections of HTTP headers used by the <xref:System.Net.Http?displayProperty=nameWithType> namespace</span></span>  
  
 <xref:System.Net.Mail?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-159">Třídy pro vytváření a odesílání e-mailů pomocí protokolu SMTP</span><span class="sxs-lookup"><span data-stu-id="1c885-159">Classes to compose and send mail using the SMTP protocol.</span></span>  
  
 <xref:System.Net.Mime?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-160">Definuje typy, které se používají k vyjádření používané třídy v záhlaví e-mailu Exchange MIME (Multipurpose Internet) <xref:System.Net.Mail?displayProperty=nameWithType> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="1c885-160">Defines types that are used to represent Multipurpose Internet Mail Exchange (MIME) headers used by classes in the <xref:System.Net.Mail?displayProperty=nameWithType> namespace.</span></span>  
  
 <xref:System.Net.NetworkInformation?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-161">Třídy, které umožňují získávat v kódu programu informace o událostech sítě, změnách, statistických údajích a vlastnostech</span><span class="sxs-lookup"><span data-stu-id="1c885-161">Classes to programmatically gather information about network events, changes, statistics, and properties.</span></span>  
  
 <xref:System.Net.PeerToPeer?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-162">Poskytuje spravovanou implementaci protokolu PNRP (Peer Name) pro vývojáře.</span><span class="sxs-lookup"><span data-stu-id="1c885-162">Provides a managed implementation of the Peer Name Resolution Protocol (PNRP) for developers.</span></span>  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-163">Poskytuje spravovanou implementaci rozhraní pro spolupráci Peer-to-Peer pro vývojáře.</span><span class="sxs-lookup"><span data-stu-id="1c885-163">Provides a managed implementation of the Peer-to-Peer Collaboration interface for developers.</span></span>  
  
 <xref:System.Net.Security?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-164">Třídy, které poskytují síťové datové proudy pro zabezpečenou komunikaci mezi hostiteli</span><span class="sxs-lookup"><span data-stu-id="1c885-164">Classes to provide network streams for secure communications between hosts.</span></span>  
  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-165">Poskytuje spravovatelnou implementaci rozhraní Windows Sockets (Winsock) pro vývojáře, kteří potřebují řídit přístup k síti.</span><span class="sxs-lookup"><span data-stu-id="1c885-165">Provides a managed implementation of the Windows Sockets (Winsock) interface for developers who need to help control access to the network.</span></span>  
  
 <xref:System.Net.WebSockets?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-166">Poskytuje spravovanou implementaci rozhraní WebSocket pro vývojáře.</span><span class="sxs-lookup"><span data-stu-id="1c885-166">Provides a managed implementation of the WebSocket interface for developers.</span></span>  
  
 <xref:System.Uri?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-167">Poskytuje reprezentaci identifikátoru URI ve formě objektu a snadný přístup k částem identifikátoru URI.</span><span class="sxs-lookup"><span data-stu-id="1c885-167">Provides an object representation of a uniform resource identifier (URI) and easy access to the parts of the URI.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-168">Poskytuje podporu pro ověřování s použitím rozšířené ochrany pro aplikace.</span><span class="sxs-lookup"><span data-stu-id="1c885-168">Provides support for authentication using extended protection for applications.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="1c885-169">Poskytuje podporu pro konfiguraci ověřování s použitím rozšířené ochrany pro aplikace.</span><span class="sxs-lookup"><span data-stu-id="1c885-169">Provides support for configuration of authentication using extended protection for applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c885-170">Viz také</span><span class="sxs-lookup"><span data-stu-id="1c885-170">See Also</span></span>  
 [<span data-ttu-id="1c885-171">Síťové programování – postupy</span><span class="sxs-lookup"><span data-stu-id="1c885-171">Network Programming How-to Topics</span></span>](../../../docs/framework/network-programming/network-programming-how-to-topics.md)  
 [<span data-ttu-id="1c885-172">Síťové programování ukázky</span><span class="sxs-lookup"><span data-stu-id="1c885-172">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 [<span data-ttu-id="1c885-173">Ukázky sítě pro .NET na galerie kódů MSDN</span><span class="sxs-lookup"><span data-stu-id="1c885-173">Networking Samples for .NET on MSDN Code Gallery</span></span>](http://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples)  
 [<span data-ttu-id="1c885-174">Ukázka HttpClient</span><span class="sxs-lookup"><span data-stu-id="1c885-174">HttpClient Sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=242550)