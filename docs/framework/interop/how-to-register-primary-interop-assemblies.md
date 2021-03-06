---
title: 'Postupy: Registrace primárních sestavení spolupráce'
ms.date: 03/30/2017
helpviewer_keywords:
- registering primary interop assemblies
- primary interop assemblies, registering
ms.assetid: 4b2fcf8a-429d-43ce-8334-e026040be8bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c5f1882c37861fe7dd7997348dc51e30ce2950e
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/13/2019
ms.locfileid: "56218538"
---
# <a name="how-to-register-primary-interop-assemblies"></a>Postupy: Registrace primárních sestavení spolupráce

Třídy lze zařadit pouze pomocí zprostředkovatele komunikace s objekty COM a jsou vždy zařadit jako rozhraní. V některých případech rozhraní použitý k zařazování třídy se nazývá třídy rozhraní. Informace o přepsání rozhraní třídy s rozhraním podle vašeho výběru, najdete v části [obálka volatelná aplikacemi COM](../../../docs/framework/interop/com-callable-wrapper.md).

 I když kterýkoli vývojář, který chce používat typy modelu COM z aplikace rozhraní .NET Framework mohou generovat sestavení vzájemné spolupráce, vytvoří to uděláte tak problém. Pokaždé, když vývojář importuje a zaregistruje knihovnu typů modelu COM, který vytvoří sadu jedinečných typů, které nejsou kompatibilní s těmi, importovat a být podepsáno stranou jiným vývojářem pro vývojáře. Řešení tohoto problému nekompatibility typu je pro každý vývojář získat dodavatele a podepsaný primárního spolupracujícího sestavení.

 Pokud chcete vystavit typy modelu COM třetích stran k ostatním aplikacím, vždy používejte primárního spolupracujícího sestavení od stejného výrobce jako knihovny typů, které definuje. Kromě zajištění zaručené typ kompatibility, jsou často primárních sestavení vzájemné spolupráce přizpůsobit podle dodavatele a zlepšení interakce.

 I v případě, že nechcete vystavit typy modelu COM třetích stran, pomocí primárního spolupracujícího sestavení můžete zjednodušují spolupráci s COM komponent. Tato strategie však nabízí žádné izolaci od dodavatele může provádět typy definované v primární spolupracující sestavení změny. Když vaše aplikace vyžaduje tato izolace, generování spolupráce sestavení místo sestavení primární spolupráce.

 Předtím, než je můžete odkazovat pomocí sady Visual Studio, je nutné zaregistrovat všechny načtené sestavení primární spolupráce na vašem vývojovém počítači. Visual Studio vyhledá a používá primární spolupracující sestavení poprvé odkazovat na typ z knihovny typů modelu COM. Pokud aplikace Visual Studio nemůže najít primární sestavení vzájemné spolupráce přidružené ke knihovně typů, vyzve vás k získání nebo nabízí definiční sestavení místo toho chcete vytvořit. Stejně tak [Importér knihovny typů (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) registru také používá k vyhledání sestavení primární spolupráce.

 Ačkoli to není potřeba registrace primárních sestavení spolupráce, jen pokud plánujete použití sady Visual Studio, registrace přináší dvě výhody:

-   Registrované primární definiční sestavení je přehledně označen v klíči registru původní knihovny typů. Registrace je nejlepší způsob, jak vám umožňuje vyhledávat primární spolupracující sestavení v počítači.

-   Náhodně generování a použití nového sestavení zprostředkovatele komunikace, pokud někdy v budoucnu, pomocí sady Visual Studio odkazovat na typ, pro které je nutné zrušit primární definiční sestavení se můžete vyhnout.

Použití [nástroj registrace sestavení (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) registrovat primární definiční sestavení.

## <a name="to-register-a-primary-interop-assembly"></a>Registrace primárního spolupracujícího sestavení

1.  V příkazovém řádku zadejte příkaz:

     **RegAsm** *assemblyname*

     V tomto příkazu *assemblyname* je název souboru sestavení, které je zaregistrovaný. RegAsm.exe přidá položka pro primární spolupracující sestavení v klíči registru jako původní knihovny typů.

## <a name="example"></a>Příklad
 Následující příklad registruje `CompanyA.UtilLib.dll` primární definiční sestavení.

```console
regasm CompanyA.UtilLib.dll
```

## <a name="see-also"></a>Viz také:

- [Programování s primárními sestaveními spolupráce](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/baxfadst(v=vs.100))
- [Vyhledání sestavení primární spolupráce](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/y06sxw56(v=vs.100))
- [Opětovná distribuce sestavení primární spolupráce](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w0dt2w20(v=vs.100))