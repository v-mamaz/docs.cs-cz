---
title: System.DateTimeOffset metody
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25b3e5c0-7603-4a70-b3e5-2149e3da69a2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: cbcd2af0b06eeb85c30c8a451877f5913e5d89e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="systemdatetimeoffset-methods"></a>System.DateTimeOffset metody
Jakmile namapovány v modelu objektu nebo externí mapování souboru, technologie LINQ to SQL umožňuje volat většinu <xref:System.DateTimeOffset?displayProperty=nameWithType> metody, operátory a vlastnosti z vaší LINQ dotazy SQL.  
  
 Pouze metody není podporované jsou tyto zděděné z <xref:System.Object?displayProperty=nameWithType> , smysl v kontextu LINQ dotazy SQL, jako například: `Finalize`, `GetHashCode`, `GetType`, a `MemberwiseClone`. Tyto metody nejsou podporovány, protože technologie LINQ to SQL nemůže překládat pro spuštění systému SQL Server.  
  
> [!NOTE]
>  Modul CLR (CLR) <xref:System.DateTimeOffset?displayProperty=nameWithType> strukturu a možnost mapovat SQL `DATETIMEOFFSET` sloupec s technologie LINQ to SQL, vyžaduje rozhraní .NET Framework 3.5 SP1 nebo novější. SQL `DATETIMEOFFSET` sloupec je k dispozici v systému Microsoft SQL Server 2008 a nad rámec.  
  
## <a name="sqlmethods-date-and-time-methods"></a>SQLMethods datum a čas metody  
 Kromě metod, které nabízí <xref:System.DateTimeOffset> struktura, technologie LINQ to SQL nabízí metody uvedené v následující tabulce z <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> třídy pro práci s datum a čas.  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a>Viz také  
 [Koncepty dotazu](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [Vytváření objektový Model](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [Mapování typu SQL CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)