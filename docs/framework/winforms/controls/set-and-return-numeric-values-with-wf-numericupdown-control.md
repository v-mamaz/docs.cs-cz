---
title: 'Postupy: Nastavení a vracení číselných hodnot pomocí ovládacího prvku Windows Forms NumericUpDown'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: 166b14fca2009d0609fa48a5f07912b33f074071
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703198"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>Postupy: Nastavení a vracení číselných hodnot pomocí ovládacího prvku Windows Forms NumericUpDown
Číselná hodnota prvku modelu Windows Forms <xref:System.Windows.Forms.NumericUpDown> ovládací prvek je dáno jeho <xref:System.Windows.Forms.NumericUpDown.Value%2A> vlastnost. Stejně jako u jakékoli jiné vlastnosti můžete psát podmíněného testy pro hodnotu ovládacího prvku. Jednou <xref:System.Windows.Forms.NumericUpDown.Value%2A> je hodnota nastavena, můžete upravit přímo napsáním kódu k provádění operací na něj nebo můžete volat <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> a <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> metody.  
  
### <a name="to-set-the-numeric-value"></a>Chcete-li nastavit číselnou hodnotu  
  
1.  Přiřaďte hodnotu <xref:System.Windows.Forms.NumericUpDown.Value%2A> vlastností v kódu nebo v okně Vlastnosti.  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     -nebo-  
  
2.  Volání <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> nebo <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> metoda chcete zvýšit nebo snížit hodnotu zadanou v <xref:System.Windows.Forms.NumericUpDown.Increment%2A> vlastnost.  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a>Vrátit číselnou hodnotu  
  
-   Přístup <xref:System.Windows.Forms.NumericUpDown.Value%2A> vlastností v kódu.  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [Ovládací prvek NumericUpDown](numericupdown-control-windows-forms.md)
- [Přehled ovládacího prvku NumericUpDown](numericupdown-control-overview-windows-forms.md)
