---
title: "Postupy: načtení hodnoty elementu (technologie LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ceb803eff68f72378ca195120ed96990d62d3593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="2dfc2-102">Postupy: načtení hodnoty elementu (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2dfc2-102">How to: Retrieve the Value of an Element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="2dfc2-103">Toto téma ukazuje, jak má být získána hodnota elementů.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="2dfc2-104">Chcete-li to provést dvěma způsoby.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-104">There are two main ways to do this.</span></span> <span data-ttu-id="2dfc2-105">Jedním ze způsobů je přetypovat <xref:System.Xml.Linq.XElement> nebo <xref:System.Xml.Linq.XAttribute> na požadovaný typ.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="2dfc2-106">Explicitní převod operátor potom převede obsah elementu nebo atributu na zadaný typ a přiřadí ji k vaše proměnná.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="2dfc2-107">Alternativně můžete použít <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> vlastnost nebo <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="2dfc2-108">Pomocí C# ale přetypování je obecně lepší přístup.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-108">With C#, however, casting is generally the better approach.</span></span> <span data-ttu-id="2dfc2-109">Pokud přetypovat element nebo atribut na typ s možnou hodnotou Null, kód je jednodušší zápis při načítání hodnoty elementu (nebo atributu), který může nebo nemusí existovat.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-109">If you cast the element or attribute to a nullable type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="2dfc2-110">Poslední příklad v tomto tématu ukazuje to.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-110">The last example in this topic demonstrates this.</span></span> <span data-ttu-id="2dfc2-111">Však nelze nastavit obsah elementu přetypování, protože můžete prostřednictvím <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-111">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dfc2-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="2dfc2-112">Example</span></span>  
 <span data-ttu-id="2dfc2-113">K načtení hodnoty elementu, je právě přetypovat <xref:System.Xml.Linq.XElement> objekt, který má požadovaný typ.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-113">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="2dfc2-114">Element na řetězec, můžete vždy přetypovat následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="2dfc2-114">You can always cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="2dfc2-115">Tento příklad vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="2dfc2-115">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="2dfc2-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="2dfc2-116">Example</span></span>  
 <span data-ttu-id="2dfc2-117">Můžete také přetypování elementy na typy jiné než řetězec.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-117">You can also cast elements to types other than string.</span></span> <span data-ttu-id="2dfc2-118">Například pokud máte elementu, který obsahuje celé číslo, vám může vysílat `int`, jak je znázorněno v následujícím kódu:</span><span class="sxs-lookup"><span data-stu-id="2dfc2-118">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="2dfc2-119">Tento příklad vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="2dfc2-119">This example produces the following output:</span></span>  
  
```  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="2dfc2-120">poskytuje operátory explicitní přetypování pro následující typy dat: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`a `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-120"> provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="2dfc2-121">poskytuje stejné operátory přetypování pro <xref:System.Xml.Linq.XAttribute> objekty.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-121"> provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dfc2-122">Příklad</span><span class="sxs-lookup"><span data-stu-id="2dfc2-122">Example</span></span>  
 <span data-ttu-id="2dfc2-123">Můžete použít <xref:System.Xml.Linq.XElement.Value%2A> vlastnost můžete načíst obsah elementu:</span><span class="sxs-lookup"><span data-stu-id="2dfc2-123">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");   
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="2dfc2-124">Tento příklad vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="2dfc2-124">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="2dfc2-125">Příklad</span><span class="sxs-lookup"><span data-stu-id="2dfc2-125">Example</span></span>  
 <span data-ttu-id="2dfc2-126">Někdy pokusu načíst hodnotu elementu, i když si nejste jisti, že existuje.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-126">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="2dfc2-127">V takovém případě přiřadíte-li převedena element na typ s možnou hodnotou Null (buď `string` nebo jeden z typů s povolenou hodnotou Null v [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]), pokud element neexistuje přiřazená proměnná je nastavená pouze na `null`.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-127">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable types in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]), if the element does not exist the assigned variable is just set to `null`.</span></span> <span data-ttu-id="2dfc2-128">Následující kód ukazuje, že pokud element může nebo nemusí existovat, je jednodušší použít přetypování než k použijte <xref:System.Xml.Linq.XElement.Value%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-128">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 <span data-ttu-id="2dfc2-129">Tento kód vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="2dfc2-129">This code produces the following output:</span></span>  
  
```  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 <span data-ttu-id="2dfc2-130">Obecně platí můžete napsat kód jednodušší při použití přetypování můžete načíst obsah elementů a atributů.</span><span class="sxs-lookup"><span data-stu-id="2dfc2-130">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dfc2-131">Viz také</span><span class="sxs-lookup"><span data-stu-id="2dfc2-131">See Also</span></span>  
 [<span data-ttu-id="2dfc2-132">Technologie LINQ to XML osy (C#)</span><span class="sxs-lookup"><span data-stu-id="2dfc2-132">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)