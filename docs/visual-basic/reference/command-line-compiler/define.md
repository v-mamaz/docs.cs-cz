---
title: -definovat (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: c21223cc353b7a4614511aa97340c6bc5d61e70e
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200651"
---
# <a name="-define-visual-basic"></a>-definovat (Visual Basic)
Definuje podmíněné konstanty kompilátoru.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Arguments  
  
|Termín|Definice|  
|---|---|  
|`symbol`|Povinný parametr. Symbol definovat.|  
|`value`|Volitelné. Hodnota pro přiřazení `symbol`. Pokud `value` je řetězec, musí být uzavřen v pořadí zpětné lomítko a znak uvozovek (\\") místo uvozovek. Pokud není zadána žádná hodnota, pak je provedena na hodnotu True.|  
  
## <a name="remarks"></a>Poznámky  
 `-define` Možnost má efekt se používá podobně jako `#Const` direktivy preprocesoru ve zdrojovém souboru, s výjimkou této konstanty definované pomocí `-define` jsou veřejné a použít na všechny soubory v projektu.  
  
 Symboly, které jsou vytvořené pomocí této možnosti se můžete `#If`... `Then`... `#Else` direktivy podmíněné kompilace zdrojové soubory.  
  
 `-d` je zkratka pro `-define`.  
  
 Můžete definovat více symbolů se `-define` s použitím čárky k oddělení definice symbolů.  
  
|Chcete-li nastavit / define v integrovaném vývojovém prostředí sady Visual Studio|  
|---|  
|1.  Mají projekt vybraný v **Průzkumníka řešení**. Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. <br />2.  Klikněte na tlačítko **kompilaci** kartu.<br />3.  Klikněte na tlačítko **Advanced**.<br />4.  Upravte hodnotu v **konstanty vlastní** pole.|  
  
## <a name="example"></a>Příklad  
 Následující kód definuje a pak používá dva podmíněné konstanty kompilátoru.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>Viz také:
- [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Direktivy #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Direktiva #Const](../../../visual-basic/language-reference/directives/const-directive.md)
- [Příkazové řádky ukázkové kompilace](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
