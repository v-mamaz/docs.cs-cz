---
title: -win32res (možnosti kompilátoru C#)
ms.date: 07/20/2015
f1_keywords:
- /win32res
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
ms.openlocfilehash: 522d80ce6be277c048fa62cc1a7b077d8bb08bfe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544699"
---
# <a name="-win32res-c-compiler-options"></a>-win32res (možnosti kompilátoru C#)
**-Win32res** možnost vloží prostředek systému Win32 do výstupního souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Soubor prostředků, kterou chcete přidat do výstupního souboru.  
  
## <a name="remarks"></a>Poznámky  
 Soubor prostředků Win32 lze vytvořit pomocí [Resource Compiler](../../language-reference/compiler-options/resource-compiler-option.md). Nástroj Resource Compiler je vyvolán při kompilaci programu Visual C++; soubor .res je vytvořen ze souboru .rc.  
  
 Prostředek systému Win32 mohou obsahovat verzi nebo rastrový obrázek (ikona) informace, které by pomohl identifikovat aplikace v Průzkumníkovi souborů. Pokud nezadáte **-win32res**, bude kompilátor generovat informace o verzi na základě verze sestavení.  
  
 Zobrazit [- linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (na odkaz) nebo [– prostředků](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (pro připojení) soubor prostředků rozhraní .NET Framework.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Nastavení tohoto parametru kompilátoru ve vývojovém prostředí Visual Studio  
  
1.  Otevřete v projektu **vlastnosti** stránky.  
  
2.  Klikněte na tlačítko **aplikace** stránku vlastností.  
  
3.  Klikněte na **soubor prostředků** tlačítko a vyberte soubor s použitím pole se seznamem.  
  
## <a name="example"></a>Příklad  
 Kompilace `in.cs` a připojte soubor prostředků Win32 `rf.res` k vytvoření `in.exe`:  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a>Viz také:

- [Možnosti kompilátoru jazyka C#](../../../csharp/language-reference/compiler-options/index.md)
- [Správa vlastností projektů a řešení](/visualstudio/ide/managing-project-and-solution-properties)
