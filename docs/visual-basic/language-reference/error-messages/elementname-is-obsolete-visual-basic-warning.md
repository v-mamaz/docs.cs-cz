---
title: Element '<elementname>' je zastaralý (upozornění jazyka Visual Basic).
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: c6d927ef6681838d8a77a0c6018eb6bbe30913e8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255858"
---
# <a name="elementname-is-obsolete-visual-basic-warning"></a>"\<elementname >' je zastaralý (upozornění jazyka Visual Basic)
Příkaz se pokusí o přístup k programový element, která byla označena atributem <xref:System.ObsoleteAttribute> atribut a směrnice s ní zacházet jako upozornění.  
  
 Můžete označit libovolný programovací element jako se už používá použitím <xref:System.ObsoleteAttribute> k němu. Pokud to uděláte, můžete nastavit atributu <xref:System.ObsoleteAttribute.IsError%2A> vlastnost buď `True` nebo `False`. Pokud ji nastavíte na `True`, kompilátor zpracovává pokus o použití prvku za chybu. Pokud ji nastavíte na `False`, nebo jej jako výchozí `False`, kompilátor vyvolá upozornění, pokud se pokus o použití elementu.  
  
 Ve výchozím nastavení, je tato zpráva upozornění, protože <xref:System.ObsoleteAttribute.IsError%2A> vlastnost <xref:System.ObsoleteAttribute> je `False`. Další informace o zobrazení nebo skrytí upozornění zpracování upozornění jako chyby, najdete v části [Konfigurace upozornění v jazyce Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID chyby:** BC40008  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Ujistěte se, že odkaz zdrojového kódu je správně kontroly pravopisu název elementu.  
  
## <a name="see-also"></a>Viz také:
- [Přehled atributy](../../../visual-basic/programming-guide/concepts/attributes/index.md)
