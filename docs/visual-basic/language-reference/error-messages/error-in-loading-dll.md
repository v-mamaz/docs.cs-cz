---
title: Chyba při načítání knihovny DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 76a0a443fd9f8a6dec5ead24bc75c97d89d6c36b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518459"
---
# <a name="error-in-loading-dll-visual-basic"></a>Chyba při načítání knihovny DLL (Visual Basic)
Dynamická knihovna (DLL) je knihovna podle `Lib` klauzuli `Declare` příkazu. Možné příčiny této chyby patří:  
  
-   Soubor není spustitelný soubor knihovny DLL.  
  
-   Soubor není knihovny DLL Microsoft Windows.  
  
-   Knihovnu DLL odkazuje na jiné knihovně DLL, která není k dispozici.  
  
-   Knihovna DLL nebo odkazované knihovny DLL není v adresáři uvedeném na cestu.  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Pokud je soubor zdroj textového souboru a proto není spustitelný soubor knihovny DLL, musí být zkompilovány a propojeny s DLL spustitelný soubor formuláře.  
  
-   Pokud soubor není knihovny DLL Microsoft Windows, získáte odpovídající Microsoft Windows.  
  
-   Pokud je knihovna DLL odkazuje na jiné knihovně DLL, která není k dispozici, získejte odkazované knihovny DLL a ji dejte k dispozici.  
  
-   Pokud knihovna DLL nebo odkazované knihovny DLL není v adresáři zadané cesty, přesune odkazovaný adresáře knihovny DLL.  
  
## <a name="see-also"></a>Viz také:
- [Příkaz Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
