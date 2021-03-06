---
title: Vstupní znaková sada (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
ms.openlocfilehash: 7bed10f6e4a9fb01abe825e5eb798da2d866ca84
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976756"
---
# <a name="input-character-set-entity-sql"></a>Vstupní znaková sada (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] přijímá zakódován do kódování UTF-16 znaků UNICODE.  
  
 Řetězcové literály může obsahovat libovolný UTF-16 znak uzavřen v jednoduchých uvozovkách. Například N "文字列リテラル". Srovnání řetězcové literály se používají původní hodnoty UTF-16. Například N'ABC "se liší v japonštině a latinky kódové stránky.  
  
 Komentáře mohou obsahovat libovolný znak kódování UTF-16.  
  
 Identifikátory uvozené uvozovacími znaky může obsahovat libovolný znak kódování UTF-16 uzavřeny do hranatých závorek. Například [エスケープされた識別子]. Porovnání identifikátory UTF-16 uvozen řídicími znaky, velká a malá písmena. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zpracovává verzích zpravodaje, které se zobrazí stejná, ale jsou z různých znakových stránek jako jiné znaky. Například [ABC] odpovídá [abc] Pokud odpovídající znaky jsou od stejné znakové stránky. Nicméně pokud dva stejné identifikátory jsou z různých znakových stránek, nejsou ekvivalentní.  
  
 Prázdné místo je libovolný znak bílého prostoru řádku UTF-16.  
  
 Nový řádek je všechny normalizované znak nového řádku UTF-16. Například "\n" a "\r\n" jsou považovány za znaky nového řádku, ale '\r; není znak nového řádku.  
  
 Klíčová slova, výrazy a interpunkční znaménka, může být libovolný znak UTF-16, které normalizuje do latiny. Například vyberte v japonské znaková stránka je platný – klíčové slovo.  
  
 Klíčová slova, výrazy a interpunkční znaménka lze pouze znaky latinky. `SELECT` v japonské znakové stránce není klíčové slovo. +,-, \*, /, =, (,), ", [,] a jiné jazykové konstrukce není v uvozovkách zde lze pouze znaky latinky.  
  
 Jednoduché identifikátory lze pouze znaky latinky. Tím se vyhnete nejednoznačnosti při porovnání, protože jsou porovnány původní hodnoty. ABC například bude v japonštině a latinky kódové stránky liší.  
  
## <a name="see-also"></a>Viz také:
- [Přehled Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
