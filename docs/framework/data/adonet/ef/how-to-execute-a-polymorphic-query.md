---
title: 'Postupy: Spuštění Polymorfního dotazu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 08ae5722267ef781ed6bee59c7895269f63a75e5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355533"
---
# <a name="how-to-execute-a-polymorphic-query"></a>Postupy: Spuštění Polymorfního dotazu

Toto téma ukazuje, jak spustit polymorfní [!INCLUDE[esql](../../../../../includes/esql-md.md)] dotazování pomocí [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operátor.

### <a name="to-run-the-code-in-this-example"></a>Chcete-li spustit kód v tomto příkladu

1. Přidat [školní modelu](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) do vašeho projektu a konfigurace projektu pro použití rozhraní Entity Framework. Další informace najdete v tématu [jak: Použijte Průvodce datovým modelem Entity](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

2. V kódové stránce pro vaši aplikaci, přidejte následující `using` příkazy (`Imports` v jazyce Visual Basic):

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. Upravit konceptuálního modelu má tabulka za hierarchie dědičnosti pomocí následujících kroků v [názorný postup: Mapování dědičnosti - Table za Hierarchy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).

## <a name="example"></a>Příklad

Následující příklad používá operátor OFTYPE k získání a zobrazení kolekce pouze `OnsiteCourses` z kolekce `Courses`.

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a>Viz také:

- [Zprostředkovatel EntityClient pro Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
- [Jazyk Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
