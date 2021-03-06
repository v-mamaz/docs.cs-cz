---
title: Souhrn typů trasování
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 73777df2b58b14947c416ce409bcb42d439499ec
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512535"
---
# <a name="trace-type-summary"></a>Souhrn typů trasování
[Zdrojové úrovně](https://go.microsoft.com/fwlink/?LinkID=94943) definuje různé úrovně trasování: kritické, chyba, upozornění, informace a podrobné, stejně jako obsahuje popis `ActivityTracing` příznak, které přepíná výstup trasování událostí pro přenos hranice a aktivity.  
  
 Můžete také zkontrolovat [parametrem TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) pro typy trasování, které může být generována z <xref:System.Diagnostics>.  
  
 V následující tabulce jsou uvedeny nejdůležitější ty.  
  
|Typ sledování|Popis|  
|----------------|-----------------|  
|Kritická|Závažná chyba nebo aplikaci k chybě.|  
|Chyba|Došlo k opravitelné chybě.|  
|Upozornění|Informační zpráva.|  
|Informace o|Nekritická problém.|  
|verbose|Ladění trasování.|  
|Spustit|Spouští se zpracování logické jednotky.|  
|Pozastavit|Pozastavení logické jednotky zpracování.|  
|Resume|Obnovení logické jednotky zpracování.|  
|Zastavit|Zastavuje se logické jednotky zpracování.|  
|Přenos|Změna identity korelace.|  
  
 Aktivita je definován jako kombinace výše uvedených typů trasování.  
  
 Tady je regulární výraz, který definuje ideální aktivitu v oboru místní (Zdroj trasování)  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 To znamená, že aktivita musí splňovat následující podmínky.  
  
-   Musí začínat a zastavte v uvedeném pořadí spouštění a zastavování trasování  
  
-   Musí mít přenos trasování bezprostředně před pozastavení nebo obnovení činnosti trasování  
  
-   Nesmí mít žádné trasování mezi pozastavit a obnovit trasování, pokud existují tato trasování  
  
-   Tak dlouho, dokud jsou dodržovány předchozích podmínek může mít libovolný a libovolný počet kritických/Chyba/upozornění / / Verbose/přenosu informací trasování  
  
 Tady je regulární výraz, který definuje ideální aktivitu v globálním oboru  
  
```  
R+   
```  
  
 s R se regulární výraz pro aktivitu v místním oboru. Výsledkem je,  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
