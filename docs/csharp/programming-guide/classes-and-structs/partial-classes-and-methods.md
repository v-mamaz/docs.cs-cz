---
title: Částečné třídy a metody - C# Průvodce programováním
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: 7e91d77393c4d2980cce73a92589b752124e8077
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965199"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a>Částečné třídy a metody (Průvodce programováním v C#)
Je možné rozdělit definici [třídy](../../../csharp/language-reference/keywords/class.md), [struktura](../../../csharp/language-reference/keywords/struct.md), [rozhraní](../../../csharp/language-reference/keywords/interface.md) nebo metoda přes dvě nebo více zdrojových souborů. Každý zdrojový soubor obsahuje část definice typu nebo metodě a všechny části spolu při kompilaci aplikace.  
  
## <a name="partial-classes"></a>Částečné třídy  
 Při rozdělování definici třídy je žádoucí, existuje několik situací:  
  
-   Při práci na velkých projektech, rozdělit třídu samostatné soubory umožňuje více programátorům s ní pracují ve stejnou dobu.  
  
-   Při práci se automaticky generovaná zdrojem, lze přidat kód do třídy bez nutnosti opětovného vytváření zdrojového souboru. Visual Studio používá tento přístup při vytváření formulářů Windows, obálky kódu webové služby a tak dále. Můžete vytvořit kód, který používá tyto třídy, aniž byste museli upravovat soubor vytvořený pomocí sady Visual Studio.  
  
-   Pro rozdělení definice třídy, použijte [částečné](../../../csharp/language-reference/keywords/partial-type.md) – klíčové slovo modifikátoru, jak je znázorněno zde:  
  
 [!code-csharp[csProgGuideObjects#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#26)]  
  
 `partial` – Klíčové slovo Určuje další části třídy, struktury nebo rozhraní lze definovat v oboru názvů. Musíte použít všechny části `partial` – klíčové slovo. Všechno, co musí být k dispozici v části doby kompilace a finální typu formuláře. Všechny součásti musí mít stejné usnadnění, například `public`, `private`, a tak dále.  
  
 Pokud některá část je deklarováno jako abstraktní, pak celý typ je považován za abstraktní. Pokud některá část je deklarován zapečetěné, pak celý typ je považován za zapečetěná. Pokud některá část deklaruje základní typ, dědí celý typ třídy.  
  
 Všechny součásti, které určují základní třída musí souhlasit, ale části, které vynechat základní třída dědí stále základního typu. Části můžete zadat různé základní rozhraní a poslední typ implementuje všechna rozhraní, které jsou seřazené podle částečné deklarace. Všechny třídy, struktury nebo rozhraní členy deklarované v definici dílčí jsou k dispozici pro všechny ostatní součásti. Poslední typ je kombinací všech částí v době kompilace.  
  
> [!NOTE]
>  `partial` Modifikátor není k dispozici v deklaracích delegáta nebo výčtu.  
  
 Následující příklad ukazuje, že vnořené typy může být částečně, i když není typu, které jsou vnořené uvnitř částečné samotný.  
  
 [!code-csharp[csProgGuideObjects#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#25)]  
  
 V době kompilace jsou sloučeny atributy částečný typ definice. Zvažte například následující deklarace:  
  
 [!code-csharp[csProgGuideObjects#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#23)]  
  
 Jsou ekvivalentní následující deklarace:  
  
 [!code-csharp[csProgGuideObjects#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#24)]  
  
 Tyto jsou sloučeny ze všech definic částečného typu:  
  
-   XML – komentáře  
  
-   rozhraní  
  
-   atributy parametru obecného typu  
  
-   class – atributy  
  
-   členy  
  
 Zvažte například následující deklarace:  
  
 [!code-csharp[csProgGuideObjects#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#21)]  
  
 Jsou ekvivalentní následující deklarace:  
  
 [!code-csharp[csProgGuideObjects#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#22)]  
  
### <a name="restrictions"></a>Omezení  
 Existuje několik pravidel dodržovat při práci s definicí částečné třídy:  
  
-   Všechny definice částečný typ má být součástí stejného typu musí být upravena se `partial`. Například následující deklarace třídy vygenerují chybu:  
  
     [!code-csharp[csProgGuideObjects#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#20)]  
  
-   `partial` Modifikátor se může objevit jenom bezprostředně před klíčová slova `class`, `struct`, nebo `interface`.  
  
-   Vnořené částečné typy jsou povoleny v definicích typu částečně, jak je znázorněno v následujícím příkladu:  
  
     [!code-csharp[csProgGuideObjects#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#19)]  
  
-   Všechny definice částečný typ má být součástí stejného typu musí být definován ve stejné sestavení a stejném modulu (soubor .exe nebo .dll). Částečné definice nemůžou zahrnovat více modulů.  
  
-   Název třídy a parametry obecného typu musí odpovídat na všechny definice typu části. Obecné typy mohou být neúplná. Každý částečná deklarace musí používat stejné názvy parametrů ve stejném pořadí.  
  
-   Následující klíčová slova v definici typu částečné jsou volitelné, ale pokud jsou k dispozici na jednu definici částečného typu, nemohou kolidovat s klíčovými slovy zadaný v jiné částečné deklaraci pro stejného typu:  
  
    -   [public](../../../csharp/language-reference/keywords/public.md)  
  
    -   [private](../../../csharp/language-reference/keywords/private.md)  
  
    -   [protected](../../../csharp/language-reference/keywords/protected.md)  
  
    -   [internal](../../../csharp/language-reference/keywords/internal.md)  
  
    -   [abstract](../../../csharp/language-reference/keywords/abstract.md)  
  
    -   [sealed](../../../csharp/language-reference/keywords/sealed.md)  
  
    -   base – třída  
  
    -   [nové](../../../csharp/language-reference/keywords/new.md) modifikátor (vnořené částí)  
  
    -   Obecná omezení  
  
         Další informace najdete v tématu [omezení parametrů typů](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## <a name="example-1"></a>Příklad 1  
  
### <a name="description"></a>Popis  
 V následujícím příkladu, polí a konstruktor třídy `Coords`, jsou deklarovány v jedné definici částečné třídy a člena, `PrintCoords`, je deklarována v jiné definici částečné třídy.  
  
### <a name="code"></a>Kód  
 [!code-csharp[csProgGuideObjects#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#17)]  
  
## <a name="example-2"></a>Příklad 2  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje, že můžete také vyvíjet částečné struktury a rozhraní.  
  
### <a name="code"></a>Kód  
 [!code-csharp[csProgGuideObjects#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#18)]  
  
## <a name="partial-methods"></a>Částečné metody  
 Částečné třídy nebo struktury může obsahovat částečná metoda. Jednou ze součástí sady třídy obsahuje podpis metody. Volitelné implementace může být definovaná v části stejné nebo jiné části. Pokud implementace není zadán, pak metoda a všechna volání do metody se odeberou v době kompilace.  
  
 Částečné metody umožňují implementátorovi jedné části třídy definují metody, podobné události. Implementátor druhou část třídy můžete rozhodnout, jestli se má implementovat metodu, nebo ne. Pokud metoda není implementována, pak kompilátor odebere metodu podpis a všechna volání do metody. Volání metody, včetně žádné výsledky, které by tomu bylo ze zkušební verze argumentů ve volání, nemají žádný vliv za běhu. Proto žádný kód v dílčí třídě mohou volně používat částečné metody i v případě, že implementace není součástí. Žádné chyby kompilace nebo runtime dojde, pokud je metoda volána, ale není implementováno.  
  
 Částečné metody jsou zvláště užitečné jako způsob, jak přizpůsobit generovaného kódu. Povolit pro název metody a podpis, které budou rezervovány, tak, že generovaný kód lze volat metodu, ale vývojář můžete rozhodnout, jestli se má implementovat metodu. Podobně jako částečné třídy částečné metody umožňují kód vytvořený pomocí generátoru kódu a kód vytvořený vývojářem lidské spolupracovat bez nákladů za běhu.  
  
 Deklarace částečné metody se skládá ze dvou částí: definice a implementaci. Může to být v samostatné části částečné třídy nebo ve stejné části. Pokud neexistuje žádná deklarace implementace, pak kompilátor optimalizuje okamžitě obou definování prohlášení a všechna volání do metody.  
  
```csharp  
// Definition in file1.cs  
partial void onNameChanged();  
  
// Implementation in file2.cs  
partial void onNameChanged()  
{  
  // method body  
}  
```  
  
-   Deklarace částečné metody musí začínat kontextové klíčové slovo [částečné](../../../csharp/language-reference/keywords/partial-type.md) a metoda musí vracet [void](../../../csharp/language-reference/keywords/void.md).  
  
-   Částečné metody mohou mít [v](../../../csharp/language-reference/keywords/in-parameter-modifier.md) nebo [ref](../../../csharp/language-reference/keywords/ref.md) , ale ne [si](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parametry.  
  
-   Částečné metody jsou implicitně [privátní](../../../csharp/language-reference/keywords/private.md), a proto nemůže být [virtuální](../../../csharp/language-reference/keywords/virtual.md).  
  
-   Částečné metody nemohou být [extern](../../../csharp/language-reference/keywords/extern.md), protože existenci textu určuje, zda jejich definování nebo implementace.  
  
-   Částečné metody mohou mít [statické](../../../csharp/language-reference/keywords/static.md) a [nebezpečné](../../../csharp/language-reference/keywords/unsafe.md) modifikátory.  
  
-   Částečné metody může být obecný. Omezení se použijí na definující deklarace částečné metody a může volitelně opakována na implementující jeden. Názvy parametrů a typ parametrů není potřeba, aby měly stejnou v implementující deklarace, jako je definování.  
  
-   Můžete provést [delegovat](../../../csharp/language-reference/keywords/delegate.md) částečné metody, která byla definována a implementována, ale ne k částečné metody, která obsahuje jenom definice.  
  
## <a name="c-language-specification"></a>Specifikace jazyka C#  

Další informace najdete v tématu [částečné typy](~/_csharplang/spec/classes.md#partial-types) v [ C# specifikace jazyka](../../language-reference/language-specification/index.md). Specifikace jazyka je úplným a rozhodujícím zdrojem pro syntaxi a použití jazyka C#.
  
## <a name="see-also"></a>Viz také:

- [Průvodce programováním v jazyce C#](../../../csharp/programming-guide/index.md)
- [Třídy](../../../csharp/programming-guide/classes-and-structs/classes.md)
- [Struktury](../../../csharp/programming-guide/classes-and-structs/structs.md)
- [Rozhraní](../../../csharp/programming-guide/interfaces/index.md)
- [partial (typ)](../../../csharp/language-reference/keywords/partial-type.md)
