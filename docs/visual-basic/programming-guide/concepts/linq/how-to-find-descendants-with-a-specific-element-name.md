---
title: 'Postupy: Vyhledání potomků s konkrétním názvem elementu (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 78915518-0d25-4051-ab55-929779989510
ms.openlocfilehash: 4311eb0a4062c01b2c8e1c19355c5284298e39dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557156"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-visual-basic"></a>Postupy: Vyhledání potomků s konkrétním názvem elementu (Visual Basic)
Někdy budete chtít vyhledání všech potomků s konkrétním názvem. Můžete napsat kód k iteraci v rámci všechny následníky, ale je jednodušší použít <xref:System.Xml.Linq.XContainer.Descendants%2A> osy.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak vyhledání potomků vycházet z názvu elementu.  
  
```vb  
Dim root As XElement = _  
    <root>  
        <para>  
            <r>  
                <t>Some text </t>  
            </r>  
            <n>  
                <r>  
                    <t>that is broken up into </t>  
                </r>  
            </n>  
            <n>  
                <r>  
                    <t>multiple segments.</t>  
                </r>  
            </n>  
        </para>  
    </root>  
  
Dim textSegs As IEnumerable(Of String) = _  
    From seg In root...<t> _  
    Select seg.Value  
  
Dim str As String = textSegs.Aggregate( _  
    New StringBuilder, _  
    Function(sb, i) sb.Append(i), _  
    Function(sb) sb.ToString)  
  
Console.WriteLine(str)  
```  
  
 Tento kód vytvoří následující výstup:  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje stejný dotaz pro soubor XML, který je v oboru názvů. Další informace najdete v tématu [práce s názvovými prostory XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <root>  
                <para>  
                    <r>  
                        <t>Some text </t>  
                    </r>  
                    <n>  
                        <r>  
                            <t>that is broken up into </t>  
                        </r>  
                    </n>  
                    <n>  
                        <r>  
                            <t>multiple segments.</t>  
                        </r>  
                    </n>  
                </para>  
            </root>  
  
        Dim textSegs As IEnumerable(Of String) = _  
            From seg In root...<t> _  
            Select seg.Value  
  
        Dim str As String = textSegs.Aggregate( _  
            New StringBuilder, _  
            Function(sb, i) sb.Append(i), _  
            Function(sb) sb.ToString)  
  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 Tento kód vytvoří následující výstup:  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- [Základní dotazy (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
