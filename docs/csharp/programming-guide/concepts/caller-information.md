---
title: "Informace o subjektu volajícím (C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ffad3d24-2fb7-4641-9124-53b5bc91d339
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 05c153afd502da1f290b3bc36460ded27789e21c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information-c"></a><span data-ttu-id="67e39-102">Informace o subjektu volajícím (C#)</span><span class="sxs-lookup"><span data-stu-id="67e39-102">Caller Information (C#)</span></span>
<span data-ttu-id="67e39-103">Pomocí atributů Informace o volajícím můžete získat informace o volajícím metody.</span><span class="sxs-lookup"><span data-stu-id="67e39-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="67e39-104">Můžete získat cestu k souboru zdrojového kódu, číslo řádku ve zdrojovém kódu a název členu volajícího.</span><span class="sxs-lookup"><span data-stu-id="67e39-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="67e39-105">Tyto informace jsou užitečné pro trasování, ladění a vytváření diagnostických nástrojů.</span><span class="sxs-lookup"><span data-stu-id="67e39-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="67e39-106">Pro získání těchto informací můžete použít atributy, které jsou použity na volitelné parametry, z nichž každý má výchozí hodnotu.</span><span class="sxs-lookup"><span data-stu-id="67e39-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="67e39-107">Následující tabulka uvádí informace o volajícím atributy, které jsou definovány v <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> obor názvů:</span><span class="sxs-lookup"><span data-stu-id="67e39-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="67e39-108">Atribut</span><span class="sxs-lookup"><span data-stu-id="67e39-108">Attribute</span></span>|<span data-ttu-id="67e39-109">Popis</span><span class="sxs-lookup"><span data-stu-id="67e39-109">Description</span></span>|<span data-ttu-id="67e39-110">Typ</span><span class="sxs-lookup"><span data-stu-id="67e39-110">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="67e39-111">Úplná cesta zdrojového souboru, který obsahuje volajícího.</span><span class="sxs-lookup"><span data-stu-id="67e39-111">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="67e39-112">Toto je cesta k souboru v době kompilace.</span><span class="sxs-lookup"><span data-stu-id="67e39-112">This is the file path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="67e39-113">Číslo řádku ve zdrojovém souboru, ve kterém je volána metoda.</span><span class="sxs-lookup"><span data-stu-id="67e39-113">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="67e39-114">Název metody nebo vlastnosti volajícího.</span><span class="sxs-lookup"><span data-stu-id="67e39-114">Method or property name of the caller.</span></span> <span data-ttu-id="67e39-115">V tématu [názvy členů](#MEMBERNAMES) dál v tomto tématu.</span><span class="sxs-lookup"><span data-stu-id="67e39-115">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="67e39-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="67e39-116">Example</span></span>  
 <span data-ttu-id="67e39-117">Následující příklad ukazuje způsob použití atributů Informace o volajícím.</span><span class="sxs-lookup"><span data-stu-id="67e39-117">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="67e39-118">Při každém volání `TraceMessage` metoda, informace o subjektu volajícím je nahrazena jako argumenty pro volitelné parametry.</span><span class="sxs-lookup"><span data-stu-id="67e39-118">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
```csharp  
public void DoProcessing()  
{  
    TraceMessage("Something happened.");  
}  
  
public void TraceMessage(string message,  
        [System.Runtime.CompilerServices.CallerMemberName] string memberName = "",  
        [System.Runtime.CompilerServices.CallerFilePath] string sourceFilePath = "",  
        [System.Runtime.CompilerServices.CallerLineNumber] int sourceLineNumber = 0)  
{  
    System.Diagnostics.Trace.WriteLine("message: " + message);  
    System.Diagnostics.Trace.WriteLine("member name: " + memberName);  
    System.Diagnostics.Trace.WriteLine("source file path: " + sourceFilePath);  
    System.Diagnostics.Trace.WriteLine("source line number: " + sourceLineNumber);  
}  
  
// Sample Output:  
//  message: Something happened.  
//  member name: DoProcessing  
//  source file path: c:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoCS\CallerInfoCS\Form1.cs  
//  source line number: 31  
```  
  
## <a name="remarks"></a><span data-ttu-id="67e39-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="67e39-119">Remarks</span></span>  
 <span data-ttu-id="67e39-120">Pro každý volitelný parametr je třeba zadat explicitní výchozí hodnotu.</span><span class="sxs-lookup"><span data-stu-id="67e39-120">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="67e39-121">Atributy Informace o volajícím nelze použít u parametrů, které nejsou uvedeny jako volitelné.</span><span class="sxs-lookup"><span data-stu-id="67e39-121">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="67e39-122">Atributy Informace o volajícím neučiní parametr volitelným.</span><span class="sxs-lookup"><span data-stu-id="67e39-122">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="67e39-123">Místo toho mají vliv na výchozí hodnotu, která je předána, pokud je argument vynechán.</span><span class="sxs-lookup"><span data-stu-id="67e39-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="67e39-124">Hodnoty atributů Informace o volajícím jsou emitovány jako literály do jazyka Intermediate Language (IL) v době kompilace.</span><span class="sxs-lookup"><span data-stu-id="67e39-124">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="67e39-125">Na rozdíl od výsledky <xref:System.Exception.StackTrace%2A> maskováním nemá vliv vlastnost pro výjimky, výsledky.</span><span class="sxs-lookup"><span data-stu-id="67e39-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="67e39-126">Volitelné argumenty můžete explicitně zadat, chcete-li řídit nebo skrýt informace o volajícím.</span><span class="sxs-lookup"><span data-stu-id="67e39-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
###  <span data-ttu-id="67e39-127"><a name="MEMBERNAMES"></a>Názvy členů</span><span class="sxs-lookup"><span data-stu-id="67e39-127"><a name="MEMBERNAMES"></a> Member Names</span></span>  
 <span data-ttu-id="67e39-128">Můžete použít `CallerMemberName` atribut Vyhněte se zadání název člena jako `String` argument volané metodě.</span><span class="sxs-lookup"><span data-stu-id="67e39-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="67e39-129">Pomocí Tato technika tomuto problému vyhnout, **přejmenovat refaktoring** nezmění `String` hodnoty.</span><span class="sxs-lookup"><span data-stu-id="67e39-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="67e39-130">Tato výhoda se hodí zvláště v těchto úlohách:</span><span class="sxs-lookup"><span data-stu-id="67e39-130">This benefit is especially useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="67e39-131">Použití trasování a diagnostických rutin.</span><span class="sxs-lookup"><span data-stu-id="67e39-131">Using tracing and diagnostic routines.</span></span>  
  
-   <span data-ttu-id="67e39-132">Implementace <xref:System.ComponentModel.INotifyPropertyChanged> rozhraní při vytváření vazby data.</span><span class="sxs-lookup"><span data-stu-id="67e39-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="67e39-133">Toto rozhraní umožňuje vlastnosti objektu oznámit vázanému ovládacímu prvku, že došlo ke změně vlastnosti, aby ovládací prvek mohl zobrazit aktualizované informace.</span><span class="sxs-lookup"><span data-stu-id="67e39-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="67e39-134">Bez `CallerMemberName` atribut, musíte zadat název vlastnosti jako literál.</span><span class="sxs-lookup"><span data-stu-id="67e39-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="67e39-135">Následující tabulka ukazuje člen názvy, které jsou vráceny při použití `CallerMemberName` atribut.</span><span class="sxs-lookup"><span data-stu-id="67e39-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="67e39-136">K volání dochází v rámci</span><span class="sxs-lookup"><span data-stu-id="67e39-136">Calls occurs within</span></span>|<span data-ttu-id="67e39-137">Výsledek názvu členu</span><span class="sxs-lookup"><span data-stu-id="67e39-137">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="67e39-138">Metoda, vlastnost nebo událost</span><span class="sxs-lookup"><span data-stu-id="67e39-138">Method, property, or event</span></span>|<span data-ttu-id="67e39-139">Název metody, vlastnosti nebo události, z nichž bylo volání provedeno.</span><span class="sxs-lookup"><span data-stu-id="67e39-139">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="67e39-140">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="67e39-140">Constructor</span></span>|<span data-ttu-id="67e39-141">Řetězec „.ctor“</span><span class="sxs-lookup"><span data-stu-id="67e39-141">The string ".ctor"</span></span>|  
|<span data-ttu-id="67e39-142">Statický konstruktor</span><span class="sxs-lookup"><span data-stu-id="67e39-142">Static constructor</span></span>|<span data-ttu-id="67e39-143">Řetězec „.cctor“</span><span class="sxs-lookup"><span data-stu-id="67e39-143">The string ".cctor"</span></span>|  
|<span data-ttu-id="67e39-144">Destruktor</span><span class="sxs-lookup"><span data-stu-id="67e39-144">Destructor</span></span>|<span data-ttu-id="67e39-145">Řetězec „Finalize“</span><span class="sxs-lookup"><span data-stu-id="67e39-145">The string "Finalize"</span></span>|  
|<span data-ttu-id="67e39-146">Operátory nebo převody definované uživatelem</span><span class="sxs-lookup"><span data-stu-id="67e39-146">User-defined operators or conversions</span></span>|<span data-ttu-id="67e39-147">Vygenerovaný název pro člen, například „op_Addition“.</span><span class="sxs-lookup"><span data-stu-id="67e39-147">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="67e39-148">Konstruktor atributu</span><span class="sxs-lookup"><span data-stu-id="67e39-148">Attribute constructor</span></span>|<span data-ttu-id="67e39-149">Název členu, na který se atribut používá.</span><span class="sxs-lookup"><span data-stu-id="67e39-149">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="67e39-150">Pokud je atribut libovolný prvek v členu (například parametr, návratová hodnota nebo parametr obecného typu), je tento výsledek názvem členu, který je přidružen k tomuto prvku.</span><span class="sxs-lookup"><span data-stu-id="67e39-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="67e39-151">Žádný obsahující člen (například úroveň sestavení nebo atributy, které jsou použity na typy)</span><span class="sxs-lookup"><span data-stu-id="67e39-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="67e39-152">Výchozí hodnota volitelného parametru.</span><span class="sxs-lookup"><span data-stu-id="67e39-152">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67e39-153">Viz také</span><span class="sxs-lookup"><span data-stu-id="67e39-153">See Also</span></span>  
 [<span data-ttu-id="67e39-154">Atributy (C#)</span><span class="sxs-lookup"><span data-stu-id="67e39-154">Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="67e39-155">Mezi běžné atributy (C#)</span><span class="sxs-lookup"><span data-stu-id="67e39-155">Common Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
 [<span data-ttu-id="67e39-156">Pojmenované a nepovinné argumenty</span><span class="sxs-lookup"><span data-stu-id="67e39-156">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)  
 [<span data-ttu-id="67e39-157">Programování konceptů (C#)</span><span class="sxs-lookup"><span data-stu-id="67e39-157">Programming Concepts (C#)</span></span>](../../../csharp/programming-guide/concepts/index.md)