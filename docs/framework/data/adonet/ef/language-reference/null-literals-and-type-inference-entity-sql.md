---
title: "Null literály a odvození typu (entita SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 52a46758a8dd53adf583da40de36d640eee9c5d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="null-literals-and-type-inference-entity-sql"></a>Null literály a odvození typu (entita SQL)
Null – literály jsou kompatibilní s žádným typem v [!INCLUDE[esql](../../../../../../includes/esql-md.md)] systém typů. Pro typ literál null na odvodit správně, ale [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ukládá určitá omezení, na kterém můžou použít literálu s hodnotou null.  
  
## <a name="typed-nulls"></a>Hodnotou Null  
 Hodnotou Null lze použít kdekoli. Odvození typu není vyžadována pro hodnotou Null, protože typ je znám. Například můžete vytvořit hodnotu null typu Int16 s následující [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vytvořit:  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a>Plovoucí Null literály  
 Plovoucí literály null lze použít v kontextech následující:  
  
-   Jako argument k PŘETYPOVÁNÍ nebo ZPRACOVÁVAT výraz. Toto je doporučeným způsobem, jak vytvořit výraz typu hodnotu null.  
  
-   Jako argument pro metodu nebo funkce. Standardní přetížení pravidla použít.  
  
-   Jako jeden z argumentů pro aritmetické výraz například +, -, nebo /. Další argumenty nemůže být null literály, jinak odvození typu není možné.  
  
-   Jako některý z argumentů logický výraz (AND, OR, nebo ne). Všechny argumenty jsou známé být typu logická hodnota.  
  
-   Jako argument výraz IS NOT NULL nebo je NULL.  
  
-   Jako jeden nebo více argumenty, které se výraz LIKE. Všechny argumenty jsou očekávány řetězce.  
  
-   Jako jeden nebo více argumenty pro konstruktor s názvem typu.  
  
-   Jako jeden nebo více argumentů multiset konstruktoru. Výraz, který není null literál musí být alespoň jeden argument multiset konstruktoru.  
  
-   Jako jeden nebo více výrazů ve výrazu případu pak, jinak. Alespoň jeden z výrazů v případu výraz pak, jinak musí být výrazem jiným než literálu s hodnotou null.  
  
 Plovoucí literály null nelze použít v jiné scénáře. Například se nelze použít jako argumenty pro konstruktor row.  
  
## <a name="see-also"></a>Viz také  
 [Přehled SQL entity](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)