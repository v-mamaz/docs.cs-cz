---
title: 'Postupy: Analýze řetězce (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 513a82cbed796be42eb8e531ec71221ef0ac267f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652446"
---
# <a name="how-to-parse-a-string-visual-basic"></a>Postupy: Analýze řetězce (Visual Basic)
Toto téma ukazuje, jak vytvořit stromu XML v C#.  
  
## <a name="example"></a>Příklad  
 Řetězec v jazyce Visual Basic můžete analyzovat pomocí `XElement.Parse` metody. Je však efektivnější použijte literály XML, jak je znázorněno v následujícím kódu, protože není literály XML mají stejný snížení výkonu jako analýza kódu XML z řetězce.  
  
 Pomocí literálů XML můžete stačí zkopírovat a vložit soubor XML do programu Visual Basic.  
  
> [!NOTE]
>  Analýza textu nebo načítání dokumentu XML z textového souboru je méně efektivní než funkční konstrukce. Pokud se inicializace stromu XML z kódu, trvá méně času procesoru použít funkční konstrukce, než se analyzovat text.  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a>Viz také:
- [Analýza kódu XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
