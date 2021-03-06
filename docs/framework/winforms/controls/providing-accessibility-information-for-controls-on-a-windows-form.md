---
title: Poskytování informací o usnadnění pro ovládací prvky ve formuláři Windows
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 976aff327a5212c181d455bab1cdc84f98d75a2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540910"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a>Poskytování informací o usnadnění pro ovládací prvky ve formuláři Windows
Usnadnění jsou specializované programy a zařízení, která pomůže uživatelům s postižením používání počítačů efektivněji. Mezi příklady patří čtečky obrazovky pro uživatele, kteří jsou blind a způsobu vyjadřování vstupní nástroje pro uživatele, kteří poskytují slovní příkazy místo pomocí myši nebo klávesnice. Tyto usnadnění interakci s usnadnění vlastností vystavovaných třídami ovládacích prvků Windows Forms. Tyto vlastnosti jsou:  
  
-   **AccessibilityObject**  
  
-   **AccessibleDefaultActionDescription**  
  
-   **AccessibleDescription**  
  
-   **AccessibleName**  
  
-   **AccessibleRole**  
  
## <a name="accessibilityobject-property"></a>Vlastnost AccessibilityObject  
 Tato vlastnost jen pro čtení obsahuje <xref:System.Windows.Forms.AccessibleObject> instance. **Třída AccessibleObject** implementuje <xref:Accessibility.IAccessible> rozhraní, který poskytuje informace o popis ovládacího prvku, umístění na obrazovce, navigační schopnosti a hodnotu. Návrhář nastaví tuto hodnotu, pokud ovládací prvek je přidán do formuláře.  
  
## <a name="accessibledefaultactiondescription-property"></a>Vlastnost AccessibleDefaultActionDescription  
 Tento řetězec popisuje akci ovládacího prvku. V okně Vlastnosti se nezobrazí a může být nastavena pouze v kódu. Následující příklad nastaví tuto vlastnost pro ovládací prvek tlačítka:  
  
```  
' Visual Basic  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
  
// C#  
Button1.AccessibleDefaultActionDescription =   
   "Closes the application.";  
  
// C++  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a>Vlastnost AccessibleDescription  
 Tento řetězec popisuje ovládací prvek. To může být nastavena v okně Vlastnosti, nebo v kódu následujícím způsobem:  
  
```  
' Visual Basic  
Button1.AccessibleDescription = "A button with text 'Exit'."  
  
// C#  
Button1.AccessibleDescription = "A button with text 'Exit'";  
  
// C++  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a>Vlastnost AccessibleName  
 Toto je název ovládacího prvku ohlášených pro usnadnění. To může být nastavena v okně Vlastnosti, nebo v kódu následujícím způsobem:  
  
```  
' Visual Basic  
Button1.AccessibleName = "Order"  
  
// C#  
Button1.AccessibleName = "Order";  
  
// C++  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a>Vlastnost AccessibleRole  
 Tuto vlastnost, která obsahuje <xref:System.Windows.Forms.AccessibleRole> výčet, popisuje role uživatele rozhraní ovládacího prvku. Nový ovládací prvek je nastavena hodnota `Default`. To znamená, že ve výchozím nastavení, **tlačítko** ovládací prvek funguje jako **tlačítko**. Chcete resetovat tuto vlastnost, pokud ovládací prvek obsahuje jiné role. Například využíváte **PictureBox** ovládací prvek jako **grafu**, a může být vhodné usnadnění hlášení role jako **grafu**, ne jako **ovládací prvek PictureBox** . Můžete také určit tuto vlastnost u vlastních ovládacích prvků, které jste vytvořili. Tato vlastnost může být nastavena v okně Vlastnosti, nebo v kódu následujícím způsobem:  
  
```  
' Visual Basic  
PictureBox1.AccessibleRole = AccessibleRole.Chart  
  
// C#  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
  
// C++  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
