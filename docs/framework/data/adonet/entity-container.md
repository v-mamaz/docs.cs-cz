---
title: kontejner entit
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: d2ad565ce73b2de4b10d2f15406b283a13bbef6e
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409884"
---
# <a name="entity-container"></a>kontejner entit
*Kontejneru entity* je logické seskupení [sad entit](../../../../docs/framework/data/adonet/entity-set.md), [sad přidružení](../../../../docs/framework/data/adonet/association-set.md), a [importů funkci](../../../../docs/framework/data/adonet/model-declared-function.md).  
  
 Musí být splněné tyto požadavky definované v konceptuálním modelu entity kontejneru:  
  
-   Minimálně jednu entitu kontejneru musí být definován v každé koncepčního modelu.  
  
-   Kontejner entit musí mít jedinečný název v rámci každé koncepčního modelu.  
  
 Kontejner entit můžete definovat, sad entit a sad přidružení, které používají typy entit a přidružení, které jsou definovány v jedné nebo více oborů názvů. Další informace najdete v tématu [modelu Entity Data Model: Obory názvů](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).  
  
## <a name="example"></a>Příklad  
 Následující diagram znázorňuje Koncepční model s tři typy entit: `Book`, `Publisher`, a `Author`.  Podívejte se na další příklad pro další informace.  
  
 ![Příklad modelu s tři typy entit](./media/entity-container/example-model-three-entity-types.gif)  
  
 I když diagramu neznamená informací o entitách kontejneru, musí definovat konceptuálního modelu kontejnerem entity. [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) používá DSL volá Konceptuální schéma definici jazyka ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) k definování konceptuálních modelů. Následující CSDL definuje kontejneru entity pro koncepční model je vidět na obrázku výše. Všimněte si, že název kontejneru entity je definován v atributu XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Viz také:
- [Koncepty modelu EDM (Entity Data Model)](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Model EDM (Entity Data Model)](../../../../docs/framework/data/adonet/entity-data-model.md)
