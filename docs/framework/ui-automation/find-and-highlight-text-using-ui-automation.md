---
title: Hledání a zvýrazňování textu s použitím automatizace uživatelského rozhraní
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: a0df93b153f16dd09dfcc6da5d690dc69141435a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2019
ms.locfileid: "57673701"
---
# <a name="find-and-highlight-text-using-ui-automation"></a>Hledání a zvýrazňování textu s použitím automatizace uživatelského rozhraní
> [!NOTE]
>  Tato dokumentace je určená pro vývojáře rozhraní .NET Framework, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tříd definovaných v <xref:System.Windows.Automation> oboru názvů. Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], naleznete v tématu [Windows Automation API: Automatizace uživatelského rozhraní](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Toto téma ukazuje, jak se postupně vyhledat a zvýraznit všechny výskyty řetězce v rámci obsahu textu ovládacího prvku pomocí [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].  
  
## <a name="example"></a>Příklad  
 Následující příklad získá <xref:System.Windows.Automation.TextPattern> objekt z textového ovládacího prvku. A <xref:System.Windows.Automation.Text.TextPatternRange> objekt představující textový obsah celý dokument se pak vytvoří pomocí <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> vlastnosti tohoto <xref:System.Windows.Automation.TextPattern>. Další dva <xref:System.Windows.Automation.Text.TextPatternRange> objekty jsou pak vytvořeny pro sekvenčního vyhledávání a zvýraznit funkce.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a>Viz také:
- [Hledání a zvýrazňování textu s použitím automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
