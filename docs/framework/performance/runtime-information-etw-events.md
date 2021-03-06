---
title: Události Trasování událostí pro Windows běhových informací
ms.date: 03/30/2017
helpviewer_keywords:
- runtime information events [.NET Framework]
- ETW, runtime information events
ms.assetid: 68b4edbc-7f3b-45f6-ab75-4fd066d6af9a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb213ef4a335cf6784c2889cd9cf0214a1411da2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735711"
---
# <a name="runtime-information-etw-events"></a>Události Trasování událostí pro Windows běhových informací
Informace o modulu runtime, včetně SKU, číslo verze, způsobem, ve kterém se aktivovala modul runtime, parametry příkazového řádku, který byl spuštěn s GUID (Pokud je k dispozici) a další relevantní informace protokolu tyto události trasování událostí pro Windows. Pokud různými moduly runtime jsou spuštěny v rámci procesu, tyto události (ClrInstanceID) na základě informací poskytnutých pomáhá rozlišit modulů runtime.  
  
 V následující tabulce jsou uvedeny dvě události běhových informací. Události může být vyvolána v rámci žádné klíčové slovo nebo masky. (Další informace najdete v tématu [CLR ETW – klíčová slova a úrovně](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Událost|ID události|Poskytovatel|Popis|  
|-----------|--------------|--------------|-----------------|  
|`RuntimeInformationEvent`|187|CLRRuntime|Vyvolá se při načtení modulu runtime.|  
|`RuntimeInformationDCStart`|187|CLRRundown|Vytvoří výčet modulů runtime, které jsou načteny.|  
  
 Následující tabulka zobrazuje data událostí.  
  
|Název pole|Datový typ|Popis|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:UInt16|Jedinečné ID instance CLR nebo CoreCLR.|  
|Sku|win:UInt16|1 – desktop CLR.<br /><br /> 2 – CoreCLR.|  
|BclVersion – hlavní verze|win:UInt16|Major version of mscorlib.dll.|  
|BclVersion – vedlejší verze aktualizace|win:UInt16|Číslo podverze souboru mscorlib.dll.|  
|BclVersion – číslo sestavení|win:UInt16|Číslo knihovny mscorlib.dll sestavení.|  
|BclVersion – oprava QFE|win:UInt16|Oprava hotfix číslo verze souboru mscorlib.dll.|  
|VMVersion – hlavní verze|win:UInt16|Verze clr.dll nebo coreclr.dll, v závislosti na SKU.|  
|VMVersion – vedlejší verze aktualizace|win:UInt16|Podverze clr.dll nebo coreclr.dll, v závislosti na SKU.|  
|VMVersion – číslo sestavení|win:UInt16|Číslo clr.dll nebo coreclr.dll sestavení.|  
|VMVersion – oprava QFE|win:UInt16|Oprava hotfix číslo verze clr.dll nebo coreclr.dll.|  
|StartupFlags|win:UInt32|Po spuštění příznaky definované v mscoree.h.|  
|StartupMode|win:UInt8|0x01 - spravované spustitelný soubor.<br /><br /> 0x02 - Hosted CLR.<br /><br /> 0x04 - C++ spravovaného zprostředkovatele komunikace s objekty.<br /><br /> 0x08 - COM aktivována.<br /><br /> 0x10 – ostatní.|  
|příkazový řádek|win:UnicodeString|Pouze v případě nenulovou StartupMode = 0x01.|  
|ComObjectGUID|win:GUID|Pouze v případě nenulovou StartupMode = 0x08.|  
|RuntimeDLLPath|win:UnicodeString|Cesta k souboru DLL modulu CLR, který byl načten do procesu.|  
  
## <a name="see-also"></a>Viz také:
- [Události Trasování událostí pro Windows v CLR](../../../docs/framework/performance/clr-etw-events.md)
