---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: fdea071f8c41f2e707d10c96c8b6ab1fbb44bad0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733308"
---
# <a name="-optionstrict"></a>-optionstrict
Vynutí sémantiku přísného typu pro omezení převodů implicitních typů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a>Arguments  
 `+` &#124; `-`  
 Volitelné. `-optionstrict+` Omezí implicitní převod typu. Výchozí hodnota pro tuto možnost je `-optionstrict-`. `-optionstrict+` Možnost je stejný jako `-optionstrict`. Můžete je používat pro typ povolující sémantiku.  
  
 `custom`  
 Povinný parametr. Zobrazit upozornění, pokud není respektována striktní sémantika jazyka.  
  
## <a name="remarks"></a>Poznámky  
 Když `-optionstrict+` platí, pouze rozšiřující převody typu lze implicitně. Implicitní zužující převody typů, jako je například přiřazení `Decimal` zadejte objekt na objekt typu celé číslo, které jsou hlášeny jako chyby.  
  
 Chcete-li generovat upozornění pro implicitní zužující převody typů, použijte `-optionstrict:custom`. Použití `-nowarn:numberlist` ignorovat konkrétní varování a `-warnaserror:numberlist` považovat konkrétní upozornění jako chyby.  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>Chcete-li nastavit - optionstrict v integrovaném vývojovém prostředí sady Visual Studio  
  
1.  Mají projekt vybraný v **Průzkumníka řešení**. Na **projektu** nabídky, klikněte na tlačítko **vlastnosti.**   
  
2.  Klikněte na tlačítko **kompilaci** kartu.  
  
3.  Upravte hodnotu v **Option Strict** pole.  
  
### <a name="to-set--optionstrict-programmatically"></a>Chcete-li nastavit - optionstrict prostřednictvím kódu programu  
  
-   Zobrazit [Option Strict – příkaz](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="example"></a>Příklad  
 Následující kód zkompiluje `Test.vb` pomocí sémantiku přísného typu.  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a>Viz také:
- [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [-warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [Příkazové řádky ukázkové kompilace](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Příkaz Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Výchozí hodnoty pro Visual Basic, Projekty, dialogové okno Možnosti](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
