---
title: WSTrustChannelFactory a WSTrustChannel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96cec467-e963-4132-b18b-7d0b3a2e979f
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e400d68924f1ed57ea1e71892e52f5aae2f5eebc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="wstrustchannelfactory-and-wstrustchannel"></a><span data-ttu-id="2b0e2-102">WSTrustChannelFactory a WSTrustChannel</span><span class="sxs-lookup"><span data-stu-id="2b0e2-102">WSTrustChannelFactory and WSTrustChannel</span></span>
<span data-ttu-id="2b0e2-103">Pokud jste již obeznámeni s Windows Communication Foundation (WCF), víte, že klienta WCF již federační vědět.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-103">If you are already familiar with Windows Communication Foundation (WCF), you know that a WCF client is already federation aware.</span></span> <span data-ttu-id="2b0e2-104">Podle konfigurace klienta WCF s <xref:System.ServiceModel.WSFederationHttpBinding> nebo podobné vlastní vazby, můžete povolit federovaného ověřování do služby.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-104">By configuring a WCF client with a <xref:System.ServiceModel.WSFederationHttpBinding> or similar custom binding, you can enable federated authentication to a service.</span></span>  
  
 <span data-ttu-id="2b0e2-105">WCF získá token, který je vydaný služby tokenů zabezpečení (STS) na pozadí a používá tento token k ověření služby.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-105">WCF obtains the token that is issued by the security token service (STS) behind the scenes and uses this token to authenticate to the service.</span></span> <span data-ttu-id="2b0e2-106">Hlavní omezení tohoto přístupu je, že neexistuje žádná přehled komunikaci klienta se serverem.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-106">The main limitation to this approach is that there is no visibility into the client’s communications with the server.</span></span> <span data-ttu-id="2b0e2-107">WCF automaticky generuje token zabezpečení požadavku (RVNÍ) na službu STS založenou na parametrech vydaných tokenů na vazby.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-107">WCF automatically generates the request security token (RST) to the STS based on the issued token parameters on the binding.</span></span> <span data-ttu-id="2b0e2-108">To znamená, že klienta nelze měnit parametry RVNÍ každý požadavek, zkontrolujte odpovědi tokenu zabezpečení požadavku (RSTR) Chcete-li získat informace, jako jsou deklarace identity zobrazení nebo mezipaměti token pro budoucí použití.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-108">This means that the client cannot vary the RST parameters per request, inspect the request security token response (RSTR) to get information such as display claims, or cache the token for future use.</span></span>  
  
 <span data-ttu-id="2b0e2-109">V současné době je vhodná pro scénáře základní federační klienta WCF.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-109">Currently, the WCF client is suitable for basic federation scenarios.</span></span> <span data-ttu-id="2b0e2-110">Mezi hlavní scénáře, které podporuje Windows Identity Foundation (WIF) ale vyžaduje kontrolu nad RVNÍ na úrovni, který WCF neumožňuje snadno.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-110">However, one of the major scenarios that Windows Identity Foundation (WIF) supports requires control over the RST at a level that WCF does not easily allow.</span></span> <span data-ttu-id="2b0e2-111">Proto WIF přidá funkce, které získáte větší kontrolu nad komunikace s Služba tokenů zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-111">Therefore, WIF adds features that give you more control over communication with the STS.</span></span>  
  
 <span data-ttu-id="2b0e2-112">WIF podporuje následující scénáře federation:</span><span class="sxs-lookup"><span data-stu-id="2b0e2-112">WIF supports the following federation scenarios:</span></span>  
  
-   <span data-ttu-id="2b0e2-113">Pomocí klienta WCF bez závislostí WIF k ověření federované služby</span><span class="sxs-lookup"><span data-stu-id="2b0e2-113">Using a WCF client without any WIF dependencies to authenticate to a federated service</span></span>  
  
-   <span data-ttu-id="2b0e2-114">Povolit WIF na klienta WCF vložení element ActAs nebo OnBehalfOf do RVNÍ na službu STS</span><span class="sxs-lookup"><span data-stu-id="2b0e2-114">Enabling WIF on a WCF client to insert an ActAs or OnBehalfOf element into the RST to the STS</span></span>  
  
-   <span data-ttu-id="2b0e2-115">Použití WIF samostatně k získání tokenu z Služba tokenů zabezpečení a pak povolte klienta WCF k ověřování pro tento token.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-115">Using WIF alone to obtain a token from the STS and then enable a WCF client to authenticate with this token.</span></span> <span data-ttu-id="2b0e2-116">Další informace najdete v tématu [ClaimsAwareWebService](http://go.microsoft.com/fwlink/?LinkID=248406) ukázka.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-116">For more information, see [ClaimsAwareWebService](http://go.microsoft.com/fwlink/?LinkID=248406) sample.</span></span>  
  
 <span data-ttu-id="2b0e2-117">První scénář je není potřeba vysvětlovat: Klienti existující WCF bude pokračovat v práci s WIF předávající strany a STSs.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-117">The first scenario is self-explanatory: Existing WCF clients will continue to work with WIF relying parties and STSs.</span></span> <span data-ttu-id="2b0e2-118">Toto téma popisuje zbývající dva scénáře.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-118">This topic discusses the remaining two scenarios.</span></span>  
  
## <a name="enhancing-an-existing-wcf-client-with-actas--onbehalfof"></a><span data-ttu-id="2b0e2-119">Rozšíření stávajícího klienta WCF s ActAs / OnBehalfOf</span><span class="sxs-lookup"><span data-stu-id="2b0e2-119">Enhancing an Existing WCF Client with ActAs / OnBehalfOf</span></span>  
 <span data-ttu-id="2b0e2-120">Ve scénáři delegování typické identity klienta volá střední vrstvy služby, která pak zavolá back-end službu.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-120">In a typical identity delegation scenario, a client calls a middle-tier service, which then calls a back-end service.</span></span> <span data-ttu-id="2b0e2-121">Služba střední vrstvy funguje jako nebo funguje jménem klienta.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-121">The middle-tier service acts as, or acts on behalf of, the client.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="2b0e2-122">Jaký je rozdíl mezi ActAs a OnBehalfOf?</span><span class="sxs-lookup"><span data-stu-id="2b0e2-122">What is the difference between ActAs and OnBehalfOf?</span></span>  
>   
>  <span data-ttu-id="2b0e2-123">Z hlediska získáváním WS-Trust:</span><span class="sxs-lookup"><span data-stu-id="2b0e2-123">From the WS-Trust procotol standpoint:</span></span>  
>   
>  1.  <span data-ttu-id="2b0e2-124">Element ActAs RVNÍ označuje, že žadatel chce token, který obsahuje deklarace identity o dvou různých entit: žadatel a externí entity reprezentována v elementu ActAs token.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-124">An ActAs RST element indicates that the requestor wants a token that contains claims about two distinct entities: the requestor, and an external entity represented by the token in the ActAs element.</span></span>  
> 2.  <span data-ttu-id="2b0e2-125">Element OnBehalfOf RVNÍ označuje, že žadatel chce token, který obsahuje pouze jednu entitu deklarací identity: externí entitu reprezentovanou objektem token v elementu OnBehalfOf.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-125">An OnBehalfOf RST element indicates that the requestor wants a token that contains claims only about one entity: the external entity represented by the token in the OnBehalfOf element.</span></span>  
>   
>  <span data-ttu-id="2b0e2-126">Funkci ActAs se obvykle používá ve scénářích, které vyžadují složené delegování, kde můžete konečné příjemce vydaných tokenu zkontrolujte řetězu celý delegování a najdete v části nejen klienta, ale všichni zprostředkovatelé.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-126">The ActAs feature is typically used in scenarios that require composite delegation, where the final recipient of the issued token can inspect the entire delegation chain and see not just the client, but all intermediaries.</span></span> <span data-ttu-id="2b0e2-127">To umožňuje, aby ji provést řízení přístupu, auditování a další související aktivity podle řetězu delegování celý identity.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-127">This lets it perform access control, auditing and other related activities based on the entire identity delegation chain.</span></span> <span data-ttu-id="2b0e2-128">Funkci ActAs je běžně používaných v systémech víceúrovňových k ověření a předání informací o identitách mezi vrstvami bez nutnosti předejte tyto informace ve vrstvě aplikace nebo obchodní logiku.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-128">The ActAs feature is commonly used in multi-tiered systems to authenticate and pass information about identities between the tiers without having to pass this information at the application/business logic layer.</span></span>  
>   
>  <span data-ttu-id="2b0e2-129">Funkce OnBehalfOf se používá ve scénářích, kde je důležité pouze identitu původního klienta a je efektivně stejná jako identity zosobnění funkce dostupné v systému Windows.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-129">The OnBehalfOf feature is used in scenarios where only the identity of the original client is important and is effectively the same as the identity impersonation feature available in Windows.</span></span> <span data-ttu-id="2b0e2-130">Když OnBehalfOf se používá, konečné příjemce vydaných tokenu uvidí jenom deklarace identity o původní klienta a informace o prostředníci není zachován.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-130">When OnBehalfOf is used, the final recipient of the issued token can only see claims about the original client, and the information about intermediaries is not preserved.</span></span> <span data-ttu-id="2b0e2-131">Jednou z běžných vzor, kde se používá funkci OnBehalfOf je vzor proxy serveru, kde klient nemůže získat službu STS přímo, ale místo toho komunikuje prostřednictvím proxy serveru brány.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-131">One common pattern where the OnBehalfOf feature is used is the proxy pattern where the client cannot access the STS directly but instead communicates through a proxy gateway.</span></span> <span data-ttu-id="2b0e2-132">Proxy server brány ověří volajícího a vloží informace o volajícím do elementu OnBehalfOf RVNÍ zprávy, které pak odešle skutečné služby tokenů zabezpečení pro zpracování.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-132">The proxy gateway authenticates the caller and puts information about the caller into the OnBehalfOf element of the RST message that it then sends to the real STS for processing.</span></span> <span data-ttu-id="2b0e2-133">Výsledný token obsahuje jenom deklarace identity související se proxy serveru, provedení zcela transparentní proxy serveru k příjemce vydaných tokenu. Všimněte si, že WIF nepodporuje \<wsse: SecurityTokenReference > nebo \<wsa:EndpointReferences > jako podřízený \<wst:OnBehalfOf >.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-133">The resulting token contains only claims related to the client of the proxy, making the proxy completely transparent to the receiver of the issued token.Note that WIF does not support \<wsse:SecurityTokenReference> or \<wsa:EndpointReferences> as a child of \<wst:OnBehalfOf>.</span></span> <span data-ttu-id="2b0e2-134">Specifikace WS-Trust umožňuje tři způsoby, jak identifikovat původnímu žadateli (jménem kterého je funguje proxy serveru).</span><span class="sxs-lookup"><span data-stu-id="2b0e2-134">The WS-Trust specification allows for three ways to identify the original requestor (on behalf of whom the proxy is acting).</span></span> <span data-ttu-id="2b0e2-135">Jsou to:</span><span class="sxs-lookup"><span data-stu-id="2b0e2-135">These are:</span></span>  
>   
>  -   <span data-ttu-id="2b0e2-136">Informace o tokenu zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-136">Security token reference.</span></span> <span data-ttu-id="2b0e2-137">Odkaz na token, buď ve zprávě, nebo může být načtena z vzdálené).</span><span class="sxs-lookup"><span data-stu-id="2b0e2-137">A reference to a token, either in the message, or possibly retrieved out of band).</span></span>  
> -   <span data-ttu-id="2b0e2-138">Odkaz na koncový bod.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-138">Endpoint reference.</span></span> <span data-ttu-id="2b0e2-139">Použít jako klíč pro vyhledávání dat, opět vzdáleně.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-139">Used as a key to look up data, again out of band.</span></span>  
> -   <span data-ttu-id="2b0e2-140">Token zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-140">Security token.</span></span> <span data-ttu-id="2b0e2-141">Identifikuje původní žadatele přímo.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-141">Identifies the original requestor directly.</span></span>  
>   
>  <span data-ttu-id="2b0e2-142">WIF podporuje tokeny pouze zabezpečení, šifrován nebo bez šifrování, jako přímý podřízeného prvku \<wst:OnBehalfOf >.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-142">WIF supports only security tokens, either encrypted or unencrypted, as a direct child element of \<wst:OnBehalfOf>.</span></span>  
  
 <span data-ttu-id="2b0e2-143">Tyto informace předávají v tokenu elementy ActAs a OnBehalfOf RVNÍ WS-Trust Issuer.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-143">This information is conveyed to a WS-Trust issuer using the ActAs and OnBehalfOf token elements in the RST.</span></span>  
  
 <span data-ttu-id="2b0e2-144">WCF zpřístupní bod rozšiřitelnosti na vazba, která umožňuje libovolné elementů XML pro přidání do RVNÍ.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-144">WCF exposes an extensibility point on the binding that allows arbitrary XML elements to be added to the RST.</span></span> <span data-ttu-id="2b0e2-145">Ale vzhledem k tomu, že bod rozšiřitelnosti je vázaný na vazby, scénáře, které vyžadují obsah RVNÍ k odlišení za volání nutné znovu vytvořit klienta pro každé volání, takže se sníží výkon.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-145">However, because the extensibility point is tied to the binding, scenarios that require the RST contents to vary per call must re-create the client for every call, which decreases performance.</span></span> <span data-ttu-id="2b0e2-146">WIF používá rozšiřující metody na `ChannelFactory` třídu, která umožňuje vývojářům připojit žádné token, který je získat vzdálenou správu na RVNÍ.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-146">WIF uses extension methods on the `ChannelFactory` class to allow developers to attach any token that is obtained out of band to the RST.</span></span> <span data-ttu-id="2b0e2-147">Následující příklad kódu ukazuje, jak provést token, který představuje klienta (například X.509, uživatelské jméno nebo token zabezpečení kontrolního výrazu SAML (Markup Language)) a připojte ji k RVNÍ, které je odesláno vystavitele.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-147">The following code example shows how to take a token that represents the client (such as an X.509, username, or Security Assertion Markup Language (SAML) token) and attach it to the RST that is sent to the issuer.</span></span>  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelActingAs<IHelloService>( clientSamlToken );  
serviceChannel.Hello("Hi!");  
```  
  
 <span data-ttu-id="2b0e2-148">WIF poskytuje následující výhody:</span><span class="sxs-lookup"><span data-stu-id="2b0e2-148">WIF provides the following benefits:</span></span>  
  
-   <span data-ttu-id="2b0e2-149">RVNÍ můžete změnit na kanál; střední vrstvy služby nemusí proto se znovu vytvořit vytváření kanálů pro každého klienta, což zvyšuje výkon.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-149">The RST can be modified per channel; therefore, middle-tier services do not have to re-create the channel factory for each client, which improves performance.</span></span>  
  
-   <span data-ttu-id="2b0e2-150">Tento postup funguje s existující klienti WCF, který umožňuje snadnou cestu upgradu pro stávající střední vrstvy služby WCF, které chcete povolit sémantiku delegování identity.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-150">This works with existing WCF clients, which makes an easy upgrade path possible for existing WCF middle-tier services that want to enable identity delegation semantics.</span></span>  
  
 <span data-ttu-id="2b0e2-151">Je však stále žádné Přehled komunikace klienta s Služba tokenů zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-151">However, there is still no visibility into the client’s communication with the STS.</span></span> <span data-ttu-id="2b0e2-152">Podíváme to v třetí scénář.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-152">We’ll examine this in the third scenario.</span></span>  
  
## <a name="communicating-directly-with-an-issuer-and-using-the-issued-token-to-authenticate"></a><span data-ttu-id="2b0e2-153">Komunikovat přímo s vystavitele a k ověření pomocí vydaných tokenu</span><span class="sxs-lookup"><span data-stu-id="2b0e2-153">Communicating Directly with an Issuer and Using the Issued Token to Authenticate</span></span>  
 <span data-ttu-id="2b0e2-154">Pro některé pokročilé scénáře rozšíření klienta WCF nestačí.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-154">For some advanced scenarios, enhancing a WCF client is not enough.</span></span> <span data-ttu-id="2b0e2-155">Vývojáři, kteří používají pouze WCF obvykle používat zprávy v / zpráva se měnící a zpracování na straně klienta analýze odpovědi vystavitele ručně.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-155">Developers who use only WCF typically use Message In / Message Out contracts and handle client-side parsing of the issuer response manually.</span></span>  
  
 <span data-ttu-id="2b0e2-156">Zavádí WIF <xref:System.ServiceModel.Security.WSTrustChannelFactory> a <xref:System.ServiceModel.Security.WSTrustChannel> třídy umožníte klient komunikovat přímo s WS-Trust vystavitele.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-156">WIF introduces the <xref:System.ServiceModel.Security.WSTrustChannelFactory> and <xref:System.ServiceModel.Security.WSTrustChannel> classes to let the client communicate directly with a WS-Trust issuer.</span></span> <span data-ttu-id="2b0e2-157"><xref:System.ServiceModel.Security.WSTrustChannelFactory> a <xref:System.ServiceModel.Security.WSTrustChannel> třídy povolit RVNÍ a RSTR objektů se silným typem tok mezi klientem a vystavitele, jak je znázorněno v následujícím příkladu kódu.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-157">The <xref:System.ServiceModel.Security.WSTrustChannelFactory> and <xref:System.ServiceModel.Security.WSTrustChannel> classes enable strongly typed RST and RSTR objects to flow between the client and issuer, as shown in the following code example.</span></span>  
  
```  
WSTrustChannelFactory trustChannelFactory = new WSTrustChannelFactory( stsBinding, stsAddress );  
WSTrustChannel channel = (WSTrustChannel) trustChannelFactory.CreateChannel();  
RequestSecurityToken rst = new RequestSecurityToken(RequestTypes.Issue);  
rst.AppliesTo = new EndpointAddress(serviceAddress);  
RequestSecurityTokenResponse rstr = null;  
SecurityToken token = channel.Issue(rst, out rstr);  
```  
  
 <span data-ttu-id="2b0e2-158">Všimněte si, že `out` parametr na <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> metoda umožňuje přístup k RSTR kontroly na straně klienta.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-158">Note that the `out` parameter on the <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> method allows access to the RSTR for client-side inspection.</span></span>  
  
 <span data-ttu-id="2b0e2-159">Zatím jste pouze viděli jak získat token.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-159">So far, we’ve only seen how to obtain a token.</span></span> <span data-ttu-id="2b0e2-160">Token, který je vrácen z <xref:System.ServiceModel.Security.WSTrustChannel> objekt `GenericXmlSecurityToken` obsahující všechny informace, které jsou nezbytné pro ověřování k předávající straně.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-160">The token that is returned from the <xref:System.ServiceModel.Security.WSTrustChannel> object is a `GenericXmlSecurityToken` that contains all of the information that is necessary for authentication to a relying party.</span></span> <span data-ttu-id="2b0e2-161">Následující příklad kódu ukazuje, jak používat tento token.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-161">The following code example shows how to use this token.</span></span>  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelWithIssuedToken<IHelloService>( token ); serviceChannel.Hello("Hi!");  
```  
  
 <span data-ttu-id="2b0e2-162"><xref:System.ServiceModel.ChannelFactory%601.CreateChannelWithIssuedToken%2A> Rozšiřující metody na `ChannelFactory` objektu určuje WIF, který jste získali token vzdálené správy a měl by zastavit normální WCF volání vystavitele a místo toho použít token, který jste získali k ověření předávající straně.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-162">The <xref:System.ServiceModel.ChannelFactory%601.CreateChannelWithIssuedToken%2A> extension method on the `ChannelFactory` object indicates to WIF that you have obtained a token out of band, and that it should stop the normal WCF call to the issuer and instead use the token that you obtained to authenticate to the relying party.</span></span> <span data-ttu-id="2b0e2-163">To má tyto výhody:</span><span class="sxs-lookup"><span data-stu-id="2b0e2-163">This has the following benefits:</span></span>  
  
-   <span data-ttu-id="2b0e2-164">Nabízí úplnou kontrolu nad tímto procesem vystavování tokenů.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-164">It gives you complete control over the token issuance process.</span></span>  
  
-   <span data-ttu-id="2b0e2-165">Podporuje ActAs / OnBehalfOf scénáře pomocí přímo odchozí RVNÍ nastavení těchto vlastností.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-165">It supports ActAs / OnBehalfOf scenarios by directly setting these properties on the outgoing RST.</span></span>  
  
-   <span data-ttu-id="2b0e2-166">Umožňuje dynamické klienta vztahu důvěryhodnosti z RSTR obsahu na základě rozhodnutí, která má být provedeno.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-166">It enables dynamic client-side trust decisions to be made based on the contents of the RSTR.</span></span>  
  
-   <span data-ttu-id="2b0e2-167">Umožňuje ukládat do mezipaměti a opakovaně používat token, který je vrácen z <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-167">It lets you cache and reuse the token that is returned from the <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> method.</span></span>  
  
-   <span data-ttu-id="2b0e2-168"><xref:System.ServiceModel.Security.WSTrustChannelFactory>a <xref:System.ServiceModel.Security.WSTrustChannel> povolit pro řízení kanál ukládání do mezipaměti, selhání a obnovení sémantiku podle doporučených postupů WCF.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-168"><xref:System.ServiceModel.Security.WSTrustChannelFactory> and <xref:System.ServiceModel.Security.WSTrustChannel> allow for control of channel caching, fault, and recovery semantics according to WCF best practices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b0e2-169">Viz také</span><span class="sxs-lookup"><span data-stu-id="2b0e2-169">See Also</span></span>  
 [<span data-ttu-id="2b0e2-170">Funkce WIF</span><span class="sxs-lookup"><span data-stu-id="2b0e2-170">WIF Features</span></span>](../../../docs/framework/security/wif-features.md)