---
title: Zadejte zařazování – .NET
description: Zjistěte, jak .NET zařazuje vaše typy pro nativní reprezentace.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: b4846f2e6cd945a25ec6a747c9038d48fe115559
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185412"
---
# <a name="type-marshalling"></a>Zařazování typů

**Zařazování** je proces transformace typy, když je budou potřebovat pro různé mezi spravovaný a nativní kód.

Zařazování je potřeba, protože se liší typy v spravovaným a nespravovaným kódem. Ve spravovaném kódu, například můžete mít `String`, zatímco nespravované světě mohou být řetězce Unicode ("širokých"), kódování Unicode, zakončený hodnotou null, ASCII, atd. Ve výchozím nastavení P/Invoke subsystému pokouší provést správné věci na základě výchozí chování, je popsáno v tomto článku. Pro tyto situace, kdy potřebujete další ovládací prvek, ale můžete použít [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) atribut k určení, co je očekávaný typ v nespravované oblasti. Například pokud chcete řetězec, který má být odeslán jako ANSI řetězec zakončený hodnotou null, lze nastavit takto:

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshalling-common-types"></a>Výchozí pravidla pro zařazování běžných typů

Obecně platí, modul runtime pokusí provést "správné věci" při vyžadování minimální množství práce, které od vás sběrného systému. Následující tabulky popisují, jak je každý typ zařazeno ve výchozím nastavení při použití v parametru nebo pole. C99 / C ++ 11 celočíselné neproporcionální a typy znaků se používají k ověření, že v následující tabulce je správná pro všechny platformy. Můžete použít nativní typ, který má stejné zarovnání a požadavky na velikost jako tyto typy.

V první tabulce popisuje mapování pro různé typy, pro které zařazování je stejný pro P/Invoke a zařazování pro pole.

| Typ formátu .NET | Nativní typ  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | Buď `char` nebo `char16_t` v závislosti na tom `CharSet` P/Invoke nebo struktury. Zobrazit [znaková sada dokumentace](charset.md). |
| `string`  | Buď `char*` nebo `char16_t*` v závislosti na tom `CharSet` P/Invoke nebo struktury. Zobrazit [znaková sada dokumentace](charset.md). |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| Typy ukazatelů rozhraní .NET (např.) `void*`)  | `void*` |
| Typ odvozený od `System.Runtime.InteropServices.SafeHandle` | `void*` |
| Typ odvozený od `System.Runtime.InteropServices.CriticalHandle` | `void*`          |
| `bool`    | Win32 `BOOL` typu       |
| `decimal` | COM `DECIMAL` – struktura |
| Delegát .NET | Ukazatel na nativní funkci |
| `System.DateTime` | Win32 `DATE` typu |
| `System.Guid` | Win32 `GUID` typu |

Několik kategorií zařazování používají různé výchozí hodnoty, pokud jste zařazování jako parametr nebo strukturu.

| Typ formátu .NET | Nativní typ (parametr) | Nativní typ (pole) |
|-----------|-------------------------|---------------------|
| Pole .NET | Ukazatel na začátku pole nativní reprezentace prvků pole. | Není povoleno bez `[MarshalAs]` atribut|
| Třída s atributem `LayoutKind` z `Sequential` nebo `Explicit` | Ukazatel na nativní reprezentace třídy | Nativní reprezentace třídy |

Následující tabulka obsahuje výchozí zařazování pro pravidla, která jsou jen pro Windows. Na platformách než Windows nelze zařadit těchto typů.

| Typ formátu .NET | Nativní typ (parametr) | Nativní typ (pole) |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | Rozhraní modelu COM | Není povoleno bez `[MarshalAs]` atribut |
| `System.ArgIterator` | `va_list` | Nepovoleno |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | Nepovoleno |
| `System.Collections.IEnumerable` | `IDispatch*` | Nepovoleno |
| `System.DateTimeOffset` | `int64_t` představuje počet taktů od půlnoci 1. ledna 1601 || `int64_t` představuje počet taktů od půlnoci 1. ledna 1601 |

Některé typy může být zařazeno pouze jako parametry a ne jako pole. Tyto typy jsou uvedeny v následující tabulce:

| Typ formátu .NET | Nativní typ (pouze parametr) |
|-----------|------------------------------|
| `System.Text.StringBuilder` | Buď `char*` nebo `char16_t*` v závislosti na tom `CharSet` P/Invoke.  Zobrazit [znaková sada dokumentace](charset.md). |
| `System.ArgIterator` | `va_list` (pro Windows x86/x64/arm64 jenom) |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

Pokud tyto výchozí hodnoty neprovádějte přesně to, co chcete, můžete přizpůsobit, jak zařazeno parametry. [Zařazování parametru](customize-parameter-marshalling.md) článek vás provede přizpůsobení jak různé typy parametrů zařazeno procházení.

## <a name="marshalling-classes-and-structs"></a>Zařazování tříd a struktur

Dalším aspektem typu zařazování je jak předat strukturu pro nespravované metody. Například některé metody nespravovaného vyžadují strukturu jako parametr. V těchto případech je potřeba vytvořit odpovídající struktury nebo třídy součástí spravované mohli používat jako parametr. Však stačí definování třídy nestačí, budete potřebovat dáte pokyn, aby zařazování odvozovalo způsob mapování polí ve třídě do nespravované struktury. Tady `StructLayout` atribut je užitečné.

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

Předchozí kód ukazuje jednoduchý příklad volání do `GetSystemTime()` funkce. Zajímavé bit je na řádku 4. Atribut určuje, že pole třídy musí být mapována postupně do struktury na druhé straně (nespravovaného). To znamená, že názvy polí není důležité, že jenom jejich pořadí je důležité, protože je potřeba tak, aby odpovídaly nespravované struktury, je znázorněno v následujícím příkladu:

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME*;
```

Výchozí zařazování pro struktury někdy neumí, co potřebujete. [Přizpůsobení zařazování pro struktury](./customize-struct-marshalling.md) článku se naučíte, jak přizpůsobit, jak je zařadit strukturu.
