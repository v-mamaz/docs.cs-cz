---
title: 'Postupy: Vyhledání uzlů na stejné úrovni (XPath – LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 73082738-2113-4438-8545-98d5df0927cb
ms.openlocfilehash: 740123077c24dd27fe1a4810d0cb45c4775894aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622634"
---
# <a name="how-to-find-sibling-nodes-xpath-linq-to-xml-visual-basic"></a>Postupy: Vyhledání uzlů na stejné úrovni (XPath – LINQ to XML) (Visual Basic)
Můžete chtít najít všechny na stejné úrovni uzlu, které mají určitý název. Výsledný kolekce může zahrnovat kontextu uzlu, pokud kontextový uzel nemá taky určitý název.  
  
 Výraz XPath je:  
  
 `../Book`  
  
## <a name="example"></a>Příklad  
 V tomto příkladu nejdříve vyhledá `Book` elementu a najde všechny prvky na stejné úrovni s názvem `Book`. Výsledný kolekce obsahuje uzel kontextu.  
  
 Tento příklad používá následujícího dokumentu XML: [Ukázkový soubor XML: Knihy (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim book As XElement = books.Root.<Book>.Skip(1).First()  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = book.Parent.<Book>  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = book.XPathSelectElements("../Book")  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Tento příklad vytvoří následující výstup:  
  
```  
Results are identical  
<Book id="bk101">  
  <Author>Garghentini, Davide</Author>  
  <Title>XML Developer's Guide</Title>  
  <Genre>Computer</Genre>  
  <Price>44.95</Price>  
  <PublishDate>2000-10-01</PublishDate>  
  <Description>An in-depth look at creating applications   
      with XML.</Description>  
</Book>  
<Book id="bk102">  
  <Author>Garcia, Debra</Author>  
  <Title>Midnight Rain</Title>  
  <Genre>Fantasy</Genre>  
  <Price>5.95</Price>  
  <PublishDate>2000-12-16</PublishDate>  
  <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
</Book>  
```  
  
## <a name="see-also"></a>Viz také:
- [LINQ to XML pro uživatele jazyka XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
