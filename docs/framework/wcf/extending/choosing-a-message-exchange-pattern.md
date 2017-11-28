---
title: "Výběr vzorce výměny zpráv"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f502ca1-6a8e-4607-ba15-59198c0e6146
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fd45d9522d40c0760c3aa231b6a0f07c9bcbc9af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="choosing-a-message-exchange-pattern"></a><span data-ttu-id="f4b4e-102">Výběr vzorce výměny zpráv</span><span class="sxs-lookup"><span data-stu-id="f4b4e-102">Choosing a Message Exchange Pattern</span></span>
<span data-ttu-id="f4b4e-103">Prvním krokem při psaní vlastních přenosu je rozhodnout, které *zprávy exchange vzory* (nebo MEPs) jsou povinné pro kanál vyvíjíte.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-103">The first step in writing a custom transport is to decide which *message exchange patterns* (or MEPs) are required for the channel you are developing.</span></span> <span data-ttu-id="f4b4e-104">Toto téma popisuje možnosti dostupné a popisuje různé požadavky.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-104">This topic describes the options available and discusses the various requirements.</span></span> <span data-ttu-id="f4b4e-105">Toto je první úloha v seznamu úkolů vývoj kanálu popsané v [rozvojových kanály](../../../../docs/framework/wcf/extending/developing-channels.md).</span><span class="sxs-lookup"><span data-stu-id="f4b4e-105">This is the first task in the channel development task list described in [Developing Channels](../../../../docs/framework/wcf/extending/developing-channels.md).</span></span>  
  
## <a name="six-message-exchange-patterns"></a><span data-ttu-id="f4b4e-106">Šest vzory Exchange zpráv</span><span class="sxs-lookup"><span data-stu-id="f4b4e-106">Six Message Exchange Patterns</span></span>  
 <span data-ttu-id="f4b4e-107">Existují tři MEPs zvolit:</span><span class="sxs-lookup"><span data-stu-id="f4b4e-107">There are three MEPs to choose from:</span></span>  
  
-   <span data-ttu-id="f4b4e-108">Datagram (<xref:System.ServiceModel.Channels.IInputChannel> a <xref:System.ServiceModel.Channels.IOutputChannel>)</span><span class="sxs-lookup"><span data-stu-id="f4b4e-108">Datagram (<xref:System.ServiceModel.Channels.IInputChannel> and <xref:System.ServiceModel.Channels.IOutputChannel>)</span></span>  
  
     <span data-ttu-id="f4b4e-109">Pokud používáte datagram MEP, klient odešle zprávu pomocí *fire a zapomněli* exchange.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-109">When using a datagram MEP, a client sends a message using a *fire and forget* exchange.</span></span> <span data-ttu-id="f4b4e-110">A fire a zapomněli exchange je ten, který vyžaduje out-of-band potvrzení úspěšné doručení.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-110">A fire and forget exchange is one that requires out-of-band confirmation of successful delivery.</span></span> <span data-ttu-id="f4b4e-111">Zpráva může dojít ke ztrátě během přenosu a nikdy nedorazí službu.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-111">The message might be lost in transit and never reach the service.</span></span> <span data-ttu-id="f4b4e-112">Operaci odeslání po úspěšném dokončení na konci klienta, nezaručuje to, že vzdálený koncový bod se zobrazila zpráva.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-112">If the send operation completes successfully at the client end, it does not guarantee that the remote endpoint has received the message.</span></span> <span data-ttu-id="f4b4e-113">Datagram je základní stavební blok pro zasílání zpráv, jak můžete vytvořit vlastní protokoly nad jeho – včetně protokoly spolehlivé a bezpečné protokoly.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-113">The datagram is a fundamental building block for messaging, as you can build your own protocols on top of it—including reliable protocols and secure protocols.</span></span> <span data-ttu-id="f4b4e-114">Implementace klienta datagram kanály <xref:System.ServiceModel.Channels.IOutputChannel> implementovat rozhraní a služba datagramu kanály <xref:System.ServiceModel.Channels.IInputChannel> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-114">Client datagram channels implement the <xref:System.ServiceModel.Channels.IOutputChannel> interface and service datagram channels implement the <xref:System.ServiceModel.Channels.IInputChannel> interface.</span></span>  
  
-   <span data-ttu-id="f4b4e-115">Požadavků a odpovědí (<xref:System.ServiceModel.Channels.IRequestChannel> a <xref:System.ServiceModel.Channels.IReplyChannel>)</span><span class="sxs-lookup"><span data-stu-id="f4b4e-115">Request-Response (<xref:System.ServiceModel.Channels.IRequestChannel> and <xref:System.ServiceModel.Channels.IReplyChannel>)</span></span>  
  
     <span data-ttu-id="f4b4e-116">V této MEP je odeslána zpráva a odpoví.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-116">In this MEP, a message is sent, and a reply is received.</span></span> <span data-ttu-id="f4b4e-117">Vzor se skládá z dvojice požadavků a odpovědí.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-117">The pattern consists of request-response pairs.</span></span> <span data-ttu-id="f4b4e-118">Příkladem volání požadavků a odpovědí jsou vzdálených volání procedur (RPC) a prohlížeče GET požadavky.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-118">Examples of request-response calls are remote procedure calls (RPC) and browser GET requests.</span></span> <span data-ttu-id="f4b4e-119">Tento vzor se také označuje jako poloduplexní.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-119">This pattern is also known as half-duplex.</span></span> <span data-ttu-id="f4b4e-120">V této MEP klienta kanály implementovat <xref:System.ServiceModel.Channels.IRequestChannel> a implementaci služby kanály <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-120">In this MEP, client channels implement <xref:System.ServiceModel.Channels.IRequestChannel> and service channels implement <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span>  
  
-   <span data-ttu-id="f4b4e-121">Duplexní (<xref:System.ServiceModel.Channels.IDuplexChannel>)</span><span class="sxs-lookup"><span data-stu-id="f4b4e-121">Duplex (<xref:System.ServiceModel.Channels.IDuplexChannel>)</span></span>  
  
     <span data-ttu-id="f4b4e-122">Duplexní MEP umožňuje libovolný počet zpráv, které mají být odeslány klientem a přijaté v libovolném pořadí.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-122">The duplex MEP allows an arbitrary number of messages to be sent by a client and received in any order.</span></span> <span data-ttu-id="f4b4e-123">Duplexní MEP je třeba je telefonní hovor, kde je jednotlivých slov použitém zprávu.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-123">The duplex MEP is like a phone conversation, where each word being spoken is a message.</span></span> <span data-ttu-id="f4b4e-124">Vzhledem k tomu, že na obou stranách můžete odesílat a přijímat v této MEP, rozhraní implementované kanály klienta a služby je <xref:System.ServiceModel.Channels.IDuplexChannel>.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-124">Because both sides can send and receive in this MEP, the interface implemented by the client and service channels is <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
 <span data-ttu-id="f4b4e-125">![Výběr vzorce výměny zpráv](../../../../docs/framework/wcf/extending/media/wcfc-basicthreemepsc.gif "wcfc_BasicThreeMEPsc")</span><span class="sxs-lookup"><span data-stu-id="f4b4e-125">![Choosing a message exchange pattern](../../../../docs/framework/wcf/extending/media/wcfc-basicthreemepsc.gif "wcfc_BasicThreeMEPsc")</span></span>  
<span data-ttu-id="f4b4e-126">Tři vzory exchange základní zpráva.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-126">The three basic message exchange patterns.</span></span> <span data-ttu-id="f4b4e-127">Shora dolů: datagram, požadavků a odpovědí a duplexní režim.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-127">Top to bottom: datagram, request-response, and duplex.</span></span>  
  
 <span data-ttu-id="f4b4e-128">Každý z těchto MEPs může také podporovat *relací*.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-128">Each of these MEPs can also support *sessions*.</span></span> <span data-ttu-id="f4b4e-129">Relace (a provádění <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType> typu <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>) korelaci všechny zprávy odeslané a přijaté v kanálu.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-129">A session (and implementation of <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType> of type <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>) correlates all messages sent and received on a channel.</span></span> <span data-ttu-id="f4b4e-130">Vzor požadavků a odpovědí je samostatné relaci dvě zprávy, jako jsou korelační požadavku a odpovědi.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-130">The request-response pattern is a stand-alone two-message session, as the request and reply are correlated.</span></span> <span data-ttu-id="f4b4e-131">Naproti tomu vzor požadavků a odpovědí, který podporuje relací znamená, že všechny páry požadavků a odpovědí v tomto kanálu jsou korelační mezi sebou.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-131">In contrast, the request-response pattern that supports sessions implies that all request/response pairs on that channel are correlated with each other.</span></span> <span data-ttu-id="f4b4e-132">To vám dává celkem šest MEPs zvolit:</span><span class="sxs-lookup"><span data-stu-id="f4b4e-132">This gives you a total of six MEPs to choose from:</span></span>  
  
-   <span data-ttu-id="f4b4e-133">Datagram</span><span class="sxs-lookup"><span data-stu-id="f4b4e-133">Datagram</span></span>  
  
-   <span data-ttu-id="f4b4e-134">Požadavek odpověď</span><span class="sxs-lookup"><span data-stu-id="f4b4e-134">Request-response</span></span>  
  
-   <span data-ttu-id="f4b4e-135">Duplex</span><span class="sxs-lookup"><span data-stu-id="f4b4e-135">Duplex</span></span>  
  
-   <span data-ttu-id="f4b4e-136">Datagram s relací</span><span class="sxs-lookup"><span data-stu-id="f4b4e-136">Datagram with sessions</span></span>  
  
-   <span data-ttu-id="f4b4e-137">Požadavků a odpovědí s relací</span><span class="sxs-lookup"><span data-stu-id="f4b4e-137">Request-response with sessions</span></span>  
  
-   <span data-ttu-id="f4b4e-138">Duplexní režim s relací</span><span class="sxs-lookup"><span data-stu-id="f4b4e-138">Duplex with sessions</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4b4e-139">Pro přenosu UDP pouze MEP, která je podporována je datagram, protože UDP je ze své podstaty ještě efektivněji a zapomněli protokolu.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-139">For the UDP transport, the only MEP that is supported is datagram, because UDP is inherently a fire and forget protocol.</span></span>  
  
## <a name="sessions-and-sessionful-channels"></a><span data-ttu-id="f4b4e-140">Relace a Sessionful kanály</span><span class="sxs-lookup"><span data-stu-id="f4b4e-140">Sessions and Sessionful Channels</span></span>  
 <span data-ttu-id="f4b4e-141">Na světě sítě jsou orientované na připojení protokoly (například TCP) a protokoly bez připojení (například UDP).</span><span class="sxs-lookup"><span data-stu-id="f4b4e-141">In the networking world, there are connection-oriented protocols (for example, TCP) and connection-less protocols (for example, UDP).</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f4b4e-142">používá termín relace rozumí abstrakce logické jako připojení.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-142"> uses the term session to mean a connection-like logical abstraction.</span></span> <span data-ttu-id="f4b4e-143">Relacemi WCF protokoly jsou podobná orientovaná na připojení síťové protokoly a protokoly nerelační WCF jsou podobná připojení méně síťových protokolů.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-143">Sessionful WCF protocols are similar to connection-oriented network protocols and sessionless WCF protocols are similar to connection-less network protocols.</span></span>  
  
 <span data-ttu-id="f4b4e-144">V modelu objektu kanál každé logické relaci manifesty jako instanci kanál s relacemi.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-144">In the channel object model, each logical session manifests as an instance of a sessionful channel.</span></span> <span data-ttu-id="f4b4e-145">Proto všechny nové relace vytvoření klient a přijal na službu, odpovídá nové kanálu relací na každé straně.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-145">Therefore every new session created by the client, and accepted on the service, corresponds to a new sessionful channel on each side.</span></span> <span data-ttu-id="f4b4e-146">Následující diagram ukazuje, nahoře, struktura nerelační kanály a v dolní části, struktura relacemi kanály.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-146">The following diagram shows, on the top, the structure of sessionless channels, and on the bottom, the structure of sessionful channels.</span></span>  
  
 <span data-ttu-id="f4b4e-147">![Výběr vzorce výměny zpráv](../../../../docs/framework/wcf/extending/media/wcfc-sessionandsessionlesschannelsc.gif "wcfc_SessionAndSessionlessChannelsc")</span><span class="sxs-lookup"><span data-stu-id="f4b4e-147">![Choosing a message exchange pattern](../../../../docs/framework/wcf/extending/media/wcfc-sessionandsessionlesschannelsc.gif "wcfc_SessionAndSessionlessChannelsc")</span></span>  
  
 <span data-ttu-id="f4b4e-148">Klient vytvoří nové kanálu relací a odešle zprávu.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-148">A client creates a new sessionful channel and sends a message.</span></span> <span data-ttu-id="f4b4e-149">Na straně služby naslouchací proces kanálu nástroje obdrží tuto zprávu a zjistí, že patří do novou relaci tak, aby se vytvoří nový kanál s relacemi a předá ji do aplikace (jako reakce na aplikaci volání AcceptChannel na naslouchací proces kanálu nástroje).</span><span class="sxs-lookup"><span data-stu-id="f4b4e-149">On the service side, the channel listener receives this message and detects that it belongs to a new session so it creates a new sessionful channel and hands it to the application (in response to the application calling AcceptChannel on the channel listener).</span></span> <span data-ttu-id="f4b4e-150">Aplikace se pak obdrží tuto zprávu a všechny následné zprávy odeslané ve stejné relaci prostřednictvím kanálu stejné relací.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-150">The application then receives this message and all subsequent messages sent in the same session through the same sessionful channel.</span></span>  
  
 <span data-ttu-id="f4b4e-151">Jiného klienta (nebo stejného klienta) vytvoří nové sessionful a odešle zprávu.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-151">Another client (or the same client) creates a new sessionful and sends a message.</span></span> <span data-ttu-id="f4b4e-152">Naslouchací proces kanálu nástroje zjišťuje, tato zpráva je v nové relaci a vytvoří nový kanál s relacemi, a postup se opakuje.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-152">The channel listener detects this message is in a new session and creates a new sessionful channel and the process repeats.</span></span>  
  
 <span data-ttu-id="f4b4e-153">Bez relace neexistuje žádný korelace mezi kanály a relace.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-153">Without sessions, there is no correlation between channels and sessions.</span></span> <span data-ttu-id="f4b4e-154">Proto vytvoří naslouchací proces kanálu jenom jeden kanál, pomocí kterého jsou všechny přijaté zprávy doručí aplikaci.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-154">Therefore a channel listener creates only one channel through which all received messages are delivered to the application.</span></span> <span data-ttu-id="f4b4e-155">Neexistuje žádná zpráva, protože neexistuje žádná relace v rámci které má udržovat zpráva pořadí řazení.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-155">There is also no message ordering because there is no session within which to maintain message order.</span></span> <span data-ttu-id="f4b4e-156">Horní části na předchozím obrázku znázorňuje nerelační zpráva systému exchange.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-156">The top portion of the preceding graphic illustrates a sessionless message exchange.</span></span>  
  
## <a name="starting-and-terminating-sessions"></a><span data-ttu-id="f4b4e-157">Spuštění a ukončení relace</span><span class="sxs-lookup"><span data-stu-id="f4b4e-157">Starting and Terminating Sessions</span></span>  
 <span data-ttu-id="f4b4e-158">Jednoduše vytvořením nového kanálu relací jsou spuštěné relace na straně klienta.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-158">Sessions are started on the client by simply creating a new sessionful channel.</span></span> <span data-ttu-id="f4b4e-159">Když služba obdrží zprávu, která byla odeslána v nové relaci jsou spuštěny služby.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-159">They are started on the service when the service receives a message that was sent in a new session.</span></span> <span data-ttu-id="f4b4e-160">Relace ukončena, zavřít nebo přerušení kanál s relacemi.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-160">Likewise, sessions are terminated by closing or aborting a sessionful channel.</span></span>  
  
 <span data-ttu-id="f4b4e-161">Výjimkou je <xref:System.ServiceModel.Channels.IDuplexSessionChannel> používaný pro odesílání a přijímání zpráv ve tvaru relacemi, duplexní komunikace.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-161">The exception to this is <xref:System.ServiceModel.Channels.IDuplexSessionChannel> which is used for both sending and receiving messages in a duplex, sessionful communication pattern.</span></span> <span data-ttu-id="f4b4e-162">Je možné, že jedné straně budou chtít zastavit odesílání zpráv, ale i nadále přijímat zprávy proto při použití <xref:System.ServiceModel.Channels.IDuplexSessionChannel> mechanismus, který vám umožní zavřete výstup relace označující odeslat další zprávy, nebudou ale ponechali relaci vstupní otevřít, takže budete moci přijímat zprávy.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-162">It is possible that one side will want to stop sending messages but continue to receive messages therefore when using <xref:System.ServiceModel.Channels.IDuplexSessionChannel> there is a mechanism that lets you close the output session indicating you will not send any more messages but keep the input session opened allowing you to continue to receive messages.</span></span>  
  
 <span data-ttu-id="f4b4e-163">Obecně platí relace jsou uzavřeny na straně pro odchozí a ne na straně pro příchozí.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-163">In general, sessions are closed on the outgoing side and not on the incoming side.</span></span> <span data-ttu-id="f4b4e-164">To znamená kanály relacemi výstup je možné uzavřít, a tím řádně ukončení relace.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-164">That is, sessionful output channels can be closed, thereby cleanly terminating the session.</span></span> <span data-ttu-id="f4b4e-165">Zavření kanálu relacemi výstup způsobí, že odpovídající kanálu relací vstupní k vrácení hodnoty null pro volání aplikace <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A?displayProperty=nameWithType> na <xref:System.ServiceModel.Channels.IDuplexSessionChannel>.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-165">Closing a sessionful output channel causes the corresponding sessionful input channel to return null to the application calling <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A?displayProperty=nameWithType> on the <xref:System.ServiceModel.Channels.IDuplexSessionChannel>.</span></span>  
  
 <span data-ttu-id="f4b4e-166">Ale nesmí relacemi vstupní kanály uzavřen, není-li <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A?displayProperty=nameWithType> na <xref:System.ServiceModel.Channels.IDuplexSessionChannel> , vrátí hodnotu null, která určuje, že relace již byl uzavřen.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-166">However sessionful input channels should not be closed unless <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A?displayProperty=nameWithType> on the <xref:System.ServiceModel.Channels.IDuplexSessionChannel> returns null, indicating that the session is already closed.</span></span> <span data-ttu-id="f4b4e-167">Pokud <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A?displayProperty=nameWithType> na <xref:System.ServiceModel.Channels.IDuplexSessionChannel> má není vrátil hodnotu null, zavření vstupní kanál s relacemi může vyvolat výjimku, protože obdržet neočekávanou zprávy při zavírání.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-167">If <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A?displayProperty=nameWithType> on the <xref:System.ServiceModel.Channels.IDuplexSessionChannel> has not returned null, closing a sessionful input channel may throw an exception because it may receive unexpected messages while closing.</span></span> <span data-ttu-id="f4b4e-168">Pokud příjemce, které chcete ukončit relaci před odesílatele, by měly volat <xref:System.ServiceModel.ICommunicationObject.Abort%2A> na vstupní kanál, který náhle ukončí relace.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-168">If a receiver wishes to terminate a session before the sender does, it should call <xref:System.ServiceModel.ICommunicationObject.Abort%2A> on the input channel, which abruptly terminates the session.</span></span>  
  
## <a name="writing-sessionful-channels"></a><span data-ttu-id="f4b4e-169">Zápis Sessionful kanály</span><span class="sxs-lookup"><span data-stu-id="f4b4e-169">Writing Sessionful Channels</span></span>  
 <span data-ttu-id="f4b4e-170">Jako autor kanálu relací jsou pár věcí, které musíte provést kanál zajistit relací.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-170">As a sessionful channel author, there are a few things your channel must do to provide sessions.</span></span> <span data-ttu-id="f4b4e-171">Na straně odesílání kanál, musí:</span><span class="sxs-lookup"><span data-stu-id="f4b4e-171">On the send side, your channel needs to:</span></span>  
  
-   <span data-ttu-id="f4b4e-172">Pro každý nový kanál vytvořte novou relaci a přidružte ji k nové relaci id, které jsou jedinečné řetězce.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-172">For each new channel, create a new session and associate it with a new session id which is a unique string.</span></span> <span data-ttu-id="f4b4e-173">Nebo získejte novou relaci z kanálu relací níže v zásobníku.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-173">Or obtain a new session from the sessionful channel below you in the stack.</span></span>  
  
-   <span data-ttu-id="f4b4e-174">Pro každá zpráva odeslaná pomocí tohoto kanálu Pokud kanál vytvořit relaci (na rozdíl od jeho získání z vrstvy níže), budete muset přidružit relace zprávy.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-174">For each message sent using this channel, if your channel created the session (as opposed to obtaining it from the layer below you), you need to associate the message with the session.</span></span> <span data-ttu-id="f4b4e-175">Pro kanály protokolů to je obvykle potřeba přidání hlavičky SOAP.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-175">For protocol channels, this is typically done by adding a SOAP header.</span></span> <span data-ttu-id="f4b4e-176">Pro přenosové kanály je obvykle důvodem vytvořením nového připojení přenosu nebo přidání informací o relaci rámcovacích protokolu.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-176">For transport channels, this is typically done by creating a new transport connection or adding session information to the framing protocol.</span></span>  
  
-   <span data-ttu-id="f4b4e-177">Každá zpráva odeslaná pomocí tohoto kanálu budete muset zadat záruky doručení uvedených výše.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-177">For each message sent using this channel, you need to provide the delivery guarantees mentioned above.</span></span> <span data-ttu-id="f4b4e-178">Pokud se spoléhat na kanál níže zadejte relace, bude tento kanál také poskytovat záruky doručení.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-178">If you are relying on the channel below you to provide the session, that channel will also provide the delivery guarantees.</span></span> <span data-ttu-id="f4b4e-179">Pokud zadáváte relaci sami, potřebujete implementovat tyto záruky jako součást vaší protokolu.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-179">If you’re providing the session yourself, you need to implement those guarantees as part of your protocol.</span></span> <span data-ttu-id="f4b4e-180">Obecně platí Pokud píšete protokol kanálu, který předpokládá WCF na obou stranách můžete vyžadují přenos TCP nebo kanál spolehlivé zasílání zpráv a spoléhají na některý zajistit relaci.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-180">In general, if you are writing a protocol channel that assumes WCF on both sides you may require the TCP transport or the Reliable Messaging channel and rely on either one to provide a session.</span></span>  
  
-   <span data-ttu-id="f4b4e-181">Když <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType> je volána v kanálu, proveďte nezbytné práce k ukončení relace pomocí zadaného časového limitu nebo výchozí nastavení.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-181">When <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType> is called on your channel, perform the necessary work to close the session using either the specified timeout or the default one.</span></span> <span data-ttu-id="f4b4e-182">To může být stejně jednoduché jako volání <xref:System.ServiceModel.ICommunicationObject.Close%2A> na kanálu níže můžete (Pokud jste právě získali relace z něj) nebo odesílání speciální protokolu SOAP zprávy nebo uzavřením připojení přenosu.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-182">This can be as simple as calling <xref:System.ServiceModel.ICommunicationObject.Close%2A> on the channel below you (if you just obtained the session from it) or sending a special SOAP message or closing a transport connection.</span></span>  
  
-   <span data-ttu-id="f4b4e-183">Když <xref:System.ServiceModel.ICommunicationObject.Abort%2A> je volána v kanálu, bude relace ukončena náhle bez provádění vstupně-výstupní operace.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-183">When <xref:System.ServiceModel.ICommunicationObject.Abort%2A> is called on your channel, terminate the session abruptly without performing I/O.</span></span> <span data-ttu-id="f4b4e-184">To může znamenat žádným způsobem nebo může zahrnovat přerušení připojení k síti nebo jiný prostředek.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-184">This may mean doing nothing or may involve aborting a network connection or some other resource.</span></span>  
  
 <span data-ttu-id="f4b4e-185">Na straně příjmu kanál, musí:</span><span class="sxs-lookup"><span data-stu-id="f4b4e-185">On the receive side, your channel needs to:</span></span>  
  
-   <span data-ttu-id="f4b4e-186">Pro příchozí zprávy musí rozpoznat naslouchací proces kanálu nástroje, které patří do relace.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-186">For each incoming message, the channel listener must detect the session it belongs to.</span></span> <span data-ttu-id="f4b4e-187">Pokud je to první zprávu v relaci, musíte vytvořit nový kanál a vrátit z volání naslouchací proces kanálu nástroje <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-187">If this is the first message in the session, the channel listener must create a new channel and return it from the call to <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f4b4e-188">V opačném případě musí naslouchací proces kanálu nástroje najít existující kanálu, který odpovídá relace a doručení zprávy prostřednictvím tohoto kanálu.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-188">Otherwise the channel listener must find the existing channel that corresponds to the session and deliver the message through that channel.</span></span>  
  
-   <span data-ttu-id="f4b4e-189">Pokud kanál poskytuje relace (spolu s záruky požadované doručení) může být na straně příjmu nutné provést některé akce, jako je například změnit pořadí zprávy nebo odeslání potvrzení.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-189">If your channel is providing the session (along with the required delivery guarantees) the receive side may be required to perform some actions such as re-order messages or send acknowledgements.</span></span>  
  
-   <span data-ttu-id="f4b4e-190">Když <xref:System.ServiceModel.ICommunicationObject.Close%2A> je volána v kanálu, proveďte nezbytné práce k ukončení relace zadaného časového limitu nebo výchozí nastavení.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-190">When <xref:System.ServiceModel.ICommunicationObject.Close%2A> is called on your channel, perform the necessary work to close the session either the specified timeout or the default one.</span></span> <span data-ttu-id="f4b4e-191">To může vést k výjimkám, pokud kanál přijme zprávu o při čekání na časový limit pro uzavření vyprší.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-191">This could result in exceptions if the channel receives a message while waiting for the close timeout to expire.</span></span> <span data-ttu-id="f4b4e-192">Je to způsobeno kanál bude ve stavu ukončovací přijme nějakou zprávu, takže by výjimku.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-192">That’s because the channel will be in the Closing state when it receives a message so it would throw.</span></span>  
  
-   <span data-ttu-id="f4b4e-193">Když <xref:System.ServiceModel.ICommunicationObject.Abort%2A> je volána v kanálu, bude relace ukončena náhle bez provádění vstupně-výstupní operace.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-193">When <xref:System.ServiceModel.ICommunicationObject.Abort%2A> is called on your channel, terminate the session abruptly without performing I/O.</span></span> <span data-ttu-id="f4b4e-194">To znovu, může to znamenat žádným způsobem nebo může zahrnovat přerušení připojení k síti nebo jiný prostředek.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-194">Again, this may mean doing nothing or may involve aborting a network connection or some other resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b4e-195">Viz také</span><span class="sxs-lookup"><span data-stu-id="f4b4e-195">See Also</span></span>  
 [<span data-ttu-id="f4b4e-196">Přehled modelu kanálu</span><span class="sxs-lookup"><span data-stu-id="f4b4e-196">Channel Model Overview</span></span>](../../../../docs/framework/wcf/extending/channel-model-overview.md)