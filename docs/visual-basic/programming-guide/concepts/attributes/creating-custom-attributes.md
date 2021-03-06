---
title: Vytváření vlastních atributů (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: 4bc60e20d163c6aec231152940f548fcb58442f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526350"
---
# <a name="creating-custom-attributes-visual-basic"></a>Vytváření vlastních atributů (Visual Basic)
Můžete vytvořit vlastní atributy definováním třídy atributu, třídu, která je odvozena přímo nebo nepřímo z <xref:System.Attribute>, díky kterému budou Identifikace definice atributu v metadatech rychlé a snadné. Předpokládejme, že chcete typy značek s názvem programátora, který napsal typu. Můžete třeba definovat vlastní `Author` třídy atributů:  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
        version = 1.0  
    End Sub  
End Class  
```  
  
 Název třídy je název atributu, `Author`. Je odvozen z `System.Attribute`, tak, aby byl třídu vlastního atributu. Vlastní atribut poziční parametry jsou parametry konstruktoru. V tomto příkladu `name` je poziční parametr. Žádné vlastnosti nebo pole veřejné čtení a zápis jsou pojmenované parametry. V takovém případě `version` je pouze s názvem parametru. Všimněte si použití `AttributeUsage` atribut, aby `Author` atribut je platný pouze pro třídy a `Structure` deklarace.  
  
 Tento nový atribut můžete použít takto:  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 `AttributeUsage` nemá parametr pojmenovaný `AllowMultiple`, pomocí které můžete vytvořit vlastní atribut jedno použití nebo multiuse. V následujícím příkladu kódu je vytvořen multiuse atribut.  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 V následujícím příkladu kódu se více atributů stejného typu aplikován na třídu.  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  Pokud vaše třída atributů obsahuje vlastnost, musí být tuto vlastnost pro čtení i zápis.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Reflection>
- [Průvodce programováním v jazyce Visual Basic](../../../../visual-basic/programming-guide/index.md)
- [Zápis vlastních atributů](../../../../standard/attributes/writing-custom-attributes.md)
- [Reflexe (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [Atributy (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)
- [Přístup k atributům pomocí reflexe (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
- [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
