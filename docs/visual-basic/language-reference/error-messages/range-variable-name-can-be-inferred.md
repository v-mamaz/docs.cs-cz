---
title: Název proměnné rozsahu lze odvodit jen z jednoduchého nebo kvalifikovaného názvu bez argumentů.
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: 8b95bb3c53210cc11966466d32924c13aee8234b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54581934"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>Název proměnné rozsahu lze odvodit jen z jednoduchého nebo kvalifikovaného názvu bez argumentů.
Programový element, který přijímá jeden nebo více argumentů je zahrnutý v dotazu LINQ. Kompilátor nedokáže odvodit proměnnou rozsahu z této programovací element.  
  
 **ID chyby:** BC36599  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Zadejte explicitní název proměnné pro programový element, jak je znázorněno v následujícím kódu:  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a>Viz také:
- [Úvod do LINQ v JAZYKU Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Klauzule Select](../../../visual-basic/language-reference/queries/select-clause.md)
