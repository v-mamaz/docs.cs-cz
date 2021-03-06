---
title: 'Omezení rizik: Období blokování fondu'
ms.date: 03/30/2017
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4c90a75ebbb9e4bc6248aadd709be8b5285ecd6
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409117"
---
# <a name="mitigation-pool-blocking-period"></a>Omezení rizik: Období blokování fondu
Odebrali jsme blokování období fondu připojení pro připojení k databázím Azure SQL.  
  
## <a name="additional-description"></a>Další popis  
 V [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] a předchozími verzemi, pokud aplikace zjistí chyba přechodného připojení při připojování k databázi, pokus o připojení se nedá opakovat, rychle, protože fond připojení ukládá do mezipaměti, chyby a znovu vyvolá po dobu 5 sekund do 1 min. Další informace najdete v tématu [SQL sdružování připojení serveru (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md). Toto chování je problematické pro připojení k databázím Azure SQL, které často dojde k přechodným chybám, které jsou obvykle obnovila během několika sekund. Funkce připojení k fondu blokování znamená, že aplikace nemůže připojit k databázi rozsáhlé dobu, i v případě, že databáze je k dispozici. Toto chování je zvláště problematický pro webové aplikace, které se připojovat k databázím Azure SQL a, které je potřeba vykreslit během několika sekund.  
  
 Počínaje [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], připojení otevřené žádosti o známých databází Azure SQL (*. database.windows.net, \*. database.chinacloudapi.cn, \*. database.usgovcloudapi.net, \*. database.cloudapi.de), Otevřít chyby připojení nejsou uložené v mezipaměti. Pro všechny ostatní pokusy o připojení pokračuje v období blokování fondu připojení vynucení.  
  
## <a name="impact"></a>Dopad  
 Tato změna umožňuje otevřít pokus o připojení k opakovat okamžitě pro Azure SQL Database, následné vylepšení výkonu aplikací povolenou podporu cloudu.  
  
## <a name="mitigation"></a>Zmírnění  
 U aplikací, které jsou této změně nepříznivě ovlivněny doby blokování fond připojení se dá nakonfigurovat nastavení nové <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A?displayProperty=nameWithType> vlastnost.  Hodnota vlastnosti je členem skupiny <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> výčet, který může mít jednu ze tří hodnot:  
  
-   <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>
  
-   <xref:System.Data.SqlClient.PoolBlockingPeriod.Auto?displayProperty=nameWithType>
  
-   <xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock?displayProperty=nameWithType>
  
 Předchozí chování můžete obnovit nastavením <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> vlastnost <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Viz také:
- [Změny v modulu runtime](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
