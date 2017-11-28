---
title: "Testování služeb ASP.NET Core a webové aplikace"
description: "Architektura Mikroslužeb .NET pro aplikace .NET Kontejnerizované | Testování služeb ASP.NET Core a webové aplikace"
keywords: "Docker, Mikroslužeb, ASP.NET, kontejneru"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f756a679befee676db2bf6d402fd7e34b1621b9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="7e276-104">Testování služeb ASP.NET Core a webové aplikace</span><span class="sxs-lookup"><span data-stu-id="7e276-104">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="7e276-105">Řadiče jsou centrální součástí všechny služby rozhraní API ASP.NET Core a ASP.NET MVC webové aplikace.</span><span class="sxs-lookup"><span data-stu-id="7e276-105">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="7e276-106">Jako takový měli byste mít přitom jistotu, že chovají se jako určený pro vaši aplikaci.</span><span class="sxs-lookup"><span data-stu-id="7e276-106">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="7e276-107">Automatizované testy vám může poskytnout tento spolehlivosti a chyby může zjistit, než dosáhnou produkční.</span><span class="sxs-lookup"><span data-stu-id="7e276-107">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="7e276-108">Budete muset testování chování podle platný nebo neplatný vstupy kontroleru a testování řadiče odpovědí na základě výsledku operace firmy, které provádí.</span><span class="sxs-lookup"><span data-stu-id="7e276-108">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="7e276-109">Tyto typy testů, ale musí mít vaše mikroslužeb:</span><span class="sxs-lookup"><span data-stu-id="7e276-109">However, you should have these types of tests your microservices:</span></span>

-   <span data-ttu-id="7e276-110">Testování částí.</span><span class="sxs-lookup"><span data-stu-id="7e276-110">Unit tests.</span></span> <span data-ttu-id="7e276-111">Tyto Ujistěte se, že jednotlivé součásti aplikace fungovat podle očekávání.</span><span class="sxs-lookup"><span data-stu-id="7e276-111">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="7e276-112">Kontrolní výrazy otestovat rozhraní API součásti.</span><span class="sxs-lookup"><span data-stu-id="7e276-112">Assertions test the component API.</span></span>

-   <span data-ttu-id="7e276-113">Integrace testy.</span><span class="sxs-lookup"><span data-stu-id="7e276-113">Integration tests.</span></span> <span data-ttu-id="7e276-114">Tyto Ujistěte se, že interakce komponenty fungují podle očekávání proti externí artefaktů, jako jsou databáze.</span><span class="sxs-lookup"><span data-stu-id="7e276-114">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="7e276-115">Kontrolní výrazy můžete otestovat součást rozhraní API, uživatelského rozhraní nebo vedlejší účinky akcí jako vstupně-výstupní operace databáze protokolování atd.</span><span class="sxs-lookup"><span data-stu-id="7e276-115">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

-   <span data-ttu-id="7e276-116">Funkčních testů pro každý mikroslužby.</span><span class="sxs-lookup"><span data-stu-id="7e276-116">Functional tests for each microservice.</span></span> <span data-ttu-id="7e276-117">Tyto Ujistěte se, že aplikace funguje podle očekávání z pohledu uživatele.</span><span class="sxs-lookup"><span data-stu-id="7e276-117">These ensure that the application works as expected from the user’s perspective.</span></span>

-   <span data-ttu-id="7e276-118">Služba testy.</span><span class="sxs-lookup"><span data-stu-id="7e276-118">Service tests.</span></span> <span data-ttu-id="7e276-119">Tyto Ujistěte se, že případy použití služby začátku do konce, včetně testování víc služeb ve stejnou dobu, jsou testovány.</span><span class="sxs-lookup"><span data-stu-id="7e276-119">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="7e276-120">Pro tento typ testování musíte nejdřív připravit prostředí.</span><span class="sxs-lookup"><span data-stu-id="7e276-120">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="7e276-121">V takovém případě znamená spouštění služeb (například pomocí docker tvoří nahoru).</span><span class="sxs-lookup"><span data-stu-id="7e276-121">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="7e276-122">Implementuje testy částí pro rozhraní API webové jádro ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7e276-122">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="7e276-123">Testování částí zahrnuje testování součástí aplikace izolovaně od jeho infrastruktury a závislosti.</span><span class="sxs-lookup"><span data-stu-id="7e276-123">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="7e276-124">Když jste jednotkové testování řadiče logiku, obsah jenom jednu akci nebo metoda je testován, není chování jeho závislé součásti nebo rozhraní samotného.</span><span class="sxs-lookup"><span data-stu-id="7e276-124">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="7e276-125">Testování částí Nezjišťovat problémy v interakci mezi součástmi – to znamená účelem integrace testování.</span><span class="sxs-lookup"><span data-stu-id="7e276-125">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="7e276-126">Jako jednotku můžete otestovat vaše akce kontroleru, ujistěte se, že byste se zaměřit pouze na jejich chování.</span><span class="sxs-lookup"><span data-stu-id="7e276-126">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="7e276-127">Testování částí řadiče zabraňuje věcmi, jako jsou filtry, směrování nebo vazby modelu.</span><span class="sxs-lookup"><span data-stu-id="7e276-127">A controller unit test avoids things like filters, routing, or model binding.</span></span> <span data-ttu-id="7e276-128">Protože se zaměřuje na testování právě jednou z věcí, testy jednotek jsou obecně jednoduché k zápisu a rychlé spuštění.</span><span class="sxs-lookup"><span data-stu-id="7e276-128">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="7e276-129">Kvalitně sadu testů jednotek se může spouštět často bez mnoho zásahů.</span><span class="sxs-lookup"><span data-stu-id="7e276-129">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="7e276-130">Testování částí se implementují podle testovací architektury, jako je xUnit.net Mstestu, Moq nebo NUnit.</span><span class="sxs-lookup"><span data-stu-id="7e276-130">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="7e276-131">Pro ukázkovou aplikaci eShopOnContainers používáme XUnit.</span><span class="sxs-lookup"><span data-stu-id="7e276-131">For the eShopOnContainers sample application, we are using XUnit.</span></span>

<span data-ttu-id="7e276-132">Když píšete testů jednotek pro kontroler Web API, můžete vytvořit instanci třídy controller přímo pomocí new – klíčové slovo v jazyce C\#tak, aby se test spustí co nejrychleji.</span><span class="sxs-lookup"><span data-stu-id="7e276-132">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="7e276-133">Následující příklad ukazuje, jak postupovat při použití [XUnit](https://xunit.github.io/) jako Test framework.</span><span class="sxs-lookup"><span data-stu-id="7e276-133">The following example shows how to do this when using [XUnit](https://xunit.github.io/) as the Test framework.</span></span>

```csharp
[Fact]
public void Add_new_Order_raises_new_event()
{
    // Arrange
    var street = " FakeStreet ";
    var city = "FakeCity";
    // Other variables omitted for brevity ...
    // Act
    var fakeOrder = new Order(new Address(street, city, state, country, zipcode),
        cardTypeId, cardNumber,
        cardSecurityNumber, cardHolderName,
        cardExpiration);
    // Assert
    Assert.Equal(fakeOrder.DomainEvents.Count, expectedResult);
}
```

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="7e276-134">Implementace integrace a funkčních testů pro každý mikroslužbu</span><span class="sxs-lookup"><span data-stu-id="7e276-134">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="7e276-135">Jak jsme uvedli, integrace testy a funkčních testů mají různé účely a cíle.</span><span class="sxs-lookup"><span data-stu-id="7e276-135">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="7e276-136">Způsob, jakým implementujete i při testování řadiče ASP.NET Core je však podobný, takže v této části jsme soustředit se jenom na integraci testy.</span><span class="sxs-lookup"><span data-stu-id="7e276-136">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="7e276-137">Testování integrace zajistí, že součásti aplikace fungovat správně při sestaví.</span><span class="sxs-lookup"><span data-stu-id="7e276-137">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="7e276-138">Integrace podporuje ASP.NET Core testování pomocí systémů testování částí a integrované testovací webového hostitele, který lze použít ke zpracování požadavků bez nároky na síť.</span><span class="sxs-lookup"><span data-stu-id="7e276-138">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="7e276-139">Na rozdíl od testování částí integrace testy často zahrnují aspekty infrastruktury aplikace, jako je například databáze, systém souborů, síťové prostředky, nebo webové požadavky a odpovědi.</span><span class="sxs-lookup"><span data-stu-id="7e276-139">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="7e276-140">Testování částí použijte fakes nebo model objektů místo tyto problémy.</span><span class="sxs-lookup"><span data-stu-id="7e276-140">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="7e276-141">Ale účelem testů integrace je potvrďte, že systém funguje podle očekávání se tyto systémy, tak pro testování integrace nemáte použít fakes nebo model objektů.</span><span class="sxs-lookup"><span data-stu-id="7e276-141">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="7e276-142">Místo toho můžete zahrnout infrastruktury, jako je databáze přístupu nebo služba volání z jiné služby.</span><span class="sxs-lookup"><span data-stu-id="7e276-142">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="7e276-143">Protože integrace testy prověření větší segmenty kódu než testy jednotek a protože integrace testy využívají prvky infrastruktury, že jsou obvykle pořadí podle velikosti pomalejší než testování částí.</span><span class="sxs-lookup"><span data-stu-id="7e276-143">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="7e276-144">Proto je vhodné omezit kolik integrace testy zápisu a spustit.</span><span class="sxs-lookup"><span data-stu-id="7e276-144">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="7e276-145">ASP.NET Core zahrnuje integrovanou test webové hostitele, který lze použít pro zpracování požadavků HTTP bez nároky na síť, což znamená, že můžete spustit tyto testy rychlejší při použití skutečné webového hostitele.</span><span class="sxs-lookup"><span data-stu-id="7e276-145">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster when using a real web host.</span></span> <span data-ttu-id="7e276-146">Test webového hostitele je k dispozici v komponentě NuGet jako Microsoft.AspNetCore.TestHost.</span><span class="sxs-lookup"><span data-stu-id="7e276-146">The test web host is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="7e276-147">Jej lze přidat do projektů testování integrace a použít k hostiteli ASP.NET Core aplikace.</span><span class="sxs-lookup"><span data-stu-id="7e276-147">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="7e276-148">Jak můžete vidět v následujícím kódu, při vytváření integrace testy pro ASP.NET Core řadiče, vytvoří instanci řadiče prostřednictvím testovacího hostitele.</span><span class="sxs-lookup"><span data-stu-id="7e276-148">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="7e276-149">Toto je porovnatelný z hlediska na požadavek HTTP, ale běží rychleji.</span><span class="sxs-lookup"><span data-stu-id="7e276-149">This is comparable to an HTTP request, but it runs faster.</span></span>

```csharp
public class PrimeWebDefaultRequestShould
{
    private readonly TestServer _server;
    private readonly HttpClient _client;

    public PrimeWebDefaultRequestShould()
    {
        // Arrange
        _server = new TestServer(new WebHostBuilder()
           .UseStartup<Startup>());
           _client = _server.CreateClient();
    }

    [Fact]
    public async Task ReturnHelloWorld()
    {
        // Act
        var response = await _client.GetAsync("/");
        response.EnsureSuccessStatusCode();
        var responseString = await response.Content.ReadAsStringAsync();
        // Assert
        Assert.Equal("Hello World!", responseString);
    }
}
```

#### <a name="additional-resources"></a><span data-ttu-id="7e276-150">Další zdroje</span><span class="sxs-lookup"><span data-stu-id="7e276-150">Additional resources</span></span>

-   <span data-ttu-id="7e276-151">**Steve Smith. Testování řadiče** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span><span class="sxs-lookup"><span data-stu-id="7e276-151">**Steve Smith. Testing controllers** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span></span>

-   <span data-ttu-id="7e276-152">**Steve Smith. Testování integrace** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span><span class="sxs-lookup"><span data-stu-id="7e276-152">**Steve Smith. Integration testing** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span></span>

-   <span data-ttu-id="7e276-153">**Testování v .NET Core pomocí dotnet testů částí**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span><span class="sxs-lookup"><span data-stu-id="7e276-153">**Unit testing in .NET Core using dotnet test**
[*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span></span>

-   <span data-ttu-id="7e276-154">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="7e276-154">**xUnit.net**.</span></span> <span data-ttu-id="7e276-155">Oficiální web.</span><span class="sxs-lookup"><span data-stu-id="7e276-155">Official site.</span></span>
    [<span data-ttu-id="7e276-156">*https://xunit.github.IO/*</span><span class="sxs-lookup"><span data-stu-id="7e276-156">*https://xunit.github.io/*</span></span>](https://xunit.github.io/)

-   <span data-ttu-id="7e276-157">**Testování částí. ** 
     [ *https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e276-157">**Unit Test Basics.**
[*https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span></span>

-   <span data-ttu-id="7e276-158">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="7e276-158">**Moq**.</span></span> <span data-ttu-id="7e276-159">Úložiště GitHub.</span><span class="sxs-lookup"><span data-stu-id="7e276-159">GitHub repo.</span></span>
    [<span data-ttu-id="7e276-160">*https://github.com/moq/moq*</span><span class="sxs-lookup"><span data-stu-id="7e276-160">*https://github.com/moq/moq*</span></span>](https://github.com/moq/moq)

-   <span data-ttu-id="7e276-161">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="7e276-161">**NUnit**.</span></span> <span data-ttu-id="7e276-162">Oficiální web.</span><span class="sxs-lookup"><span data-stu-id="7e276-162">Official site.</span></span>
    [<span data-ttu-id="7e276-163">*https://www.nunit.org/*</span><span class="sxs-lookup"><span data-stu-id="7e276-163">*https://www.nunit.org/*</span></span>](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="7e276-164">Implementace služby testy na aplikace s více kontejnerů</span><span class="sxs-lookup"><span data-stu-id="7e276-164">Implementing service tests on a multi-container application</span></span> 

<span data-ttu-id="7e276-165">Jak jsme uvedli dříve, při testování aplikace s více kontejner, musíte používat v rámci clusteru hostitele nebo kontejner Docker všechny mikroslužeb.</span><span class="sxs-lookup"><span data-stu-id="7e276-165">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="7e276-166">Testy začátku do konce služby, které zahrnují více operací zahrnujících několik mikroslužeb musíte nasadit a spustit celou aplikaci na hostiteli Docker spuštěním docker-tvoří nahoru (nebo srovnatelný mechanismus, pokud používáte produktu orchestrator).</span><span class="sxs-lookup"><span data-stu-id="7e276-166">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="7e276-167">Po celou aplikaci a všechny její služby běží, můžete provést integraci začátku do konce a funkčních testů.</span><span class="sxs-lookup"><span data-stu-id="7e276-167">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="7e276-168">Existuje několik přístupů, které můžete použít.</span><span class="sxs-lookup"><span data-stu-id="7e276-168">There are a few approaches you can use.</span></span> <span data-ttu-id="7e276-169">V soubor docker-compose.yml, který můžete použít k nasazení aplikace (nebo podobné těm, které jsou, jako je docker compose.ci.build.yml), na úrovni řešení můžete rozšířit vstupní bod používat [dotnet testovací](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span><span class="sxs-lookup"><span data-stu-id="7e276-169">In the docker-compose.yml file that you use to deploy the application (or similar ones, like docker-compose.ci.build.yml), at the solution level you can expand the entry point to use [dotnet test](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span></span> <span data-ttu-id="7e276-170">Můžete taky jiné vytvářené soubor, který by spouštění testů do bitové kopie, které se zaměříte.</span><span class="sxs-lookup"><span data-stu-id="7e276-170">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="7e276-171">Pomocí jiného souboru vytvářené pro integraci testy, které zahrnuje mikroslužeb a databáze na kontejnery měli jistotu, že související data se vždy vynuluje do původního stavu před spuštěním testů.</span><span class="sxs-lookup"><span data-stu-id="7e276-171">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="7e276-172">Jakmile vytvářené aplikace spuštěná, můžete využít výhod zarážky a výjimky, pokud používáte Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7e276-172">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="7e276-173">Nebo můžete spustit testy integrace automaticky v kanálu vaší konfigurace v sadě Visual Studio Team Services nebo všechny ostatní systémy CI/CD, který podporuje Docker kontejnery.</span><span class="sxs-lookup"><span data-stu-id="7e276-173">Or you can run the integration tests automatically in your CI pipeline in Visual Studio Team Services or any other CI/CD system that supports Docker containers.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="7e276-174">[Předchozí] (přihlášení k odběru events.md) [Další] (.. /microservice-ddd-cqrs-Patterns/index.MD)</span><span class="sxs-lookup"><span data-stu-id="7e276-174">[Previous] (subscribe-events.md) [Next] (../microservice-ddd-cqrs-patterns/index.md)</span></span>