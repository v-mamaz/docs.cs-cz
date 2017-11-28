---
title: "Vazby do ve třídách (F#)"
description: "Naučte se používat F # \"do\" vazby v definici třídy, který provádí akce, když je objekt vytvořený, nebo při prvním použití typu."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 78987cb8-bdba-46e2-b5b2-994c83fe42c4
ms.openlocfilehash: f9582338306d87c3dd799425083037cc95b31b1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="58ddf-104">Vazby do ve třídách</span><span class="sxs-lookup"><span data-stu-id="58ddf-104">do Bindings in Classes</span></span>

<span data-ttu-id="58ddf-105">A `do` vazby v definici třídy provede akce, když je objekt vytvořený nebo pro statického `do` vazby, pokud typ prvním použití.</span><span class="sxs-lookup"><span data-stu-id="58ddf-105">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>


## <a name="syntax"></a><span data-ttu-id="58ddf-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="58ddf-106">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="58ddf-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="58ddf-107">Remarks</span></span>
<span data-ttu-id="58ddf-108">A `do` vazba se zobrazí, společně s nebo po `let` vazby, ale před definice člen v definici třídy.</span><span class="sxs-lookup"><span data-stu-id="58ddf-108">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="58ddf-109">I když `do` – klíčové slovo je pro volitelné `do` vazby na úrovni modulu, není pro volitelné `do` vazby v definici třídy.</span><span class="sxs-lookup"><span data-stu-id="58ddf-109">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="58ddf-110">Pro tvorbu každý objekt libovolného daného typu, nestatické `do` vazby a nestatické `let` vazby jsou spouštěny v pořadí, ve kterém se zobrazí v definici třídy.</span><span class="sxs-lookup"><span data-stu-id="58ddf-110">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="58ddf-111">Více `do` vazby se může objevit v jednoho typu.</span><span class="sxs-lookup"><span data-stu-id="58ddf-111">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="58ddf-112">Nestatické `let` vazby a nestatické `do` vazby stane textem primární konstruktoru.</span><span class="sxs-lookup"><span data-stu-id="58ddf-112">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="58ddf-113">Kód v nestatickou `do` vazby části odkazovat primární konstruktor parametry a všechny hodnoty nebo funkce, které jsou definovány v `let` části vazby.</span><span class="sxs-lookup"><span data-stu-id="58ddf-113">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="58ddf-114">Nestatické `do` vazby můžete přístup ke členům třídy tak dlouho, dokud třída má vlastní identifikátor, který je definován `as` – klíčové slovo v třídě nadpis a pokud jsou všechny používá tyto členů kvalifikovaný pomocí vlastní identifikátor pro třídu.</span><span class="sxs-lookup"><span data-stu-id="58ddf-114">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="58ddf-115">Protože `let` vazby inicializovat soukromá pole třídy, který je často nutné zajistit, že členové chovat podle očekávání, `do` vazby jsou obvykle ukládat po `let` vazby, že kód `do` může vazby spustit s objektem plně inicializovaném.</span><span class="sxs-lookup"><span data-stu-id="58ddf-115">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="58ddf-116">Pokud váš kód se pokusí použít člen před dokončením inicializace, je vyvolána výjimkou InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="58ddf-116">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="58ddf-117">Statické `do` vazby mohou odkazovat statické členy nebo pole uzavření do třídy, ale není instance členů nebo pole.</span><span class="sxs-lookup"><span data-stu-id="58ddf-117">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="58ddf-118">Statické `do` vazby stane součástí statické inicializátoru pro třídu, která záruku, že se provést před prvním použití třídy.</span><span class="sxs-lookup"><span data-stu-id="58ddf-118">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="58ddf-119">Atributy jsou ignorovány pro `do` vazeb v typy.</span><span class="sxs-lookup"><span data-stu-id="58ddf-119">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="58ddf-120">Pokud atribut je požadován pro kód, který spustí `do` vazba, je nutné použít na primární konstruktoru.</span><span class="sxs-lookup"><span data-stu-id="58ddf-120">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="58ddf-121">V následujícím kódu, třída má statického `do` vazby a nestatickou `do` vazby.</span><span class="sxs-lookup"><span data-stu-id="58ddf-121">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="58ddf-122">Objekt nemá konstruktor, který má dva parametry `a` a `b`, a dva privátní pole jsou definovány v `let` vazby pro třídu.</span><span class="sxs-lookup"><span data-stu-id="58ddf-122">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="58ddf-123">Dvě vlastnosti je definována.</span><span class="sxs-lookup"><span data-stu-id="58ddf-123">Two properties are also defined.</span></span> <span data-ttu-id="58ddf-124">Všechny jsou v oboru v nestatickou `do` vazby části, jak je znázorněno použitím řádek, který vypíše všechny tyto hodnoty.</span><span class="sxs-lookup"><span data-stu-id="58ddf-124">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="58ddf-125">Výstup je následující.</span><span class="sxs-lookup"><span data-stu-id="58ddf-125">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="58ddf-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="58ddf-126">See Also</span></span>
[<span data-ttu-id="58ddf-127">Členy</span><span class="sxs-lookup"><span data-stu-id="58ddf-127">Members</span></span>](index.md)

[<span data-ttu-id="58ddf-128">Třídy</span><span class="sxs-lookup"><span data-stu-id="58ddf-128">Classes</span></span>](../classes.md)

[<span data-ttu-id="58ddf-129">Konstruktory</span><span class="sxs-lookup"><span data-stu-id="58ddf-129">Constructors</span></span>](constructors.md)

[<span data-ttu-id="58ddf-130">`let`Vazby do ve třídách</span><span class="sxs-lookup"><span data-stu-id="58ddf-130">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)

[<span data-ttu-id="58ddf-131">`do`Vazby</span><span class="sxs-lookup"><span data-stu-id="58ddf-131">`do` Bindings</span></span>](../functions/do-Bindings.md)