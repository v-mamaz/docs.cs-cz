---
title: Metody System.Math
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: 45a674c86fc2f19f3e273834b8cb9d6adee5b3ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576860"
---
# <a name="systemmath-methods"></a>Metody System.Math
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nepodporuje následující <xref:System.Math> metody.  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a>Rozdíl oproti .NET  
 Rozhraní .NET Framework má odlišnou sémantiku zaokrouhlení z SQL serveru. <xref:System.Math.Round%2A> Provádí metoda v rozhraní .NET Framework *je bankovní zaokrouhlení*, kde čísla, která končí v.5 zaokrouhlit na nejbližší sudé číslice místo na další vyšší číslo. Například 2.5 zaokrouhlí na 2, zatímco 3.5 zaokrouhlí na 4. (Tento postup pomáhá zabránit systematické Posun směrem k vyšší hodnoty ve velkých objemů dat transakcí.)  
  
 V SQL `ROUND` funkce místo toho vždy zaokrouhlí směrem od 0. Proto 2.5 zaokrouhlí na 3, rozdíly s jeho zaokrouhluje se směrem 2 v rozhraní .NET Framework.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] prochází na SQL `ROUND` sémantiku a nepokusí se implementovat bankovní zaokrouhlení.  
  
## <a name="see-also"></a>Viz také:
- [Datové typy a funkce](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
