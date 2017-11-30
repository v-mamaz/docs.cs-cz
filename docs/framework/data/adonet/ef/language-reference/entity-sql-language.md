---
title: Jazyk SQL entity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 08e366e8bbd9df31f367496ca5e106b876921896
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="entity-sql-language"></a>Jazyk SQL entity
Entita SQL je nezávislé na úložiště dotazovací jazyk, který je podobný SQL. Entity SQL vám umožní zadat dotaz na data entity, jako objekty nebo ve formě tabulky. Měli byste zvážit použití Entity SQL v následujících případech:  
  
-   Pokud dotaz musí dynamicky zkonstruovat za běhu. V takovém případě měli byste také zvážit použití metody Tvůrce dotazů z <xref:System.Data.Objects.ObjectQuery%601> místo vytváření Entity SQL řetězec za běhu dotazu.  
  
-   Pokud chcete definovat dotaz jako součást definice modelu. Pouze Entity SQL je podporována v datovém modelu. Další informace najdete v tématu [Element QueryView (MSL)](http://msdn.microsoft.com/en-us/f0426b34-45cb-4fd7-9777-e0570c5e0e80)  
  
-   Při použití EntityClient vrátit data jen pro čtení entity jako pomocí sady řádků <xref:System.Data.EntityClient.EntityDataReader>. Další informace najdete v tématu [zprostředkovatel EntityClient rozhraní Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
-   Pokud už jste odborník v jazycích dotazů SQL, se může zdát nejvíce přirozené vám Entity SQL.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Pomocí Entity SQL se zprostředkovatelem EntityClient  
 Pokud chcete použít entitu SQL se zprostředkovatelem EntityClient, najdete další informace v následujících tématech:  
  
 [Zprostředkovatel EntityClient rozhraní Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [Postupy: sestavení řetězec připojení EntityConnection](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Postup: provedení dotazu, který vrátí výsledky PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Postup: provedení dotazu, který vrátí výsledky StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Postup: provedení dotazu, který vrátí výsledky RefType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Postup: provedení dotazu, který vrací komplexní typy](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Postupy: spuštění dotaz, který vrátí vnořené kolekce](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Postupy: spuštění dotazu SQL parametrizované Entity pomocí objekt EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Postup: provedení parametrizované uložené procedury pomocí objekt EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Postup: provedení polymorfní dotazu](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Postupy: procházení vztahů pomocí přejděte – operátor](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Pomocí objektu dotazy Entity SQL  
 Pokud chcete použít s dotazy na objekt Entity SQL, najdete další informace v následujících tématech:  
  
 [Postup: provedení dotazu, který vrátí objekty typu Entity](http://msdn.microsoft.com/en-us/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [Postup: provedení parametrizovaného dotazu](http://msdn.microsoft.com/en-us/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [Postupy: procházení vztahů pomocí navigační vlastnosti](http://msdn.microsoft.com/en-us/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [Postupy: volání funkce uživatelem definované](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [Postupy: filtrování dat](http://msdn.microsoft.com/en-us/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [Postupy: řazení dat](http://msdn.microsoft.com/en-us/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [Postupy: seskupení dat](http://msdn.microsoft.com/en-us/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [Postupy: agregace dat](http://msdn.microsoft.com/en-us/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [Postup: provedení dotazu, který vrátí objekty anonymního typu](http://msdn.microsoft.com/en-us/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [Postup: provedení dotazu, který vrátí kolekce primitivní typy](http://msdn.microsoft.com/en-us/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [Postupy: dotazování související objekty v EntityCollection](http://msdn.microsoft.com/en-us/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [Postupy: řazení sjednocení dva dotazy](http://msdn.microsoft.com/en-us/853c583a-eaba-4400-830d-be974e735313)  
  
 [Postupy: výsledky stránky prostřednictvím dotazu](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přehled SQL entity](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [Odkaz na entitu SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a>Viz také  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [Referenční dokumentace jazyka](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)