---
title: Není připojena myš
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: c0e4e2a8cb0aa641b179d8b2608af384d7d4181e
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "58044641"
---
# <a name="no-mouse-is-present"></a>Není připojena myš
Jedna z vlastností objektu `My.Computer.Mouse` byla volána objektu, ale počítač nemá žádné myši a portem myši nainstalované.  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Přidat `Try...Catch` blok po volání na vlastnost `My.Computer.Mouse` objektu.  
  
     – nebo –  
  
-   Nainstalujte do počítače myši.  
  
## <a name="see-also"></a>Viz také:

- [My.Computer.Mouse](xref:Microsoft.VisualBasic.Devices.Mouse)
- [Zpracování a vyvolání výjimek v rozhraní .NET](../../standard/exceptions/index.md)
- [Příkaz Try...Catch...Finally](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
