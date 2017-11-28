---
title: "\\ – operátor (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38718b109b4b3865238267039908ea1d51d06229
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="bfa87-102">\ – operátor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfa87-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="bfa87-103">Provede podíl dvou čísel a vrátí celé číslo.</span><span class="sxs-lookup"><span data-stu-id="bfa87-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa87-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bfa87-104">Syntax</span></span>  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="bfa87-105">Součásti</span><span class="sxs-lookup"><span data-stu-id="bfa87-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="bfa87-106">Požadováno.</span><span class="sxs-lookup"><span data-stu-id="bfa87-106">Required.</span></span> <span data-ttu-id="bfa87-107">Jakýkoli číselný výraz.</span><span class="sxs-lookup"><span data-stu-id="bfa87-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="bfa87-108">Požadováno.</span><span class="sxs-lookup"><span data-stu-id="bfa87-108">Required.</span></span> <span data-ttu-id="bfa87-109">Jakýkoli číselný výraz.</span><span class="sxs-lookup"><span data-stu-id="bfa87-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="bfa87-110">Podporované typy</span><span class="sxs-lookup"><span data-stu-id="bfa87-110">Supported Types</span></span>  
 <span data-ttu-id="bfa87-111">Všechny číselné typy, včetně typy bez znaménka a s plovoucí desetinnou čárkou a `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="bfa87-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="bfa87-112">Výsledek</span><span class="sxs-lookup"><span data-stu-id="bfa87-112">Result</span></span>  
 <span data-ttu-id="bfa87-113">Výsledkem je celé číslo podíl `expression1` dělený `expression2`, která zruší všechny zbývající a zachová jenom ta část celé číslo.</span><span class="sxs-lookup"><span data-stu-id="bfa87-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="bfa87-114">To se označuje jako *zkrácení*.</span><span class="sxs-lookup"><span data-stu-id="bfa87-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="bfa87-115">Datový typ výsledků je vhodné pro datové typy číselného typu `expression1` a `expression2`.</span><span class="sxs-lookup"><span data-stu-id="bfa87-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="bfa87-116">Podívejte se na tabulky "Celočíselné aritmetiky" v [typy výsledků operátoru Data](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="bfa87-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="bfa87-117">[/ – Operátor (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) vrátí úplné podílu, který uchovává zbývající v zlomkové části.</span><span class="sxs-lookup"><span data-stu-id="bfa87-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfa87-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="bfa87-118">Remarks</span></span>  
 <span data-ttu-id="bfa87-119">Před provedením divizi, pokusí převést jakýkoli s plovoucí desetinnou čárkou číselný výraz jazyka Visual Basic `Long`.</span><span class="sxs-lookup"><span data-stu-id="bfa87-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="bfa87-120">Pokud `Option Strict` je `On`, dojde k chybě kompilátoru.</span><span class="sxs-lookup"><span data-stu-id="bfa87-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="bfa87-121">Pokud `Option Strict` je `Off`, <xref:System.OverflowException> je možné, pokud je hodnota mimo rozsah [dlouho datový typ](../../../visual-basic/language-reference/data-types/long-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="bfa87-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="bfa87-122">Převod na `Long` je také podléhají *banker je zaokrouhlení*.</span><span class="sxs-lookup"><span data-stu-id="bfa87-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="bfa87-123">Další informace najdete v tématu "Zlomkové části" v [funkce pro převod typů](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="bfa87-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="bfa87-124">Pokud `expression1` nebo `expression2` vyhodnotí jako [nic](../../../visual-basic/language-reference/nothing.md), je považován za nula.</span><span class="sxs-lookup"><span data-stu-id="bfa87-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="bfa87-125">Pokus o dělení nulou</span><span class="sxs-lookup"><span data-stu-id="bfa87-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="bfa87-126">Pokud `expression2` vyhodnotí na hodnotu nula, `\` vyvolá operátor <xref:System.DivideByZeroException> výjimka.</span><span class="sxs-lookup"><span data-stu-id="bfa87-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="bfa87-127">To platí pro všechny číselné datové typy operandy.</span><span class="sxs-lookup"><span data-stu-id="bfa87-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfa87-128">`\` Může být operátor *přetížený*, což znamená, že třídu nebo strukturu lze znovu definovat své chování při operand má typ třídy nebo struktura.</span><span class="sxs-lookup"><span data-stu-id="bfa87-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="bfa87-129">Pokud váš kód používá tento operátor na takové třídu nebo strukturu, ujistěte se, že rozumíte své Předefinovaná chování.</span><span class="sxs-lookup"><span data-stu-id="bfa87-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="bfa87-130">Další informace najdete v tématu [procedury operátoru](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="bfa87-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfa87-131">Příklad</span><span class="sxs-lookup"><span data-stu-id="bfa87-131">Example</span></span>  
 <span data-ttu-id="bfa87-132">Následující příklad používá `\` operátor provést dělení celého čísla.</span><span class="sxs-lookup"><span data-stu-id="bfa87-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="bfa87-133">Výsledkem je celé číslo, které představuje celé číslo podíl dva operandy zbývajícími zahozeny.</span><span class="sxs-lookup"><span data-stu-id="bfa87-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 <span data-ttu-id="bfa87-134">Výrazy v předchozím příkladu návratové hodnoty 2, 3, 33 a-22, v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="bfa87-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa87-135">Viz také</span><span class="sxs-lookup"><span data-stu-id="bfa87-135">See Also</span></span>  
 [<span data-ttu-id="bfa87-136">\\= – Operátor</span><span class="sxs-lookup"><span data-stu-id="bfa87-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="bfa87-137">/ – Operátor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfa87-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [<span data-ttu-id="bfa87-138">Option Strict – příkaz</span><span class="sxs-lookup"><span data-stu-id="bfa87-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="bfa87-139">Aritmetické operátory</span><span class="sxs-lookup"><span data-stu-id="bfa87-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="bfa87-140">Priorita operátorů v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bfa87-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="bfa87-141">Operátory uvedené podle funkce</span><span class="sxs-lookup"><span data-stu-id="bfa87-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="bfa87-142">Aritmetické operátory v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bfa87-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)