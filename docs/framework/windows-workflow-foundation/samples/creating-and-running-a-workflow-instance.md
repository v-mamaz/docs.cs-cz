---
title: Vytvoření a spuštění Instance pracovního postupu
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: d0c59946b6419e7088e3426d7ddd08537cfab5a4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722006"
---
# <a name="creating-and-running-a-workflow-instance"></a>Vytvoření a spuštění Instance pracovního postupu
Tento příklad ukazuje, jak spustit instanci pracovního postupu. Ukazuje, jak k jeho provedení synchronního a asynchronního.  
  
## <a name="demonstrates"></a>Demonstruje  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>Diskuse  
 První část Ukázka používá <xref:System.Activities.WorkflowInvoker.Invoke%2A>. Toto je nejzákladnější možnost pro spuštění pracovního postupu. Pracovní postupy provést s <xref:System.Activities.WorkflowInvoker.Invoke%2A> provádějí synchronně.  
  
 Druhá část Ukázka používá <xref:System.Activities.WorkflowApplication> třídy. <xref:System.Activities.WorkflowApplication> umožňuje mít větší kontrolu nad každou instanci, včetně možnosti pro interakci s běžícím workflowem a pracovní postup spouští asynchronně.  
  
> [!IMPORTANT]
>  Vzorky mohou již být nainstalováno na svém počítači. Před pokračováním zkontrolujte následující adresář (výchozí).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) stáhnout všechny Windows Communication Foundation (WCF) a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky. Tato ukázka se nachází v následujícím adresáři.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>Viz také:
- [Použití WorkflowInvoker a WorkflowApplication](../using-workflowinvoker-and-workflowapplication.md)
