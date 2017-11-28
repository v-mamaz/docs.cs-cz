---
title: "DirectCast – operátor (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords: DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="c973c-102">DirectCast – operátor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c973c-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="c973c-103">Představuje operaci převodu typ na základě dědičnosti nebo implementace.</span><span class="sxs-lookup"><span data-stu-id="c973c-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c973c-104">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c973c-104">Remarks</span></span>  
 <span data-ttu-id="c973c-105">`DirectCast`nepoužívá Visual Basicu běhu pomocné rutiny pro převod, můžou poskytovat, poněkud lepší výkon než `CType` při převodu z datového typu `Object`.</span><span class="sxs-lookup"><span data-stu-id="c973c-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="c973c-106">Můžete použít `DirectCast` – klíčové slovo podobným způsobem můžete použít [CType – funkce](../../../visual-basic/language-reference/functions/ctype-function.md) a [TryCast – operátor](../../../visual-basic/language-reference/operators/trycast-operator.md) – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="c973c-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="c973c-107">Můžete zadat jako první argument a zadejte ji do převést jako druhý argument výrazu.</span><span class="sxs-lookup"><span data-stu-id="c973c-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="c973c-108">`DirectCast`vyžaduje relaci dědičnosti nebo implementace mezi typy dat dva argumenty.</span><span class="sxs-lookup"><span data-stu-id="c973c-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="c973c-109">To znamená, že jeden typ musí dědit z nebo implementovat dalších.</span><span class="sxs-lookup"><span data-stu-id="c973c-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="c973c-110">Chyby a selhání</span><span class="sxs-lookup"><span data-stu-id="c973c-110">Errors and Failures</span></span>  
 <span data-ttu-id="c973c-111">`DirectCast`Chyba kompilátoru generuje, pokud zjistí, že neexistuje žádný vztah dědičnosti nebo implementace.</span><span class="sxs-lookup"><span data-stu-id="c973c-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="c973c-112">Ale nedostatek Chyba kompilátoru nezaručuje úspěšné převod.</span><span class="sxs-lookup"><span data-stu-id="c973c-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="c973c-113">Pokud je zužující převod požadované, pravděpodobně nezdaří za běhu.</span><span class="sxs-lookup"><span data-stu-id="c973c-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="c973c-114">Pokud k tomu dojde, modul runtime vyvolá <xref:System.InvalidCastException> chyby.</span><span class="sxs-lookup"><span data-stu-id="c973c-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="c973c-115">Klíčová slova převodu</span><span class="sxs-lookup"><span data-stu-id="c973c-115">Conversion Keywords</span></span>  
 <span data-ttu-id="c973c-116">Porovnání klíčová slova převodu typu je následující.</span><span class="sxs-lookup"><span data-stu-id="c973c-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="c973c-117">– Klíčové slovo</span><span class="sxs-lookup"><span data-stu-id="c973c-117">Keyword</span></span>|<span data-ttu-id="c973c-118">Typy dat</span><span class="sxs-lookup"><span data-stu-id="c973c-118">Data types</span></span>|<span data-ttu-id="c973c-119">Argument relace</span><span class="sxs-lookup"><span data-stu-id="c973c-119">Argument relationship</span></span>|<span data-ttu-id="c973c-120">Běhové chyby</span><span class="sxs-lookup"><span data-stu-id="c973c-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="c973c-121">CType – funkce</span><span class="sxs-lookup"><span data-stu-id="c973c-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="c973c-122">Žádné datové typy</span><span class="sxs-lookup"><span data-stu-id="c973c-122">Any data types</span></span>|<span data-ttu-id="c973c-123">Je nutné definovat rozšiřující nebo zužující převod mezi dvěma datovými typy</span><span class="sxs-lookup"><span data-stu-id="c973c-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="c973c-124">Vyvolá<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="c973c-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="c973c-125">Žádné datové typy</span><span class="sxs-lookup"><span data-stu-id="c973c-125">Any data types</span></span>|<span data-ttu-id="c973c-126">Jeden typ musí dědit z nebo provádět další typ.</span><span class="sxs-lookup"><span data-stu-id="c973c-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="c973c-127">Vyvolá<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="c973c-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="c973c-128">TryCast – operátor</span><span class="sxs-lookup"><span data-stu-id="c973c-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="c973c-129">Odkazové typy pouze</span><span class="sxs-lookup"><span data-stu-id="c973c-129">Reference types only</span></span>|<span data-ttu-id="c973c-130">Jeden typ musí dědit z nebo provádět další typ.</span><span class="sxs-lookup"><span data-stu-id="c973c-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="c973c-131">Vrátí [nic](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="c973c-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c973c-132">Příklad</span><span class="sxs-lookup"><span data-stu-id="c973c-132">Example</span></span>  
 <span data-ttu-id="c973c-133">Následující příklad ukazuje dva použití `DirectCast`, jeden, který selže na dobu spuštění a jeden neuspěje.</span><span class="sxs-lookup"><span data-stu-id="c973c-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 <span data-ttu-id="c973c-134">V předchozím příkladu běhu typ `q` je `Double`.</span><span class="sxs-lookup"><span data-stu-id="c973c-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="c973c-135">`CType`úspěšné, protože `Double` lze převést na `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c973c-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="c973c-136">Však první `DirectCast` nezdaří za běhu, protože běhu typ `Double` nemá žádný vztah dědičnosti s `Integer`, i když existuje převod.</span><span class="sxs-lookup"><span data-stu-id="c973c-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="c973c-137">Druhý `DirectCast` úspěšné, protože převede z typu <xref:System.Windows.Forms.Form> na typ <xref:System.Windows.Forms.Control>, ze kterého <xref:System.Windows.Forms.Form> dědí.</span><span class="sxs-lookup"><span data-stu-id="c973c-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c973c-138">Viz také</span><span class="sxs-lookup"><span data-stu-id="c973c-138">See Also</span></span>  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="c973c-139">Rozšíření a zúžení převodů</span><span class="sxs-lookup"><span data-stu-id="c973c-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="c973c-140">Implicitní a explicitní převody</span><span class="sxs-lookup"><span data-stu-id="c973c-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)