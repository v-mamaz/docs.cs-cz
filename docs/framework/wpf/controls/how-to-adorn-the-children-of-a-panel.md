---
title: 'Postupy: Doplnění podřízených položek panelu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 9f840180edf55c3e10e6859dfc2b9f4b6495b878
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358188"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Postupy: Doplnění podřízených položek panelu
Tento příklad ukazuje, jak prostřednictvím kódu programu připojení doplňku k podřízené položky zadaného <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Příklad  
 K připojení doplňku k podřízených položek <xref:System.Windows.Controls.Panel>, postupujte podle těchto kroků:  
  
1.  Deklarovat nový <xref:System.Windows.Documents.AdornerLayer> objektu a volání `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> metody k vyhledání vrstvu doplněk pro úpravy pro element, jehož potomci mají být opatřený.  
  
2.  Zobrazit výčet prostřednictvím podřízené objekty nadřazeného elementu a volání <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodu připojení doplňku k každý podřízený prvek.  
  
 Následující příklad vytvoří vazbu SimpleCircleAdorner (popsaný výš) do podřízených položek <xref:System.Windows.Controls.StackPanel> s názvem *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  Pomocí [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pro vazbu na jiný prvek pro úpravy v tuto chvíli nepodporuje.  
  
## <a name="see-also"></a>Viz také:
- [Přehled doplňků pro úpravy](adorners-overview.md)
