---
title: "Vytvoření nové atributy pro elementy v modelu DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6970ffc38e900c9b47c58c8ae4b81b9551f5589b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="f657c-102">Vytvoření nové atributy pro elementy v modelu DOM</span><span class="sxs-lookup"><span data-stu-id="f657c-102">Creating New Attributes for Elements in the DOM</span></span>
<span data-ttu-id="f657c-103">Vytvoření nového atributu se liší od vytvoření jiných typů uzlů, protože atributy nejsou uzly, ale jsou vlastnosti uzlu elementu a jsou součástí **XmlAttributeCollection** přidružené k elementu.</span><span class="sxs-lookup"><span data-stu-id="f657c-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="f657c-104">Vytvořte atribut a jeho připojení pro element několika způsoby:</span><span class="sxs-lookup"><span data-stu-id="f657c-104">There are multiple ways to create an attribute and attach it to an element:</span></span>  
  
-   <span data-ttu-id="f657c-105">Získat uzlu elementu a použít **SetAttribute** přidání atributu do atribut kolekce daný element.</span><span class="sxs-lookup"><span data-stu-id="f657c-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>  
  
-   <span data-ttu-id="f657c-106">Vytvoření **XmlAttribute** uzlu pomocí **CreateAttribute** metoda, získat uzel elementu, potom použijte **SetAttributeNode** přidání uzlu do atribut kolekce, element.</span><span class="sxs-lookup"><span data-stu-id="f657c-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>  
  
 <span data-ttu-id="f657c-107">Následující příklad ukazuje, jak přidat atribut k elementu pomocí **SetAttribute** metoda.</span><span class="sxs-lookup"><span data-stu-id="f657c-107">The following example shows how to add an attribute to an element using the **SetAttribute** method.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
public class Sample  
  
  public shared sub Main()  
  
  Dim doc as XmlDocument = new XmlDocument()  
  doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _  
              "<title>Pride And Prejudice</title>" & _  
              "</book>")  
  Dim root as XmlElement = doc.DocumentElement  
  
  'Add a new attribute.  
  root.SetAttribute("genre", "urn:samples", "novel")  
  
  Console.WriteLine("Display the modified XML...")  
  Console.WriteLine(doc.InnerXml)  
  
  end sub  
end class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  public static void Main()  
  {  
    XmlDocument doc = new XmlDocument();  
    doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +  
                "<title>Pride And Prejudice</title>" +  
                "</book>");  
    XmlElement root = doc.DocumentElement;  
  
    // Add a new attribute.  
    root.SetAttribute("genre", "urn:samples", "novel");  
  
    Console.WriteLine("Display the modified XML...");  
    Console.WriteLine(doc.InnerXml);  
  }  
```  
  
 <span data-ttu-id="f657c-108">Následující příklad ukazuje nový atribut vytváří pomocí **CreateAttribute** metoda.</span><span class="sxs-lookup"><span data-stu-id="f657c-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="f657c-109">Se potom zobrazí atribut přidán do atribut kolekce **kniha** element pomocí **SetAttributeNode** metoda.</span><span class="sxs-lookup"><span data-stu-id="f657c-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>  
  
 <span data-ttu-id="f657c-110">Zadané následující kód XML:</span><span class="sxs-lookup"><span data-stu-id="f657c-110">Given the following XML:</span></span>  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="f657c-111">Vytvořte nový atribut a přiřaďte mu hodnotu:</span><span class="sxs-lookup"><span data-stu-id="f657c-111">create a new attribute and give it a value:</span></span>  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 <span data-ttu-id="f657c-112">a připojte ji k prvku:</span><span class="sxs-lookup"><span data-stu-id="f657c-112">and attach it to the element:</span></span>  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 <span data-ttu-id="f657c-113">**Výstup**</span><span class="sxs-lookup"><span data-stu-id="f657c-113">**Output**</span></span>  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="f657c-114">Úplný příklad najdete na <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="f657c-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>  
  
 <span data-ttu-id="f657c-115">Můžete taky vytvořit **XmlAttribute** uzel a použití **InsertBefore** nebo **InsertAfter** metody pro jeho umístění v příslušné pozici v kolekci.</span><span class="sxs-lookup"><span data-stu-id="f657c-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="f657c-116">Pokud atribut se stejným názvem již existuje v kolekci atributů existující **XmlAttribute** uzel je odebrán z kolekce a nové **XmlAttribute** je vložen uzlu.</span><span class="sxs-lookup"><span data-stu-id="f657c-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="f657c-117">Provede stejným způsobem jako **SetAttribute** metoda.</span><span class="sxs-lookup"><span data-stu-id="f657c-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="f657c-118">Tyto metody přijímají jako parametr, stávající uzel jako referenční bod uděláte **InsertBefore** a **InsertAfter**.</span><span class="sxs-lookup"><span data-stu-id="f657c-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="f657c-119">Pokud nezadáte uzlu odkazu, která určuje, kam chcete vložit nový uzel, je výchozí hodnotou **InsertAfter** metodou, je na začátek kolekce vložte nový uzel.</span><span class="sxs-lookup"><span data-stu-id="f657c-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="f657c-120">Výchozí umístění **InsertBefore**, pokud je k dispozici žádný uzel odkazu, je na konec kolekce.</span><span class="sxs-lookup"><span data-stu-id="f657c-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>  
  
 <span data-ttu-id="f657c-121">Pokud jste vytvořili **XmlNamedNodeMap** atributů, můžete přidat atribut pomocí názvu <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="f657c-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span></span> <span data-ttu-id="f657c-122">Další informace najdete v tématu [uzlu kolekce v NamedNodeMaps a NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span><span class="sxs-lookup"><span data-stu-id="f657c-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span></span>  
  
## <a name="default-attributes"></a><span data-ttu-id="f657c-123">Výchozí atributy</span><span class="sxs-lookup"><span data-stu-id="f657c-123">Default Attributes</span></span>  
 <span data-ttu-id="f657c-124">Pokud vytvoříte element, který je deklarován tak, aby měl výchozí atribut, nový výchozí atribut s jeho výchozí hodnota je vytvořen pomocí XML modelu DOM (Document Object) a připojen k elementu.</span><span class="sxs-lookup"><span data-stu-id="f657c-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="f657c-125">V tuto chvíli se také vytvořit podřízené uzly výchozí atribut.</span><span class="sxs-lookup"><span data-stu-id="f657c-125">The child nodes of the default attribute are also created at this time.</span></span>  
  
## <a name="attribute-child-nodes"></a><span data-ttu-id="f657c-126">Atribut podřízené uzly</span><span class="sxs-lookup"><span data-stu-id="f657c-126">Attribute Child Nodes</span></span>  
 <span data-ttu-id="f657c-127">Hodnota uzlu atributu se změní jeho podřízené uzly.</span><span class="sxs-lookup"><span data-stu-id="f657c-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="f657c-128">Existují jenom dva typy platný podřízené uzly: **XmlText** uzly, a **XmlEntityReference** uzlů.</span><span class="sxs-lookup"><span data-stu-id="f657c-128">There are only two types of valid child nodes: **XmlText** nodes, and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="f657c-129">Tyto jsou podřízené uzly v tom smyslu, že tyto metody, jako **hodnotu FirstChild** a **LastChild** zpracovat jako podřízené uzly.</span><span class="sxs-lookup"><span data-stu-id="f657c-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="f657c-130">Tento rozdíl atributu s podřízenými uzly je důležité při pokusu o odebrání atributů nebo atribut podřízené uzly.</span><span class="sxs-lookup"><span data-stu-id="f657c-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="f657c-131">Další informace najdete v tématu [odebrání atributů z uzlu elementu v modelu DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="f657c-131">For more information, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f657c-132">Viz také</span><span class="sxs-lookup"><span data-stu-id="f657c-132">See Also</span></span>  
 [<span data-ttu-id="f657c-133">XML Document Object Model (DOM).</span><span class="sxs-lookup"><span data-stu-id="f657c-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)