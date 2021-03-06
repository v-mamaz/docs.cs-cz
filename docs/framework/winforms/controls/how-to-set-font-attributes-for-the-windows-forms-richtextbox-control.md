---
title: 'Postupy: Nastavení atributů písma pro ovládací prvek Windows Forms RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
ms.openlocfilehash: 92578bd267230f5878bda9533bd117e8f98d8f13
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714681"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>Postupy: Nastavení atributů písma pro ovládací prvek Windows Forms RichTextBox
Windows Forms <xref:System.Windows.Forms.RichTextBox> ovládací prvek má mnoho možností pro formátování textu se zobrazí. Provedením vybrané znaky tučně nebo kurzívy, pomocí <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> vlastnost. Tuto vlastnost můžete také změnit velikost a písmo vybrané znaky. <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> Vlastnost umožňuje změnit barvu vybrané znaky.  
  
### <a name="to-change-the-appearance-of-characters"></a>Chcete-li změnit vzhled znaků  
  
1.  Nastavte <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> vlastnosti k odpovídající písmo.  
  
     Pokud chcete povolit uživatelům nastavit rodina písem, velikost a písmo v aplikaci, obvykle použijete <xref:System.Windows.Forms.FontDialog> komponenty. Přehled najdete v tématu [FontDialog – přehled komponenty](fontdialog-component-overview-windows-forms.md).  
  
2.  Nastavte <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> vlastnost na požadovanou barvu.  
  
     Pokud chcete povolit uživatelům nastavit barvu v aplikaci, obvykle použijete <xref:System.Windows.Forms.ColorDialog> komponenty. Přehled najdete v tématu [ColorDialog – přehled komponenty](colordialog-component-overview-windows-forms.md).  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  Těchto vlastností ovlivní pouze vybraný text nebo, pokud není vybraný žádný text, text, který je zadaný na aktuální pozici kurzoru. Další informace o výběru textu prostřednictvím kódu programu, najdete v článku <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Forms.RichTextBox>
- [Ovládací prvek RichTextBox](richtextbox-control-windows-forms.md)
- [Ovládací prvky používané ve Windows Forms](controls-to-use-on-windows-forms.md)
