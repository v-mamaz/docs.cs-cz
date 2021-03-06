---
title: objekt – C# odkaz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
ms.openlocfilehash: a1917a7925d4ed90ede40248fa394f9c45d09b4e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238962"
---
# <a name="object-c-reference"></a>object (Referenční dokumentace jazyka C#)

`object` Typ je alias pro <xref:System.Object> v rozhraní .NET. V systému unified typů jazyka C#, všechny typy, typy odkazů předdefinovaných a definovaný uživatelem, a typů hodnot, dědí přímo nebo nepřímo <xref:System.Object>. Můžete přiřadit proměnné typu hodnoty libovolného typu `object`. Když je proměnné typu hodnoty převeden na objekt, je označen jako *boxed*. Pokud proměnnou typu objektu je převeden na typ hodnoty, je označen jako *nezabalené*. Další informace najdete v tématu [zabalení a rozbalení](../../../csharp/programming-guide/types/boxing-and-unboxing.md).

## <a name="example"></a>Příklad

Následující ukázkový ukazuje, jak proměnné typu `object` může přijmout hodnoty libovolného typu dat a jak proměnné typu `object` můžete použít metody na <xref:System.Object> z rozhraní .NET Framework.

[!code-csharp[csrefKeywordsTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#16)]

## <a name="c-language-specification"></a>specifikace jazyka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Viz také:

- [Referenční dokumentace jazyka C#](../index.md)
- [Průvodce programováním v jazyce C#](../../programming-guide/index.md)
- [Klíčová slova jazyka C#](index.md)
- [Odkazové typy](reference-types.md)
- [Typy hodnot](value-types.md)