---
title: 'Postupy: Určete, jestli je stránka hostovaná prohlížečem'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: ebc5612f059a6cf26f2568bbc08e705b4b3014c1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359988"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>Postupy: Určete, jestli je stránka hostovaná prohlížečem
Tento příklad ukazuje, jak zjistit, jestli <xref:System.Windows.Controls.Page> je hostována v prohlížeči.  
  
## <a name="example"></a>Příklad  
 A <xref:System.Windows.Controls.Page> může být nezávislá na hostitele a v důsledku toho může být načtena do několika různých typů hostitele, včetně <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, nebo v prohlížeči. K tomu může dojít, když máte sestavení knihovny, která obsahuje jednu nebo více stránek a která je odkazovaná více samostatná a nelze procházet ([!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]) hostování aplikací.  
  
 Následující příklad ukazuje, jak používat <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> k určení, zda <xref:System.Windows.Controls.Page> je hostována v prohlížeči.  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
