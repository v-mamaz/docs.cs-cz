---
title: "Navrhování orientované DDD mikroslužbu"
description: "Architektura Mikroslužeb .NET pro aplikace .NET Kontejnerizované | Navrhování orientované DDD mikroslužbu"
keywords: "Docker, Mikroslužeb, ASP.NET, kontejneru"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: df45441089fd59d5e0e52b4bcec409adcc11fb71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="designing-a-ddd-oriented-microservice"></a><span data-ttu-id="4b511-104">Navrhování orientované DDD mikroslužbu</span><span class="sxs-lookup"><span data-stu-id="4b511-104">Designing a DDD-oriented microservice</span></span>

<span data-ttu-id="4b511-105">Řízené domény návrhu (DDD) obhajuje modelování podle když ve skutečnosti firmy jako relevantní pro vaše případy použití.</span><span class="sxs-lookup"><span data-stu-id="4b511-105">Domain-driven design (DDD) advocates modeling based on the reality of business as relevant to your use cases.</span></span> <span data-ttu-id="4b511-106">V rámci sestavení aplikací DDD zmíněn problémy jako domény.</span><span class="sxs-lookup"><span data-stu-id="4b511-106">In the context of building applications, DDD talks about problems as domains.</span></span> <span data-ttu-id="4b511-107">Popisuje nezávislé problémových oblastí jako ohraničenou kontexty (každý kontext ohraničenou koreluje s mikroslužbu) a klade důraz běžné jazyka, který má v souvislosti se tyto problémy.</span><span class="sxs-lookup"><span data-stu-id="4b511-107">It describes independent problem areas as Bounded Contexts (each Bounded Context correlates to a microservice), and emphasizes a common language to talk about these problems.</span></span> <span data-ttu-id="4b511-108">Rovněž nabízí mnoho technické koncepty a vzory, třeba domény entity s bohatou modely (žádné [modelu anemic domény](https://martinfowler.com/bliki/AnemicDomainModel.html)), hodnota objekty, agregace a agregační kořenové (nebo kořenové entity) pravidla pro podporu interní implementace.</span><span class="sxs-lookup"><span data-stu-id="4b511-108">It also suggests many technical concepts and patterns, like domain entities with rich models (no [anemic-domain model](https://martinfowler.com/bliki/AnemicDomainModel.html)), value objects, aggregates and aggregate root (or root entity) rules to support the internal implementation.</span></span> <span data-ttu-id="4b511-109">Tato část představuje návrh a implementaci tyto interní vzorce.</span><span class="sxs-lookup"><span data-stu-id="4b511-109">This section introduces the design and implementation of those internal patterns.</span></span>

<span data-ttu-id="4b511-110">Tyto technické pravidla DDD a vzory jsou někdy považován za překážky, které mají zvládnutí křivku pro implementaci DDD přístupy.</span><span class="sxs-lookup"><span data-stu-id="4b511-110">Sometimes these DDD technical rules and patterns are perceived as obstacles that have a steep learning curve for implementing DDD approaches.</span></span> <span data-ttu-id="4b511-111">Ale je důležitou součástí není vzorky sami, ale uspořádání kód, takže je umístěno na obchodní problémy a pomocí stejných podmínek firmy (všudypřítomný language).</span><span class="sxs-lookup"><span data-stu-id="4b511-111">But the important part is not the patterns themselves, but organizing the code so it is aligned to the business problems, and using the same business terms (ubiquitous language).</span></span> <span data-ttu-id="4b511-112">Kromě toho DDD přístupy bude použito pouze v případě, že implementujete komplexní mikroslužeb s významné obchodní pravidla.</span><span class="sxs-lookup"><span data-stu-id="4b511-112">In addition, DDD approaches should be applied only if you are implementing complex microservices with significant business rules.</span></span> <span data-ttu-id="4b511-113">Jednodušší odpovědnosti, jako je služba CRUD, lze spravovat pomocí jednodušší přístupy.</span><span class="sxs-lookup"><span data-stu-id="4b511-113">Simpler responsibilities, like a CRUD service, can be managed with simpler approaches.</span></span>

<span data-ttu-id="4b511-114">Kde kreslení hranice je klíče úloha při návrhu a definování mikroslužby.</span><span class="sxs-lookup"><span data-stu-id="4b511-114">Where to draw the boundaries is the key task when designing and defining a microservice.</span></span> <span data-ttu-id="4b511-115">DDD vzory vám pomohou porozumět složitost v doméně.</span><span class="sxs-lookup"><span data-stu-id="4b511-115">DDD patterns help you understand the complexity in the domain.</span></span> <span data-ttu-id="4b511-116">Pro model domény pro každý kontext ohraničenou identifikovat a definovat entity, hodnota objekty a agregace, které modelu domény.</span><span class="sxs-lookup"><span data-stu-id="4b511-116">For the domain model for each Bounded Context, you identify and define the entities, value objects, and aggregates that model your domain.</span></span> <span data-ttu-id="4b511-117">Sestavení a upřesněte modelu domény, který je obsažen v rámci hranice, která definuje váš kontext.</span><span class="sxs-lookup"><span data-stu-id="4b511-117">You build and refine a domain model that is contained within a boundary that defines your context.</span></span> <span data-ttu-id="4b511-118">A který bude velmi explicitní ve formě mikroslužby.</span><span class="sxs-lookup"><span data-stu-id="4b511-118">And that is very explicit in the form of a microservice.</span></span> <span data-ttu-id="4b511-119">Součásti v rámci těchto hranicích skončili se mikroslužeb, i když v některých případech a BC nebo obchodní mikroslužeb se může skládat z několika fyzických služeb.</span><span class="sxs-lookup"><span data-stu-id="4b511-119">The components within those boundaries end up being your microservices, although in some cases a BC or business microservices can be composed of several physical services.</span></span> <span data-ttu-id="4b511-120">DDD je o hranice a proto nejsou mikroslužeb.</span><span class="sxs-lookup"><span data-stu-id="4b511-120">DDD is about boundaries and so are microservices.</span></span>

## <a name="keep-the-microservice-context-boundaries-relatively-small"></a><span data-ttu-id="4b511-121">Zachovat mikroslužbu kontextu hranice poměrně malý</span><span class="sxs-lookup"><span data-stu-id="4b511-121">Keep the microservice context boundaries relatively small</span></span>

<span data-ttu-id="4b511-122">Určení, kam umístit hranice mezi ohraničenou kontexty vyrovnává dvě konkurenční cíle.</span><span class="sxs-lookup"><span data-stu-id="4b511-122">Determining where to place boundaries between Bounded Contexts balances two competing goals.</span></span> <span data-ttu-id="4b511-123">Nejprve chcete nejprve vytvořit nejmenší možné mikroslužeb, i když, který by neměl být hlavní ovladač; měli byste vytvořit hranici kolem věcí, které je třeba soudržnost.</span><span class="sxs-lookup"><span data-stu-id="4b511-123">First, you want to initially create the smallest possible microservices, although that should not be the main driver; you should create a boundary around things that need cohesion.</span></span> <span data-ttu-id="4b511-124">Druhý budete chtít vyhnout chatty komunikace mezi mikroslužeb.</span><span class="sxs-lookup"><span data-stu-id="4b511-124">Second, you want to avoid chatty communications between microservices.</span></span> <span data-ttu-id="4b511-125">Těchto cílů může být v rozporu jednu na druhou.</span><span class="sxs-lookup"><span data-stu-id="4b511-125">These goals can contradict one another.</span></span> <span data-ttu-id="4b511-126">Je měli vyvážit podle decomposing systému do tolik malé mikroslužeb, jako je možné, dokud neuvidíte komunikace hranice narůstají rychle s každou další pokus o oddělení nový kontext vázaný.</span><span class="sxs-lookup"><span data-stu-id="4b511-126">You should balance them by decomposing the system into as many small microservices as you can until you see communication boundaries growing quickly with each additional attempt to separate a new Bounded Context.</span></span> <span data-ttu-id="4b511-127">Soudržnost se klíč v rámci jedné ohraničené kontextu.</span><span class="sxs-lookup"><span data-stu-id="4b511-127">Cohesion is key within a single bounded context.</span></span>

<span data-ttu-id="4b511-128">Je podobná [pach kód nepotřebnými Intimacy](https://sourcemaking.com/refactoring/smells/inappropriate-intimacy) při implementaci třídy.</span><span class="sxs-lookup"><span data-stu-id="4b511-128">It is similar to the [Inappropriate Intimacy code smell](https://sourcemaking.com/refactoring/smells/inappropriate-intimacy) when implementing classes.</span></span> <span data-ttu-id="4b511-129">Pokud dva mikroslužeb potřebovat mnoho vzájemnou spolupráci, měly by být pravděpodobně stejné mikroslužby.</span><span class="sxs-lookup"><span data-stu-id="4b511-129">If two microservices need to collaborate a lot with each other, they should probably be the same microservice.</span></span>

<span data-ttu-id="4b511-130">Dalším způsobem podívejte se na to je nezávislé.</span><span class="sxs-lookup"><span data-stu-id="4b511-130">Another way to look at this is autonomy.</span></span> <span data-ttu-id="4b511-131">Pokud mikroslužbu musíte spoléhat na jiné služby pro přímo obsloužit požadavek, není skutečně autonomní.</span><span class="sxs-lookup"><span data-stu-id="4b511-131">If a microservice must rely on another service to directly service a request, it is not truly autonomous.</span></span>

## <a name="layers-in-ddd-microservices"></a><span data-ttu-id="4b511-132">Vrstvy v DDD mikroslužeb</span><span class="sxs-lookup"><span data-stu-id="4b511-132">Layers in DDD microservices</span></span>

<span data-ttu-id="4b511-133">Většina aplikací enterprise významné obchodních a technických složitosti jsou definovány více vrstev.</span><span class="sxs-lookup"><span data-stu-id="4b511-133">Most enterprise applications with significant business and technical complexity are defined by multiple layers.</span></span> <span data-ttu-id="4b511-134">Vrstvy, které jsou logické artefaktů a nesouvisí se nasazení služby.</span><span class="sxs-lookup"><span data-stu-id="4b511-134">The layers are a logical artifact, and are not related to the deployment of the service.</span></span> <span data-ttu-id="4b511-135">Existují, což vývojářům zvládnout složité v kódu.</span><span class="sxs-lookup"><span data-stu-id="4b511-135">They exist to help developers manage the complexity in the code.</span></span> <span data-ttu-id="4b511-136">Různé vrstvy (jako vrstva modelu domény oproti prezentační vrstvy, atd.) může mít různé typy, které vyžaduje převody mezi tyto typy.</span><span class="sxs-lookup"><span data-stu-id="4b511-136">Different layers (like the domain model layer versus the presentation layer, etc.) might have different types, which mandates translations between those types.</span></span>

<span data-ttu-id="4b511-137">Například může entity načíst z databáze.</span><span class="sxs-lookup"><span data-stu-id="4b511-137">For example, an entity could be loaded from the database.</span></span> <span data-ttu-id="4b511-138">Součástí těchto informací nebo agregaci informace, včetně další data z jinými entitami, potom můžete odeslat klientovi uživatelského rozhraní pomocí webového rozhraní API REST.</span><span class="sxs-lookup"><span data-stu-id="4b511-138">Then part of that information, or an aggregation of information including additional data from other entities, can be sent to the client UI through a REST Web API.</span></span> <span data-ttu-id="4b511-139">Bodem tady je, že entita domény je obsažena v vrstva modelu domény a neměli rozšíří do jiných oblastí, které nepatří, jako je třeba do prezentační vrstvy.</span><span class="sxs-lookup"><span data-stu-id="4b511-139">The point here is that the domain entity is contained within the domain model layer and should not be propagated to other areas that it does not belong to, like to the presentation layer.</span></span>

<span data-ttu-id="4b511-140">Kromě toho je potřeba mít vždy platné entity (najdete v článku [navrhování ověření ve vrstvě modelu domény](#designing-validations-in-the-domain-model-layer) část) řízené agregační kořenových certifikačních autorit (kořenové entity).</span><span class="sxs-lookup"><span data-stu-id="4b511-140">Additionally, you need to have always-valid entities (see the [Designing validations in the domain model layer](#designing-validations-in-the-domain-model-layer) section) controlled by aggregate roots (root entities).</span></span> <span data-ttu-id="4b511-141">Proto entity by neměl být vázána na zobrazení klientů, protože úrovni uživatelského rozhraní nemusí stále ověřit některá data.</span><span class="sxs-lookup"><span data-stu-id="4b511-141">Therefore, entities should not be bound to client views, because at the UI level some data might still not be validated.</span></span> <span data-ttu-id="4b511-142">Toto je, co ViewModel je.</span><span class="sxs-lookup"><span data-stu-id="4b511-142">This is what the ViewModel is for.</span></span> <span data-ttu-id="4b511-143">ViewModel je datový model výhradně pro potřeby prezentační vrstvy.</span><span class="sxs-lookup"><span data-stu-id="4b511-143">The ViewModel is a data model exclusively for presentation layer needs.</span></span> <span data-ttu-id="4b511-144">Domény entity, které nejsou členy přímo ViewModel.</span><span class="sxs-lookup"><span data-stu-id="4b511-144">The domain entities do not belong directly to the ViewModel.</span></span> <span data-ttu-id="4b511-145">Místo toho musíte k převodu mezi ViewModels a domény entity a naopak.</span><span class="sxs-lookup"><span data-stu-id="4b511-145">Instead, you need to translate between ViewModels and domain entities and vice versa.</span></span>

<span data-ttu-id="4b511-146">Při boji se složitost, je důležité mít modelu domény řídí agregační kořeny (jsme přejděte do této podrobněji později), které Ujistěte se, že všechny výstupních podmínek a pravidel, vztahuje k této skupině entit (agregační) se provádí prostřednictvím jednu položku bod nebo brány, kořenu agregační.</span><span class="sxs-lookup"><span data-stu-id="4b511-146">When tackling complexity, it is important to have a domain model controlled by aggregate roots (we go into this in more detail later) that make sure that all the invariants and rules related to that group of entities (aggregate) are performed through a single entry point or gate, the aggregate root.</span></span>

<span data-ttu-id="4b511-147">Obrázek 9-5 ukazuje, jak je implementována vrstvený návrh v aplikaci eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="4b511-147">Figure 9-5 shows how a layered design is implemented in the eShopOnContainers application.</span></span>

![](./media/image6.png)

<span data-ttu-id="4b511-148">**Obrázek 9-5**.</span><span class="sxs-lookup"><span data-stu-id="4b511-148">**Figure 9-5**.</span></span> <span data-ttu-id="4b511-149">DDD vrstvy v řazení mikroslužbu v eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="4b511-149">DDD layers in the ordering microservice in eShopOnContainers</span></span>

<span data-ttu-id="4b511-150">Chcete navrhnout systému tak, aby každé vrstvě komunikuje jenom s některých jiných vrstev.</span><span class="sxs-lookup"><span data-stu-id="4b511-150">You want to design the system so that each layer communicates only with certain other layers.</span></span> <span data-ttu-id="4b511-151">Které mohou být snazší vynutit v případě, že vrstvy jsou implementované jako jinou třídu knihovny, protože jasně zjistíte, jaké závislosti jsou nastaveny mezi knihovny.</span><span class="sxs-lookup"><span data-stu-id="4b511-151">That may be easier to enforce if layers are implemented as different class libraries, because you can clearly identify what dependencies are set between libraries.</span></span> <span data-ttu-id="4b511-152">Například vrstva modelu domény by neměly být závislý na další vrstvou (třídy modelu domény by měl být prostý staré objekty CLR nebo [objektů POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object), třídy).</span><span class="sxs-lookup"><span data-stu-id="4b511-152">For instance, the domain model layer should not take a dependency on any other layer (the domain model classes should be Plain Old CLR Objects, or [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object), classes).</span></span> <span data-ttu-id="4b511-153">Jak je znázorněno na obrázku 9-6 **Ordering.Domain** vrstvy knihovny má závislosti, jenom na knihovny .NET Core, ale ne na žádné jiné vlastní knihovny (knihovna dat, trvalost knihovny atd.).</span><span class="sxs-lookup"><span data-stu-id="4b511-153">As shown in Figure 9-6, the **Ordering.Domain** layer library has dependencies only on the .NET Core libraries but not on any other custom library (data library, persistence library, etc.).</span></span>

![](./media/image7.PNG)

<span data-ttu-id="4b511-154">**Obrázek 9-6**.</span><span class="sxs-lookup"><span data-stu-id="4b511-154">**Figure 9-6**.</span></span> <span data-ttu-id="4b511-155">Vrstvy, které jsou implementované jako knihovny umožňují lepší kontrolu nad závislosti mezi vrstvami</span><span class="sxs-lookup"><span data-stu-id="4b511-155">Layers implemented as libraries allow better control of dependencies between layers</span></span>

### <a name="the-domain-model-layer"></a><span data-ttu-id="4b511-156">Vrstva modelu domény</span><span class="sxs-lookup"><span data-stu-id="4b511-156">The domain model layer</span></span>

<span data-ttu-id="4b511-157">Zařízení Erica Evans vynikající kniha [řízené návrhu domény](http://domainlanguage.com/ddd/) s následujícím textem o vrstva modelu domény a aplikační vrstvu.</span><span class="sxs-lookup"><span data-stu-id="4b511-157">Eric Evans's excellent book [Domain Driven Design](http://domainlanguage.com/ddd/) says the following about the domain model layer and the application layer.</span></span>

<span data-ttu-id="4b511-158">**Vrstva modelu domény**: zodpovědná za představující koncepty firmy, informace o obchodní situaci a obchodní pravidla.</span><span class="sxs-lookup"><span data-stu-id="4b511-158">**Domain Model Layer**: Responsible for representing concepts of the business, information about the business situation, and business rules.</span></span> <span data-ttu-id="4b511-159">Stav, který se vztahuje k obchodní situaci je řízena a použít se zde, i když jsou delegovanými technické informace o ukládání do infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="4b511-159">State that reflects the business situation is controlled and used here, even though the technical details of storing it are delegated to the infrastructure.</span></span> <span data-ttu-id="4b511-160">Tato vrstva jsou srdcem obchodní softwaru.</span><span class="sxs-lookup"><span data-stu-id="4b511-160">This layer is the heart of business software.</span></span>

<span data-ttu-id="4b511-161">Vrstva modelu domény je, kde je vyjádřen firmy.</span><span class="sxs-lookup"><span data-stu-id="4b511-161">The domain model layer is where the business is expressed.</span></span> <span data-ttu-id="4b511-162">Pokud implementujete vrstva mikroslužbu domény modelu v rozhraní .NET, této vrstvy je zakódovaný jako knihovny tříd s entitami domény, které zaznamenání dat a chování (metody s logiku).</span><span class="sxs-lookup"><span data-stu-id="4b511-162">When you implement a microservice domain model layer in .NET, that layer is coded as a class library with the domain entities that capture data plus behavior (methods with logic).</span></span>

<span data-ttu-id="4b511-163">Následující [trvalost které](http://deviq.com/persistence-ignorance/) a [infrastruktury, které](https://ayende.com/blog/3137/infrastructure-ignorance) zásady, tato vrstva musí být zcela ignorovat podrobnosti trvalosti dat.</span><span class="sxs-lookup"><span data-stu-id="4b511-163">Following the [Persistence Ignorance](http://deviq.com/persistence-ignorance/) and the [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles, this layer must completely ignore data persistence details.</span></span> <span data-ttu-id="4b511-164">Vrstvě infrastruktury by měli provádět tyto úlohy trvalost.</span><span class="sxs-lookup"><span data-stu-id="4b511-164">These persistence tasks should be performed by the infrastructure layer.</span></span> <span data-ttu-id="4b511-165">Proto tuto vrstvu by neměl trvat přímé závislosti na infrastruktuře, což znamená, že pravidlo důležité je, že by měl být tříd domény modelu entity [objektů POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)s.</span><span class="sxs-lookup"><span data-stu-id="4b511-165">Therefore, this layer should not take direct dependencies on the infrastructure, which means that an important rule is that your domain model entity classes should be [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)s.</span></span>

<span data-ttu-id="4b511-166">Entity domény by neměl mít žádné přímé závislosti (např. odvozování od třídy base) na libovolnou architekturu data přístup infrastruktury jako Entity Framework nebo NHibernate.</span><span class="sxs-lookup"><span data-stu-id="4b511-166">Domain entities should not have any direct dependency (like deriving from a base class) on any data access infrastructure framework like Entity Framework or NHibernate.</span></span> <span data-ttu-id="4b511-167">V ideálním případě by neměl odvozena z vaší domény entity nebo jsou implementovány libovolného typu definované v libovolnou architekturu infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="4b511-167">Ideally, your domain entities should not derive from or implement any type defined in any infrastructure framework.</span></span>

<span data-ttu-id="4b511-168">Většina moderních ORM architektury, jako je Entity Framework Core povolit tuto metodu tak, aby tříd modelu domény nejsou doplněná infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="4b511-168">Most modern ORM frameworks like Entity Framework Core allow this approach, so that your domain model classes are not coupled to the infrastructure.</span></span> <span data-ttu-id="4b511-169">Nicméně s entity objektů POCO není vždy možné při použití určitých databáze NoSQL a rozhraní, jako je aktéři a spolehlivé kolekcí v Azure Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="4b511-169">However, having POCO entities is not always possible when using certain NoSQL databases and frameworks, like Actors and Reliable Collections in Azure Service Fabric.</span></span>

<span data-ttu-id="4b511-170">I v případě, že je důležité dodržet zásadu které trvalosti pro domény model, by neměl ignorovat trvalost otázky.</span><span class="sxs-lookup"><span data-stu-id="4b511-170">Even when it is important to follow the Persistence Ignorance principle for you Domain model, you should not ignore persistence concerns.</span></span> <span data-ttu-id="4b511-171">Stále je velmi důležité, abyste pochopili, fyzický datový model a jak se mapuje na objekt modelu entity.</span><span class="sxs-lookup"><span data-stu-id="4b511-171">It is still very important to understand the physical data model and how it maps to your entity object model.</span></span> <span data-ttu-id="4b511-172">V opačném případě můžete vytvořit možné návrhů.</span><span class="sxs-lookup"><span data-stu-id="4b511-172">Otherwise you can create impossible designs.</span></span>

<span data-ttu-id="4b511-173">Navíc neznamená to můžete provést model určený pro relační databázi a přímo ho přesunout do NoSQL nebo orientované dokumentu databáze.</span><span class="sxs-lookup"><span data-stu-id="4b511-173">Also, this does not mean you can take a model designed for a relational database and directly move it to a NoSQL or document-oriented database.</span></span> <span data-ttu-id="4b511-174">V některých modelů entity může přizpůsobit modelu, ale obvykle je nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="4b511-174">In some entity models, the model might fit, but usually it does not.</span></span> <span data-ttu-id="4b511-175">Stále existují omezení, která musí splňovat modelu entity na základě technologie úložiště a ORM technologie.</span><span class="sxs-lookup"><span data-stu-id="4b511-175">There are still constraints that your entity model must adhere to, based both on the storage technology and ORM technology.</span></span>

### <a name="the-application-layer"></a><span data-ttu-id="4b511-176">Aplikační vrstvu</span><span class="sxs-lookup"><span data-stu-id="4b511-176">The application layer</span></span>

<span data-ttu-id="4b511-177">Přejdete na aplikační vrstvu, jsme můžete znovu cite zařízení Erica Evans kniha [řízené návrhu domény](http://domainlanguage.com/ddd/):</span><span class="sxs-lookup"><span data-stu-id="4b511-177">Moving on to the application layer, we can again cite Eric Evans's book [Domain Driven Design](http://domainlanguage.com/ddd/):</span></span>

<span data-ttu-id="4b511-178">**Aplikační vrstvu:** definuje úloh softwaru by měla provést a přesměruje objekty výrazovou domény k vyřešení problémů.</span><span class="sxs-lookup"><span data-stu-id="4b511-178">**Application Layer:** Defines the jobs the software is supposed to do and directs the expressive domain objects to work out problems.</span></span> <span data-ttu-id="4b511-179">Úlohy, které tuto vrstvu zodpovídá za jsou důležité pro jejich podnikání nebo potřebné pro interakci s aplikačními vrstvami jiných systémů.</span><span class="sxs-lookup"><span data-stu-id="4b511-179">The tasks this layer is responsible for are meaningful to the business or necessary for interaction with the application layers of other systems.</span></span> <span data-ttu-id="4b511-180">Tuto vrstvu je udržováno dynamické.</span><span class="sxs-lookup"><span data-stu-id="4b511-180">This layer is kept thin.</span></span> <span data-ttu-id="4b511-181">Neobsahuje obchodní pravidla nebo znalostní báze, ale pouze souřadnice úlohy a delegáti spolupracovat na spolupráce objektů domény v další vrstva dolů.</span><span class="sxs-lookup"><span data-stu-id="4b511-181">It does not contain business rules or knowledge, but only coordinates tasks and delegates work to collaborations of domain objects in the next layer down.</span></span> <span data-ttu-id="4b511-182">Nemá stav odrážející stav firmy, ale může mít stav, který zobrazuje průběh úlohy pro uživatele nebo program.</span><span class="sxs-lookup"><span data-stu-id="4b511-182">It does not have state reflecting the business situation, but it can have state that reflects the progress of a task for the user or the program.</span></span>

<span data-ttu-id="4b511-183">Mikroslužbu na aplikační vrstvu v rozhraní .NET je běžně programového jako projekt webového rozhraní API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b511-183">A microservice’s application layer in .NET is commonly coded as an ASP.NET Core Web API project.</span></span> <span data-ttu-id="4b511-184">Projekt implementuje interakce mikroslužbu, vzdálený přístup k síti a externí webovým rozhraním API používá z aplikací uživatelského rozhraní nebo klienta.</span><span class="sxs-lookup"><span data-stu-id="4b511-184">The project implements the microservice’s interaction, remote network access, and the external Web APIs used from the UI or client apps.</span></span> <span data-ttu-id="4b511-185">Pokud pomocí CQRS přístupu příkazy přijatý mikroslužbu a i událostmi řízené komunikace mezi mikroslužeb (integrace událostí) obsahuje dotazy.</span><span class="sxs-lookup"><span data-stu-id="4b511-185">It includes queries if using a CQRS approach, commands accepted by the microservice, and even the event-driven communication between microservices (integration events).</span></span> <span data-ttu-id="4b511-186">Rozhraní ASP.NET Web API Core, který představuje aplikační vrstvu nesmí obsahovat obchodní pravidla a znalosti domény (zejména domény pravidla pro transakce nebo aktualizace); Tyto vlastníkem by měl být knihovny tříd modelu domény.</span><span class="sxs-lookup"><span data-stu-id="4b511-186">The ASP.NET Core Web API that represents the application layer must not contain business rules or domain knowledge (especially domain rules for transactions or updates); these should be owned by the domain model class library.</span></span> <span data-ttu-id="4b511-187">Souřadnice pouze aplikace vrstvy musí úloh a nesmí obsahovat nebo definovat stav všechny domény (modelu domény).</span><span class="sxs-lookup"><span data-stu-id="4b511-187">The application layer must only coordinate tasks and must not hold or define any domain state (domain model).</span></span> <span data-ttu-id="4b511-188">Deleguje provádění obchodní pravidla domény modelu třídy sami (agregační kořeny a entity domény), které bude nakonec aktualizovat data v rámci těchto domény entity.</span><span class="sxs-lookup"><span data-stu-id="4b511-188">It delegates the execution of business rules to the domain model classes themselves (aggregate roots and domain entities), which will ultimately update the data within those domain entities.</span></span>

<span data-ttu-id="4b511-189">Logiku aplikace je v podstatě, kde budete implementovat všechny případy použití, které jsou závislé na danou front-end.</span><span class="sxs-lookup"><span data-stu-id="4b511-189">Basically, the application logic is where you implement all use cases that depend on a given front end.</span></span> <span data-ttu-id="4b511-190">Například implementace související s webového rozhraní API služby.</span><span class="sxs-lookup"><span data-stu-id="4b511-190">For example, the implementation related to a Web API service.</span></span>

<span data-ttu-id="4b511-191">Cílem je, že logiku domény v vrstva modelu domény, jeho výstupních podmínek, datový model a související obchodní pravidla musí být zcela nezávislé na vrstvy prezentace a aplikace.</span><span class="sxs-lookup"><span data-stu-id="4b511-191">The goal is that the domain logic in the domain model layer, its invariants, the data model, and related business rules must be completely independent from the presentation and application layers.</span></span> <span data-ttu-id="4b511-192">Vrstva modelu domény nesmí nejvíce všech, závisí přímo na libovolnou architekturu infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="4b511-192">Most of all, the domain model layer must not directly depend on any infrastructure framework.</span></span>

### <a name="the-infrastructure-layer"></a><span data-ttu-id="4b511-193">Vrstvě infrastruktury</span><span class="sxs-lookup"><span data-stu-id="4b511-193">The infrastructure layer</span></span>

<span data-ttu-id="4b511-194">Vrstvě infrastruktury je, jak je databáze nebo jiného trvalé úložiště trvalá data, která je původně uchovávat v doméně entity (v paměti).</span><span class="sxs-lookup"><span data-stu-id="4b511-194">The infrastructure layer is how the data that is initially held in domain entities (in memory) is persisted in databases or another persistent store.</span></span> <span data-ttu-id="4b511-195">Příklad používá Entity Framework Core kód pro implementaci třídy vzor úložiště, které pomocí konstruktoru DBContext lze zachovat data z relační databáze.</span><span class="sxs-lookup"><span data-stu-id="4b511-195">An example is using Entity Framework Core code to implement the Repository pattern classes that use a DBContext to persist data in a relational database.</span></span>

<span data-ttu-id="4b511-196">V souladu s výše uvedených [trvalost které](http://deviq.com/persistence-ignorance/) a [infrastruktury které](https://ayende.com/blog/3137/infrastructure-ignorance) zásady, vrstvě infrastruktury nesmí "kontaminovat" vrstva modelu domény.</span><span class="sxs-lookup"><span data-stu-id="4b511-196">In accordance with the previously mentioned [Persistence Ignorance](http://deviq.com/persistence-ignorance/) and [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles, the infrastructure layer must not “contaminate” the domain model layer.</span></span> <span data-ttu-id="4b511-197">Je nutné zachovat třídy vznikl domény modelu entity z infrastruktury, který používáte k zachování dat (EF nebo jiných framework) není provedením pevný závislosti na rozhraní.</span><span class="sxs-lookup"><span data-stu-id="4b511-197">You must keep the domain model entity classes agnostic from the infrastructure that you use to persist data (EF or any other framework) by not taking hard dependencies on frameworks.</span></span> <span data-ttu-id="4b511-198">Knihovny tříd vrstvy modelu domény by měl mít jenom kódu domény, právě [objektů POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object) entity třídy implementace srdcem váš software a úplně odpojená od technologií infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="4b511-198">Your domain model layer class library should have only your domain code, just [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object) entity classes implementing the heart of your software and completely decoupled from infrastructure technologies.</span></span>

<span data-ttu-id="4b511-199">Proto vrstvy nebo knihovny tříd a projekty by měl nakonec záviset na vrstvě modelu domény (knihovna), ne naopak, jak je znázorněno na obrázku 9-7.</span><span class="sxs-lookup"><span data-stu-id="4b511-199">Thus, your layers or class libraries and projects should ultimately depend on your domain model layer (library), not vice versa, as shown in Figure 9-7.</span></span>

![](./media/image8.png)

<span data-ttu-id="4b511-200">**Obrázek 9-7**.</span><span class="sxs-lookup"><span data-stu-id="4b511-200">**Figure 9-7**.</span></span> <span data-ttu-id="4b511-201">Závislosti mezi vrstvy v DDD</span><span class="sxs-lookup"><span data-stu-id="4b511-201">Dependencies between layers in DDD</span></span>

<span data-ttu-id="4b511-202">Tento návrh vrstvy musí být pro každý mikroslužbu nezávislé.</span><span class="sxs-lookup"><span data-stu-id="4b511-202">This layer design should be independent for each microservice.</span></span> <span data-ttu-id="4b511-203">Jak již bylo uvedeno dříve, můžete implementovat těch nejsložitějších mikroslužeb následující vzory DDD, při implementaci jednodušší řízené daty mikroslužeb (jednoduché CRUD v jedné vrstvě) v jednodušší způsob.</span><span class="sxs-lookup"><span data-stu-id="4b511-203">As noted earlier, you can implement the most complex microservices following DDD patterns, while implementing simpler data-driven microservices (simple CRUD in a single layer) in a simpler way.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="4b511-204">Další zdroje</span><span class="sxs-lookup"><span data-stu-id="4b511-204">Additional resources</span></span>

-   <span data-ttu-id="4b511-205">**DevIQ. Princip které trvalost**
    [*http://deviq.com/persistence-ignorance/*](http://deviq.com/persistence-ignorance/)</span><span class="sxs-lookup"><span data-stu-id="4b511-205">**DevIQ. Persistence Ignorance principle**
[*http://deviq.com/persistence-ignorance/*](http://deviq.com/persistence-ignorance/)</span></span>

-   <span data-ttu-id="4b511-206">**Oren Eini. Které infrastruktury**
    [*https://ayende.com/blog/3137/infrastructure-ignorance*](https://ayende.com/blog/3137/infrastructure-ignorance)</span><span class="sxs-lookup"><span data-stu-id="4b511-206">**Oren Eini. Infrastructure Ignorance**
[*https://ayende.com/blog/3137/infrastructure-ignorance*](https://ayende.com/blog/3137/infrastructure-ignorance)</span></span>

-   <span data-ttu-id="4b511-207">**Anděl Lopez. Architektura v řízené domény návrhu na základě**
    [*https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/*](https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/)</span><span class="sxs-lookup"><span data-stu-id="4b511-207">**Angel Lopez. Layered Architecture In Domain-Driven Design**
[*https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/*](https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="4b511-208">[Předchozí] (cqrs mikroslužbu reads.md) [Další] (mikroslužbu model.md domény)</span><span class="sxs-lookup"><span data-stu-id="4b511-208">[Previous] (cqrs-microservice-reads.md) [Next] (microservice-domain-model.md)</span></span>