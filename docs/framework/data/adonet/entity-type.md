---
title: Typ entity
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: cb542a1750a6b45dd2fca4d32501719470d9a78a
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410885"
---
# <a name="entity-type"></a>Typ entity
*Typ entity* je základním stavebním blokem pro popis struktury data pomocí modelu Entity Data Model (EDM). Typ entity v konceptuálním modelu reprezentuje strukturu těchto koncepty nejvyšší úrovně, jako je například Zákazníci a objednávky. Typ entity je šablona pro instance typu entity. Každá šablona obsahuje následující informace:  
  
-   Jedinečný název. (Povinné).  
  
-   [Klíč entity](../../../../docs/framework/data/adonet/entity-key.md) určené jednu nebo více vlastností. (Povinné).  
  
-   Data ve formě [vlastnosti](../../../../docs/framework/data/adonet/property.md). (Volitelné).  
  
-   [Navigační vlastnosti](../../../../docs/framework/data/adonet/navigation-property.md) , která umožňují navigaci z jednoho [end](../../../../docs/framework/data/adonet/association-end.md) ze [přidružení](../../../../docs/framework/data/adonet/association-type.md) na druhém konci. (Volitelné)  
  
 V aplikaci, která představuje instance typu entity na konkrétní objekt (například konkrétního zákazníka nebo pořadí). Každá instance typu entity musí mít jedinečnou [klíč entity](../../../../docs/framework/data/adonet/entity-key.md) v rámci [sadu entit](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Dvě instance typu entity se považovat za rovné pouze v případě, že jsou stejného typu a hodnoty jejich klíče entity jsou stejné.  
  
## <a name="example"></a>Příklad  
 Následující diagram znázorňuje Koncepční model s tři typy entit: `Book`, `Publisher`, a `Author`:  
  
 ![Příklad modelu s tři typy entit](./media/entity-type/example-model-three-entity-types.gif)  
  
 Všimněte si, že vlastnosti každého typu entity, které tvoří jeho klíč entity, jsou označeny "(klíč)".  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) používá jazyka specifického pro doménu (DSL) volá Konceptuální schéma definici jazyka ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) k definování konceptuálních modelů. Definuje následující CSDL `Book` typ entity, které jsou zobrazeny ve výše uvedeném diagramu:  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Viz také:
- [Koncepty modelu EDM (Entity Data Model)](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Model EDM (Entity Data Model)](../../../../docs/framework/data/adonet/entity-data-model.md)
- [facet](../../../../docs/framework/data/adonet/facet.md)
