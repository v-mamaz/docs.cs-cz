---
title: 'Postupy: Dotazu na Metadata sestavení s reflexí (LINQ) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 53caa336-ab83-4181-b0f6-5c87c5f9e4ee
ms.openlocfilehash: 7966b85172af48c7762027877a03b12dd6e2b62d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255156"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-visual-basic"></a>Postupy: Dotazu na Metadata sestavení s reflexí (LINQ) (Visual Basic)
Následující příklad ukazuje, jak LINQ lze pomocí reflexe k načtení metadat konkrétní metody, které odpovídají zadanému vyhledávacímu kritériu. Dotaz v tomto případě se vyhledat názvy všechny metody v sestavení, které vrací vyčíslitelné typy například pole.  
  
## <a name="example"></a>Příklad  
  
```vb  
Imports System.Reflection  
Imports System.IO  
Imports System.Linq  
Module Module1  
  
    Sub Main()  
        Dim asmbly As Assembly =   
            Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089")  
  
        Dim pubTypesQuery = From type In asmbly.GetTypes()   
                            Where type.IsPublic   
                            From method In type.GetMethods()   
                            Where method.ReturnType.IsArray = True   
                            Let name = method.ToString()   
                            Let typeName = type.ToString()   
                            Group name By typeName Into methodNames = Group  
  
        Console.WriteLine("Getting ready to iterate")  
        For Each item In pubTypesQuery  
            Console.WriteLine(item.methodNames)  
  
            For Each type In item.methodNames  
                Console.WriteLine(" " & type)  
            Next  
        Next  
        Console.ReadKey()  
    End Sub  
  
End Module  
```  
  
 V příkladu se používá <xref:System.Reflection.Assembly.GetTypes%2A> metoda vrátí pole typů v zadaném sestavení. [Klauzule Where](../../../../visual-basic/language-reference/queries/where-clause.md) filtr tak, aby se vrátí pouze veřejné typy. Pro každý veřejný typ poddotaz je generována pomocí <xref:System.Reflection.MethodInfo> pole, která je vrácena z <xref:System.Type.GetMethods%2A> volání. Tyto výsledky se filtrují pro vrácení pouze těch metod, jehož návratový typ je pole, jinak se typ, který implementuje <xref:System.Collections.Generic.IEnumerable%601>. A konečně jsou tyto výsledky seskupené podle pomocí názvu typu jako klíč.  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Vytvořit projekt, který cílí na rozhraní .NET Framework verze 3.5 nebo vyšší s odkazem na knihovnu System.Core.dll a `Imports` příkaz pro obor názvů System.Linq.  
  
## <a name="see-also"></a>Viz také:
- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
