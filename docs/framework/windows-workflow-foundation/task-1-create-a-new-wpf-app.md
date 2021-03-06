---
title: 'Úloha 1: Vytvoření nové aplikace Windows Presentation Foundation'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 533b4a1030ab5f47eb96ca62dc2805eae7933b9b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711882"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Úloha 1: Vytvoření nové aplikace Windows Presentation Foundation
Při plnění tohoto úkolu Vytvoření prázdné aplikace Windows Presentation Foundation (WPF) pomocí šablony WPF aplikace Visual Studio a přidejte odkazy na příslušné [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] sestavení pracovních postupů.  
  
### <a name="to-create-the-wpf-application-project"></a>Vytvoření projektu aplikace WPF  
  
1.  Otevřete sadu Visual Studio a na **souboru** nabídky, přejděte k **nový**a potom klikněte na tlačítko **projektu**.  
  
2.  V **nový projekt** dialogové okno Vyberte buď **Visual C#**  nebo **jazyka Visual Basic** z **nainstalované šablony** podokna na levé straně na straně pole. Pokud jazyk podle vašeho výběru se nezobrazí, podívejte se do části **jiné jazyky**.  
  
3.  Vyberte **Windows** v **nainstalované šablony** podokně.  
  
4.  V horním podokně, ujistěte se, že (výchozí hodnota) **rozhraní .NET Framework 4** vybrané v rozevíracím seznamu a pak vyberte **aplikace WPF**.  
  
5.  Nastavte název projekt tak, aby **HostingApplication** v dolní části okna.  
  
6.  Nastavte název řešení **RehostingTheDesigner**.  
  
7.  Klikněte na tlačítko **OK** vytvoření projektu aplikace. Visual Studio vytvoří základní rozhraní WPF pro vaši aplikaci a obsahuje odpovídající XAML a soubory kódu na pozadí.  
  
8.  Přidání odkazů na **WorkflowModel** sestavení. Chcete-li to provést, v **Průzkumníka řešení**, klikněte pravým tlačítkem myši **HostingApplication** projektu a vyberte **přidat odkaz**.  
  
9. V **přidat odkaz** dialogové okno, klikněte na tlačítko **.NET** kartu, podržte stisknutou klávesu CTRL, vyberte následující sestavení a pak klikněte na tlačítko **OK**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Klikněte na **OK**.  
  
11. Zobrazit [úloha 2: Hostování návrháře postupu provádění](task-2-host-the-workflow-designer.md) informace o hostování pracovního postupu návrháře návrhové plátno.  
  
## <a name="see-also"></a>Viz také:
- [Změna hostování Návrháře postupu provádění](rehosting-the-workflow-designer.md)
- [Úloha 2: Hostování návrháře postupu provádění](task-2-host-the-workflow-designer.md)
