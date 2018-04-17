---
title: '% – operátor (Referenční dokumentace jazyka C#)'
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 796b4a40347fc5881db27a8a8a28404c7c4e8c5b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="93936-102">% – operátor (Referenční dokumentace jazyka C#)</span><span class="sxs-lookup"><span data-stu-id="93936-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="93936-103">Operátor zbytku (`%`) vypočítá zbytek po dělení jeho první operand jeho sekundu.</span><span class="sxs-lookup"><span data-stu-id="93936-103">The remainder operator (`%`) computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="93936-104">Všechny číselné typy obsahuje předdefinované zbývající operátory.</span><span class="sxs-lookup"><span data-stu-id="93936-104">All numeric types have predefined remainder operators.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="93936-105">Poznámky</span><span class="sxs-lookup"><span data-stu-id="93936-105">Remarks</span></span>  
 <span data-ttu-id="93936-106">Vzorec `a % b` vždy vrátí hodnotu v rozsahu `(-b, b)`, výhradní (nikdy může vrátit `b` nebo `-b`), udržování znaménko dělenec.</span><span class="sxs-lookup"><span data-stu-id="93936-106">The formula `a % b` will always return a value on the range `(-b, b)`, exclusive (it can never return `b` or `-b`), keeping the sign of the dividend.</span></span> <span data-ttu-id="93936-107">Pro dělení celého čísla, operátor zbytku splňuje pravidlo `a % b = a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="93936-107">For integer division, the remainder operator satisfies the rule `a % b = a - (a / b) * b`.</span></span>
  
 <span data-ttu-id="93936-108">Toto je Nezaměňovat s kanonický numerického zbytku, který splňuje požadavky podobné pravidlo, ale s floored dělení a vrací hodnoty v rozsahu `[0, b)`.</span><span class="sxs-lookup"><span data-stu-id="93936-108">This is not to be confused with canonical modulus, which satisfies a similar rule but with floored division and returns values on the range `[0, b)`.</span></span> <span data-ttu-id="93936-109">C# nemá operátor numerického zbytku kanonickém tvaru.</span><span class="sxs-lookup"><span data-stu-id="93936-109">C# does not have an operator for canonical modulus.</span></span> <span data-ttu-id="93936-110">Chování je však pro pozitivní dividendy stejný.</span><span class="sxs-lookup"><span data-stu-id="93936-110">However, the behavior is the same for positive dividends.</span></span>
  
 <span data-ttu-id="93936-111">Uživatelem definované typy může přetížit `%` – operátor (najdete v části [operátor](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="93936-111">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="93936-112">Při binární operátor je přetížena, odpovídající operátor přiřazení, pokud existuje, je také implicitně přetížená.</span><span class="sxs-lookup"><span data-stu-id="93936-112">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93936-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="93936-113">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="93936-114">Komentáře</span><span class="sxs-lookup"><span data-stu-id="93936-114">Comments</span></span>  
 <span data-ttu-id="93936-115">Všimněte si zaokrouhlovací chyby související s typ double.</span><span class="sxs-lookup"><span data-stu-id="93936-115">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93936-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="93936-116">See Also</span></span>  
 [<span data-ttu-id="93936-117">Referenční dokumentace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="93936-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="93936-118">Průvodce programováním v jazyce C#</span><span class="sxs-lookup"><span data-stu-id="93936-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="93936-119">Operátory jazyka C#</span><span class="sxs-lookup"><span data-stu-id="93936-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)