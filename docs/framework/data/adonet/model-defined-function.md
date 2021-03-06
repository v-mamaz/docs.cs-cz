---
title: Modelově definovaných funkcí
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 371af3ae090e37cfd425a9e9d5946bb0751dc527
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538879"
---
# <a name="model-defined-function"></a>Modelově definovaných funkcí
A *modelově definovaných funkcí* je funkce, která je definována v konceptuálním modelu. Tělo funkce definované model je vyjádřen v [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), který umožňuje pro funkce, který má být vyjádřena nezávisle na pravidla nebo ve zdroji dat podporuje jazyky.  
  
 Definice pro definovaný model funkci obsahuje následující informace:  
  
-   Název funkce. (Povinné)  
  
-   Typ vrácené hodnoty. (Volitelné)  
  
    > [!NOTE]
    >  Pokud není zadán žádný návratový typ, vrácená hodnota je typu void.  
  
-   Informace o parametrech. (Volitelné)  
  
-   [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) výraz, který definuje těla funkce.  
  
 Všimněte si, že modelově definovaných funkcí nepodporuje výstupní parametry. Toto omezení je na místě, tak, aby se může skládat modelově definovaných funkcí.  
  
## <a name="example"></a>Příklad  
 Následující diagram znázorňuje Koncepční model s tři typy entit: `Book`, `Publisher`, a `Author`.  
  
 ![Model s datum publikování](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) používá jazyka specifického pro doménu (DSL) volá Konceptuální schéma definici jazyka ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) k definování konceptuálních modelů. Následující CSDL definuje funkci v konceptuálním modelu, který vrací počet let od instance `Book` (ve výše uvedeném diagramu) publikoval.  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>Viz také:
- [Koncepty modelu EDM (Entity Data Model)](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Model EDM (Entity Data Model)](../../../../docs/framework/data/adonet/entity-data-model.md)
- [Model Entity Data Model: Primitivní datové typy](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
