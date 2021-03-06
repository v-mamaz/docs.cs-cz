---
title: -win32icon (možnosti kompilátoru C#)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: e4558084357c8ce07004a8ed71aef586a707f1a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591744"
---
# <a name="-win32icon-c-compiler-options"></a>-win32icon (možnosti kompilátoru C#)
**-Win32icon** možnost vloží soubor .ico do výstupního souboru, který dává výstupnímu souboru požadovaný vzhled v Průzkumníku souborů.  
  
## <a name="syntax"></a>Syntaxe  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Soubor .ico, který chcete přidat do výstupního souboru.  
  
## <a name="remarks"></a>Poznámky  
 Soubor .ico, který lze vytvořit pomocí [Resource Compiler](/windows/desktop/menurc/resource-compiler). Nástroj Resource Compiler je vyvolán při kompilaci programu v jazyce Visual C++; soubor .ico je vytvořen ze souboru .rc.  
  
 Zobrazit [- linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (na odkaz) nebo [– prostředků](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (pro připojení) soubor prostředků rozhraní .NET Framework. Zobrazit [-win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) importovat soubor .res.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Nastavení tohoto parametru kompilátoru ve vývojovém prostředí Visual Studio  
  
1.  Otevřete v projektu **vlastnosti** stránky.  
  
2.  Klikněte na tlačítko **aplikace** stránku vlastností.  
  
3.  Upravit **ikona aplikace** vlastnost.  
  
 Informace o tom, jak prostřednictvím kódu programu nastavení tohoto parametru kompilátoru najdete v tématu <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.  
  
## <a name="example"></a>Příklad  
 Kompilace `in.cs` a připojte soubor .ico `rf.ico` k vytvoření `in.exe`:  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a>Viz také:

- [Možnosti kompilátoru jazyka C#](../../../csharp/language-reference/compiler-options/index.md)
- [Správa vlastností projektů a řešení](/visualstudio/ide/managing-project-and-solution-properties)
