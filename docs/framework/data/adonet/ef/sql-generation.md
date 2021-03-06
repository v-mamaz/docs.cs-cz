---
title: Generování SQL
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 1eb2830d96000e61d62b2fc934cd246df3ad3e0f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701505"
---
# <a name="sql-generation"></a>Generování SQL
Při psaní zprostředkovatele [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], musí překládat [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] příkaz stromů do SQL, který konkrétní databázi můžete pochopit, jako je například příkazů jazyka Transact-SQL pro SQL Server nebo PL/SQL pro databázi Oracle. V této části se dozvíte postupy při vývoji komponentu generování SQL (pro dotazů SELECT) pro [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] zprostředkovatele. Informace o vložení, aktualizace a odstraňování dotazů naleznete v tématu [úpravy generování SQL](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).  
  
 Informace o tom v této části, měli byste se seznámit s [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] a podle modelu poskytovatele ADO.NET. Také je třeba porozumět stromů příkazů a <xref:System.Data.Common.CommandTrees.DbExpression>.  
  
## <a name="the-role-of-the-sql-generation-module"></a>Role modulu generování SQL  
 Modul generování SQL [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] poskytovatele přeloží daný dotaz stromu příkazů na jeden příkaz SQL SELECT, který se zaměřuje SQL:1999 – databáze kompatibilní. Vygenerovaný SQL by měla mít jako pár vnořené dotazy nejvíce. Modul generování SQL by neměla zjednodušit stromu příkazů výstup dotazu. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Se to provést, například odstranění spojení a sbalení uzlů po sobě jdoucích filtru.  
  
 <xref:System.Data.Common.DbProviderServices> Třída je výchozím bodem pro přístup k vrstvě generování SQL pro převod stromů příkazů do <xref:System.Data.Common.DbCommand>.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Tvar stromu příkazů](../../../../../docs/framework/data/adonet/ef/the-shape-of-the-command-trees.md)  
  
 [Generování SQL ze stromů příkazů – osvědčené postupy](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)  
  
 [Generování SQL ve zprostředkovateli ukázek](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>Viz také:
- [Zápis zprostředkovatele dat Entity Framework](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
