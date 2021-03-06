---
title: 'Výjimky: Funkce raise'
description: Zjistěte, jak F# "vyvolat" funkce se používá k označení, že došlo k chybě nebo výjimečné podmínce.
ms.date: 05/16/2016
ms.openlocfilehash: 87773ead7773c62a325c7e7ff105c729e10dd69c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610148"
---
# <a name="exceptions-the-raise-function"></a>Výjimky: Funkce raise

`raise` Funkce se používá k označení, že došlo k chybě nebo výjimečné podmínce. Informace o této chybě je zachycena v objektu výjimky.

## <a name="syntax"></a>Syntaxe

```fsharp
raise (expression)
```

## <a name="remarks"></a>Poznámky

`raise` Funkce vytvoří objekt výjimky a zahájí proces odvíjení zásobníku. Procesu odvíjení zásobníku je spravován modulem common language runtime (CLR), takže chování tohoto procesu je stejný, jako je v kterémkoli jazyce platformy .NET. Procesu odvíjení zásobníku je hledání pro obslužnou rutinu výjimky, která odpovídá generované výjimky. Hledání se spustí v aktuálním `try...with` výrazu, pokud existuje. Každý vzor v `with` bloku je zaškrtnuto, v pořadí. Když je nalezena odpovídající obslužná rutina výjimky, bude výjimka považována zpracovat; v opačném případě je zásobník odvinut a `with` bloky řetězem volání jsou kontrolovány, dokud není nalezena odpovídající obslužná rutina. Žádné `finally` bloky, které se vyskytují v řetězu volání jsou také provést postupně, protože unwinds zásobníku.

`raise` Funkce je obdobou `throw` v jazyce C# nebo C++. Použití `reraise` v rozšíření stejná výjimka řetězem volání obslužné rutiny catch.

Následující příklady kódu znázorňují použití `raise` funkce generují výjimku.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

`raise` Funkce také umožňuje vyvolávat výjimky .NET, jak je znázorněno v následujícím příkladu.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a>Viz také:

- [Zpracování výjimek](index.md)
- [Typy výjimek](exception-types.md)
- [Výjimky: `try...with` Výraz](the-try-with-expression.md)
- [Výjimky: `try...finally` Výraz](the-try-finally-expression.md)
- [Výjimky: `failwith` – Funkce](the-failwith-function.md)
- [Výjimky: `invalidArg` – Funkce](the-invalidArg-function.md)