---
title: násobnost end přidružení
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 183bbafaf1de3adf8719c7ee562be3513832ef10
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412094"
---
# <a name="association-end-multiplicity"></a>násobnost end přidružení
*Násobnost end přidružení* definuje počet [typ entity](../../../../docs/framework/data/adonet/entity-type.md) instancí, které mohou být na jednom konci [přidružení](../../../../docs/framework/data/adonet/association-type.md).  
  
 Násobnost end přidružení může mít jednu z následujících hodnot:  
  
-   jedna (1): Označuje, že tuto instanci typu přesně jedna entita existuje na konci přidružení.  
  
-   nula nebo jedna (0..1): Udává, že existuje žádnou nebo jednou instancí typu entity na konci přidružení.  
  
-   Mnoho (\*): Udává, že existuje žádného, jednoho nebo více instancí typu entity na konci přidružení.  
  
 Asociace je často vyznačují Násobnosti zakončení její přidružení. Například, pokud konce asociace mají násobnosti jeden (1) a mnoho (\*), přidružení je označováno jako jeden mnoho přidružení. V následujícím příkladu `PublishedBy` přidružení je přidružení jednoho k několika (vydavatel publikuje mnoho knih a knihy se publikuje vydavatele). `WrittenBy` Přidružení je přidružení many-to-many (knihu můžete mít více autoři a autor můžete psát více seznamů).  
  
## <a name="example"></a>Příklad  
 Následující diagram znázorňuje Koncepční model se dvěma přidružení: `PublishedBy` a `WrittenBy`. Konec asociace `PublishedBy` přidružení se `Book` a `Publisher` typy entit. Násobnost `Publisher` end je jedna (1) a násobnost `Book` end je mnoho (\*).  
  
 ![Příklad modelu s tři typy entit](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 ADO.NET Entity Framework používá jazyka specifického pro doménu (DSL) volá Konceptuální schéma definici jazyka ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) k definování konceptuálních modelů. Definuje následující CSDL `PublishedBy` přidružení, které jsou zobrazeny ve výše uvedeném diagramu:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Viz také:
- [Koncepty modelu EDM (Entity Data Model)](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Model EDM (Entity Data Model)](../../../../docs/framework/data/adonet/entity-data-model.md)
