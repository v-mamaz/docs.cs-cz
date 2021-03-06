---
title: Yield – příkaz (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: 15cfe48797066986f5c4679e85d5899230c516e9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484950"
---
# <a name="yield-statement-visual-basic"></a>Yield – příkaz (Visual Basic)
Další prvek kolekce, která se odešle `For Each...Next` příkazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Yield expression  
```  
  
## <a name="parameters"></a>Parametry  
  
|Termín|Definice|  
|---|---|  
|`expression`|Povinný parametr. Výraz, který je implicitně převést na typ funkce iterátoru nebo `Get` přístupový objekt, který obsahuje `Yield` příkazu.|  
  
## <a name="remarks"></a>Poznámky  
 `Yield` Příkaz vrátí jeden element v kolekci najednou. `Yield` Příkazu je součástí funkce iterátoru nebo `Get` přístupový objekt, který provedení vlastní iterace nad kolekcí.  
  
 Funkce iterátoru spotřebujete pomocí [For Each... Další příkaz](../../../visual-basic/language-reference/statements/for-each-next-statement.md) nebo dotazu LINQ. Každá iterace `For Each` smyčky volání funkce iterátoru. Když `Yield` je ve funkci iterátoru dosažen příkaz `expression` dochází, a je zachováno aktuální umístění v kódu. Provádění je restartováno ze zmíněného umístění pokaždé, když je zavolána funkce iterátoru.  
  
 Musí existovat implicitní převod z typu `expression` v `Yield` příkaz a návratový typ iterátoru.  
  
 Můžete použít `Exit Function` nebo `Return` příkaz do konce iterace.  
  
 "Yield" není vyhrazené slovo a má zvláštní význam pouze v případě, že se používá `Iterator` funkce nebo `Get` přistupující objekt.  
  
 Další informace o funkcích iterátoru a `Get` přístupové objekty, najdete v článku [iterátory](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Funkce iterátorů a přístupové objekty Get  
 Deklarace funkce iterátoru nebo `Get` přístupový objekt, musí splňovat následující požadavky:  
  
-   Musí obsahovat [iterátoru](../../../visual-basic/language-reference/modifiers/iterator.md) modifikátor.  
  
-   Návratový typ musí být <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, nebo <xref:System.Collections.Generic.IEnumerator%601>.  
  
-   Nesmí obsahovat žádné `ByRef` parametry.  
  
 Funkce iterátoru nelze provést v událost, konstruktor instance, statického konstruktoru nebo destruktoru statické.  
  
 Funkce iterátoru, může být anonymní funkce. Další informace najdete v tématu [iterátory](../../programming-guide/concepts/iterators.md).  
  
## <a name="exception-handling"></a>Zpracování výjimek  
 A `Yield` příkaz může být v rámci `Try` bloku [zkuste... Catch... Příkaz finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). A `Try` blok, který má `Yield` může mít příkaz `Catch` a ostatní porty blokuje může mít `Finally` bloku.  
  
 A `Yield` příkaz nejde provést uvnitř `Catch` bloku nebo `Finally` bloku.  
  
 Pokud `For Each` text (mimo funkce iterátoru) vyvolá výjimku, `Catch` bloku funkce iterátoru není spuštěn, ale `Finally` je proveden blok v funkce iterátoru. A `Catch` bloku funkce iterátoru zachytává pouze výjimky, ke kterým dochází uvnitř funkce iterátoru.  
  
## <a name="technical-implementation"></a>Technická implementace  
 V následujícím kódu vrátí `IEnumerable (Of String)` z funkce iterátoru a poté iteruje skrz prvky `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 Volání `MyIteratorFunction` neprovede tělo funkce. Místo toho volání vrátí `IEnumerable(Of String)` do `elements` proměnné.  
  
 Při iteraci `For Each` smyčky, <xref:System.Collections.IEnumerator.MoveNext%2A> metoda je volána pro `elements`. Toto volání provádí tělo `MyIteratorFunction` až do další `Yield` je dosažen příkaz. `Yield` Příkaz vrátí výraz, který určuje nejen hodnotu `element` proměnné k využití v těle smyčky, ale také <xref:System.Collections.Generic.IEnumerator%601.Current%2A> vlastnosti prvků, který je `IEnumerable (Of String)`.  
  
 Na každé další iteraci `For Each` smyčky, tělo iterátoru pokračuje odkud zastaví se opět tehdy, když se dosáhne `Yield` příkazu. `For Each` Smyčky je dokončen, když na konec funkce iterátoru nebo `Return` nebo `Exit Function` je dosažen příkaz.  
  
## <a name="example"></a>Příklad  
 Následující příklad obsahuje `Yield` , který se nachází uvnitř [pro... Další](../../../visual-basic/language-reference/statements/for-next-statement.md) smyčky. Každá iterace [pro každou](../../../visual-basic/language-reference/statements/for-each-next-statement.md) tělo s příkazy v `Main` vytváří volání `Power` funkce iterátoru. Každé volání funkce iterátoru pokračuje do dalšího provedení příkazu `Yield` prohlášení, které nastane při další iteraci `For…Next` smyčky.  
  
 Návratový typ metody iterátoru je <xref:System.Collections.Generic.IEnumerable%601>, typ rozhraní iterátoru. Při volání metody iterátoru je vrácen vyčíslitelný objekt, který obsahuje mocniny čísla.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje `Get` přístupovou metodu iterátoru. Deklarace vlastnosti zahrnuje `Iterator` modifikátor.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Další příklady najdete v tématu [iterátory](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Viz také:
- [Příkazy](../../../visual-basic/language-reference/statements/index.md)
