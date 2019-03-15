---
title: Použít porovnávání vzorů funkce k rozšíření datových typů
description: V tomto kurzu pokročilé ukazuje, jak použít porovnávání vzorů techniky k vytvoření funkce pomocí dat a algoritmy, které se vytvářejí zvlášť.
ms.date: 03/13/2019
ms.custom: mvc
ms.openlocfilehash: 210cb15699057482e36984f80dd08f8b19db55d3
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "58051543"
---
# <a name="tutorial-using-pattern-matching-features-to-extend-data-types"></a><span data-ttu-id="0a407-103">Kurz: Použití porovnávání vzorů funkce k rozšíření datových typů</span><span class="sxs-lookup"><span data-stu-id="0a407-103">Tutorial: Using pattern matching features to extend data types</span></span>

<span data-ttu-id="0a407-104">C#7 zavedené základní vzor odpovídající funkce.</span><span class="sxs-lookup"><span data-stu-id="0a407-104">C# 7 introduced basic pattern matching features.</span></span> <span data-ttu-id="0a407-105">Tyto funkce jsou rozšířeny v C# 8 s výrazy typu new a vzory.</span><span class="sxs-lookup"><span data-stu-id="0a407-105">Those features are extended in C# 8 with new expressions and patterns.</span></span> <span data-ttu-id="0a407-106">Můžete napsat funkci, která se chová, jako jste rozšířili typy, které mohou být v jiných knihovnách.</span><span class="sxs-lookup"><span data-stu-id="0a407-106">You can write functionality that behaves as though you extended types that may be in other libraries.</span></span> <span data-ttu-id="0a407-107">Další možností použití vzorců je vytvoření funkce, které vaše aplikace vyžaduje, která nejsou základní funkce rozšiřovaného typu.</span><span class="sxs-lookup"><span data-stu-id="0a407-107">Another use for patterns is to create functionality your application requires that isn't a fundamental feature of the type being extended.</span></span>

<span data-ttu-id="0a407-108">V tomto kurzu se dozvíte jak:</span><span class="sxs-lookup"><span data-stu-id="0a407-108">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="0a407-109">Jak rozpoznat situacích, kdy porovnávání vzorů by měl být použít.</span><span class="sxs-lookup"><span data-stu-id="0a407-109">How to recognize situations where pattern matching should be used.</span></span>
> * <span data-ttu-id="0a407-110">Způsob použití vzoru porovnávání výrazů k implementaci chování na základě typů a hodnot vlastností.</span><span class="sxs-lookup"><span data-stu-id="0a407-110">How to use pattern matching expressions to implement behavior based on types and property values.</span></span>
> * <span data-ttu-id="0a407-111">Jak kombinovat porovnávání vzorů s dalšími technikami, chcete-li vytvořit kompletní algoritmy.</span><span class="sxs-lookup"><span data-stu-id="0a407-111">How to combine pattern matching with other techniques to create complete algorithms.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0a407-112">Požadavky</span><span class="sxs-lookup"><span data-stu-id="0a407-112">Prerequisites</span></span>

<span data-ttu-id="0a407-113">Budete muset nastavit počítač pro spuštění .NET Core, včetně C# kompilátoru 8.0 ve verzi preview.</span><span class="sxs-lookup"><span data-stu-id="0a407-113">You'll need to set up your machine to run .NET Core, including the C# 8.0 preview compiler.</span></span> <span data-ttu-id="0a407-114">C# 8 kompilátoru ve verzi preview jsou k dispozici nejnovější [Visual Studio 2019 preview](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+preview), nebo si prohlédnout nejnovější [ve verzi preview rozhraní .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="0a407-114">The C# 8 preview compiler is available with the latest [Visual Studio 2019 preview](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+preview), or the latest [.NET Core 3.0 preview](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="0a407-115">Tento kurz předpokládá, že jste obeznámeni s C# a .NET, včetně sady Visual Studio nebo rozhraní příkazového řádku .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0a407-115">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="scenarios-for-pattern-matching"></a><span data-ttu-id="0a407-116">Scénáře pro porovnávání vzorů</span><span class="sxs-lookup"><span data-stu-id="0a407-116">Scenarios for pattern matching</span></span>

<span data-ttu-id="0a407-117">Moderní vývoj často zahrnuje integraci dat z více zdrojů a vám informace a přehledy na základě těchto dat v jedné aplikaci získá na ucelenosti.</span><span class="sxs-lookup"><span data-stu-id="0a407-117">Modern development often includes integrating data from multiple sources and presenting information and insights from that data in a single cohesive application.</span></span> <span data-ttu-id="0a407-118">Vy a váš tým nebude mít ovládací prvek nebo přístupu pro všechny typy, které představují příchozí data.</span><span class="sxs-lookup"><span data-stu-id="0a407-118">You and your team won't have control or access for all the types that represent the incoming data.</span></span>

<span data-ttu-id="0a407-119">Pro vytváření typů ve vaší aplikaci, které představují jednotlivé typy dat z těchto různých zdrojů dat by volat klasické objektově orientovaný návrh.</span><span class="sxs-lookup"><span data-stu-id="0a407-119">The classic object-oriented design would call for creating types in your application that represent each data type from those multiple data sources.</span></span> <span data-ttu-id="0a407-120">Aplikace by pak pracovat s těmito novými typy, vytváření hierarchie dědičnosti, vytvoření virtuální metody a implementaci abstrakcí.</span><span class="sxs-lookup"><span data-stu-id="0a407-120">Then, your application would work with those new types, build inheritance hierarchies, create virtual methods, and implement abstractions.</span></span> <span data-ttu-id="0a407-121">Tyto techniky fungují a někdy jsou ty nejlepší nástroje.</span><span class="sxs-lookup"><span data-stu-id="0a407-121">Those techniques work, and sometimes they are the best tools.</span></span> <span data-ttu-id="0a407-122">Jindy můžete napsat menším množstvím kódu.</span><span class="sxs-lookup"><span data-stu-id="0a407-122">Other times you can write less code.</span></span> <span data-ttu-id="0a407-123">Můžete napsat další kód zrušte pomocí technik, které oddělují data od operací, které zpracovávají data.</span><span class="sxs-lookup"><span data-stu-id="0a407-123">You can write more clear code using techniques that separate the data from the operations that manipulate that data.</span></span>

<span data-ttu-id="0a407-124">V tomto kurzu vytvoříte a prozkoumejte aplikaci, která přebere příchozí data z několika externích zdrojů pro jeden scénář.</span><span class="sxs-lookup"><span data-stu-id="0a407-124">In this tutorial, you'll create and explore an application that takes incoming data from several external sources for a single scenario.</span></span> <span data-ttu-id="0a407-125">Uvidíte jak **porovnávání vzorů** poskytuje efektivní způsob, jak spotřebovat a zpracovat data způsoby, které nebyly součástí původního systému.</span><span class="sxs-lookup"><span data-stu-id="0a407-125">You'll see how **pattern matching** provides an efficient way to consume and process that data in ways that weren't part of the original system.</span></span>

<span data-ttu-id="0a407-126">Vezměte v úvahu hlavní metro oblast, která používá ke správě přenosů dat mýtné a ceny za dobu ve špičce.</span><span class="sxs-lookup"><span data-stu-id="0a407-126">Consider a major metro area that is using tolls and peak time pricing to manage traffic.</span></span> <span data-ttu-id="0a407-127">Můžete napsat aplikaci, která vypočítá mýtné vozidla na základě jeho typu.</span><span class="sxs-lookup"><span data-stu-id="0a407-127">You write an application that calculates tolls for a vehicle based on its type.</span></span> <span data-ttu-id="0a407-128">Novější vylepšení zahrnují ceny na základě počtu osob ve vozidle.</span><span class="sxs-lookup"><span data-stu-id="0a407-128">Later enhancements incorporate pricing based on the number of occupants in the vehicle.</span></span> <span data-ttu-id="0a407-129">Dále přidejte ceny založené na čas a den v týdnu.</span><span class="sxs-lookup"><span data-stu-id="0a407-129">Further enhancements add pricing based on the time and the day of the week.</span></span>

<span data-ttu-id="0a407-130">Z tohoto stručný popis vám může mít rychle šrafují si hierarchii objektů modelování tohoto systému.</span><span class="sxs-lookup"><span data-stu-id="0a407-130">From that brief description, you may have quickly sketched out an object hierarchy to model this system.</span></span> <span data-ttu-id="0a407-131">Však vaše data pochází z více zdrojů, jako jsou jinými systémy pro správu registrace vozidlo.</span><span class="sxs-lookup"><span data-stu-id="0a407-131">However, your data is coming from multiple sources like other vehicle registration management systems.</span></span> <span data-ttu-id="0a407-132">Tyto systémy poskytují různé třídy k modelování dat a není nutné jeden objekt modelu, která vám pomůže.</span><span class="sxs-lookup"><span data-stu-id="0a407-132">These systems provide different classes to model that data and you don't have a single object model you can use.</span></span> <span data-ttu-id="0a407-133">V tomto kurzu použijete tyto zjednodušené třídy k modelování dat vozidla mezi těmito externími systémy, jak je znázorněno v následujícím kódu:</span><span class="sxs-lookup"><span data-stu-id="0a407-133">In this tutorial, you'll use these simplified classes to model for the vehicle data from these external systems, as shown in the following code:</span></span>

[!code-csharp[ExternalSystems](../../../samples/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

<span data-ttu-id="0a407-134">Můžete stáhnout počáteční kód z [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) úložiště GitHub.</span><span class="sxs-lookup"><span data-stu-id="0a407-134">You can download the starter code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) GitHub repository.</span></span> <span data-ttu-id="0a407-135">Uvidíte, že třídy vozidlo jsou z různých systémů a jsou v různých oborech názvů.</span><span class="sxs-lookup"><span data-stu-id="0a407-135">You can see that the vehicle classes are from different systems, and are in different namespaces.</span></span> <span data-ttu-id="0a407-136">Žádné společné základní třídy, jiné než `System.Object` můžete využít.</span><span class="sxs-lookup"><span data-stu-id="0a407-136">No common base class, other than `System.Object` can be leveraged.</span></span>

## <a name="pattern-matching-designs"></a><span data-ttu-id="0a407-137">Vzor odpovídající návrhy</span><span class="sxs-lookup"><span data-stu-id="0a407-137">Pattern matching designs</span></span>

<span data-ttu-id="0a407-138">Scénář použitý v tomto kurzu jsou uvedeny druhy problémů, které jsou vhodné pro použití porovnávání vzorů vyřešit:</span><span class="sxs-lookup"><span data-stu-id="0a407-138">The scenario used in this tutorial highlights the kinds of problems that are well suited to use pattern matching to solve:</span></span> 

- <span data-ttu-id="0a407-139">Objekty, které potřebujete k práci s nejsou v hierarchii objektů, který odpovídá vaše cíle.</span><span class="sxs-lookup"><span data-stu-id="0a407-139">The objects you need to work with aren't in an object hierarchy that matches your goals.</span></span> <span data-ttu-id="0a407-140">Pracujete s třídami, které jsou součástí nesouvisejících systémy.</span><span class="sxs-lookup"><span data-stu-id="0a407-140">You may be working with classes that are part of unrelated systems.</span></span>
- <span data-ttu-id="0a407-141">Funkce, které přidáváte, které nejsou součástí základní abstrakce pro tyto třídy.</span><span class="sxs-lookup"><span data-stu-id="0a407-141">The functionality you're adding isn't part of the core abstraction for these classes.</span></span> <span data-ttu-id="0a407-142">Linka zaplaceno vozidla *změny* pro různé typy vozidel, ale linka není základní funkce vozidlo.</span><span class="sxs-lookup"><span data-stu-id="0a407-142">The toll paid by a vehicle *changes* for different types of vehicles, but the toll isn't a core function of the vehicle.</span></span>

<span data-ttu-id="0a407-143">Když *tvar* dat a *operace* zabývat data nejsou společně popsané porovnávání vzorů funkce v C# usnadňují práci s.</span><span class="sxs-lookup"><span data-stu-id="0a407-143">When the *shape* of the data and the *operations* on that data are not described together, the pattern matching features in C# make it easier to work with.</span></span> 

## <a name="implement-the-basic-toll-calculations"></a><span data-ttu-id="0a407-144">Provádění výpočtů základní linka</span><span class="sxs-lookup"><span data-stu-id="0a407-144">Implement the basic toll calculations</span></span>

<span data-ttu-id="0a407-145">Pouze na typ, který využívá nejzákladnější výpočtu linka:</span><span class="sxs-lookup"><span data-stu-id="0a407-145">The most basic toll calculation relies only on the vehicle type:</span></span>

- <span data-ttu-id="0a407-146">A `Car` je $2.00.</span><span class="sxs-lookup"><span data-stu-id="0a407-146">A `Car` is $2.00.</span></span>
- <span data-ttu-id="0a407-147">A `Taxi` je 3.50 $.</span><span class="sxs-lookup"><span data-stu-id="0a407-147">A `Taxi` is $3.50.</span></span>
- <span data-ttu-id="0a407-148">A `Bus` je 5.00 $.</span><span class="sxs-lookup"><span data-stu-id="0a407-148">A `Bus` is $5.00.</span></span>
- <span data-ttu-id="0a407-149">A `DeliveryTruck` je 10,00 USD</span><span class="sxs-lookup"><span data-stu-id="0a407-149">A `DeliveryTruck` is $10.00</span></span>

<span data-ttu-id="0a407-150">Vytvořte nový `TollCalculator` třídy a implementovat vzorce pro porovnávání na typ, který má získat velikost linka.</span><span class="sxs-lookup"><span data-stu-id="0a407-150">Create a new `TollCalculator` class, and implement pattern matching on the vehicle type to get the toll amount.</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    public class TollCalculator
    {
        public decimal CalculateToll(object vehicle) =>
            vehicle switch
        {
            Car c => 2.00m,
            Taxi t => 3.50m,
            Bus b => 5.00m,
            DeliveryTruck t => 10.00m,
            { } => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
            null => throw new ArgumentNullException(nameof(vehicle))
        };
    }
}
```

<span data-ttu-id="0a407-151">Předchozí kód používá **výraz switch** (není stejný jako [ `switch` ](../language-reference/keywords/switch.md) příkaz), který testuje **vzor typu**.</span><span class="sxs-lookup"><span data-stu-id="0a407-151">The preceding code uses a **switch expression** (not the same as a [`switch`](../language-reference/keywords/switch.md) statement) that tests the **type pattern**.</span></span> <span data-ttu-id="0a407-152">A **výraz switch** začíná proměnnou, `vehicle` v předchozím kódu, za nímž následuje `switch` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="0a407-152">A **switch expression** begins with the variable, `vehicle` in the preceding code, followed by the `switch` keyword.</span></span> <span data-ttu-id="0a407-153">Dále obsahuje všechny přepínače arms uvnitř složených závorek.</span><span class="sxs-lookup"><span data-stu-id="0a407-153">Next comes all the switch arms inside curly braces.</span></span> <span data-ttu-id="0a407-154">`switch` Výraz vytvoří další upřesnění zpráv o syntaxi, která obklopuje `switch` příkazu.</span><span class="sxs-lookup"><span data-stu-id="0a407-154">The `switch` expression makes other refinements to the syntax that surrounds the `switch` statement.</span></span> <span data-ttu-id="0a407-155">`case` – Klíčové slovo je vynechán, a výsledek každého arm je výraz.</span><span class="sxs-lookup"><span data-stu-id="0a407-155">The `case` keyword is omitted, and the result of each arm is an expression.</span></span> <span data-ttu-id="0a407-156">Poslední dva arms zobrazit novou funkci jazyka.</span><span class="sxs-lookup"><span data-stu-id="0a407-156">The last two arms show a new language feature.</span></span> <span data-ttu-id="0a407-157">`{ }` Případ odpovídá libovolný nenulový objekt, který neodpovídal starší arm.</span><span class="sxs-lookup"><span data-stu-id="0a407-157">The `{ }` case matches any non-null object that didn't match an earlier arm.</span></span> <span data-ttu-id="0a407-158">Tato arm zachytí nesprávné typy předaný této metodě.</span><span class="sxs-lookup"><span data-stu-id="0a407-158">This arm catches any incorrect types passed to this method.</span></span> <span data-ttu-id="0a407-159">Nakonec `null` vzor zachytí při `null` je předaný této metodě.</span><span class="sxs-lookup"><span data-stu-id="0a407-159">Finally, the `null` pattern catches when `null` is passed to this method.</span></span> <span data-ttu-id="0a407-160">`null` Model může být poslední, protože jiné vzory typ shodný s pouze nenulový objekt nesprávného typu.</span><span class="sxs-lookup"><span data-stu-id="0a407-160">The `null` pattern can be last because the other type patterns match only a non-null object of the correct type.</span></span>

<span data-ttu-id="0a407-161">Můžete otestovat tento kód, pomocí následujícího kódu v `Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="0a407-161">You can test this code using the following code in `Program.cs`:</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    class Program
    {
        static void Main(string[] args)
        {
            var tollCalc = new TollCalculator();

            var car = new Car();
            var taxi = new Taxi();
            var bus = new Bus();
            var truck = new DeliveryTruck();

            Console.WriteLine($"The toll for a car is {tollCalc.CalculateToll(car)}");
            Console.WriteLine($"The toll for a taxi is {tollCalc.CalculateToll(taxi)}");
            Console.WriteLine($"The toll for a bus is {tollCalc.CalculateToll(bus)}");
            Console.WriteLine($"The toll for a truck is {tollCalc.CalculateToll(truck)}");

            try
            {
                tollCalc.CalculateToll("this will fail");
            }
            catch (ArgumentException e)
            {
                Console.WriteLine("Caught an argument exception when using the wrong type", DayOfWeek.Friday);
            }
            try
            {
                tollCalc.CalculateToll(null);
            }
            catch (ArgumentNullException e)
            {
                Console.WriteLine("Caught an argument exception when using null");
            }
        }
    }
}
```

<span data-ttu-id="0a407-162">Tento kód je součástí počáteční projekt, ale je označené jako komentář. Odstranit znaky komentářů, a budete moci otestovat, co jste napsali.</span><span class="sxs-lookup"><span data-stu-id="0a407-162">That code is included in the starter project, but is commented out. Remove the comments, and you can test what you've written.</span></span>

<span data-ttu-id="0a407-163">Začínáte naleznete v tématu Jak vzory vám může pomoci vytvořit algoritmy, kde jsou oddělené kód a data.</span><span class="sxs-lookup"><span data-stu-id="0a407-163">You're starting to see how patterns can help you create algorithms where the code and the data are separate.</span></span> <span data-ttu-id="0a407-164">`switch` Výraz testuje typ a vytváří různé hodnoty na základě výsledků.</span><span class="sxs-lookup"><span data-stu-id="0a407-164">The `switch` expression tests the type and produces different values based on the results.</span></span> <span data-ttu-id="0a407-165">To je jenom začátek.</span><span class="sxs-lookup"><span data-stu-id="0a407-165">That's only the beginning.</span></span>

## <a name="add-occupancy-pricing"></a><span data-ttu-id="0a407-166">Přidat obsazení ceny</span><span class="sxs-lookup"><span data-stu-id="0a407-166">Add occupancy pricing</span></span>

<span data-ttu-id="0a407-167">Autorita linka se chce podporovat vozidel projít využívá maximální kapacitu.</span><span class="sxs-lookup"><span data-stu-id="0a407-167">The toll authority wants to encourage vehicles to travel at maximum capacity.</span></span> <span data-ttu-id="0a407-168">Jste se rozhodli účtovat více při vozidel mají menší počet cestujících a podporovat plnou vozidel tím, že nabízí nižší ceny:</span><span class="sxs-lookup"><span data-stu-id="0a407-168">They've decided to charge more when vehicles have fewer passengers, and encourage full vehicles by offering lower pricing:</span></span>

- <span data-ttu-id="0a407-169">Auta nebo taxi s žádné cestujících platit navíc 0,50 USD.</span><span class="sxs-lookup"><span data-stu-id="0a407-169">Cars and taxis with no passengers pay an extra $0.50.</span></span>
- <span data-ttu-id="0a407-170">Auta nebo taxi s dvěma cestujících získat 0,50 slevu.</span><span class="sxs-lookup"><span data-stu-id="0a407-170">Cars and taxis with two passengers get a 0.50 discount.</span></span>
- <span data-ttu-id="0a407-171">Auta nebo taxi se třemi nebo více cestujících získat slevu 1,00 $.</span><span class="sxs-lookup"><span data-stu-id="0a407-171">Cars and taxis with three or more passengers get a $1.00 discount.</span></span>
- <span data-ttu-id="0a407-172">Sběrnice, které jsou kratší než 50 % úplné platit navíc 2.00 $.</span><span class="sxs-lookup"><span data-stu-id="0a407-172">Buses that are less than 50% full pay an extra $2.00.</span></span>
- <span data-ttu-id="0a407-173">Sběrnice, které jsou více než 90 % úplné získat slevu 1,00 $.</span><span class="sxs-lookup"><span data-stu-id="0a407-173">Buses that are more than 90% full get a $1.00 discount.</span></span>

<span data-ttu-id="0a407-174">Tato pravidla je možné implementovat pomocí **vlastnost vzor** ve stejném výrazu přepínače.</span><span class="sxs-lookup"><span data-stu-id="0a407-174">These rules can be implemented using the **property pattern** in the same switch expression.</span></span> <span data-ttu-id="0a407-175">Vzor pro vlastnost prozkoumá vlastností objektu po určil typ.</span><span class="sxs-lookup"><span data-stu-id="0a407-175">The property pattern examines properties of the object once the type has been determined.</span></span>  <span data-ttu-id="0a407-176">Jeden případ `Car` rozšíří na čtyři různé případy:</span><span class="sxs-lookup"><span data-stu-id="0a407-176">The single case for a `Car` expands to four different cases:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0} => 2.00m + 0.50m,
    Car { Passengers: 1 } => 2.0m,
    Car { Passengers: 2} => 2.0m - 0.50m,
    Car c when c.Passengers > 2 => 2.00m - 1.0m,

    // ...
};
```

<span data-ttu-id="0a407-177">První tři případy typ jako testu `Car`, zkontrolujte hodnotu `Passengers` vlastnost.</span><span class="sxs-lookup"><span data-stu-id="0a407-177">The first three cases test the type as a `Car`, then check the value of the `Passengers` property.</span></span> <span data-ttu-id="0a407-178">Pokud se obě shodovat, tento výraz je vyhodnocen a vrácena.</span><span class="sxs-lookup"><span data-stu-id="0a407-178">If both match, that expression is evaluated and returned.</span></span> <span data-ttu-id="0a407-179">Zobrazí poslední klauzule `when` klauzule pro vlastnosti modelu.</span><span class="sxs-lookup"><span data-stu-id="0a407-179">The final clause shows the `when` clause for a property pattern.</span></span> <span data-ttu-id="0a407-180">Můžete použít `when` klauzule k testování podmínek jiné než rovnost pro vlastnost.</span><span class="sxs-lookup"><span data-stu-id="0a407-180">You use the `when` clause to test conditions other than equality on a property.</span></span> <span data-ttu-id="0a407-181">V předchozím příkladu `when` klauzule testy, že jsou k dispozici více než 2 cestujících v autě.</span><span class="sxs-lookup"><span data-stu-id="0a407-181">In the preceding example, the `when` clause tests to see that there are more than 2 passengers in the car.</span></span> <span data-ttu-id="0a407-182">Přesněji řečeno není nutné v tomto příkladu.</span><span class="sxs-lookup"><span data-stu-id="0a407-182">Strictly speaking, it's not necessary in this example.</span></span>

<span data-ttu-id="0a407-183">By bylo třeba rozbalit také případy taxi podobným způsobem:</span><span class="sxs-lookup"><span data-stu-id="0a407-183">You would also expand the cases for taxis in a similar manner:</span></span>

```csharp
vehicle switch
{
    // ...

    Taxi { Fares: 0} => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2} => 3.50m - 0.50m,
    Taxi t => 3.50m - 1.00m,

    // ...
};
```

<span data-ttu-id="0a407-184">V předchozím příkladu `when` na posledním případě vynechání klauzule.</span><span class="sxs-lookup"><span data-stu-id="0a407-184">In the preceding example, the `when` clause was omitted on the final case.</span></span>

<span data-ttu-id="0a407-185">V dalším kroku implementujte obsazení pravidla tak, že rozbalíte případů pro sběrnice, jak je znázorněno v následujícím příkladu:</span><span class="sxs-lookup"><span data-stu-id="0a407-185">Next, implement the occupancy rules by expanding the cases for buses, as shown in the following exmaple:</span></span>

```csharp
vehicle switch
{
    // ...

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m, 
    Bus b => 5.00m,
    
    // ...
};
```

<span data-ttu-id="0a407-186">Autorita linka není problémem počet cestujících v trucks doručování.</span><span class="sxs-lookup"><span data-stu-id="0a407-186">The toll authority isn't concerned with the number of passengers in the delivery trucks.</span></span> <span data-ttu-id="0a407-187">Místo toho že účtovat více založené na třídě váha nákladních vozů.</span><span class="sxs-lookup"><span data-stu-id="0a407-187">Instead, they charge more based on the weight class of the trucks.</span></span> <span data-ttu-id="0a407-188">Trucks víc než 5000 lbs se účtují další 5.00 $.</span><span class="sxs-lookup"><span data-stu-id="0a407-188">Trucks over 5000 lbs are charged an extra $5.00.</span></span> <span data-ttu-id="0a407-189">Světle nákladních vozidel, v části 3000 lbs disponují $2.00 slevy.</span><span class="sxs-lookup"><span data-stu-id="0a407-189">Light trucks, under 3000 lbs are given a $2.00 discount.</span></span>  <span data-ttu-id="0a407-190">Toto pravidlo je implementováno s následujícím kódem:</span><span class="sxs-lookup"><span data-stu-id="0a407-190">That rule is implemented with the following code:</span></span>

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="0a407-191">Po dokončení budete mít metodu, která vypadá podobně jako následující:</span><span class="sxs-lookup"><span data-stu-id="0a407-191">When you've finished, you'll have a method that looks much like the following:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0} => 2.00m + 0.50m,
    Car { Passengers: 1 } => 2.0m,
    Car { Passengers: 2} => 2.0m - 0.50m,
    Car c when c.Passengers > 2 => 2.00m - 1.0m,
   
    Taxi { Fares: 0} => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2} => 3.50m - 0.50m,
    Taxi t => 3.50m - 1.00m,
    
    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m, 
    Bus b => 5.00m,
    
    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

## <a name="recursive-patterns"></a><span data-ttu-id="0a407-192">Rekurzivní vzory</span><span class="sxs-lookup"><span data-stu-id="0a407-192">Recursive patterns</span></span>

<span data-ttu-id="0a407-193">Můžete provést tento kód méně opakované pomocí **rekurzivní vzory**.</span><span class="sxs-lookup"><span data-stu-id="0a407-193">You can make this code less repetitive by using **recursive patterns**.</span></span> <span data-ttu-id="0a407-194">`Car` a `Taxi` mají čtyři různé arms v předchozích příkladech.</span><span class="sxs-lookup"><span data-stu-id="0a407-194">The `Car` and `Taxi` both have four different arms in the preceding examples.</span></span> <span data-ttu-id="0a407-195">V obou případech můžete vytvořit typ vzor, který se předají do vlastnosti modelu.</span><span class="sxs-lookup"><span data-stu-id="0a407-195">In both cases, you can create a type pattern that feeds into a property pattern.</span></span> <span data-ttu-id="0a407-196">Tato technika je znázorněno v následujícím kódu:</span><span class="sxs-lookup"><span data-stu-id="0a407-196">This technique is shown in the following code:</span></span>

```csharp
public decimal CalculateToll(object vehicle) =>
    vehicle switch
    {
        Car c => c.Passengers switch
        {
            0 => 2.00m + 0.5m,
            1 => 2.0m,
            2 => 2.0m - 0.5m,
            _ => 2.00m - 1.0m
        },
    
        Taxi t => t.Fares switch
        {
            0 => 3.50m + 1.00m,
            1 => 3.50m,
            2 => 3.50m - 0.50m,
            _ => 3.50m - 1.00m
        },
    
        Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
        Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m, 
        Bus b => 5.00m,
    
        DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
        DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
        DeliveryTruck t => 10.00m,
        { } => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
        null => throw new ArgumentNullException(nameof(vehicle))
    };
```

<span data-ttu-id="0a407-197">V předchozím příkladu, pomocí výrazu rekurzivní znamená, že nemusíte opakovat `Car` a `Taxi` arms obsahovat arms podřízený, které testují hodnotu vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="0a407-197">In the preceding sample, using a recursive expression means you don't repeat the `Car` and `Taxi` arms contain child arms that test the property value.</span></span> <span data-ttu-id="0a407-198">Tato technika se nepoužívá pro `Bus` a `DeliveryTruck` zbraní protože zbraně testování rozsahy pro vlastnost, nikoli jednotlivých hodnot.</span><span class="sxs-lookup"><span data-stu-id="0a407-198">This technique isn't used for the `Bus` and `DeliveryTruck` arms because those arms are testing ranges for the property, not discrete values.</span></span>

## <a name="add-peak-pricing"></a><span data-ttu-id="0a407-199">Přidat ceny ve špičce</span><span class="sxs-lookup"><span data-stu-id="0a407-199">Add peak pricing</span></span>

<span data-ttu-id="0a407-200">Pro poslední funkci autority linka chce přidat dobu ve špičce citlivé ceny.</span><span class="sxs-lookup"><span data-stu-id="0a407-200">For the final feature, the toll authority wants to add time sensitive peak pricing.</span></span> <span data-ttu-id="0a407-201">Během ráno a špičce hodin večer jsou mýtné dvojitá.</span><span class="sxs-lookup"><span data-stu-id="0a407-201">During the morning and evening rush hours, the tolls are doubled.</span></span> <span data-ttu-id="0a407-202">Toto pravidlo ovlivní pouze provoz v jednom směru: Město ráno příchozí a odchozí ve špičce hodině večer.</span><span class="sxs-lookup"><span data-stu-id="0a407-202">That rule only affects traffic in one direction: inbound to the city in the morning, and outbound in the evening rush hour.</span></span> <span data-ttu-id="0a407-203">Během jindy během pracovního dne mýtné zvýšit o 50 %.</span><span class="sxs-lookup"><span data-stu-id="0a407-203">During other times during the workday, tolls increase by 50%.</span></span> <span data-ttu-id="0a407-204">Noční pozdní a časná ráno, mýtné jsou sníženy o 25 %.</span><span class="sxs-lookup"><span data-stu-id="0a407-204">Late night and early morning, tolls are reduced by 25%.</span></span> <span data-ttu-id="0a407-205">Během víkendu je normální rychlosti, bez ohledu na čas.</span><span class="sxs-lookup"><span data-stu-id="0a407-205">During the weekend, it's the normal rate, regardless of the time.</span></span>

<span data-ttu-id="0a407-206">Porovnávání vzorů pro tuto funkci použijete, ale budete ji integrovat s dalšími technikami.</span><span class="sxs-lookup"><span data-stu-id="0a407-206">You'll use pattern matching for this feature, but you'll integrate it with other techniques.</span></span> <span data-ttu-id="0a407-207">Může vytvořit jeden vzor odpovídající výraz, který by účtu všechny kombinace směr, den v týdnu a čas.</span><span class="sxs-lookup"><span data-stu-id="0a407-207">You could build a single pattern match expression that would account all the combinations of direction, day of the week, and time.</span></span> <span data-ttu-id="0a407-208">Výsledek by byl složitý výraz.</span><span class="sxs-lookup"><span data-stu-id="0a407-208">The result would be a complicated expression.</span></span> <span data-ttu-id="0a407-209">By bylo obtížné číst a obtížně srozumitelné.</span><span class="sxs-lookup"><span data-stu-id="0a407-209">It would be hard to read and difficult to understand.</span></span> <span data-ttu-id="0a407-210">Díky tomu se obtížně zajistili její správnost.</span><span class="sxs-lookup"><span data-stu-id="0a407-210">That makes it hard to ensure correctness.</span></span> <span data-ttu-id="0a407-211">Místo toho sloučit tyto metody pro vytvoření n-tice hodnot, která stručně popisuje tyto stavy.</span><span class="sxs-lookup"><span data-stu-id="0a407-211">Instead, combine those methods to build a tuple of values that concisely describes all those states.</span></span> <span data-ttu-id="0a407-212">Pak pomocí porovnávání vzorů pro výpočet multiplikátor pro placená linka.</span><span class="sxs-lookup"><span data-stu-id="0a407-212">Then use pattern matching to calculate a multiplier for the toll.</span></span> <span data-ttu-id="0a407-213">Řazené kolekce členů obsahuje tři samostatné podmínky:</span><span class="sxs-lookup"><span data-stu-id="0a407-213">The tuple contains three discrete conditions:</span></span>

- <span data-ttu-id="0a407-214">Den je jeden den v týdnu nebo víkendech.</span><span class="sxs-lookup"><span data-stu-id="0a407-214">The day is either a weekday or a weekend.</span></span>
- <span data-ttu-id="0a407-215">Vzdálené čas, kdy se shromažďují linka.</span><span class="sxs-lookup"><span data-stu-id="0a407-215">The band of time when the toll is collected.</span></span>
- <span data-ttu-id="0a407-216">Směr je do město nebo z něj Město</span><span class="sxs-lookup"><span data-stu-id="0a407-216">The direction is into the city or out of the city</span></span>

<span data-ttu-id="0a407-217">Následující tabulka uvádí kombinace vstupních hodnot a ceny multiplikátor ve špičce:</span><span class="sxs-lookup"><span data-stu-id="0a407-217">The following table shows the combinations of input values and the peak pricing multiplier:</span></span>

| <span data-ttu-id="0a407-218">Den</span><span class="sxs-lookup"><span data-stu-id="0a407-218">Day</span></span>        | <span data-ttu-id="0a407-219">Čas</span><span class="sxs-lookup"><span data-stu-id="0a407-219">Time</span></span>         | <span data-ttu-id="0a407-220">Směr</span><span class="sxs-lookup"><span data-stu-id="0a407-220">Direction</span></span> | <span data-ttu-id="0a407-221">Premium</span><span class="sxs-lookup"><span data-stu-id="0a407-221">Premium</span></span> |
| ---------- | ------------ | --------- |--------:|
| <span data-ttu-id="0a407-222">Den v týdnu</span><span class="sxs-lookup"><span data-stu-id="0a407-222">Weekday</span></span>    | <span data-ttu-id="0a407-223">naléhavá ráno</span><span class="sxs-lookup"><span data-stu-id="0a407-223">morning rush</span></span> | <span data-ttu-id="0a407-224">Příchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-224">inbound</span></span>   | <span data-ttu-id="0a407-225">x 2.00</span><span class="sxs-lookup"><span data-stu-id="0a407-225">x 2.00</span></span>  |
| <span data-ttu-id="0a407-226">Den v týdnu</span><span class="sxs-lookup"><span data-stu-id="0a407-226">Weekday</span></span>    | <span data-ttu-id="0a407-227">naléhavá ráno</span><span class="sxs-lookup"><span data-stu-id="0a407-227">morning rush</span></span> | <span data-ttu-id="0a407-228">Odchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-228">outbound</span></span>  | <span data-ttu-id="0a407-229">x 1,00</span><span class="sxs-lookup"><span data-stu-id="0a407-229">x 1.00</span></span>  |
| <span data-ttu-id="0a407-230">Den v týdnu</span><span class="sxs-lookup"><span data-stu-id="0a407-230">Weekday</span></span>    | <span data-ttu-id="0a407-231">denní</span><span class="sxs-lookup"><span data-stu-id="0a407-231">daytime</span></span>      | <span data-ttu-id="0a407-232">Příchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-232">inbound</span></span>   | <span data-ttu-id="0a407-233">x 1.50</span><span class="sxs-lookup"><span data-stu-id="0a407-233">x 1.50</span></span>  |
| <span data-ttu-id="0a407-234">Den v týdnu</span><span class="sxs-lookup"><span data-stu-id="0a407-234">Weekday</span></span>    | <span data-ttu-id="0a407-235">denní</span><span class="sxs-lookup"><span data-stu-id="0a407-235">daytime</span></span>      | <span data-ttu-id="0a407-236">Odchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-236">outbound</span></span>  | <span data-ttu-id="0a407-237">x 1.50</span><span class="sxs-lookup"><span data-stu-id="0a407-237">x 1.50</span></span>  |
| <span data-ttu-id="0a407-238">Den v týdnu</span><span class="sxs-lookup"><span data-stu-id="0a407-238">Weekday</span></span>    | <span data-ttu-id="0a407-239">večer špičce</span><span class="sxs-lookup"><span data-stu-id="0a407-239">evening rush</span></span> | <span data-ttu-id="0a407-240">Příchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-240">inbound</span></span>   | <span data-ttu-id="0a407-241">x 1,00</span><span class="sxs-lookup"><span data-stu-id="0a407-241">x 1.00</span></span>  |
| <span data-ttu-id="0a407-242">Den v týdnu</span><span class="sxs-lookup"><span data-stu-id="0a407-242">Weekday</span></span>    | <span data-ttu-id="0a407-243">večer špičce</span><span class="sxs-lookup"><span data-stu-id="0a407-243">evening rush</span></span> | <span data-ttu-id="0a407-244">Odchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-244">outbound</span></span>  | <span data-ttu-id="0a407-245">x 2.00</span><span class="sxs-lookup"><span data-stu-id="0a407-245">x 2.00</span></span>  |
| <span data-ttu-id="0a407-246">Den v týdnu</span><span class="sxs-lookup"><span data-stu-id="0a407-246">Weekday</span></span>    | <span data-ttu-id="0a407-247">přes noc</span><span class="sxs-lookup"><span data-stu-id="0a407-247">overnight</span></span>    | <span data-ttu-id="0a407-248">Příchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-248">inbound</span></span>   | <span data-ttu-id="0a407-249">x 0,75.</span><span class="sxs-lookup"><span data-stu-id="0a407-249">x 0.75</span></span>  |
| <span data-ttu-id="0a407-250">Den v týdnu</span><span class="sxs-lookup"><span data-stu-id="0a407-250">Weekday</span></span>    | <span data-ttu-id="0a407-251">přes noc</span><span class="sxs-lookup"><span data-stu-id="0a407-251">overnight</span></span>    | <span data-ttu-id="0a407-252">Odchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-252">outbound</span></span>  | <span data-ttu-id="0a407-253">x 0,75.</span><span class="sxs-lookup"><span data-stu-id="0a407-253">x 0.75</span></span>  |
| <span data-ttu-id="0a407-254">Víkendu</span><span class="sxs-lookup"><span data-stu-id="0a407-254">Weekend</span></span>    | <span data-ttu-id="0a407-255">naléhavá ráno</span><span class="sxs-lookup"><span data-stu-id="0a407-255">morning rush</span></span> | <span data-ttu-id="0a407-256">Příchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-256">inbound</span></span>   | <span data-ttu-id="0a407-257">x 1,00</span><span class="sxs-lookup"><span data-stu-id="0a407-257">x 1.00</span></span>  |
| <span data-ttu-id="0a407-258">Víkendu</span><span class="sxs-lookup"><span data-stu-id="0a407-258">Weekend</span></span>    | <span data-ttu-id="0a407-259">naléhavá ráno</span><span class="sxs-lookup"><span data-stu-id="0a407-259">morning rush</span></span> | <span data-ttu-id="0a407-260">Odchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-260">outbound</span></span>  | <span data-ttu-id="0a407-261">x 1,00</span><span class="sxs-lookup"><span data-stu-id="0a407-261">x 1.00</span></span>  |
| <span data-ttu-id="0a407-262">Víkendu</span><span class="sxs-lookup"><span data-stu-id="0a407-262">Weekend</span></span>    | <span data-ttu-id="0a407-263">denní</span><span class="sxs-lookup"><span data-stu-id="0a407-263">daytime</span></span>      | <span data-ttu-id="0a407-264">Příchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-264">inbound</span></span>   | <span data-ttu-id="0a407-265">x 1,00</span><span class="sxs-lookup"><span data-stu-id="0a407-265">x 1.00</span></span>  |
| <span data-ttu-id="0a407-266">Víkendu</span><span class="sxs-lookup"><span data-stu-id="0a407-266">Weekend</span></span>    | <span data-ttu-id="0a407-267">denní</span><span class="sxs-lookup"><span data-stu-id="0a407-267">daytime</span></span>      | <span data-ttu-id="0a407-268">Odchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-268">outbound</span></span>  | <span data-ttu-id="0a407-269">x 1,00</span><span class="sxs-lookup"><span data-stu-id="0a407-269">x 1.00</span></span>  |
| <span data-ttu-id="0a407-270">Víkendu</span><span class="sxs-lookup"><span data-stu-id="0a407-270">Weekend</span></span>    | <span data-ttu-id="0a407-271">večer špičce</span><span class="sxs-lookup"><span data-stu-id="0a407-271">evening rush</span></span> | <span data-ttu-id="0a407-272">Příchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-272">inbound</span></span>   | <span data-ttu-id="0a407-273">x 1,00</span><span class="sxs-lookup"><span data-stu-id="0a407-273">x 1.00</span></span>  |
| <span data-ttu-id="0a407-274">Víkendu</span><span class="sxs-lookup"><span data-stu-id="0a407-274">Weekend</span></span>    | <span data-ttu-id="0a407-275">večer špičce</span><span class="sxs-lookup"><span data-stu-id="0a407-275">evening rush</span></span> | <span data-ttu-id="0a407-276">Odchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-276">outbound</span></span>  | <span data-ttu-id="0a407-277">x 1,00</span><span class="sxs-lookup"><span data-stu-id="0a407-277">x 1.00</span></span>  |
| <span data-ttu-id="0a407-278">Víkendu</span><span class="sxs-lookup"><span data-stu-id="0a407-278">Weekend</span></span>    | <span data-ttu-id="0a407-279">přes noc</span><span class="sxs-lookup"><span data-stu-id="0a407-279">overnight</span></span>    | <span data-ttu-id="0a407-280">Příchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-280">inbound</span></span>   | <span data-ttu-id="0a407-281">x 1,00</span><span class="sxs-lookup"><span data-stu-id="0a407-281">x 1.00</span></span>  |
| <span data-ttu-id="0a407-282">Víkendu</span><span class="sxs-lookup"><span data-stu-id="0a407-282">Weekend</span></span>    | <span data-ttu-id="0a407-283">přes noc</span><span class="sxs-lookup"><span data-stu-id="0a407-283">overnight</span></span>    | <span data-ttu-id="0a407-284">Odchozí</span><span class="sxs-lookup"><span data-stu-id="0a407-284">outbound</span></span>  | <span data-ttu-id="0a407-285">x 1,00</span><span class="sxs-lookup"><span data-stu-id="0a407-285">x 1.00</span></span>  |

<span data-ttu-id="0a407-286">Existují 16 různé kombinace tří proměnných.</span><span class="sxs-lookup"><span data-stu-id="0a407-286">There are 16 different combinations of the three variables.</span></span> <span data-ttu-id="0a407-287">Díky kombinaci některá z podmínek, zjednodušíte výraz konečné přepínače.</span><span class="sxs-lookup"><span data-stu-id="0a407-287">By combining some of the conditions, you'll simplify the final switch expression.</span></span>

<span data-ttu-id="0a407-288">Používá systém, který shromažďuje nástroje <xref:System.DateTime> strukturu pro čas, kdy linka byla kolekce.</span><span class="sxs-lookup"><span data-stu-id="0a407-288">The system that collects the tools uses a <xref:System.DateTime> structure for the time when the toll was collection.</span></span> <span data-ttu-id="0a407-289">Vytvořte člena metody, které z předchozí tabulky vytvořte proměnné.</span><span class="sxs-lookup"><span data-stu-id="0a407-289">Build member methods that create the variables from the preceding table.</span></span>  <span data-ttu-id="0a407-290">Následující funkce používá jako vzor odpovídající výraz přepínače vyjádřit, jestli <xref:System.DateTime> představuje víkend nebo jeden den v týdnu:</span><span class="sxs-lookup"><span data-stu-id="0a407-290">The following function uses as pattern matching switch expression to express whether a <xref:System.DateTime> represents a weekend or a weekday:</span></span>

```csharp
private static bool IsWeekDay(DateTime timeOfToll) =>
    timeOfToll.DayOfWeek switch
    {
        DayOfWeek.Monday => true,
        DayOfWeek.Tuesday => true,
        DayOfWeek.Wednesday => true,
        DayOfWeek.Thursday => true,
        DayOfWeek.Friday => true,
        DayOfWeek.Saturday => false,
        DayOfWeek.Sunday => false
    };
```

<span data-ttu-id="0a407-291">Tato metoda funguje, ale je automatizujete.</span><span class="sxs-lookup"><span data-stu-id="0a407-291">That method works, but it's repetitious.</span></span> <span data-ttu-id="0a407-292">Nemůžete zjednodušit, jak je znázorněno v následujícím kódu:</span><span class="sxs-lookup"><span data-stu-id="0a407-292">You can simplify it, as shown in the following code:</span></span>

```csharp
private static bool IsWeekDay(DateTime timeOfToll) =>
    timeOfToll.DayOfWeek switch
    {
        DayOfWeek.Saturday,  => false,
        DayOfWeek.Sunday => false,
        _ => true
    };
```

<span data-ttu-id="0a407-293">Kombinací dvou hodnot do jedné arm, můžete provést další zjednodušení na tento výraz:</span><span class="sxs-lookup"><span data-stu-id="0a407-293">You can make a further simplification to this expression by combining the two values into one arm:</span></span>

[!code-csharp[IsWeekDay](../../../samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

<span data-ttu-id="0a407-294">V dalším kroku přidejte podobnou funkci ke kategorizaci času bloky:</span><span class="sxs-lookup"><span data-stu-id="0a407-294">Next, add a similar function to categorize the time into the blocks:</span></span>

[!code-csharp[GetTimeBand](../../../samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

<span data-ttu-id="0a407-295">Předchozí metoda nepoužívá porovnávání vzorů.</span><span class="sxs-lookup"><span data-stu-id="0a407-295">The previous method doesn't use pattern matching.</span></span> <span data-ttu-id="0a407-296">Je jasnější, pomocí známých cascade z `if` příkazy.</span><span class="sxs-lookup"><span data-stu-id="0a407-296">It's clearer using a familiar cascade of `if` statements.</span></span> <span data-ttu-id="0a407-297">Přidat soukromé `enum` převést každý časový rozsah na diskrétní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="0a407-297">You do add a private `enum` to convert each range of time to a discrete value.</span></span>

<span data-ttu-id="0a407-298">Po vytvoření tyto metody můžete použít jiné `switch` výraz s **vzor n-tice** k výpočtu cenové úrovně premium.</span><span class="sxs-lookup"><span data-stu-id="0a407-298">After you create those methods, you can use another `switch` expression with the **tuple pattern** to calculate the pricing premium.</span></span> <span data-ttu-id="0a407-299">Může vytvářet `switch` výraz s všechny 16 arms:</span><span class="sxs-lookup"><span data-stu-id="0a407-299">You could build a `switch` expression with all 16 arms:</span></span>

[!code-csharp[FullTuplePattern](../../../samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

<span data-ttu-id="0a407-300">Výše kód funguje, ale můžete se dá zjednodušit.</span><span class="sxs-lookup"><span data-stu-id="0a407-300">The above code works, but it can be simplified.</span></span> <span data-ttu-id="0a407-301">Všechny osm kombinace pro víkendu mají stejné linka.</span><span class="sxs-lookup"><span data-stu-id="0a407-301">All eight combinations for the weekend have the same toll.</span></span> <span data-ttu-id="0a407-302">Můžete nahradit všechny osm tento jeden řádek:</span><span class="sxs-lookup"><span data-stu-id="0a407-302">You can replace all eight with the following one line:</span></span>

```csharp
(false, _, _) => 1.0m,
```

<span data-ttu-id="0a407-303">Příchozí a odchozí provoz mají stejné multiplikátor během denní den v týdnu a hodiny přes noc.</span><span class="sxs-lookup"><span data-stu-id="0a407-303">Both inbound and outbound traffic have the same multiplier during the weekday daytime and overnight hours.</span></span> <span data-ttu-id="0a407-304">Tyto čtyři přepínač arms je možné nahradit následující dva řádky:</span><span class="sxs-lookup"><span data-stu-id="0a407-304">Those four switch arms can be replaced with the follow two lines:</span></span>

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _) => 1.5m,
```

<span data-ttu-id="0a407-305">Kód by měl vypadat jako v následujícím kódu až tyto dvě změny:</span><span class="sxs-lookup"><span data-stu-id="0a407-305">The code should look like the following code after those two changes:</span></span>

```csharp
public decimal PeakTimePremium(DateTime timeOfToll, bool inbound) =>
    (IsWeekDay(timeOfToll), GetTimeBand(timeOfToll), inbound) switch
    {
        (true, TimeBand.MorningRush, true) => 2.00m,
        (true, TimeBand.MorningRush, false) => 1.00m,
        (true, TimeBand.Daytime, _) => 1.50m,
        (true, TimeBand.EveningRush, true) => 1.00m,
        (true, TimeBand.EveningRush, false) => 2.00m,
        (true, TimeBand.Overnight, _) => 0.75m,
        (false, _, _) => 1.00m,
    };
```

<span data-ttu-id="0a407-306">Nakonec můžete odebrat dvě špičce hodinu případů, kdy platíte běžná cena.</span><span class="sxs-lookup"><span data-stu-id="0a407-306">Finally, you can remove the two rush hour times that pay the regular price.</span></span> <span data-ttu-id="0a407-307">Po odebrání těchto arms můžete nahradit `false` s zahození (`_`) v posledním přepínač arm.</span><span class="sxs-lookup"><span data-stu-id="0a407-307">Once you remove those arms, you can replace the `false` with a discard (`_`) in the final switch arm.</span></span> <span data-ttu-id="0a407-308">Budete mít hotové následující metodu:</span><span class="sxs-lookup"><span data-stu-id="0a407-308">You'll have the following finished method:</span></span>

[!code-csharp[SimplifiedTuplePattern](../../../samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

<span data-ttu-id="0a407-309">Tento příklad ukazuje, jednou z výhod porovnávání vzorů.</span><span class="sxs-lookup"><span data-stu-id="0a407-309">This example highlights one of the advantages of pattern matching.</span></span> <span data-ttu-id="0a407-310">Vzor větví se vyhodnocují v pořadí.</span><span class="sxs-lookup"><span data-stu-id="0a407-310">The pattern branches are evaluated in order.</span></span> <span data-ttu-id="0a407-311">Pokud změníte uspořádání, je tak, aby starší větev zpracovává jeden z novějších případy, kompilátor zobrazí upozornění.</span><span class="sxs-lookup"><span data-stu-id="0a407-311">If you rearrange them so that an earlier branch handles one of your later cases, the compiler warns you.</span></span> <span data-ttu-id="0a407-312">Tato pravidla jazyk usnadnili provést předchozí zjednodušení s vědomím, že kód nezměnila.</span><span class="sxs-lookup"><span data-stu-id="0a407-312">Those language rules made it easier to do the preceding simplifications with confidence that the code didn't change.</span></span>

<span data-ttu-id="0a407-313">Porovnávání vzorů poskytuje přirozený syntaxi provádět jiné řešení než vytvoříte, pokud jste použili objektově orientované techniky.</span><span class="sxs-lookup"><span data-stu-id="0a407-313">Pattern matching provides a natural syntax to implement different solutions than you'd create if you used object-oriented techniques.</span></span> <span data-ttu-id="0a407-314">Data a funkce live této doby změny nepublikujete, příčinou je v cloudu.</span><span class="sxs-lookup"><span data-stu-id="0a407-314">The cloud is causing data and functionality to live apart.</span></span> <span data-ttu-id="0a407-315">*Tvar* dat a *operace* na to nejsou popsané nutně společně.</span><span class="sxs-lookup"><span data-stu-id="0a407-315">The *shape* of the data and the *operations* on it aren't necessarily described together.</span></span> <span data-ttu-id="0a407-316">V tomto kurzu využívat existující data z jeho původní funkce zcela různými způsoby.</span><span class="sxs-lookup"><span data-stu-id="0a407-316">In this tutorial, you consumed existing data in entirely different ways from its original function.</span></span> <span data-ttu-id="0a407-317">Porovnávání vzorů přiřadil schopnost psát funkce tohoto selhání jsou typy, i když nelze rozšířit, je.</span><span class="sxs-lookup"><span data-stu-id="0a407-317">Pattern matching gave you the ability to write functionality that over those types, even though you couldn't extend them.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0a407-318">Další kroky</span><span class="sxs-lookup"><span data-stu-id="0a407-318">Next steps</span></span>

<span data-ttu-id="0a407-319">Dokončený kód z si můžete stáhnout [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) úložiště GitHub.</span><span class="sxs-lookup"><span data-stu-id="0a407-319">You can download the finished code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) GitHub repository.</span></span> <span data-ttu-id="0a407-320">Prozkoumávání vzorců sami a přidejte tuto techniku regulární kódování aktivit.</span><span class="sxs-lookup"><span data-stu-id="0a407-320">Explore patterns on your own and add this technique into your regular coding activities.</span></span> <span data-ttu-id="0a407-321">Tyto techniky učení nabízí další způsob, jak přistupovat ke problémy a vytvořit nové funkce.</span><span class="sxs-lookup"><span data-stu-id="0a407-321">Learning these techniques gives you another way to approach problems and create new functionality.</span></span>