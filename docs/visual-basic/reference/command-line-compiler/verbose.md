---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 7a5dd305d1cc40e57d0f07f383151dc1a965bdda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513916"
---
# <a name="-verbose"></a>-verbose
Způsobí, že kompilátor vytvoří podrobné zprávy o stavu a chyba.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Arguments  
 `+` &#124; `-`  
 Volitelné. Určení `-verbose` je stejné jako zadání `-verbose+`, což způsobí, že kompilátor generuje podrobné zprávy. Výchozí hodnota pro tuto možnost je `-verbose-`.  
  
## <a name="remarks"></a>Poznámky  
 `-verbose` Možnost zobrazí informace o celkový počet chyb, které jsou vydány kompilátorem, sestavy, která sestavení jsou načítány modulem a zobrazí soubory, které jsou aktuálně kompilován.  
  
> [!NOTE]
>  `-verbose` Možnost není k dispozici v rámci vývojového prostředí sady Visual Studio; je k dispozici jenom při kompilaci z příkazového řádku.  
  
## <a name="example"></a>Příklad  
 Následující kód zkompiluje `In.vb` a instruuje kompilátor, aby zobrazení podrobné stavové informace.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>Viz také:
- [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Příkazové řádky ukázkové kompilace](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
