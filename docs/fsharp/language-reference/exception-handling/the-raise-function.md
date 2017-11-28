---
title: "Výjimky: Funkce raise (F#)"
description: "Zjistěte, jak F # 'vyvolat' funkce slouží k označení, že došlo k chybě nebo výjimečně vysoké počty podmínku."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b00da469-4789-4cdd-9f77-7a2e29f28637
ms.openlocfilehash: dc524a06d075b982a6aa1fd266769bfc7d883517
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="af2a3-104">Výjimky: Funkce raise</span><span class="sxs-lookup"><span data-stu-id="af2a3-104">Exceptions: the raise Function</span></span>

<span data-ttu-id="af2a3-105">`raise` Funkce slouží k označení, že došlo k chybě nebo výjimečně vysoké počty podmínku.</span><span class="sxs-lookup"><span data-stu-id="af2a3-105">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="af2a3-106">Informace o této chybě se zaznamená v objektu výjimky.</span><span class="sxs-lookup"><span data-stu-id="af2a3-106">Information about the error is captured in an exception object.</span></span>


## <a name="syntax"></a><span data-ttu-id="af2a3-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="af2a3-107">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="af2a3-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="af2a3-108">Remarks</span></span>
<span data-ttu-id="af2a3-109">`raise` Funkce generuje objekt výjimky a zahájí unwinding proces zásobníku.</span><span class="sxs-lookup"><span data-stu-id="af2a3-109">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="af2a3-110">Proces unwinding zásobníku je spravovaný modul CLR (CLR), takže chování tohoto procesu je stejný, jako je v kterémkoli jazyce platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="af2a3-110">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="af2a3-111">Proces unwinding zásobníku je vyhledávání pro obslužnou rutinu výjimky odpovídající generovaného výjimka.</span><span class="sxs-lookup"><span data-stu-id="af2a3-111">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="af2a3-112">Spustí vyhledávání v aktuální `try...with` výrazu, jestliže existuje.</span><span class="sxs-lookup"><span data-stu-id="af2a3-112">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="af2a3-113">Každý vzor v `with` bloku je zaškrtnuto, v pořadí.</span><span class="sxs-lookup"><span data-stu-id="af2a3-113">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="af2a3-114">Když se najde odpovídající obslužná rutina výjimky, výjimka považuje za zpracovává; jinak je oddělen zásobníku a `with` bloky řetězem volání jsou zaškrtnutá políčka, dokud nebude nalezen odpovídající obslužná rutina.</span><span class="sxs-lookup"><span data-stu-id="af2a3-114">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="af2a3-115">Všechny `finally` bloky, které se vyskytují v řetězu volání jsou také provést v pořadí, protože unwinds zásobníku.</span><span class="sxs-lookup"><span data-stu-id="af2a3-115">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="af2a3-116">`raise` Funkce je ekvivalentem `throw` v C# nebo C++.</span><span class="sxs-lookup"><span data-stu-id="af2a3-116">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="af2a3-117">Použití `reraise` v obslužné rutině catch potřebný k šíření bude stejná výjimka řetězem volání.</span><span class="sxs-lookup"><span data-stu-id="af2a3-117">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="af2a3-118">Následující příklady kódu ilustrují použití `raise` funkce, která se vygeneruje výjimka.</span><span class="sxs-lookup"><span data-stu-id="af2a3-118">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="af2a3-119">`raise` Funkce mohou sloužit také pro vyvolání výjimky .NET, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="af2a3-119">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a><span data-ttu-id="af2a3-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="af2a3-120">See Also</span></span>
[<span data-ttu-id="af2a3-121">Zpracování výjimek</span><span class="sxs-lookup"><span data-stu-id="af2a3-121">Exception Handling</span></span>](index.md)

[<span data-ttu-id="af2a3-122">Typy výjimek</span><span class="sxs-lookup"><span data-stu-id="af2a3-122">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="af2a3-123">Výjimky: `try...with` výraz</span><span class="sxs-lookup"><span data-stu-id="af2a3-123">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)

[<span data-ttu-id="af2a3-124">Výjimky: `try...finally` výraz</span><span class="sxs-lookup"><span data-stu-id="af2a3-124">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

[<span data-ttu-id="af2a3-125">Výjimky: `failwith` – funkce</span><span class="sxs-lookup"><span data-stu-id="af2a3-125">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)

[<span data-ttu-id="af2a3-126">Výjimky: `invalidArg` – funkce</span><span class="sxs-lookup"><span data-stu-id="af2a3-126">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)