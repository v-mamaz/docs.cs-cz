---
title: Byl vytvořen odkaz na vložené definiční sestavení '<assembly1>' z důvodu nepřímého odkazu na toto sestavení ze sestavení '<assembly2>'.
ms.date: 07/20/2015
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
ms.openlocfilehash: 058aa4891d05147756290affd60ea5fb260c33ef
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262949"
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-assembly1-because-of-an-indirect-reference-to-that-assembly-from-assembly-assembly2"></a>Vytvořil se odkaz na vložené definiční sestavení "\<assembly1 >" z důvodu nepřímého odkazu na toto sestavení ze sestavení '\<assembly2 > "
Vytvořil se odkaz na vložené definiční sestavení "\<assembly1 >" z důvodu nepřímého odkazu na toto sestavení ze sestavení '\<assembly2 > ". Zvažte změnu vlastnosti 'Vložit typy spolupráce' u obou sestavení.  
  
 Přidáte odkaz na sestavení (assembly1), který má `Embed Interop Types` nastavenou na `True`. Toto dá pokyn kompilátoru k vložení typu spolupráce informace z tohoto sestavení. Kompilátor však nelze vložit informace o typu spolupráce ze sestavení, protože jiné sestavení, které se vám (assembly2) také odkazuje na sestavení (assembly1) a má `Embed Interop Types` nastavenou na `False`.  
  
> [!NOTE]
>  Nastavení `Embed Interop Types` vlastnost na odkaz na sestavení do `True` je ekvivalentní k odkazování na sestavení s použitím `/link` – možnost kompilátoru příkazového řádku.  
  
 **ID chyby:** BC40059  
  
### <a name="to-address-this-warning"></a>Chcete-li vyřešit tato upozornění  
  
-   Chcete-li vložit informace o typu spolupráce u obou sestavení, nastavte `Embed Interop Types` vlastnost u všech odkazů na assembly1 na `True`.  
  
-   Chcete-li odebrat upozornění, můžete nastavit `Embed Interop Types` vlastnost assembly1 na `False`. Informace o typu spolupráce v tomto případě poskytuje primární definiční sestavení (PIA).  
  
## <a name="see-also"></a>Viz také:
- [/ Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)
- [Spolupráce s nespravovaným kódem](../../../framework/interop/index.md)
