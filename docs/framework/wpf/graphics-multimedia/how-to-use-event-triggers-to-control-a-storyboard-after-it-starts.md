---
title: 'Postupy: Použití aktivačních procedur událostí pro řízení scénáře po spuštění'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: d0b25f56caf3f25b6e649c05ecf1cbe50046dd93
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362367"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Postupy: Použití aktivačních procedur událostí pro řízení scénáře po spuštění
Tento příklad ukazuje, jak řídit <xref:System.Windows.Media.Animation.Storyboard> po jeho spuštění. Spustit <xref:System.Windows.Media.Animation.Storyboard> pomocí [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], použijte <xref:System.Windows.Media.Animation.BeginStoryboard>, který distribuuje animace objektů a vlastností animace a pak spustí scénáři. Pokud dáte <xref:System.Windows.Media.Animation.BeginStoryboard> název tak, že zadáte jeho <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> vlastnost, provedete to může ovládat scénáře. Pak můžete interaktivně ovládat scénáře po jeho spuštění.  
  
 Použijte následující scénáře akce spolu s <xref:System.Windows.EventTrigger> objekty pro řízení scénáře.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Pozastaví scénáři.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Obnoví pozastavenou scénáře.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Změní rychlost scénáře.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Pokročilé funkce scénáře do konce doby výplň, má-li nějaký.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Zastaví scénáři.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Odebere scénáři uvolnit prostředky.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá akce může ovládat scénáře pro interaktivní řízení scénáře.  
  
 **Poznámka:** Příklad scénáře řízení pomocí kódu najdete v tématu [řízení scénáře po jeho spuštění pomocí její interaktivní metody](how-to-control-a-storyboard-after-it-starts.md).  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 Další příklady najdete v článku [animace příkladu Galerie](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [Kontrola scénáře po jeho spuštění pomocí interaktivních metod](how-to-control-a-storyboard-after-it-starts.md)
- [Přehled animace](animation-overview.md)
- [Přehled scénářů](storyboards-overview.md)
