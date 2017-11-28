---
title: "Obory názvů (F#)"
description: "Zjistěte, jak na obor názvů F # umožňuje uspořádat kódu do oblasti související funkce tím, že vám k seskupení prvků programu připojit název."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea42156f-e1b9-4535-9383-b45f46f3f7ca
ms.openlocfilehash: 4378afebe6fd0d9317f734457576dc75d7488bf0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="namespaces"></a><span data-ttu-id="e5cdb-104">Obory názvů</span><span class="sxs-lookup"><span data-stu-id="e5cdb-104">Namespaces</span></span>

<span data-ttu-id="e5cdb-105">Obor názvů umožňuje uspořádat kódu do oblasti související funkce tím, že vám k seskupení prvků programu připojit název.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-105">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of program elements.</span></span>


## <a name="syntax"></a><span data-ttu-id="e5cdb-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e5cdb-106">Syntax</span></span>

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="e5cdb-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e5cdb-107">Remarks</span></span>
<span data-ttu-id="e5cdb-108">Pokud chcete uvést kódu v oboru názvů, je třeba deklarovat první deklarace v souboru obor názvů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="e5cdb-109">Obsah celý soubor pak mohou stát součástí oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-109">The contents of the entire file then become part of the namespace.</span></span>

<span data-ttu-id="e5cdb-110">Obory názvů nemůže přímo obsahovat hodnoty a funkce.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-110">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="e5cdb-111">Místo toho hodnoty a funkce musí být součástí moduly a moduly, které jsou zahrnuty v oborech názvů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-111">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="e5cdb-112">Obory názvů může obsahovat typy modulů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-112">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="e5cdb-113">Obory názvů lze deklarovat explicitně pomocí klíčového slova oboru názvů nebo implicitně když modul deklarace.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-113">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="e5cdb-114">Chcete-li explicitně deklarovat obor názvů, použijte klíčové slovo oboru názvů a název oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-114">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="e5cdb-115">Následující příklad ukazuje soubor kód, který deklaruje obor názvů pomůcky s typem a modul zahrnuté v tomto oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-115">The following example shows a code file that declares a namespace Widgets with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="e5cdb-116">Pokud celý obsah souboru v jeden modul, můžete také deklarovat obory názvů implicitně pomocí `module` – klíčové slovo a poskytuje nový název oboru názvů v názvu plně kvalifikovaného modulu.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-116">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="e5cdb-117">Následující příklad ukazuje soubor kód, který deklaruje obor názvů `Widgets` a modul `WidgetsModule`, který obsahuje funkci.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-117">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="e5cdb-118">Následující kód je ekvivalentní předchozí kód, ale modul je deklaraci místního modulu.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-118">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="e5cdb-119">V takovém případě oboru názvů musí být na samostatném řádku.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-119">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="e5cdb-120">Pokud více než jeden modul je vyžadována ve stejném souboru v jedné nebo více oborů názvů, je nutné použít místní modul deklarace.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-120">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="e5cdb-121">Pokud používáte místní modul deklarace, nelze použít kvalifikovaný obor názvů v deklaracích modulu.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-121">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="e5cdb-122">Následující kód ukazuje soubor, který má deklaraci oboru názvů a dvě místní modul deklarace.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-122">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="e5cdb-123">V takovém případě jsou moduly obsaženy přímo v oboru názvů; neexistuje žádný implicitně vytvořených modul, který má stejný název jako soubor.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-123">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="e5cdb-124">Všechny další kód v souboru, například `do` vazba, je v oboru názvů, ale není v informacích o vnitřní moduly, takže budete muset kvalifikaci člen modulu `widgetFunction` pomocí názvu modulu.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-124">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="e5cdb-125">Výstup tohoto příkladu je následující.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-125">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="e5cdb-126">Další informace najdete v tématu [moduly](modules.md).</span><span class="sxs-lookup"><span data-stu-id="e5cdb-126">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="e5cdb-127">Vnořené obory názvů</span><span class="sxs-lookup"><span data-stu-id="e5cdb-127">Nested Namespaces</span></span>
<span data-ttu-id="e5cdb-128">Při vytváření vnořených obor názvů, musí ho plnému určení.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-128">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="e5cdb-129">Jinak vytvořte nový obor názvů nejvyšší úrovně.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-129">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="e5cdb-130">Odsazení je ignorován v deklarace oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-130">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="e5cdb-131">Následující příklad ukazuje, jak deklarovat vnořené obor názvů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-131">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="e5cdb-132">Obory názvů v souborech a sestavení</span><span class="sxs-lookup"><span data-stu-id="e5cdb-132">Namespaces in Files and Assemblies</span></span>
<span data-ttu-id="e5cdb-133">Obory názvů, může zahrnovat víc souborů v jednom projektu nebo kompilace.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-133">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="e5cdb-134">Termín *fragment obor názvů* popisuje část oboru názvů, který je zahrnutý v jednom souboru.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-134">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="e5cdb-135">Obory názvů, může také zahrnovat více sestavení.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-135">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="e5cdb-136">Například `System` obor názvů zahrnuje celou rozhraní .NET Framework, která zahrnuje mnoho sestavení a obsahuje mnoho vnořené obory názvů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-136">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>


## <a name="global-namespace"></a><span data-ttu-id="e5cdb-137">Globální Namespace</span><span class="sxs-lookup"><span data-stu-id="e5cdb-137">Global Namespace</span></span>
<span data-ttu-id="e5cdb-138">Použijte předdefinovaný obor názvů `global` uvést názvy do nejvyšší úrovně obor názvů .NET.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-138">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="e5cdb-139">Můžete také použít globální tak, aby odkazovaly nejvyšší úrovně obor názvů .NET, například, chcete-li vyřešit název je v konfliktu s další obory názvů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-139">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

##

<span data-ttu-id="e5cdb-140">F # 4.1 zavádí představu o obory názvů, který povolit pro všechny obsažené kód jako vzájemně rekurzivní.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-140">F# 4.1 introduces the notion of namespaces which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="e5cdb-141">To se provádí prostřednictvím `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-141">This is done via `namespace rec`.</span></span>  <span data-ttu-id="e5cdb-142">Použití `namespace rec` můžete zmírnit některé důsledně v nebude moci napsat vzájemně referenční kód mezi typy a modulů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-142">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="e5cdb-143">Následuje příklad tohoto:</span><span class="sxs-lookup"><span data-stu-id="e5cdb-143">The following is an example of this:</span></span>

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set
    
    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b : Banana) =
        let flip banana =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides banana =
            for side in banana.Sides do
                if side = Unpeeled then
                    side <- Peeled

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

<span data-ttu-id="e5cdb-144">Všimněte si, že výjimka `DontSqueezeTheBananaException` a třídu `Banana` odkazují na sebe navzájem.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-144">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="e5cdb-145">Kromě toho modul `BananaHelpers` a třídu `Banana` se také podívat na sebe navzájem.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-145">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="e5cdb-146">To nebude možné v jazyce F # express, pokud jste odebrali `rec` – klíčové slovo z `MutualReferences` oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-146">This would not be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="e5cdb-147">Tato funkce je také k dispozici pro nejvyšší úrovně [moduly](modules.md) v F # 4.1 nebo vyšší.</span><span class="sxs-lookup"><span data-stu-id="e5cdb-147">This feature is also available for top-level [Modules](modules.md) in F# 4.1 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5cdb-148">Viz také</span><span class="sxs-lookup"><span data-stu-id="e5cdb-148">See Also</span></span>
[<span data-ttu-id="e5cdb-149">Referenční dokumentace jazyka F #</span><span class="sxs-lookup"><span data-stu-id="e5cdb-149">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="e5cdb-150">Moduly</span><span class="sxs-lookup"><span data-stu-id="e5cdb-150">Modules</span></span>](modules.md)

[<span data-ttu-id="e5cdb-151">1009-F # RFC FS - povolit vzájemně referenční typy a moduly přes větší oborů v rámci soubory</span><span class="sxs-lookup"><span data-stu-id="e5cdb-151">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)