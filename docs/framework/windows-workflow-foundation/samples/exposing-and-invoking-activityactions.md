---
title: "Vystavení a vyvolání ActivityActions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8a87e4463689e9301045a55b16af46cb037c1fa5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="exposing-and-invoking-activityactions"></a>Vystavení a vyvolání ActivityActions
Tento příklad ukazuje, jak vyvíjet vlastní aktivity, který má <xref:System.Activities.ActivityAction>. Také ukazuje, jak tuto aktivitu použijte, tím, že poskytuje implementaci pro <xref:System.Activities.ActivityAction>.  
  
 <xref:System.Activities.ActivityAction> Umožňuje autorovi aktivity vystavit "mezery" s konkrétní podpisy kde aktivity uživatele můžete zařadit vlastní chování. Například <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` aktivitu (který funguje v rámci kolekce položek), má <xref:System.Activities.ActivityAction> umožňuje uživateli aktivity zařaďte chování, které funguje na aktuální iteraci položky.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Pokud chcete nastavit, sestavit a spustit ukázku  
  
1.  Otevřete **ActivityAction.sln** ukázkové řešení v [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Sestavení a spuštění řešení.  
  
> [!IMPORTANT]
>  Ukázky může být již nainstalována na váš počítač. Před pokračováním zkontrolovat na následující adresář (výchozí).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky. Tato ukázka se nachází v následujícím adresáři.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`  
  
## <a name="see-also"></a>Viz také