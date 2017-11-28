---
title: "Stromy výrazů vysvětlené"
description: "Další informace o stromů výrazů a jak jsou užitečné při překládání algoritmy pro externí provádění a provádějící kontrolu kódu před jeho provedením."
keywords: "Rozhraní .NET, .NET core"
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: bbcdd339-86eb-4ae5-9911-4c214a39a92d
ms.openlocfilehash: 1de856a139ac7a6dee25f1dae54924e33f14a33b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="expression-trees-explained"></a><span data-ttu-id="d26d4-104">Stromy výrazů vysvětlené</span><span class="sxs-lookup"><span data-stu-id="d26d4-104">Expression Trees Explained</span></span>

[<span data-ttu-id="d26d4-105">Předchozí – přehled</span><span class="sxs-lookup"><span data-stu-id="d26d4-105">Previous -- Overview</span></span>](expression-trees.md)

<span data-ttu-id="d26d4-106">Strom výrazu je datová struktura, která definuje kódu.</span><span class="sxs-lookup"><span data-stu-id="d26d4-106">An Expression Tree is a data structure that defines code.</span></span> <span data-ttu-id="d26d4-107">Jsou založené na stejné struktury, které kompilátor používá k analýze kódu a generovat kompilovaný výstup.</span><span class="sxs-lookup"><span data-stu-id="d26d4-107">They are based on the same structures that a compiler uses to analyze code and generate the compiled output.</span></span> <span data-ttu-id="d26d4-108">Při procházení tohoto kurzu si všimnete s bit podobnosti mezi stromů výrazů a typy sloužící k vytvoření rozhraní API Roslyn [analyzátory a CodeFixes](https://github.com/dotnet/roslyn-analyzers).</span><span class="sxs-lookup"><span data-stu-id="d26d4-108">As you read through this tutorial, you will notice quite a bit of similarity between Expression Trees and the types used in the Roslyn APIs to build [Analyzers and CodeFixes](https://github.com/dotnet/roslyn-analyzers).</span></span>
<span data-ttu-id="d26d4-109">(Analyzátory a CodeFixes jsou balíčky NuGet, které statické analýzám na kód a můžete navrhnout potenciální opravy pro Vývojář). Koncepty jsou podobné a konečný výsledek je datová struktura, která umožňuje prozkoumání zdrojového kódu smysluplný způsobem.</span><span class="sxs-lookup"><span data-stu-id="d26d4-109">(Analyzers and CodeFixes are NuGet packages that perform static analysis on code and can suggest potential fixes for a developer.) The concepts are similar, and the end result is a data structure that allows examination of the source code in a meaningful way.</span></span> <span data-ttu-id="d26d4-110">Stromy výrazů jsou však založené na sadu uvidíte úplně jiné třídy a rozhraní API než Roslyn rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="d26d4-110">However, Expression Trees are based on a totally different set of classes and APIs than the Roslyn APIs.</span></span>
    
<span data-ttu-id="d26d4-111">Podívejme se na jednoduchý příklad.</span><span class="sxs-lookup"><span data-stu-id="d26d4-111">Let's look at a simple example.</span></span>
<span data-ttu-id="d26d4-112">Zde je řádek kódu:</span><span class="sxs-lookup"><span data-stu-id="d26d4-112">Here's a line of code:</span></span>
```csharp
var sum = 1 + 2;
```
<span data-ttu-id="d26d4-113">Pokud byste chtěli analyzovat to jako strom výrazu, stromu obsahuje několik uzlů.</span><span class="sxs-lookup"><span data-stu-id="d26d4-113">If you were to analyze this as an expression tree, the tree contains several nodes.</span></span>
<span data-ttu-id="d26d4-114">Nejkrajnější uzel je příkaz deklarace proměnné s přiřazení (`var sum = 1 + 2;`) tento nejkrajnější uzel obsahuje několik podřízené uzly: deklarace proměnné, operátor přiřazení a výraz představující symbolem rovná se pravé straně.</span><span class="sxs-lookup"><span data-stu-id="d26d4-114">The outermost node is a variable declaration statement with assignment (`var sum = 1 + 2;`) That outermost node contains several child nodes: a variable declaration, an assignment operator, and an expression representing the right hand side of the equals sign.</span></span> <span data-ttu-id="d26d4-115">Výraz je další rozděleno na výrazy, které představují operace sčítání a levé a pravé operandy přidání.</span><span class="sxs-lookup"><span data-stu-id="d26d4-115">That expression is further subdivided into expressions that represent the addition operation, and left and right operands of the addition.</span></span>

<span data-ttu-id="d26d4-116">Umožňuje rozbalit soubor trochu více výrazů, které tvoří na pravé straně symbolem rovná se.</span><span class="sxs-lookup"><span data-stu-id="d26d4-116">Let's drill down a bit more into the expressions that make up the right side of the equals sign.</span></span>
<span data-ttu-id="d26d4-117">Výraz `1 + 2`.</span><span class="sxs-lookup"><span data-stu-id="d26d4-117">The expression is `1 + 2`.</span></span> <span data-ttu-id="d26d4-118">Které je výraz binární.</span><span class="sxs-lookup"><span data-stu-id="d26d4-118">That's a binary expression.</span></span> <span data-ttu-id="d26d4-119">Přesněji řečeno je přidání binárního výrazu.</span><span class="sxs-lookup"><span data-stu-id="d26d4-119">More specifically, it's a binary addition expression.</span></span> <span data-ttu-id="d26d4-120">Výraz binární přidání má dva podřízené objekty představující levé a pravé uzly přidání výraz.</span><span class="sxs-lookup"><span data-stu-id="d26d4-120">A binary addition expression has two children, representing the left and right nodes of the addition expression.</span></span> <span data-ttu-id="d26d4-121">Zde jsou oba uzly konstantní výrazy: levý operand je hodnota `1`, a pravý operand je hodnota `2`.</span><span class="sxs-lookup"><span data-stu-id="d26d4-121">Here, both nodes are constant expressions: The left operand is the value `1`, and the right operand is the value `2`.</span></span>

<span data-ttu-id="d26d4-122">Vizuální, je celý příkaz stromu: můžete spustit na kořenový uzel a cestovat na každý uzel ve stromu zobrazíte kód, který tvoří příkaz:</span><span class="sxs-lookup"><span data-stu-id="d26d4-122">Visually, the entire statement is a tree: You could start at the root node, and travel to each node in the tree to see the code that makes up the statement:</span></span>

- <span data-ttu-id="d26d4-123">Příkaz deklarace proměnné s přiřazení (`var sum = 1 + 2;`)</span><span class="sxs-lookup"><span data-stu-id="d26d4-123">Variable declaration statement with assignment (`var sum = 1 + 2;`)</span></span>
    * <span data-ttu-id="d26d4-124">Deklarace typu implicitní proměnné (`var sum`)</span><span class="sxs-lookup"><span data-stu-id="d26d4-124">Implicit variable type declaration (`var sum`)</span></span>
        - <span data-ttu-id="d26d4-125">Implicitní var – klíčové slovo (`var`)</span><span class="sxs-lookup"><span data-stu-id="d26d4-125">Implicit var keyword (`var`)</span></span>
        - <span data-ttu-id="d26d4-126">Název proměnné deklarace (`sum`)</span><span class="sxs-lookup"><span data-stu-id="d26d4-126">Variable name declaration (`sum`)</span></span>
    * <span data-ttu-id="d26d4-127">Operátor přiřazení (`=`)</span><span class="sxs-lookup"><span data-stu-id="d26d4-127">Assignment operator (`=`)</span></span>
    * <span data-ttu-id="d26d4-128">Binární přidání výraz (`1 + 2`)</span><span class="sxs-lookup"><span data-stu-id="d26d4-128">Binary addition expression (`1 + 2`)</span></span>
        - <span data-ttu-id="d26d4-129">Levý operand (`1`)</span><span class="sxs-lookup"><span data-stu-id="d26d4-129">Left operand (`1`)</span></span>
        - <span data-ttu-id="d26d4-130">Operátor sčítání (`+`)</span><span class="sxs-lookup"><span data-stu-id="d26d4-130">Addition operator (`+`)</span></span>
        - <span data-ttu-id="d26d4-131">Pravý operand (`2`)</span><span class="sxs-lookup"><span data-stu-id="d26d4-131">Right operand (`2`)</span></span>

<span data-ttu-id="d26d4-132">To může vypadat složité, ale je velmi efektivní.</span><span class="sxs-lookup"><span data-stu-id="d26d4-132">This may look complicated, but it is very powerful.</span></span> <span data-ttu-id="d26d4-133">Následující stejný postup můžete rozložit mnohem složitější výrazy.</span><span class="sxs-lookup"><span data-stu-id="d26d4-133">Following the same process, you can decompose much more complicated expressions.</span></span> <span data-ttu-id="d26d4-134">Vezměte v úvahu tento výraz:</span><span class="sxs-lookup"><span data-stu-id="d26d4-134">Consider this expression:</span></span>
```csharp
var finalAnswer = this.SecretSauceFunction(
    currentState.createInterimResult(), currentState.createSecondValue(1, 2),
    decisionServer.considerFinalOptions("hello")) +
    MoreSecretSauce('A', DateTime.Now, true);
```

<span data-ttu-id="d26d4-135">Výraz výše je také deklarace proměnné s přiřazení.</span><span class="sxs-lookup"><span data-stu-id="d26d4-135">The expression above is also a variable declaration with an assignment.</span></span>
<span data-ttu-id="d26d4-136">V tomto případě je pravá strana přiřazení mnohem složitější stromu.</span><span class="sxs-lookup"><span data-stu-id="d26d4-136">In this instance, the right hand side of the assignment is a much more complicated tree.</span></span>
<span data-ttu-id="d26d4-137">Není, který bude rozložit tento výraz, ale zvažte, které mohou být různé uzly.</span><span class="sxs-lookup"><span data-stu-id="d26d4-137">I'm not going to decompose this expression, but consider what the different nodes might be.</span></span> <span data-ttu-id="d26d4-138">Existují pomocí aktuálního objektu jako přijímač, ten, který má explicitního volání metod `this` příjemce, který nemá.</span><span class="sxs-lookup"><span data-stu-id="d26d4-138">There are method calls using the current object as a receiver, one that has an explicit `this` receiver, one that does not.</span></span> <span data-ttu-id="d26d4-139">Jsou volání metod pomocí jiné objekty příjemce, konstantní argumenty různých typů.</span><span class="sxs-lookup"><span data-stu-id="d26d4-139">There are method calls using other receiver objects, there are constant arguments of different types.</span></span> <span data-ttu-id="d26d4-140">A nakonec je přidání binární operátor.</span><span class="sxs-lookup"><span data-stu-id="d26d4-140">And finally, there is a binary addition operator.</span></span> <span data-ttu-id="d26d4-141">V závislosti na návratový typ `SecretSauceFunction()` nebo `MoreSecretSauce()`, že operátor sčítání binární může být volání metody přepsaného přidání operátoru řešení pro volání statickou metodu operátor binární sčítání definovaný pro třídu.</span><span class="sxs-lookup"><span data-stu-id="d26d4-141">Depending on the return type of `SecretSauceFunction()` or `MoreSecretSauce()`, that binary addition operator may be a method call to an overridden addition operator, resolving to a static method call to the binary addition operator defined for a class.</span></span>

<span data-ttu-id="d26d4-142">Výraz výše i přes tento dosahovaný složitost vytvoří stromová struktura, která lze procházet jako snadno jako první ukázka.</span><span class="sxs-lookup"><span data-stu-id="d26d4-142">Despite this perceived complexity, the expression above creates a tree structure that can be navigated as easily as the first sample.</span></span> <span data-ttu-id="d26d4-143">Můžete ponechat procházení podřízené uzly najít uzlů listu ve výrazu.</span><span class="sxs-lookup"><span data-stu-id="d26d4-143">You can keep traversing child nodes to find leaf nodes in the expression.</span></span> <span data-ttu-id="d26d4-144">Nadřazené uzly budou mít odkazy na jejich podřízené a každý uzel má vlastnost, která popisuje, jaký druh uzlu je.</span><span class="sxs-lookup"><span data-stu-id="d26d4-144">Parent nodes will have references to their children, and each node has a property that describes what kind of node it is.</span></span>

<span data-ttu-id="d26d4-145">Struktura stromu výrazů je velmi konzistentní.</span><span class="sxs-lookup"><span data-stu-id="d26d4-145">The structure of an expression tree is very consistent.</span></span> <span data-ttu-id="d26d4-146">Jakmile jste se naučili základy, můžete i těch nejsložitějších kód pochopit, když je reprezentována jako strom výrazu se nezdařilo.</span><span class="sxs-lookup"><span data-stu-id="d26d4-146">Once you've learned the basics, you can understand even the most complex code when it is represented as an expression tree.</span></span> <span data-ttu-id="d26d4-147">Eleganci ve struktuře dat vysvětluje, jak analyzovat těch nejsložitějších programy C# a vytvořit správné výstup z tohoto složitá zdrojového kódu kompilátor jazyka C#.</span><span class="sxs-lookup"><span data-stu-id="d26d4-147">The elegance in the data structure explains how the C# compiler can analyze the most complex C# programs and create proper output from that complicated source code.</span></span>

<span data-ttu-id="d26d4-148">Jakmile jste se seznámili s strukturu stromů výrazů, zjistíte, že znalostní báze, kterou získáte rychle umožňuje pracovat s mnoha více pokročilé scénáře.</span><span class="sxs-lookup"><span data-stu-id="d26d4-148">Once you become familiar with the structure of expression trees, you will find that knowledge you've gained quickly enables you to work with many more and more advanced scenarios.</span></span> <span data-ttu-id="d26d4-149">Je neuvěřitelné efektivitě k stromů výrazů.</span><span class="sxs-lookup"><span data-stu-id="d26d4-149">There is incredible power to expression trees.</span></span>

<span data-ttu-id="d26d4-150">Kromě překladu algoritmy s cílem provést v jiných prostředích, stromy výrazů slouží k usnadnění zápisu algoritmy, které Kontrola kódu před jeho provedením.</span><span class="sxs-lookup"><span data-stu-id="d26d4-150">In addition to translating algorithms to execute in other environments, expression trees can be used to make it easier to write algorithms that inspect code before executing it.</span></span> <span data-ttu-id="d26d4-151">Můžete napíše metoda, jejíž argumenty jsou výrazy a zkontrolujte tyto výrazy před provedením kód.</span><span class="sxs-lookup"><span data-stu-id="d26d4-151">You can write a method whose arguments are expressions and then examine those expressions before executing the code.</span></span> <span data-ttu-id="d26d4-152">Strom výrazu je úplná reprezentace kód: uvidíte hodnoty žádné dílčí výrazu.</span><span class="sxs-lookup"><span data-stu-id="d26d4-152">The Expression Tree is a full representation of the code: you can see values of any sub-expression.</span></span>
<span data-ttu-id="d26d4-153">Můžete zobrazit názvy metod a vlastností.</span><span class="sxs-lookup"><span data-stu-id="d26d4-153">You can see method and property names.</span></span> <span data-ttu-id="d26d4-154">Zobrazí se hodnota žádné konstantní výrazy.</span><span class="sxs-lookup"><span data-stu-id="d26d4-154">You can see the value of any constant expressions.</span></span>
<span data-ttu-id="d26d4-155">Také můžete převést strom výrazu delegáta spustitelný soubor a spouštění kódu.</span><span class="sxs-lookup"><span data-stu-id="d26d4-155">You can also convert an expression tree into an executable delegate, and execute the code.</span></span>

<span data-ttu-id="d26d4-156">Rozhraní API pro stromy výrazů umožňují vytvářet stromy, které představují téměř všechny konstrukce platný kód.</span><span class="sxs-lookup"><span data-stu-id="d26d4-156">The APIs for Expression Trees enable you to create trees that represent almost any valid code construct.</span></span> <span data-ttu-id="d26d4-157">Z důvodu zjednodušení co nejjednodušší, ale nelze některé idioms C# vytvořit v strom výrazu se nezdařilo.</span><span class="sxs-lookup"><span data-stu-id="d26d4-157">However, to keep things as simple as possible, some C# idioms cannot be created in an expression tree.</span></span> <span data-ttu-id="d26d4-158">Jedním z příkladů je asynchronní výrazy (pomocí `async` a `await` klíčová slova).</span><span class="sxs-lookup"><span data-stu-id="d26d4-158">One example is asynchronous expressions (using the `async` and `await` keywords).</span></span> <span data-ttu-id="d26d4-159">Pokud vaše potřeby vyžadují asynchronní algoritmy, potřebujete upravit `Task` objekty přímo, nikoli spoléhají na podporu kompilátoru.</span><span class="sxs-lookup"><span data-stu-id="d26d4-159">If your needs require asynchronous algorithms, you would need to manipulate the `Task` objects directly, rather than rely on the compiler support.</span></span> <span data-ttu-id="d26d4-160">Další je při vytváření smyčky.</span><span class="sxs-lookup"><span data-stu-id="d26d4-160">Another is in creating loops.</span></span> <span data-ttu-id="d26d4-161">Obvykle vytvoříte tak, že pomocí `for`, `foreach`, `while` nebo `do` smyčky.</span><span class="sxs-lookup"><span data-stu-id="d26d4-161">Typically, you create these by using `for`, `foreach`, `while` or `do` loops.</span></span> <span data-ttu-id="d26d4-162">Jak uvidíte [dál v této série](expression-trees-building.md), rozhraní API pro stromy výrazů podporovat výraz jedinou smyčku `break` a `continue` výrazů, které určují, že opakování ve smyčce opakování.</span><span class="sxs-lookup"><span data-stu-id="d26d4-162">As you'll see [later in this series](expression-trees-building.md), the APIs for expression trees support a single loop expression, with `break` and `continue` expressions that control repeating the loop.</span></span>

<span data-ttu-id="d26d4-163">Jednou z věcí, které nelze provést je upravit strom výrazu se nezdařilo.</span><span class="sxs-lookup"><span data-stu-id="d26d4-163">The one thing you can't do is modify an expression tree.</span></span>  <span data-ttu-id="d26d4-164">Stromy výrazů jsou neměnné datové struktury.</span><span class="sxs-lookup"><span data-stu-id="d26d4-164">Expression Trees are immutable data structures.</span></span> <span data-ttu-id="d26d4-165">Pokud chcete mutovat (změnit) výrazu stromu, je nutné vytvořit novou větev, který je kopií původního, ale s požadované změny.</span><span class="sxs-lookup"><span data-stu-id="d26d4-165">If you want to mutate (change) an expression tree, you must create a new tree that is a copy of the original, but with your desired changes.</span></span> 

[<span data-ttu-id="d26d4-166">Další – Framework typy podpůrné stromů výrazů</span><span class="sxs-lookup"><span data-stu-id="d26d4-166">Next -- Framework Types Supporting Expression Trees</span></span>](expression-classes.md)