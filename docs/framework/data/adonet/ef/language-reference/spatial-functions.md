---
title: Prostorové funkce
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 09402633c5e7f591a534992fc92655e6a2d1d88d
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904478"
---
# <a name="spatial-functions"></a>Prostorové funkce
Neexistuje žádný literál formát pro prostorové typy. Můžete však použít kanonické funkce Entity Framework volání pomocí řetězce ve formátu Well-Known Text. Například následující volání funkce vytvoří geometrie bodu:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> Metody mají prostorových canonical metody rozhraní Entity Framework. Klikněte na metodu vás zajímá, zobrazíte, jaké parametry by měly být předány funkci.
