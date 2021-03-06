---
title: 'Postupy: Přejděte na stránku'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: a5a0e7a8e7effac7c51f4dee92d30de56d60d90c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369333"
---
# <a name="how-to-navigate-to-a-page"></a>Postupy: Přejděte na stránku
Tento příklad ukazuje několik způsobů, jimiž stránku se dá Navigovat z <xref:System.Windows.Navigation.NavigationWindow>.  
  
## <a name="example"></a>Příklad  
 Je možné, <xref:System.Windows.Navigation.NavigationWindow> přejít na stránku pomocí jedné z následujících akcí:  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A> Vlastnost.  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> Metody.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)] může být relativní nebo absolutní. Další informace najdete v tématu [identifikátory Pack URI v subsystému WPF](pack-uris-in-wpf.md).  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
