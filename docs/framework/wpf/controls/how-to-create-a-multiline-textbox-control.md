---
title: 'Postupy: Vytvoření víceřádkového ovládacího prvku TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 75bbee806b2b7039656d6c8e7c9a64359e77d16f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352344"
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Postupy: Vytvoření víceřádkového ovládacího prvku TextBox
Tento příklad ukazuje způsob použití [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] k definování <xref:System.Windows.Controls.TextBox> ovládací prvek, který se rozbalí automaticky tak, aby vyhovovaly více řádků textu.  
  
## <a name="example"></a>Příklad  
 Nastavení <xref:System.Windows.Controls.TextBox.TextWrapping%2A> atribut **zabalení** způsobí, že zadaný text zabalit do nového řádku na okraj <xref:System.Windows.Controls.TextBox> ovládací prvek je dosaženo, automatické rozbalování <xref:System.Windows.Controls.TextBox> ovládacího prvku zahrnout místa pro nový řádek, pokud nezbytné.  
  
 Nastavení <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> atribut **true** způsobí, že nový řádek má být vložen při stisknutí klávesy RETURN, znovu automaticky rozšiřuje <xref:System.Windows.Controls.TextBox> zahrnout místa pro nový řádek, v případě potřeby.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> Přidá posuvník pro atribut <xref:System.Windows.Controls.TextBox>tak, aby obsah <xref:System.Windows.Controls.TextBox> posunout Pokud <xref:System.Windows.Controls.TextBox> rozbalí nad rámec velikost rámu nebo okna, který ji obklopuje.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.TextWrapping>
- [TextBox – přehled](textbox-overview.md)
- [RichTextBox – přehled](richtextbox-overview.md)
