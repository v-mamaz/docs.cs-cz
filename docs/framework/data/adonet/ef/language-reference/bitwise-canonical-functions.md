---
title: Bitové kanonické funkce
ms.date: 03/30/2017
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
ms.openlocfilehash: 882ecd2e82c64981dd76b3c860711433293145b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742263"
---
# <a name="bitwise-canonical-functions"></a>Bitové kanonické funkce
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] zahrnuje bitové kanonické funkce.  
  
## <a name="remarks"></a>Poznámky  
 V následující tabulce jsou uvedeny bitový [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonické funkce. Tyto funkce vrátí `Null` Pokud `Null` vstup je k dispozici. Návratový typ funkce je stejný jako typů argumentů. Argumenty musí být stejného typu, pokud funkce má více než jeden argument. K provedení bitové operace do různých typů, musíte explicitně přetypovat na stejného typu.  
  
|Funkce|Popis|  
|--------------|-----------------|  
|`BitWiseAnd (` `value1` `,`  `value2` `)`|Vrací bitové spojení z `value1` a `value2` jako typ `value1` a `value2`.<br /><br /> **Argumenty**<br /><br /> A `Byte`, `Int16`, `Int32`, a `Int64`.<br /><br /> **Příklad**<br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|`BitWiseNot (` `value` `)`|Vrací bitový negaci `value`.<br /><br /> **Argumenty**<br /><br /> A `Byte`, `Int16`, `Int32`, a `Int64`.<br /><br /> **Příklad**<br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|`BitWiseOr (` `value1` `,`  `value2` `)`|Vrátí bitovou disjunkci z `value1` a `value2` jako typ `value1` a `value2`.<br /><br /> **Argumenty**<br /><br /> A `Byte`, `Int16`, `Int32` a `Int64`.<br /><br /> **Příklad**<br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|`BitWiseXor (` `value1` `,`  `value2` `)`|Vrací bitový exkluzivní disjunkce z `value1` a `value2` jako typ `value1` a `value2`.<br /><br /> **Argumenty**<br /><br /> A `Byte`, `Int16`, `Int32` a `Int64`.<br /><br /> **Příklad**<br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a>Viz také:
- [Kanonické funkce](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
