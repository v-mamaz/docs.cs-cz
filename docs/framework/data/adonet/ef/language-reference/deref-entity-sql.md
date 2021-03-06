---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: f64580e5ca34bf094d6019e994f40f11ed9586cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506911"
---
# <a name="deref-entity-sql"></a>DEREF (Entity SQL)
Přístupů přes ukazatel referenčními hodnotami a vytváří výsledek, který přístup přes ukazatel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 Libovolný výraz platný dotaz, který vrátí kolekci.  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota entity, na který odkazuje.  
  
## <a name="remarks"></a>Poznámky  
 Operátor DEREF přístupů přes ukazatel, hodnota odkazu a vytváří výsledek, který přístup přes ukazatel. Například pokud `r` odkaz na typ ref\<T >, `Deref(r)` je výraz typu `T` , která poskytuje entita odkazuje `r`. Pokud hodnota odkazu je null nebo je nepropojená (to znamená, že cíl odkazu neexistuje), výsledek operátoru DEREF má hodnotu null.  
  
## <a name="example"></a>Příklad  
 Následující [!INCLUDE[esql](../../../../../../includes/esql-md.md)] dotazu používá operátor DEREF pokouší dereferencovat referenčními hodnotami a přístupu přes ukazatel výsledku, který vytvoří. Dotaz je založen na modelu Sales AdventureWorks. Kompilace a spuštění tohoto dotazu, postupujte podle těchto kroků:  
  
1.  Postupujte podle pokynů v [jak: Spustit dotaz, který vrátí výsledky typu PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Následující dotaz předejte jako argument k metodě ExecutePrimitiveTypeQuery:  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a>Viz také:
- [Reference k Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
- [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)
- [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)
- [Strukturované typy s možnou hodnotou Null](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
