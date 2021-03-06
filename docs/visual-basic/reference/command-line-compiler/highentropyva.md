---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 546b563276e0db4ee2472ef325d09fd337a62513
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638753"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
Označuje, zda spustitelný soubor 64-bit nebo spustitelný soubor, který je označen [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) – možnost kompilátoru podporuje vysokou entropie adresu místo rozložení náhodné (ASLR).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Arguments  
 `+` &#124; `-`  
 Volitelné. Možnost je vypnuto ve výchozím nastavení nebo pokud zadáte `-highentropyva-`. Možnost zapnutá, pokud zadáte `-highentropyva` nebo `-highentropyva+`.  
  
## <a name="remarks"></a>Poznámky  
 Pokud zadáte tuto možnost, kompatibilní verze jádra Windows můžete použít vyšší stupeň entropie při jádra náhodně rozložení prostoru adres procesu určí jako součást technologie ASLR. Pokud jádru používá vyšší stupeň entropie, větší počet adres je možné přidělit paměti oblastech, jako je zásobníky a haldy. V důsledku toho je obtížnější uhádnout umístění konkrétní paměťové oblasti.  
  
 Při možnost je pro cílový spustitelný soubor a všechny moduly, na které závisí musí být schopná zpracovat hodnoty ukazatele, které jsou větší než 4 gigabajty (GB), pokud tyto moduly spuštěné jako 64bitové procesy.  
  
## <a name="see-also"></a>Viz také:
- [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Příkazové řádky ukázkové kompilace](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
