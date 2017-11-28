---
title: "Technologie LINQ to XML přehled třídy (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bf666100-5392-4968-97f4-f6b9d3287d7b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0dc4307c3cf87fa9b5cb38bdaa9d9bf77adf1424
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-classes-overview-c"></a><span data-ttu-id="b6845-102">Technologie LINQ to XML přehled třídy (C#)</span><span class="sxs-lookup"><span data-stu-id="b6845-102">LINQ to XML Classes Overview (C#)</span></span>
<span data-ttu-id="b6845-103">Toto téma obsahuje seznam [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] třídy v <xref:System.Xml.Linq> obor názvů a krátký popis každého.</span><span class="sxs-lookup"><span data-stu-id="b6845-103">This topic provides a list of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes in the <xref:System.Xml.Linq> namespace, and a short description of each.</span></span>  
  
## <a name="linq-to-xml-classes"></a><span data-ttu-id="b6845-104">Technologie LINQ to XML třídy</span><span class="sxs-lookup"><span data-stu-id="b6845-104">LINQ to XML Classes</span></span>  
  
### <a name="xattribute-class"></a><span data-ttu-id="b6845-105">XAttribute – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-105">XAttribute Class</span></span>  
 <span data-ttu-id="b6845-106"><xref:System.Xml.Linq.XAttribute>představuje atribut XML.</span><span class="sxs-lookup"><span data-stu-id="b6845-106"><xref:System.Xml.Linq.XAttribute> represents an XML attribute.</span></span> <span data-ttu-id="b6845-107">Podrobné informace a příklady naleznete v tématu [XAttribute přehledu třídy (C#)](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b6845-107">For detailed information and examples, see [XAttribute Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md).</span></span>  
  
### <a name="xcdata-class"></a><span data-ttu-id="b6845-108">XCData – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-108">XCData Class</span></span>  
 <span data-ttu-id="b6845-109"><xref:System.Xml.Linq.XCData>představuje uzel text CDATA.</span><span class="sxs-lookup"><span data-stu-id="b6845-109"><xref:System.Xml.Linq.XCData> represents a CDATA text node.</span></span>  
  
### <a name="xcomment-class"></a><span data-ttu-id="b6845-110">XComment – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-110">XComment Class</span></span>  
 <span data-ttu-id="b6845-111"><xref:System.Xml.Linq.XComment>představuje komentáře jazyka XML.</span><span class="sxs-lookup"><span data-stu-id="b6845-111"><xref:System.Xml.Linq.XComment> represents an XML comment.</span></span>  
  
### <a name="xcontainer-class"></a><span data-ttu-id="b6845-112">XContainer – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-112">XContainer Class</span></span>  
 <span data-ttu-id="b6845-113"><xref:System.Xml.Linq.XContainer>je abstraktní základní třída pro všechny uzly, které může mít podřízené uzly.</span><span class="sxs-lookup"><span data-stu-id="b6845-113"><xref:System.Xml.Linq.XContainer> is an abstract base class for all nodes that can have child nodes.</span></span> <span data-ttu-id="b6845-114">Následující třídy odvozovat <xref:System.Xml.Linq.XContainer> třídy:</span><span class="sxs-lookup"><span data-stu-id="b6845-114">The following classes derive from the <xref:System.Xml.Linq.XContainer> class:</span></span>  
  
-   <xref:System.Xml.Linq.XElement>  
  
-   <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a><span data-ttu-id="b6845-115">XDeclaration – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-115">XDeclaration Class</span></span>  
 <span data-ttu-id="b6845-116"><xref:System.Xml.Linq.XDeclaration>představuje deklarace XML.</span><span class="sxs-lookup"><span data-stu-id="b6845-116"><xref:System.Xml.Linq.XDeclaration> represents an XML declaration.</span></span> <span data-ttu-id="b6845-117">Deklarace XML se používá k deklaraci XML verze a kódování dokumentu.</span><span class="sxs-lookup"><span data-stu-id="b6845-117">An XML declaration is used to declare the XML version and the encoding of a document.</span></span> <span data-ttu-id="b6845-118">Kromě toho deklarace XML určuje, zda je v dokumentu XML samostatné.</span><span class="sxs-lookup"><span data-stu-id="b6845-118">In addition, an XML declaration specifies whether the XML document is stand-alone.</span></span> <span data-ttu-id="b6845-119">Pokud dokument je samostatná, neexistují žádné externí značek deklarace v externí DTD nebo v entitu externí parametr na něj odkazovat z vnitřní podmnožiny.</span><span class="sxs-lookup"><span data-stu-id="b6845-119">If a document is stand-alone, there are no external markup declarations, either in an external DTD, or in an external parameter entity referenced from the internal subset.</span></span>  
  
### <a name="xdocument-class"></a><span data-ttu-id="b6845-120">XDocument – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-120">XDocument Class</span></span>  
 <span data-ttu-id="b6845-121"><xref:System.Xml.Linq.XDocument>představuje dokument XML.</span><span class="sxs-lookup"><span data-stu-id="b6845-121"><xref:System.Xml.Linq.XDocument> represents an XML document.</span></span> <span data-ttu-id="b6845-122">Podrobné informace a příklady naleznete v tématu [XDocument přehledu třídy (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b6845-122">For detailed information and examples, see [XDocument Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
### <a name="xdocumenttype-class"></a><span data-ttu-id="b6845-123">XDocumentType – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-123">XDocumentType Class</span></span>  
 <span data-ttu-id="b6845-124"><xref:System.Xml.Linq.XDocumentType>představuje definice pro typ dokumentu XML (DTD).</span><span class="sxs-lookup"><span data-stu-id="b6845-124"><xref:System.Xml.Linq.XDocumentType> represents an XML Document Type Definition (DTD).</span></span>  
  
### <a name="xelement-class"></a><span data-ttu-id="b6845-125">XElement – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-125">XElement Class</span></span>  
 <span data-ttu-id="b6845-126"><xref:System.Xml.Linq.XElement>reprezentuje element, XML.</span><span class="sxs-lookup"><span data-stu-id="b6845-126"><xref:System.Xml.Linq.XElement> represents an XML element.</span></span> <span data-ttu-id="b6845-127">Podrobné informace a příklady naleznete v tématu [XElement přehledu třídy (C#)](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b6845-127">For detailed information and examples, see [XElement Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md).</span></span>  
  
### <a name="xname-class"></a><span data-ttu-id="b6845-128">XName – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-128">XName Class</span></span>  
 <span data-ttu-id="b6845-129"><xref:System.Xml.Linq.XName>představuje názvy elementů (<xref:System.Xml.Linq.XElement>) a atributy (<xref:System.Xml.Linq.XAttribute>).</span><span class="sxs-lookup"><span data-stu-id="b6845-129"><xref:System.Xml.Linq.XName> represents names of elements (<xref:System.Xml.Linq.XElement>) and attributes (<xref:System.Xml.Linq.XAttribute>).</span></span> <span data-ttu-id="b6845-130">Podrobné informace a příklady naleznete v tématu [XDocument přehledu třídy (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b6845-130">For detailed information and examples, see [XDocument Class Overview (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="b6845-131">zajišťují, aby názvy XML maximálně jednoduché.</span><span class="sxs-lookup"><span data-stu-id="b6845-131"> is designed to make XML names as straightforward as possible.</span></span> <span data-ttu-id="b6845-132">Z důvodu jejich složitost XML názvy jsou často považuje za rozšířená v kódu XML.</span><span class="sxs-lookup"><span data-stu-id="b6845-132">Due to their complexity, XML names are often considered to be an advanced topic in XML.</span></span> <span data-ttu-id="b6845-133">Tato složitost dodává pravděpodobně, nikoli z oborů názvů, které vývojáři použít pravidelně při programování, ale z předpony oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="b6845-133">Arguably, this complexity comes not from namespaces, which developers use regularly in programming, but from namespace prefixes.</span></span> <span data-ttu-id="b6845-134">Namespace předpony může být užitečná ke snížení stisknutí kláves potřebné při zadávání XML, nebo k usnadnění XML.</span><span class="sxs-lookup"><span data-stu-id="b6845-134">Namespace prefixes can be useful to reduce the keystrokes required when you input XML, or to make XML easier to read.</span></span> <span data-ttu-id="b6845-135">Ale předpony jsou často zástupce pro používání úplné obor názvů XML a není nutné ve většině případů.</span><span class="sxs-lookup"><span data-stu-id="b6845-135">However, prefixes are often just a shortcut for using the full XML namespace, and are not required in most cases.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="b6845-136">Vyřešte všechny předpony na jejich odpovídající obor názvů XML zjednodušuje názvů XML.</span><span class="sxs-lookup"><span data-stu-id="b6845-136"> simplifies XML names by resolving all prefixes to their corresponding XML namespace.</span></span> <span data-ttu-id="b6845-137">Jsou k dispozici, pokud jsou požadována prostřednictvím předpony <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="b6845-137">Prefixes are available, if they are required, through the <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> method.</span></span>  
  
 <span data-ttu-id="b6845-138">Je možné, pokud je to nezbytné, aby se předpony oboru názvů řízení.</span><span class="sxs-lookup"><span data-stu-id="b6845-138">It is possible, if necessary, to control namespace prefixes.</span></span> <span data-ttu-id="b6845-139">V některých případech Pokud pracujete s jinými systémy XML, jako je například XSLT nebo XAML, je nutné určit předpony oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="b6845-139">In some circumstances, if you are working with other XML systems, such as XSLT or XAML, you need to control namespace prefixes.</span></span> <span data-ttu-id="b6845-140">Například pokud máte výraz XPath, který používá předpony oboru názvů a vložené do šablonu stylů XSLT, je musí ověřit, že je váš dokument XML serializovat s příznakem předpony oboru názvů, které se shodují s těmi, použít ve výrazu XPath.</span><span class="sxs-lookup"><span data-stu-id="b6845-140">For example, if you have an XPath expression that uses namespace prefixes and is embedded in an XSLT stylesheet, you must make sure that your XML document is serialized with namespace prefixes that match those used in the XPath expression.</span></span>  
  
### <a name="xnamespace-class"></a><span data-ttu-id="b6845-141">XNamespace – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-141">XNamespace Class</span></span>  
 <span data-ttu-id="b6845-142"><xref:System.Xml.Linq.XNamespace>představuje obor názvů pro <xref:System.Xml.Linq.XElement> nebo <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b6845-142"><xref:System.Xml.Linq.XNamespace> represents a namespace for an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="b6845-143">Obory názvů jsou součástí <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="b6845-143">Namespaces are a component of an <xref:System.Xml.Linq.XName>.</span></span>  
  
### <a name="xnode-class"></a><span data-ttu-id="b6845-144">XNode – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-144">XNode Class</span></span>  
 <span data-ttu-id="b6845-145"><xref:System.Xml.Linq.XNode>je abstraktní třída, která představuje uzlů stromu XML.</span><span class="sxs-lookup"><span data-stu-id="b6845-145"><xref:System.Xml.Linq.XNode> is an abstract class that represents the nodes of an XML tree.</span></span> <span data-ttu-id="b6845-146">Následující třídy odvozovat <xref:System.Xml.Linq.XNode> třídy:</span><span class="sxs-lookup"><span data-stu-id="b6845-146">The following classes derive from the <xref:System.Xml.Linq.XNode> class:</span></span>  
  
-   <xref:System.Xml.Linq.XText>  
  
-   <xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XComment>  
  
-   <xref:System.Xml.Linq.XProcessingInstruction>  
  
-   <xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a><span data-ttu-id="b6845-147">XNodeDocumentOrderComparer – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-147">XNodeDocumentOrderComparer Class</span></span>  
 <span data-ttu-id="b6845-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer>poskytuje funkce pro porovnání uzlů pro jejich dokument pořadí.</span><span class="sxs-lookup"><span data-stu-id="b6845-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> provides functionality to compare nodes for their document order.</span></span>  
  
### <a name="xnodeequalitycomparer-class"></a><span data-ttu-id="b6845-149">XNodeEqualityComparer – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-149">XNodeEqualityComparer Class</span></span>  
 <span data-ttu-id="b6845-150"><xref:System.Xml.Linq.XNodeEqualityComparer>poskytuje funkce pro porovnání uzlů pro rovnosti hodnoty.</span><span class="sxs-lookup"><span data-stu-id="b6845-150"><xref:System.Xml.Linq.XNodeEqualityComparer> provides functionality to compare nodes for value equality.</span></span>  
  
### <a name="xobject-class"></a><span data-ttu-id="b6845-151">XObjektu – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-151">XObject Class</span></span>  
 <span data-ttu-id="b6845-152"><xref:System.Xml.Linq.XObject>je abstraktní základní třída z <xref:System.Xml.Linq.XNode> a <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b6845-152"><xref:System.Xml.Linq.XObject> is an abstract base class of <xref:System.Xml.Linq.XNode> and <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="b6845-153">Nabízí funkce, poznámky a události.</span><span class="sxs-lookup"><span data-stu-id="b6845-153">It provides annotation and event functionality.</span></span>  
  
### <a name="xobjectchange-class"></a><span data-ttu-id="b6845-154">XObjectChange – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-154">XObjectChange Class</span></span>  
 <span data-ttu-id="b6845-155"><xref:System.Xml.Linq.XObjectChange>Určuje typ události, když událost se vyvolá pro <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="b6845-155"><xref:System.Xml.Linq.XObjectChange> specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>  
  
### <a name="xobjectchangeeventargs-class"></a><span data-ttu-id="b6845-156">XObjectChangeEventArgs – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-156">XObjectChangeEventArgs Class</span></span>  
 <span data-ttu-id="b6845-157"><xref:System.Xml.Linq.XObjectChangeEventArgs>poskytuje data pro <xref:System.Xml.Linq.XObject.Changing> a <xref:System.Xml.Linq.XObject.Changed> události.</span><span class="sxs-lookup"><span data-stu-id="b6845-157"><xref:System.Xml.Linq.XObjectChangeEventArgs> provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>  
  
### <a name="xprocessinginstruction-class"></a><span data-ttu-id="b6845-158">XProcessingInstruction – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-158">XProcessingInstruction Class</span></span>  
 <span data-ttu-id="b6845-159"><xref:System.Xml.Linq.XProcessingInstruction>představuje instrukcí pro zpracování XML.</span><span class="sxs-lookup"><span data-stu-id="b6845-159"><xref:System.Xml.Linq.XProcessingInstruction> represents an XML processing instruction.</span></span> <span data-ttu-id="b6845-160">Zpracování instrukcí komunikuje informace, které aplikace, která zpracovává soubor XML.</span><span class="sxs-lookup"><span data-stu-id="b6845-160">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
### <a name="xtext-class"></a><span data-ttu-id="b6845-161">XText – třída</span><span class="sxs-lookup"><span data-stu-id="b6845-161">XText Class</span></span>  
 <span data-ttu-id="b6845-162"><xref:System.Xml.Linq.XText>představuje uzel text.</span><span class="sxs-lookup"><span data-stu-id="b6845-162"><xref:System.Xml.Linq.XText> represents a text node.</span></span> <span data-ttu-id="b6845-163">Ve většině případů není nutné k použití této třídy.</span><span class="sxs-lookup"><span data-stu-id="b6845-163">In most cases, you do not have to use this class.</span></span> <span data-ttu-id="b6845-164">Tato třída se používá hlavně pro smíšený obsah.</span><span class="sxs-lookup"><span data-stu-id="b6845-164">This class is primarily used for mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6845-165">Viz také</span><span class="sxs-lookup"><span data-stu-id="b6845-165">See Also</span></span>  
 [<span data-ttu-id="b6845-166">Technologie LINQ to XML přehled programování (C#)</span><span class="sxs-lookup"><span data-stu-id="b6845-166">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)