---
title: 'Postupy: Volání vlastních databázových funkcí'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: cdb7b5c90e98f299f37cd09fc83ddfdcca31effd
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826626"
---
# <a name="how-to-call-custom-database-functions"></a>Postupy: Volání vlastních databázových funkcí
Toto téma popisuje, jak zavolat vlastní funkce, které jsou definovány v databázi z v rámci LINQ dotazy na entity.  
  
 Databázové funkce, které se volají z LINQ na dotazy na entity jsou provedeny v databázi. Provádění funkcí v databázi může zlepšit výkon aplikace.  
  
 Následující postup obsahovala hrubý nástin pro volání funkce vlastní databázi. Následující příklad obsahuje více podrobností o kroků v postupu.  
  
### <a name="to-call-custom-functions-that-are-defined-in-the-database"></a>K volání vlastní funkce, které jsou definovány v databázi  
  
1.  Vytvoření vlastní funkce ve vaší databázi.  
  
     Další informace o vytváření vlastních funkcí v systému SQL Server najdete v tématu [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).  
  
2.  Deklarování funkce v úložiště schema definition language (SSDL) souboru .edmx. Název funkce musí být stejný jako název funkce deklarovaná v databázi.  
  
     Další informace najdete v tématu [funkce – Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).  
  
3.  Přidejte odpovídající metodu na třídu v kódu aplikace a použít <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> metody Všimněte si, že <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parametry atributu se názvu oboru názvů Koncepční model a název funkce v konceptuálním model, v uvedeném pořadí. Funkce překlad názvů pro funkci LINQ je velká a malá písmena.  
  
4.  Volání metody v technologii LINQ to Entities dotazu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak volat funkci vlastní databázi z v rámci LINQ dotazu entity. V příkladu používá model školy. Informace o School modelu najdete v tématu [vytvoření ukázkové databáze školy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) a [generování školní edmx soubor](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).  
  
 Následující kód přidává `AvgStudentGrade` funkce k ukázkové databázi School.  
  
> [!NOTE]
>  Kroky pro volání funkce vlastní databázi jsou stejné bez ohledu na databázovém serveru. Následující kód je však specifické pro vytvoření funkce v databázi serveru SQL Server. Kód pro vytvoření vlastní funkce v jiné databázové servery se může lišit.  
  
 [!code-sql[DP L2E MapToDBFunction#1](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]  
  
## <a name="example"></a>Příklad  
 V dalším kroku deklarování funkce v úložiště schema definition language (SSDL) souboru .edmx. Následující kód deklaruje `AvgStudentGrade` funkce v SSDL:  
  
 [!code-xml[DP L2E MapToDBFunction#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]  
  
## <a name="example"></a>Příklad  
 Teď vytvořte metodu a jejich mapování na funkce deklarovaná v SSDL. Metoda následující třída je namapována na funkci definované v SSDL (viz výše) pomocí <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Když tato metoda je volána, je proveden odpovídající funkce v databázi.  
  
 [!code-csharp[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
 [!code-vb[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]  
  
## <a name="example"></a>Příklad  
 Nakonec proveďte volání metody v technologii LINQ to Entities dotazu. Následující kód zobrazí poslední jména studentů a průměrné známek do konzoly:  
  
 [!code-csharp[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
 [!code-vb[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]  
  
## <a name="see-also"></a>Viz také:
- [Přehled souboru EDMX](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Dotazy v technologii LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
