---
title: 'Postupy: Použití animací na text'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: e62c8288460206e7ebfbc18787bd9c2f2144a5bc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356959"
---
# <a name="how-to-apply-animations-to-text"></a>Postupy: Použití animací na text
Animace lze změnit vzhled textu ve vaší aplikaci a zobrazení. Následující příklady používají různé typy animací ovlivnit zobrazení textu v <xref:System.Windows.Controls.TextBlock> ovládacího prvku.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá <xref:System.Windows.Media.Animation.DoubleAnimation> pro animaci šířka textový blok. Hodnotu šířky změní z šířka textový blok na 0 průběhu 10 sekund a pak vrátí šířku hodnoty a pokračuje. Tento typ animace vytvoří částicový efekt vymazání.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 Následující příklad používá <xref:System.Windows.Media.Animation.DoubleAnimation> do animace krytí textový blok. Hodnota neprůhlednosti změní z 1.0 na 0 průběhu 5 sekund a potom vrátí hodnoty neprůhlednosti a pokračuje.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 Následující diagram znázorňuje vliv <xref:System.Windows.Controls.TextBlock> změna jeho neprůhlednost z ovládacího prvku `1.00` k `0.00` během 5 sekund intervalu definovaném <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 ![Textové změny krytí z 1,00 na 0,00](./media/fadedtext01.png "FadedText01")  
Změna z 1,00 0,00 krytí textu  
  
 Následující příklad používá <xref:System.Windows.Media.Animation.ColorAnimation> pro animaci barvu popředí bloku textu. Hodnota barvy popředí změní z jednu barvu na barvu druhé průběhu 5 sekund a potom obrátí hodnot barev a bude pokračovat.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 Následující příklad používá <xref:System.Windows.Media.Animation.DoubleAnimation> obměna textový blok. Textový blok provede úplné otočení průběhu 20 sekund a poté pokračuje opakovat otočení.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>Viz také:
- [Přehled animace](../graphics-multimedia/animation-overview.md)
