---
title: 'Postupy: Načtení kolekce atributů (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a07e9645-b45b-403b-b698-f652f904c7d2
ms.openlocfilehash: 691ec9edda6051ba1f598891dfb9331b85ceb278
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716609"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-visual-basic"></a>Postupy: Načtení kolekce atributů (LINQ to XML) (Visual Basic)
Toto téma představuje <xref:System.Xml.Linq.XElement.Attributes%2A> metody. Tato metoda načte atributy elementu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak k iteraci v rámci kolekce atributů elementu.  
  
```vb  
Dim val = _  
    <Value ID="1243" Type="int" ConvertableTo="double">100</Value>  
Dim listOfAttributes As IEnumerable(Of XAttribute) = _  
    From att In val.Attributes() _  
    Select att  
For Each att As XAttribute In listOfAttributes  
    Console.WriteLine(att)  
Next  
```  
  
 Tento kód vytvoří následující výstup:  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>Viz také:
- [Osy LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
