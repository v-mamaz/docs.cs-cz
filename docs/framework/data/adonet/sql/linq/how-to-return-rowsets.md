---
title: 'Postupy: Vrácení sad řádků'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: b9fcbd8aa74740a66fa6caca18067ac473891f4e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587213"
---
# <a name="how-to-return-rowsets"></a>Postupy: Vrácení sad řádků
V tomto příkladu vrátí sadu řádků z databáze a zahrnuje vstupní parametr a filtrovat výsledky.  
  
 Při spouštění uložené procedury, která vrací sadu řádků, je použít *výsledek* třída, která obsahuje tato vrátí hodnotu z úložné procedury. Další informace najdete v tématu [analýza LINQ to SQL zdrojový kód](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad představuje uloženou proceduru, která vrací řádky zákazníků a vrátit pouze řádky tohoto seznamu "Londýn" jako název města zákazníka pomocí vstupního parametru. Příklad předpokládá Výčtový objekt `CustomersByCityResult` třídy.  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a>Viz také:
- [Uložené procedury](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [Stažení ukázkových databází](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
