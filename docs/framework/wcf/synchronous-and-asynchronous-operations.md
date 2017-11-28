---
title: "Synchronní a asynchronní operace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], synchronous operations
- service contracts [WCF], asynchronous operations
ms.assetid: db8a51cb-67e6-411b-9035-e5821ed350c9
caps.latest.revision: "24"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 106a3faf11c1568f144d42514b64f4d336cf447c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="synchronous-and-asynchronous-operations"></a><span data-ttu-id="f166d-102">Synchronní a asynchronní operace</span><span class="sxs-lookup"><span data-stu-id="f166d-102">Synchronous and Asynchronous Operations</span></span>
<span data-ttu-id="f166d-103">Toto téma popisuje implementace a volání operace asynchronní služby.</span><span class="sxs-lookup"><span data-stu-id="f166d-103">This topic discusses implementing and calling asynchronous service operations.</span></span>  
  
 <span data-ttu-id="f166d-104">Mnoho aplikací volat metody asynchronně, protože umožní aplikaci pokračovat v provádění užitečné pracovní při volání metody, které běží.</span><span class="sxs-lookup"><span data-stu-id="f166d-104">Many applications call methods asynchronously because it enables the application to continue doing useful work while the method call runs.</span></span> [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="f166d-105">služby a klienti mohou účastnit volání asynchronní operaci na dvou různých úrovních aplikace, které poskytují [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] aplikace i větší flexibilitu, chcete-li maximalizovat propustnost porovnán s interaktivity.</span><span class="sxs-lookup"><span data-stu-id="f166d-105"> services and clients can participate in asynchronous operation calls at two distinct levels of the application, which provide [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] applications even more flexibility to maximize throughput balanced against interactivity.</span></span>  
  
## <a name="types-of-asynchronous-operations"></a><span data-ttu-id="f166d-106">Typy asynchronních operací</span><span class="sxs-lookup"><span data-stu-id="f166d-106">Types of Asynchronous Operations</span></span>  
 <span data-ttu-id="f166d-107">Všechny služby měnící [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], bez ohledu na typy parametry a návratové hodnoty, použijte [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] atributy zadat vzorce výměny zpráv konkrétní mezi klientem a službou.</span><span class="sxs-lookup"><span data-stu-id="f166d-107">All service contracts in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], no matter the parameters types and return values, use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] attributes to specify a particular message exchange pattern between client and service.</span></span> [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="f166d-108">automaticky směruje příchozí a odchozí zprávy do příslušné službě operaci nebo spuštění kódu klienta.</span><span class="sxs-lookup"><span data-stu-id="f166d-108"> automatically routes inbound and outbound messages to the appropriate service operation or running client code.</span></span>  
  
 <span data-ttu-id="f166d-109">Klient má pouze kontrakt služby, který určuje vzorce výměny zpráv pro konkrétní operaci.</span><span class="sxs-lookup"><span data-stu-id="f166d-109">The client possesses only the service contract, which specifies the message exchange pattern for a particular operation.</span></span> <span data-ttu-id="f166d-110">Klienti nabízejí jakékoli programovací model, která si vyberou, vývojář tak dlouho, dokud se zjištěnými základní vzorce výměny zpráv.</span><span class="sxs-lookup"><span data-stu-id="f166d-110">Clients can offer the developer any programming model they choose, so long as the underlying message exchange pattern is observed.</span></span> <span data-ttu-id="f166d-111">Ano příliš, můžete služby implementovat operations žádným způsobem tak dlouho, dokud se zjištěnými vzoru zadané zprávy.</span><span class="sxs-lookup"><span data-stu-id="f166d-111">So, too, can services implement operations in any manner, so long as the specified message pattern is observed.</span></span>  
  
 <span data-ttu-id="f166d-112">Nezávislost služby smlouvy buď z službu nebo implementace klienta umožňuje následující formy asynchronního spuštění v [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] aplikace:</span><span class="sxs-lookup"><span data-stu-id="f166d-112">The independence of the service contract from either the service or client implementation enables the following forms of asynchronous execution in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] applications:</span></span>  
  
-   <span data-ttu-id="f166d-113">Klienty můžete vyvolat operace žádosti a odpovědi asynchronně pomocí exchange synchronní zprávy.</span><span class="sxs-lookup"><span data-stu-id="f166d-113">Clients can invoke request/response operations asynchronously using a synchronous message exchange.</span></span>  
  
-   <span data-ttu-id="f166d-114">Služby můžete implementovat operaci žádosti a odpovědi asynchronně pomocí exchange synchronní zprávy.</span><span class="sxs-lookup"><span data-stu-id="f166d-114">Services can implement a request/response operation asynchronously using a synchronous message exchange.</span></span>  
  
-   <span data-ttu-id="f166d-115">Výměny zpráv může být jednosměrné, bez ohledu na implementaci klienta nebo služby.</span><span class="sxs-lookup"><span data-stu-id="f166d-115">Message exchanges can be one-way, regardless of the implementation of the client or service.</span></span>  
  
### <a name="suggested-asynchronous-scenarios"></a><span data-ttu-id="f166d-116">Navrhované asynchronní scénáře</span><span class="sxs-lookup"><span data-stu-id="f166d-116">Suggested Asynchronous Scenarios</span></span>  
 <span data-ttu-id="f166d-117">Použijte asynchronní přístup v implementaci operace služby, pokud implementace služby operace zavolá blokování, jako je například pracuje vstupně-výstupní operace.</span><span class="sxs-lookup"><span data-stu-id="f166d-117">Use an asynchronous approach in a service operation implementation if the operation service implementation makes a blocking call, such as doing I/O work.</span></span> <span data-ttu-id="f166d-118">Pokud jste v implementaci asynchronní operaci, pokuste se volání asynchronních operací a metody rozšíření cesty asynchronní volání, pokud je to možné.</span><span class="sxs-lookup"><span data-stu-id="f166d-118">When you are in an asynchronous operation implementation, try to call asynchronous operations and methods to extend the asynchronous call path as far as possible.</span></span> <span data-ttu-id="f166d-119">Například volání `BeginOperationTwo()` uvnitř `BeginOperationOne()`.</span><span class="sxs-lookup"><span data-stu-id="f166d-119">For example, call a `BeginOperationTwo()` from within `BeginOperationOne()`.</span></span>  
  
-   <span data-ttu-id="f166d-120">Použijte asynchronní přístup v klientovi nebo volající aplikace v následujících případech:</span><span class="sxs-lookup"><span data-stu-id="f166d-120">Use an asynchronous approach in a client or calling application in the following cases:</span></span>  
  
-   <span data-ttu-id="f166d-121">Pokud jsou volání operace z aplikace střední vrstvy.</span><span class="sxs-lookup"><span data-stu-id="f166d-121">If you are invoking operations from a middle-tier application.</span></span> <span data-ttu-id="f166d-122">([!INCLUDE[crabout](../../../includes/crabout-md.md)] takových scénářů, najdete v části [klientské aplikace střední vrstvy](../../../docs/framework/wcf/feature-details/middle-tier-client-applications.md).)</span><span class="sxs-lookup"><span data-stu-id="f166d-122">([!INCLUDE[crabout](../../../includes/crabout-md.md)] such scenarios, see [Middle-Tier Client Applications](../../../docs/framework/wcf/feature-details/middle-tier-client-applications.md).)</span></span>  
  
-   <span data-ttu-id="f166d-123">Pokud jsou volání operace v rámci stránky ASP.NET, použijte asynchronní stránky.</span><span class="sxs-lookup"><span data-stu-id="f166d-123">If you are invoking operations within an ASP.NET page, use asynchronous pages.</span></span>  
  
-   <span data-ttu-id="f166d-124">Pokud jsou volání operace z jakékoli aplikace, který je zřetězený, například Windows Forms nebo [!INCLUDE[avalon1](../../../includes/avalon1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f166d-124">If you are invoking operations from any application that is single threaded, such as Windows Forms or [!INCLUDE[avalon1](../../../includes/avalon1-md.md)].</span></span> <span data-ttu-id="f166d-125">Při použití na základě událostí asynchronní volání modelu, výsledek událost se vyvolá při vlákna uživatelského rozhraní, aniž by bylo potřeba zpracovat více vláken, sami přidání odezvy k aplikaci.</span><span class="sxs-lookup"><span data-stu-id="f166d-125">When using the event-based asynchronous calling model, the result event is raised on the UI thread, adding responsiveness to the application without requiring you to handle multiple threads yourself.</span></span>  
  
-   <span data-ttu-id="f166d-126">Obecně platí Pokud máte možnost volby mezi synchronní a asynchronní volání, zvolte asynchronního volání.</span><span class="sxs-lookup"><span data-stu-id="f166d-126">In general, if you have a choice between a synchronous and asynchronous call, choose the asynchronous call.</span></span>  
  
### <a name="implementing-an-asynchronous-service-operation"></a><span data-ttu-id="f166d-127">Implementace operace asynchronní služby</span><span class="sxs-lookup"><span data-stu-id="f166d-127">Implementing an Asynchronous Service Operation</span></span>  
 <span data-ttu-id="f166d-128">Asynchronní operace můžete implementovat pomocí jedné z těchto tří metod:</span><span class="sxs-lookup"><span data-stu-id="f166d-128">Asynchronous operations can be implemented by using one of the three following methods:</span></span>  
  
1.  <span data-ttu-id="f166d-129">Asynchronní vzor založený na úlohách</span><span class="sxs-lookup"><span data-stu-id="f166d-129">The task-based asynchronous pattern</span></span>  
  
2.  <span data-ttu-id="f166d-130">Asynchronní vzor založený na událostech</span><span class="sxs-lookup"><span data-stu-id="f166d-130">The event-based asynchronous pattern</span></span>  
  
3.  <span data-ttu-id="f166d-131">Asynchronní vzor IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="f166d-131">The IAsyncResult asynchronous pattern</span></span>  
  
#### <a name="task-based-asynchronous-pattern"></a><span data-ttu-id="f166d-132">Asynchronní vzor založený na úlohách</span><span class="sxs-lookup"><span data-stu-id="f166d-132">Task-Based Asynchronous Pattern</span></span>  
 <span data-ttu-id="f166d-133">Asynchronní vzor založený na úlohách je upřednostňovaný způsob, jak implementovat asynchronní operace, protože je nejjednodušší a většina forward přímo.</span><span class="sxs-lookup"><span data-stu-id="f166d-133">The task-based asynchronous pattern is the preferred way to implement asynchronous operations because it is the easiest and most straight forward.</span></span> <span data-ttu-id="f166d-134">Při použití této metody jednoduše implementovat vaše operace služby a zadejte návratový typ úlohy\<T >, kde T představuje typ vrácený logický provoz.</span><span class="sxs-lookup"><span data-stu-id="f166d-134">To use this method simply implement your service operation and specify a return type of Task\<T>, where T is the type returned by the logical operation.</span></span> <span data-ttu-id="f166d-135">Příklad:</span><span class="sxs-lookup"><span data-stu-id="f166d-135">For example:</span></span>  
  
```csharp  
public class SampleService:ISampleService   
{   
   // ...  
   public async Task<string> SampleMethodTaskAsync(string msg)   
   {   
      return Task<string>.Factory.StartNew(() =>   
      {   
         return msg;   
      });   
   }  
   // ...  
}  
```  
  
 <span data-ttu-id="f166d-136">Operace SampleMethodTaskAsync vrátí úloh\<řetězec > protože logický provoz vrátí řetězec.</span><span class="sxs-lookup"><span data-stu-id="f166d-136">The SampleMethodTaskAsync operation returns Task\<string> because the logical operation returns a string.</span></span> <span data-ttu-id="f166d-137">Další informace o asynchronní vzor založený na úlohách najdete v tématu [The Task-Based asynchronní vzor](http://go.microsoft.com/fwlink/?LinkId=232504).</span><span class="sxs-lookup"><span data-stu-id="f166d-137">For more information about the task-based asynchronous pattern, see [The Task-Based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=232504).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f166d-138">Při použití asynchronní vzor založený na úlohách, T:System.AggregateException může vyvolat, když dojde k výjimce při čekání na dokončení operace.</span><span class="sxs-lookup"><span data-stu-id="f166d-138">When using the task-based asynchronous pattern, a T:System.AggregateException may be thrown if an exception occurs while waiting on the completion of the operation.</span></span> <span data-ttu-id="f166d-139">Tato výjimka může dojít u klienta nebo služby</span><span class="sxs-lookup"><span data-stu-id="f166d-139">This exception may occur on the client or services</span></span>  
  
#### <a name="event-based-asynchronous-pattern"></a><span data-ttu-id="f166d-140">Asynchronní vzor založený na událostech</span><span class="sxs-lookup"><span data-stu-id="f166d-140">Event-Based Asynchronous Pattern</span></span>  
 <span data-ttu-id="f166d-141">Služba, která podporuje asynchronní vzor na základě událostí bude mít jednu nebo více operací s názvem MethodNameAsync.</span><span class="sxs-lookup"><span data-stu-id="f166d-141">A service that supports the Event-based Asynchronous Pattern will have one or more operations named MethodNameAsync.</span></span> <span data-ttu-id="f166d-142">Tyto metody mohou zrcadlení synchronní verze, které provádět stejné operace na aktuální vlákno.</span><span class="sxs-lookup"><span data-stu-id="f166d-142">These methods may mirror synchronous versions, which perform the same operation on the current thread.</span></span> <span data-ttu-id="f166d-143">Třídy mohou mít i MethodNameCompleted událostí a může mít MethodNameAsyncCancel (nebo jednoduše CancelAsync) metoda.</span><span class="sxs-lookup"><span data-stu-id="f166d-143">The class may also have a MethodNameCompleted event and it may have a MethodNameAsyncCancel (or simply CancelAsync) method.</span></span> <span data-ttu-id="f166d-144">Klient chtějí operaci volat definuje obslužnou rutinu události, která se má volat po dokončení operace</span><span class="sxs-lookup"><span data-stu-id="f166d-144">A client wishing to call the operation will define an event handler to be called when the operation completes,</span></span>  
  
 <span data-ttu-id="f166d-145">Následující fragment kódu ukazuje, jak se deklarovat asynchronních operací s použitím asynchronního vzoru založeného na událostech.</span><span class="sxs-lookup"><span data-stu-id="f166d-145">The following code snippet illustrates how to declare asynchronous operations using the event-based asynchronous pattern.</span></span>  
  
```csharp  
public class AsyncExample  
{  
    // Synchronous methods.  
    public int Method1(string param);  
    public void Method2(double param);  
  
    // Asynchronous methods.  
    public void Method1Async(string param);  
    public void Method1Async(string param, object userState);  
    public event Method1CompletedEventHandler Method1Completed;  
  
    public void Method2Async(double param);  
    public void Method2Async(double param, object userState);  
    public event Method2CompletedEventHandler Method2Completed;  
  
    public void CancelAsync(object userState);  
  
    public bool IsBusy { get; }  
  
    // Class implementation not shown.  
}  
```  
  
 <span data-ttu-id="f166d-146">Další informace o asynchronní vzor založený na událostech najdete v tématu [The Event-Based asynchronní vzor](http://go.microsoft.com/fwlink/?LinkId=232515).</span><span class="sxs-lookup"><span data-stu-id="f166d-146">For more information about the Event-based Asynchronous Pattern, see [The Event-Based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=232515).</span></span>  
  
#### <a name="iasyncresult-asynchronous-pattern"></a><span data-ttu-id="f166d-147">Asynchronní vzor IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="f166d-147">IAsyncResult Asynchronous Pattern</span></span>  
 <span data-ttu-id="f166d-148">Operace služby můžou se implementovat v k asynchronní způsobem pomocí [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] asynchronní programování vzor a označení `<Begin>` metoda s <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> vlastnost nastavena na hodnotu `true`.</span><span class="sxs-lookup"><span data-stu-id="f166d-148">A service operation can be implemented in an asynchronous fashion using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] asynchronous programming pattern and marking the `<Begin>` method with the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property set to `true`.</span></span> <span data-ttu-id="f166d-149">V takovém případě je vystaven asynchronní operaci v metadatech ve stejném tvaru jako synchronní operace: je zpřístupněná jako jednu operaci s zprávu požadavku a odpovědi korelační zprávou.</span><span class="sxs-lookup"><span data-stu-id="f166d-149">In this case, the asynchronous operation is exposed in metadata in the same form as a synchronous operation: It is exposed as a single operation with a request message and a correlated response message.</span></span> <span data-ttu-id="f166d-150">Programovací modely klienta potom si zvolí.</span><span class="sxs-lookup"><span data-stu-id="f166d-150">Client programming models then have a choice.</span></span> <span data-ttu-id="f166d-151">Tento vzor může představovat jako synchronní operace nebo některého asynchronní tak dlouho, dokud při vyvolání služby systému exchange zpráv požadavků a odpovědí probíhá.</span><span class="sxs-lookup"><span data-stu-id="f166d-151">They can represent this pattern as a synchronous operation or as an asynchronous one, so long as when the service is invoked a request-response message exchange takes place.</span></span>  
  
 <span data-ttu-id="f166d-152">Obecně platí s asynchronní povaha v systémech, by neměl být závislý na vláken.</span><span class="sxs-lookup"><span data-stu-id="f166d-152">In general, with the asynchronous nature of the systems, you should not take a dependency on the threads.</span></span>  <span data-ttu-id="f166d-153">Nejspolehlivějším způsobem předávání dat různé fáze zpracování operace odesílání je použití rozšíření.</span><span class="sxs-lookup"><span data-stu-id="f166d-153">The most reliable way of passing data to various stages of operation dispatch processing is to use extensions.</span></span>  
  
 <span data-ttu-id="f166d-154">Příklad, naleznete v části [postupy: implementace operace asynchronní služby](../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="f166d-154">For an example, see [How to: Implement an Asynchronous Service Operation](../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span>  
  
 <span data-ttu-id="f166d-155">K definování kontraktu operace `X` se asynchronně spustí bez ohledu na to, jak je volána v aplikaci klienta:</span><span class="sxs-lookup"><span data-stu-id="f166d-155">To define a contract operation `X` that is executed asynchronously regardless of how it is called in the client application:</span></span>  
  
-   <span data-ttu-id="f166d-156">Definovat dvě metody pomocí vzoru `BeginOperation` a `EndOperation`.</span><span class="sxs-lookup"><span data-stu-id="f166d-156">Define two methods using the pattern `BeginOperation` and `EndOperation`.</span></span>  
  
-   <span data-ttu-id="f166d-157">`BeginOperation` Metoda zahrnuje `in` a `ref` parametry pro provoz a vrátí <xref:System.IAsyncResult> typu.</span><span class="sxs-lookup"><span data-stu-id="f166d-157">The `BeginOperation` method includes `in` and `ref` parameters for the operation and returns an <xref:System.IAsyncResult> type.</span></span>  
  
-   <span data-ttu-id="f166d-158">`EndOperation` Metoda zahrnuje <xref:System.IAsyncResult> parametr společně s `out` a `ref` parametry a vrátí operace návratový typ.</span><span class="sxs-lookup"><span data-stu-id="f166d-158">The `EndOperation` method includes an <xref:System.IAsyncResult> parameter as well as the `out` and `ref` parameters and returns the operations return type.</span></span>  
  
 <span data-ttu-id="f166d-159">Například viz následující metodu.</span><span class="sxs-lookup"><span data-stu-id="f166d-159">For example, see the following method.</span></span>  
  
```csharp  
int DoWork(string data, ref string inout, out string outonly)  
```  
  
```vb  
Function DoWork(ByVal data As String, ByRef inout As String, _out outonly As out) As Integer  
```  
  
 <span data-ttu-id="f166d-160">Pokud chcete vytvořit asynchronní operaci, by se tyto dvě metody:</span><span class="sxs-lookup"><span data-stu-id="f166d-160">To create an asynchronous operation, the two methods would be:</span></span>  
  
```csharp  
[OperationContract(AsyncPattern=true)]IAsyncResult BeginDoWork(string data,                           ref string inout,                           AsyncCallback callback,                           object state);int EndDoWork(ref string inout, out string outonly, IAsyncResult result);  
```  
  
```vb  
<OperationContract(AsyncPattern := True)>  _Function BeginDoWork(ByVal data As String, _                 ByRef inout As String, _                 ByVal callback As AsyncCallback, _                 ByVal state As Object) _As IAsyncResult Function EndDoWork(ByRef inout As String, _        ByRef outonly As String, _        ByVal result As IAsyncResult) _As Integer  
```  
  
> [!NOTE]
>  <span data-ttu-id="f166d-161"><xref:System.ServiceModel.OperationContractAttribute> Atributu se použije pouze `BeginDoWork` metoda.</span><span class="sxs-lookup"><span data-stu-id="f166d-161">The <xref:System.ServiceModel.OperationContractAttribute> attribute is applied only to the `BeginDoWork` method.</span></span> <span data-ttu-id="f166d-162">Výsledný smlouva obsahuje jednu operaci WSDL s názvem `DoWork`.</span><span class="sxs-lookup"><span data-stu-id="f166d-162">The resulting contract has one WSDL operation named `DoWork`.</span></span>  
  
### <a name="client-side-asynchronous-invocations"></a><span data-ttu-id="f166d-163">Asynchronní volání na straně klienta</span><span class="sxs-lookup"><span data-stu-id="f166d-163">Client-Side Asynchronous Invocations</span></span>  
 <span data-ttu-id="f166d-164">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] klientská aplikace můžete použít některou ze tří asynchronní volání modelů popsané</span><span class="sxs-lookup"><span data-stu-id="f166d-164">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client application can use any of three asynchronous calling models described previously</span></span>  
  
 <span data-ttu-id="f166d-165">Při použití modelu založený na úlohách, jednoduše volejte operace pomocí – klíčové slovo await, jak je znázorněno v následující fragment kódu.</span><span class="sxs-lookup"><span data-stu-id="f166d-165">When using the task-based model, simply call the operation using the await keyword as shown in the following code snippet.</span></span>  
  
```  
await simpleServiceClient.SampleMethodTaskAsync("hello, world");  
```  
  
 <span data-ttu-id="f166d-166">Použití asynchronního vzoru založeného na událostech pouze vyžaduje přidání, které obslužné rutiny události pro příjem oznámení odpovědi – a výsledný událost se vyvolá při uživatelské rozhraní vlákno automaticky.</span><span class="sxs-lookup"><span data-stu-id="f166d-166">Using the event-based asynchronous pattern only requires adding an event handler to receive a notification of the response -- and the resulting event is raised on the user interface thread automatically.</span></span> <span data-ttu-id="f166d-167">Pro tento postup, zadat oba seznamy **/async** a **/tcv:Version35** příkaz Možnosti [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), jako v následující Příklad.</span><span class="sxs-lookup"><span data-stu-id="f166d-167">To use this approach, specify both the **/async** and **/tcv:Version35** command options with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), as in the following example.</span></span>  
  
```  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async /tcv:Version35  
```  
  
 <span data-ttu-id="f166d-168">Když to uděláte, Svcutil.exe generuje [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] třída klienta s infrastrukturou událostí, která umožňuje volající aplikace k implementaci a přiřadit obslužné rutiny události přijmout odpověď a proveďte příslušnou akci.</span><span class="sxs-lookup"><span data-stu-id="f166d-168">When this is done, Svcutil.exe generates a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client class with the event infrastructure that enables the calling application to implement and assign an event handler to receive the response and take the appropriate action.</span></span> <span data-ttu-id="f166d-169">Úplný příklad najdete v tématu [postupy: asynchronní volání operací služby](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="f166d-169">For a complete example, see [How to: Call Service Operations Asynchronously](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span>  
  
 <span data-ttu-id="f166d-170">Na základě událostí asynchronní modelu, ale je k dispozici pouze v [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f166d-170">The event-based asynchronous model, however, is only available in [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)].</span></span> <span data-ttu-id="f166d-171">Kromě toho není podporován i při [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] při [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kanálem klienta je vytvořená pomocí <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f166d-171">In addition, it is not supported even in [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] when a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client channel is created by using a <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f166d-172">S [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kanálem klienta objekty, je nutné použít <xref:System.IAsyncResult?displayProperty=nameWithType> objekty k vyvolání vaše operace asynchronně.</span><span class="sxs-lookup"><span data-stu-id="f166d-172">With [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client channel objects, you must use <xref:System.IAsyncResult?displayProperty=nameWithType> objects to invoke your operations asynchronously.</span></span> <span data-ttu-id="f166d-173">Chcete-li použít tuto metodu, zadejte **/async** příkaz možnost s [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), jako v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="f166d-173">To use this approach, specify the **/async** command option with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), as in the following example.</span></span>  
  
```  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async   
```  
  
 <span data-ttu-id="f166d-174">Tím se vygeneruje kontraktu služby ve které je modelovaná každé operace jako `<Begin>` metoda s <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> vlastnost nastavena na hodnotu `true` a odpovídající `<End>` metoda.</span><span class="sxs-lookup"><span data-stu-id="f166d-174">This generates a service contract in which each operation is modeled as a `<Begin>` method with the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property set to `true` and a corresponding `<End>` method.</span></span> <span data-ttu-id="f166d-175">Úplný příklad použití <xref:System.ServiceModel.ChannelFactory%601>, najdete v části [postupy: volání operace asynchronně pomocí postupu kanálu](../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="f166d-175">For a complete example using a <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
 <span data-ttu-id="f166d-176">V obou případech aplikace může vyvolat operace asynchronně i v případě, že služba se implementuje synchronně, stejným způsobem, jakým aplikace můžete použít stejný vzor pro vyvolání asynchronně místní synchronní metody.</span><span class="sxs-lookup"><span data-stu-id="f166d-176">In either case, applications can invoke an operation asynchronously even if the service is implemented synchronously, in the same way that an application can use the same pattern to invoke asynchronously a local synchronous method.</span></span> <span data-ttu-id="f166d-177">Jak je implementována operaci není důležité pro klienta. Pokud dorazí zprávu odpovědi, její obsah se odesílají do klienta asynchronní <`End`> metoda a klient načte informace.</span><span class="sxs-lookup"><span data-stu-id="f166d-177">How the operation is implemented is not significant to the client; when the response message arrives, its content is dispatched to the client's asynchronous <`End`> method and the client retrieves the information.</span></span>  
  
### <a name="one-way-message-exchange-patterns"></a><span data-ttu-id="f166d-178">Vzory Exchange jednosměrný zpráv</span><span class="sxs-lookup"><span data-stu-id="f166d-178">One-Way Message Exchange Patterns</span></span>  
 <span data-ttu-id="f166d-179">Můžete také vytvořit vzorce výměny zpráv asynchronní které Jednosměrná operace (operací, pro kterou <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> je `true` mít žádná korelační odpověď) může odeslat v obou směrech klienta služby nezávisle na druhém nebo straně.</span><span class="sxs-lookup"><span data-stu-id="f166d-179">You can also create an asynchronous message exchange pattern in which one-way operations (operations for which the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> is `true` have no correlated response) can be sent in either direction by the client or service independently of the other side.</span></span> <span data-ttu-id="f166d-180">(Tato služba využívá vzorce výměny duplexní zpráv s jednosměrný zprávy.) V takovém případě kontrakt služby určuje exchange jednosměrný zpráva, která můžete implementovat stranách jako asynchronní volání nebo implementace, nebo Ne, podle potřeby.</span><span class="sxs-lookup"><span data-stu-id="f166d-180">(This uses the duplex message exchange pattern with one-way messages.) In this case, the service contract specifies a one-way message exchange that either side can implement as asynchronous calls or implementations, or not, as appropriate.</span></span> <span data-ttu-id="f166d-181">Obecně platí když kontrakt výměnou zpráv, jednosměrné, implementace do značné míry lze asynchronní vzhledem k tomu, že jakmile je odeslána zpráva aplikace čekat na odpověď a můžete pokračovat v provádění jinou práci.</span><span class="sxs-lookup"><span data-stu-id="f166d-181">Generally, when the contract is an exchange of one-way messages, the implementations can largely be asynchronous because once a message is sent the application does not wait for a reply and can continue doing other work.</span></span>  
  
### <a name="event-based-asynchronous-clients-and-message-contracts"></a><span data-ttu-id="f166d-182">Na základě událostí asynchronní klientů a kontrakty zpráv</span><span class="sxs-lookup"><span data-stu-id="f166d-182">Event-based Asynchronous Clients and Message Contracts</span></span>  
 <span data-ttu-id="f166d-183">Podle pokynů návrhu pro asynchronní model na základě událostí stavu, že pokud je vrácen více než jednu hodnotu, se vrátí jednu hodnotu jako `Result` vlastnost a jiné jsou vrácena jako vlastnosti na <xref:System.EventArgs> objektu.</span><span class="sxs-lookup"><span data-stu-id="f166d-183">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="f166d-184">Jeden výsledek tohoto objektu je, že pokud klient naimportuje metadata pomocí možností na základě událostí asynchronní příkaz a operaci vrátí více než jednu hodnotu, výchozí <xref:System.EventArgs> objekt vrátí jednu hodnotu jako `Result` vlastnost a zbývající jsou vlastnosti <xref:System.EventArgs> objektu.</span><span class="sxs-lookup"><span data-stu-id="f166d-184">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.</span></span>  
  
 <span data-ttu-id="f166d-185">Pokud chcete dostávat zprávy objektu jako `Result` vlastnost a mít vrácené hodnoty jako vlastnosti tohoto objektu, použijte **/messageContract** příkaz možnost.</span><span class="sxs-lookup"><span data-stu-id="f166d-185">If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the **/messageContract** command option.</span></span> <span data-ttu-id="f166d-186">Tím se vygeneruje podpisu, který vrátí zprávu odpovědi jako `Result` vlastnost <xref:System.EventArgs> objektu.</span><span class="sxs-lookup"><span data-stu-id="f166d-186">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="f166d-187">Všechny interní návratové hodnoty jsou pak vlastnosti objektu zprávu odpovědi.</span><span class="sxs-lookup"><span data-stu-id="f166d-187">All internal return values are then properties of the response message object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f166d-188">Viz také</span><span class="sxs-lookup"><span data-stu-id="f166d-188">See Also</span></span>  
 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>  
 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>