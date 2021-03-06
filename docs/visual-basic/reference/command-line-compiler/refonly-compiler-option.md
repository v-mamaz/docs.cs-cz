---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 047b8b148e616c8ad94f55844f8bc4063a9e5cd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528924"
---
# <a name="-refonly-visual-basic"></a>-refout (Visual Basic)

**- Refout** možnost znamená, že primární výstup tohoto sestavení by měl být referenční sestavení místo sestavení implementace. `-refonly` Parametr tiše zakáže generování souborů pdb, jako referenční sestavení nelze spustit.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Syntaxe

```console
-refonly
```

## <a name="remarks"></a>Poznámky

Visual Basic podporuje `-refout` přepnout od verze 15.3.

Referenční sestavení jsou pouze metadata sestavení, která obsahují metadata, ale žádný implementační kód. Patří mezi ně typů a členů informace pro všechno, co s výjimkou anonymních typů. Důvod pro použití `throw null` subjektů (na rozdíl od bez těla) je tak, aby PEVerify může spuštění a předání (tedy ověřování úplnost metadata).

Zahrnout odkaz na sestavení úrovni sestavení [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) atribut. Tento atribut může být zadaný ve zdroji (a kompilátor nebude nutné tak, aby odpovídaly ho). Z důvodu tohoto atributu moduly runtime odmítne načíst referenční sestavení pro spuštění (ale stále může být načteny v kontextu pouze pro reflexi). Nástroje, které odpovídají na sestavení se muset ujistit, že se načítají referenční sestavení jako pouze pro reflexi; v opačném případě modul runtime vyvolá <xref:System.BadImageFormatException>.

`-refonly` a [ `-refout` ](refout-compiler-option.md) možnosti se vzájemně vylučují.

## <a name="see-also"></a>Viz také:
- [-refout](refout-compiler-option.md)
- [Visual Basic Command-Line Compiler](index.md)
- [Příkazové řádky ukázkové kompilace](sample-compilation-command-lines.md)
