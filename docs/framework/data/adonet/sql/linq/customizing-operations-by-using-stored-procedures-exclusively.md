---
title: Přizpůsobení operací pomocí uložených procedur komponentami TableAdapter výhradně
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 0dd8687bac8aa8ce046fb89c109debd91409aca8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573540"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>Přizpůsobení operací pomocí uložených procedur komponentami TableAdapter výhradně
Přístup k datům s použitím pouze uložené procedury je běžný scénář.  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Můžete upravit v příkladu v [přizpůsobení operací pomocí pomocí uložené procedury](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) nahrazením volání metody, která obaluje uloženou proceduru i první dotaz (což způsobí, že spuštění dynamické SQL).  
  
 Předpokládejme `CustomersByCity` je metoda, jako v následujícím příkladu.  
  
### <a name="code"></a>Kód  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 Následující kód provede bez jakékoli dynamické SQL.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Viz také:
- [Odpovědnosti vývojáře při přepisu výchozího chování](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
