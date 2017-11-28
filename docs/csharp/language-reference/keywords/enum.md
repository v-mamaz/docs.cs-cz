---
title: "enum (Referenční dokumentace jazyka C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords: enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
caps.latest.revision: "36"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 00ae9b555ae73db445fe4a4facf00753bf8c759a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="enum-c-reference"></a><span data-ttu-id="0fdd9-102">enum (Referenční dokumentace jazyka C#)</span><span class="sxs-lookup"><span data-stu-id="0fdd9-102">enum (C# Reference)</span></span>
<span data-ttu-id="0fdd9-103">`enum` – Klíčové slovo se používá k deklaraci výčet, odlišné typ, který se skládá ze sady pojmenované konstanty názvem seznamu enumerátor.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-103">The `enum` keyword is used to declare an enumeration, a distinct type that consists of a set of named constants called the enumerator list.</span></span>  
  
 <span data-ttu-id="0fdd9-104">Obvykle je nejvhodnější definovat výčet přímo v oboru názvů, aby všechny třídy v oboru názvů můžete přistupovat pomocí stejné pohodlí.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-104">Usually it is best to define an enum directly within a namespace so that all classes in the namespace can access it with equal convenience.</span></span> <span data-ttu-id="0fdd9-105">Výčet však mohou být také vnořené ve třídě nebo struktuře.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-105">However, an enum can also be nested within a class or struct.</span></span>  
  
 <span data-ttu-id="0fdd9-106">Ve výchozím nastavení první enumerátor má hodnotu 0 a hodnotu každé následných enumerátor je zvýšenou o hodnotu 1.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-106">By default, the first enumerator has the value 0, and the value of each successive enumerator is increased by 1.</span></span> <span data-ttu-id="0fdd9-107">Například v následujícím výčtu `Sat` je `0`, `Sun` je `1`, `Mon` je `2`, a tak dále.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-107">For example, in the following enumeration, `Sat` is `0`, `Sun` is `1`, `Mon` is `2`, and so forth.</span></span>  
  
```  
enum Days {Sat, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="0fdd9-108">Výčty můžete použít inicializátory přepsat výchozí hodnoty, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-108">Enumerators can use initializers to override the default values, as shown in the following example.</span></span>  
  
```  
enum Days {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="0fdd9-109">V tento výčet je nucen pořadí elementů spuštění z `1` místo `0`.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-109">In this enumeration, the sequence of elements is forced to start from `1` instead of `0`.</span></span> <span data-ttu-id="0fdd9-110">Nicméně se doporučuje včetně konstanta, která má hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-110">However, including a constant that has the value of 0 is recommended.</span></span> <span data-ttu-id="0fdd9-111">Další informace najdete v tématu [výčtové typy](../../../csharp/programming-guide/enumeration-types.md).</span><span class="sxs-lookup"><span data-stu-id="0fdd9-111">For more information, see [Enumeration Types](../../../csharp/programming-guide/enumeration-types.md).</span></span>  
  
 <span data-ttu-id="0fdd9-112">Každý typ výčtu je základní typ, který mohou být jakéhokoli typu integrální s výjimkou [char](../../../csharp/language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="0fdd9-112">Every enumeration type has an underlying type, which can be any integral type except [char](../../../csharp/language-reference/keywords/char.md).</span></span> <span data-ttu-id="0fdd9-113">Základní typ výčtu elementů výchozí hodnota je [int](../../../csharp/language-reference/keywords/int.md). Výčet integrální jiného typu, například deklarovat [bajtů](../../../csharp/language-reference/keywords/byte.md), použijte středník po identifikátor následovaný typem, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-113">The default underlying type of enumeration elements is [int](../../../csharp/language-reference/keywords/int.md). To declare an enum of another integral type, such as [byte](../../../csharp/language-reference/keywords/byte.md), use a colon after the identifier followed by the type, as shown in the following example.</span></span>  
  
```  
enum Days : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="0fdd9-114">Seznam schválených typy výčtu `byte`, [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [krátké](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [Celé_číslo](../../../csharp/language-reference/keywords/uint.md), [dlouho](../../../csharp/language-reference/keywords/long.md), nebo [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="0fdd9-114">The approved types for an enum are `byte`, [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="0fdd9-115">Proměnné typu `Days` lze přiřadit žádnou hodnotu v rozsahu základní typ; hodnoty nejsou omezeny na pojmenované konstanty.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-115">A variable of type `Days` can be assigned any value in the range of the underlying type; the values are not limited to the named constants.</span></span>  
  
 <span data-ttu-id="0fdd9-116">Výchozí hodnota `enum E` je hodnota vyprodukované výraz `(E)0`.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-116">The default value of an `enum E` is the value produced by the expression `(E)0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fdd9-117">Enumerátor nesmí obsahovat prázdné znaky v názvu.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-117">An enumerator cannot contain white space in its name.</span></span>  
  
 <span data-ttu-id="0fdd9-118">Základní typ Určuje, jak velké úložiště je přidělen pro každý enumerátor.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-118">The underlying type specifies how much storage is allocated for each enumerator.</span></span> <span data-ttu-id="0fdd9-119">Nicméně je nutné převést z explicitní přetypování `enum` typu integrální typ.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-119">However, an explicit cast is necessary to convert from `enum` type to an integral type.</span></span> <span data-ttu-id="0fdd9-120">Například následující příkaz přiřadí enumerátor `Sun` proměnné typu [int](../../../csharp/language-reference/keywords/int.md) pomocí přetypování převést z `enum` k `int`.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-120">For example, the following statement assigns the enumerator `Sun` to a variable of the type [int](../../../csharp/language-reference/keywords/int.md) by using a cast to convert from `enum` to `int`.</span></span>  
  
```  
int x = (int)Days.Sun;  
```  
  
 <span data-ttu-id="0fdd9-121">Když použijete <xref:System.FlagsAttribute?displayProperty=nameWithType> pro výčet, který obsahuje prvky, které mohou být kombinovány s bitové `OR` operace atribut má vliv na chování `enum` při použití s některé nástroje.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-121">When you apply <xref:System.FlagsAttribute?displayProperty=nameWithType> to an enumeration that contains elements that can be combined with a bitwise `OR` operation, the attribute affects the behavior of the `enum` when it is used with some tools.</span></span> <span data-ttu-id="0fdd9-122">Tyto změny může dojít, při použití nástrojů, jako <xref:System.Console> třídy metody a vyhodnocovací filtr výrazů.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-122">You can notice these changes when you use tools such as the <xref:System.Console> class methods and the Expression Evaluator.</span></span> <span data-ttu-id="0fdd9-123">(Podívejte se na třetí příklad).</span><span class="sxs-lookup"><span data-stu-id="0fdd9-123">(See the third example.)</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0fdd9-124">Robustní programování</span><span class="sxs-lookup"><span data-stu-id="0fdd9-124">Robust Programming</span></span>  
 <span data-ttu-id="0fdd9-125">Stejně jako v jakékoli konstanta všechny odkazy na jednotlivé hodnoty výčtu jsou převedeny na číselné literály v době kompilace.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-125">Just as with any constant, all references to the individual values of an enum are converted to numeric literals at compile time.</span></span> <span data-ttu-id="0fdd9-126">To můžete vytvořit potenciální problémy správy verzí, jak je popsáno v [konstanty](../../../csharp/programming-guide/classes-and-structs/constants.md).</span><span class="sxs-lookup"><span data-stu-id="0fdd9-126">This can create potential versioning issues as described in [Constants](../../../csharp/programming-guide/classes-and-structs/constants.md).</span></span>  
  
 <span data-ttu-id="0fdd9-127">Přiřazení dalších hodnot k nové verze výčty nebo změna hodnot výčtu členy v nové verzi může způsobit problémy závislé zdrojového kódu.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-127">Assigning additional values to new versions of enums, or changing the values of the enum members in a new version, can cause problems for dependent source code.</span></span> <span data-ttu-id="0fdd9-128">Hodnoty výčtu jsou často používány v [přepínač](../../../csharp/language-reference/keywords/switch.md) příkazy.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-128">Enum values often are used in [switch](../../../csharp/language-reference/keywords/switch.md) statements.</span></span> <span data-ttu-id="0fdd9-129">Pokud do nebyly přidané další prvky `enum` typu, výchozí část výrazu switch, který lze vybrat neočekávaně.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-129">If additional elements have been added to the `enum` type, the default section of the switch statement can be selected unexpectedly.</span></span>  
  
 <span data-ttu-id="0fdd9-130">Pokud jinými vývojáři použít kódu, měli byste jim poskytnout pokyny o tom, jak by měl svůj kód reagovat Pokud nové prvky jsou přidány do žádné `enum` typy.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-130">If other developers use your code, you should provide guidelines about how their code should react if new elements are added to any `enum` types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fdd9-131">Příklad</span><span class="sxs-lookup"><span data-stu-id="0fdd9-131">Example</span></span>  
 <span data-ttu-id="0fdd9-132">V následujícím příkladu, výčet, `Days`, je deklarován.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-132">In the following example, an enumeration, `Days`, is declared.</span></span> <span data-ttu-id="0fdd9-133">Dva výčty explicitně převést na celé číslo a přiřazený k proměnné celé číslo.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-133">Two enumerators are explicitly converted to integer and assigned to integer variables.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="0fdd9-134">Příklad</span><span class="sxs-lookup"><span data-stu-id="0fdd9-134">Example</span></span>  
 <span data-ttu-id="0fdd9-135">V následujícím příkladu je základní typ možnost používá k deklaraci `enum` jejíž členové jsou typu `long`.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-135">In the following example, the base-type option is used to declare an `enum` whose members are of type `long`.</span></span> <span data-ttu-id="0fdd9-136">Všimněte si, že i když je základní typ výčtu `long`, členové výčtu stále musí být explicitně převést na typ `long` pomocí přetypování.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-136">Notice that even though the underlying type of the enumeration is `long`, the enumeration members still must be explicitly converted to type `long` by using a cast.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="0fdd9-137">Příklad</span><span class="sxs-lookup"><span data-stu-id="0fdd9-137">Example</span></span>  
 <span data-ttu-id="0fdd9-138">Následující příklad kódu ukazuje použití a účinku <xref:System.FlagsAttribute?displayProperty=nameWithType> atributu u `enum` deklarace.</span><span class="sxs-lookup"><span data-stu-id="0fdd9-138">The following code example illustrates the use and effect of the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute on an `enum` declaration.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_3.cs)]  
  
## <a name="comments"></a><span data-ttu-id="0fdd9-139">Komentáře</span><span class="sxs-lookup"><span data-stu-id="0fdd9-139">Comments</span></span>  
 <span data-ttu-id="0fdd9-140">Pokud odeberete `Flags`, v příkladu se zobrazí následující hodnoty:</span><span class="sxs-lookup"><span data-stu-id="0fdd9-140">If you remove `Flags`, the example displays the following values:</span></span>  
  
 `5`  
  
 `5`  
  
## <a name="c-language-specification"></a><span data-ttu-id="0fdd9-141">Specifikace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="0fdd9-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0fdd9-142">Viz také</span><span class="sxs-lookup"><span data-stu-id="0fdd9-142">See Also</span></span>  
 [<span data-ttu-id="0fdd9-143">Referenční dokumentace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="0fdd9-143">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0fdd9-144">Výčtové typy</span><span class="sxs-lookup"><span data-stu-id="0fdd9-144">Enumeration Types</span></span>](../../../csharp/programming-guide/enumeration-types.md)  
 [<span data-ttu-id="0fdd9-145">Klíčová slova jazyka C#</span><span class="sxs-lookup"><span data-stu-id="0fdd9-145">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0fdd9-146">Tabulka celočíselných typů</span><span class="sxs-lookup"><span data-stu-id="0fdd9-146">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="0fdd9-147">Tabulka předdefinovaných typů</span><span class="sxs-lookup"><span data-stu-id="0fdd9-147">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="0fdd9-148">Tabulka implicitních číselných převodů</span><span class="sxs-lookup"><span data-stu-id="0fdd9-148">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="0fdd9-149">Tabulka explicitních číselných převodů</span><span class="sxs-lookup"><span data-stu-id="0fdd9-149">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)