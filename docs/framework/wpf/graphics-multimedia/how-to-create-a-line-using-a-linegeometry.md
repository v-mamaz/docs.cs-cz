---
title: 'Postupy: Vytvoření čáry použitím LineGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: 6d5d0b413f940a2c7f70e05135ff070c1fe5ba21
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374658"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a>Postupy: Vytvoření čáry použitím LineGeometry
Tento příklad ukazuje způsob použití <xref:System.Windows.Media.LineGeometry> tříd k popisu řádku. A <xref:System.Windows.Media.LineGeometry> je definován tak, že jeho počáteční a koncové body.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak vytvořit a vykreslování <xref:System.Windows.Media.LineGeometry>.  A <xref:System.Windows.Shapes.Path> element slouží k vykreslení řádku.  Protože řádku nemá žádné oblasti <xref:System.Windows.Shapes.Path> objektu <xref:System.Windows.Shapes.Shape.Fill%2A> nezadáte; místo toho <xref:System.Windows.Shapes.Shape.Stroke%2A> a <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> vlastnosti jsou používány.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
LineGeometry vykreslovány z (10,20) (100,130)  
  
 Zahrnout další jednoduché geometrické třídy <xref:System.Windows.Media.LineGeometry> a <xref:System.Windows.Media.EllipseGeometry>. Tyto geometrie, jakož i složitější ty lze také vytvořit pomocí <xref:System.Windows.Media.PathGeometry> nebo <xref:System.Windows.Media.StreamGeometry>. Další informace najdete v tématu [přehled geometrie](geometry-overview.md).  
  
## <a name="see-also"></a>Viz také:
- [Přehled geometrie](geometry-overview.md)
- [Vytvoření složeného tvaru](how-to-create-a-composite-shape.md)
- [Vytvoření tvaru pomocí PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
