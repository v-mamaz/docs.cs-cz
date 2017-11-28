---
title: "Postupy: hledání podřízených elementů na základě pozice (XPath-technologie LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6831e1db-5e97-444f-a7a1-d0a87104b005
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fcd7cc8d68e6eccd00abeacf3c5817d3625b8891
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="b3e06-102">Postupy: hledání podřízených elementů na základě pozice (XPath-technologie LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3e06-102">How to: Find Child Elements Based on Position (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="b3e06-103">Někdy budete chtít najít elementy, které jsou založeny na jejich umístění.</span><span class="sxs-lookup"><span data-stu-id="b3e06-103">Sometimes you want to find elements based on their position.</span></span> <span data-ttu-id="b3e06-104">Můžete chtít najít druhý prvkem, nebo můžete chtít najít třetí prostřednictvím páté elementu.</span><span class="sxs-lookup"><span data-stu-id="b3e06-104">You might want to find the second element, or you might want to find the third through the fifth element.</span></span>  
  
 <span data-ttu-id="b3e06-105">Výraz XPath je:</span><span class="sxs-lookup"><span data-stu-id="b3e06-105">The XPath expression is:</span></span>  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 <span data-ttu-id="b3e06-106">Existují dva přístupy k zápisu to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] dotazu opožděné způsobem.</span><span class="sxs-lookup"><span data-stu-id="b3e06-106">There are two approaches to writing this [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query in a lazy way.</span></span> <span data-ttu-id="b3e06-107">Můžete použít <xref:System.Linq.Enumerable.Skip%2A> a <xref:System.Linq.Enumerable.Take%2A> operátory, nebo můžete použít <xref:System.Linq.Enumerable.Where%2A> přetížení, které přijímá indexu.</span><span class="sxs-lookup"><span data-stu-id="b3e06-107">You can use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> operators, or you can use the <xref:System.Linq.Enumerable.Where%2A> overload that takes an index.</span></span> <span data-ttu-id="b3e06-108">Při použití <xref:System.Linq.Enumerable.Where%2A> přetížení, použijte výraz lambda, která přebírá dva argumenty.</span><span class="sxs-lookup"><span data-stu-id="b3e06-108">When you use the <xref:System.Linq.Enumerable.Where%2A> overload, you use a lambda expression that takes two arguments.</span></span> <span data-ttu-id="b3e06-109">Následující příklad ukazuje obě metody výběru na základě pozice.</span><span class="sxs-lookup"><span data-stu-id="b3e06-109">The following example shows both methods of selecting based on position.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3e06-110">Příklad</span><span class="sxs-lookup"><span data-stu-id="b3e06-110">Example</span></span>  
 <span data-ttu-id="b3e06-111">Tento příklad vyhledá druhý prostřednictvím čtvrtý `Test` elementu.</span><span class="sxs-lookup"><span data-stu-id="b3e06-111">This example finds the second through the fourth `Test` element.</span></span> <span data-ttu-id="b3e06-112">Výsledkem je kolekci elementů.</span><span class="sxs-lookup"><span data-stu-id="b3e06-112">The result is a collection of elements.</span></span>  
  
 <span data-ttu-id="b3e06-113">Tento příklad používá následující dokumentu XML: [ukázkový soubor XML: Konfigurace testu (technologie LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b3e06-113">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```vb  
Dim testCfg As XElement = XElement.Load("TestConfig.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test").Skip(1).Take(3)  
  
'LINQ to XML query  
Dim list2 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test"). _  
    Where(Function(ByVal el, ByVal idx) idx >= 1 And idx <= 3)  
  
' XPath expression  
Dim list3 As IEnumerable(Of XElement) = _  
    testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]")  
  
If list1.Count() = list2.Count() And _  
       list1.Count() = list3.Count() And _  
       list1.Intersect(list2).Count() = list1.Count() And _  
       list1.Intersect(list3).Count() = list1.Count() Then  
  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="b3e06-114">Tento příklad vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="b3e06-114">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3e06-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="b3e06-115">See Also</span></span>  
 [<span data-ttu-id="b3e06-116">Technologie LINQ to XML pro uživatele XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3e06-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)