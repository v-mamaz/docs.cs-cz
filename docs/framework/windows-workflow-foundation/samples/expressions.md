---
title: Expressions2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43a85905-77b5-4893-bb38-1cb9b293d69d
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c988f41966f6e7bbd87fc4552de15b28117ecde5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="expressions"></a>Výrazy
Tento příklad znázorňuje, jak používat základní výrazy v pracovním postupu. Skládá se z pracovního postupu, který vypočítá Základní mzda statistiky pro dva zaměstnanci fiktivní společnosti. Dvě třídy `Employee` a `SalaryStats`, jsou definovány v Employee.cs a SalaryStats.cs. Tyto třídy se používají v pracovním postupu, který ukazuje, jak provádět jednoduché aritmetické a řetězec operace na vlastnosti proměnných komplexních typů.  
  
 Pracovní postup výpočtu mzda je definován v jazyce XAML i v jazyce C# k předvedení dvě vytváření stylů. Verze XAML se nachází v SalaryCalculation.xaml a jde prohlížet a upravovat v Návrháři pracovních postupů. Verze jazyka C# se nachází v souboru Program.cs. Výrazy použité v jazyce XAML odpovídat syntaxe jazyka Visual Basic a používat <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> a <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> výraz aktivity. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Výrazy jazyka Visual Basic najdete [výrazy jazyka Visual Basic](http://go.microsoft.com/fwlink/?LinkId=165912). Na druhé straně výrazy v jazyce C# se zapisují jako lambda – výrazy a použít <xref:System.Activities.Expressions.LambdaValue%601> a <xref:System.Activities.Expressions.LambdaReference%601> výraz aktivity. Zapisují se výrazy jako výrazy lambda umožňuje zajistit zvýraznění syntaxe kompilátor jazyka C# a statické ověření. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]výrazy lambda v jazyce C#, najdete v části [výrazy Lambda (C# Průvodce programováním)](http://go.microsoft.com/fwlink/?LinkId=182082). Pokud pracovní postup je vytvořené v kódu jazyka Visual Basic, se používají výrazy lambda v jazyce Visual Basic. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]výrazy lambda v jazyce Visual Basic, najdete v části [výrazy Lambda (Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=152437). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]o vytváření pracovních postupů pomocí kódu, najdete v části [vytváření pracovních postupů, aktivity a výrazy pomocí imperativní kód](../../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).  
  
#### <a name="to-run-the-sample"></a>Chcete-li spustit ukázku  
  
1.  Otevřete řešení Expressions.sln v [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Stiskněte kombinaci kláves CTRL + SHIFT + B pro vytvoření řešení, nebo vyberte **sestavit řešení** z **sestavení** nabídky.  
  
    > [!NOTE]
    >  Otevřete SalaryCalculation.xaml v návrháři Visual Studio, musíte napřed zkompilovat projektu zajistit, aby `Employee` a `SalaryStats` třídy jsou k dispozici pro návrháře.  
  
3.  Po sestavení proběhla úspěšně, stiskněte klávesu F5, nebo vyberte **spustit ladění** z **ladění** nabídky. Případně můžete stisknutím kláves Ctrl + F5 nebo vybrat **spustit bez ladění** z **ladění** nabídku spustit bez ladění.  
  
> [!IMPORTANT]
>  Ukázky může být již nainstalován ve vašem počítači. Před pokračováním zkontrolovat na následující adresář (výchozí).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky. Tato ukázka se nachází v následujícím adresáři.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Expressions`  
  
## <a name="see-also"></a>Viz také