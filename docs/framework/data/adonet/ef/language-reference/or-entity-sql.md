---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 4d0bed2fb000e96e9fd0ceac6ea90e19b8fa7514
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554852"
---
# <a name="-or-entity-sql"></a>|| (OR) (Entity SQL)
Kombinuje dvě `Boolean` výrazy.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>Arguments  
 `boolean_expression`  
 Libovolný platný výraz, který vrací `Boolean`.  
  
## <a name="return-value"></a>Návratová hodnota  
 `true` Pokud některá z podmínek je `true`; v opačném případě `false`.  
  
## <a name="remarks"></a>Poznámky  
 NEBO se [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logický operátor. Používá se ke sloučení dvě podmínky. Pokud více než jeden logický operátor se používá v příkazu, nebo operátory jsou vyhodnocovány po operátory. Pořadí vyhodnocení však můžete změnit pomocí závorek.  
  
 Double svislé čáry (&#124;&#124;) mají stejné funkce jako operátor OR.  
  
 Následující tabulka uvádí možné vstupní hodnoty a návratové typy.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|HODNOTA TRUE|HODNOTA TRUE|HODNOTA TRUE|  
|`FALSE`|HODNOTA TRUE|FALSE|NULL|  
|`NULL`|HODNOTA TRUE|NULL|NULL|  
  
## <a name="example"></a>Příklad  
 Následující dotaz Entity SQL používá operátor nebo kombinace obou `Boolean` výrazy. Dotaz je založen na modelu Sales AdventureWorks. Kompilace a spuštění tohoto dotazu, postupujte podle těchto kroků:  
  
1.  Postupujte podle pokynů v [jak: Spustit dotaz, který vrátí výsledky typu StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Předat jako argument pro následující dotaz `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a>Viz také:
- [Reference k Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
