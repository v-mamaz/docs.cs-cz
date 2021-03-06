---
title: 'Postupy: Roztažení prvku ToolStripTextBox k zaplnění zbývající šířky prvku ToolStrip (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: 7a557a3d278c2b6d8d083b2ebf8c8129bc498afa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702760"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Postupy: Roztažení prvku ToolStripTextBox k zaplnění zbývající šířky prvku ToolStrip (Windows Forms)
Při nastavení <xref:System.Windows.Forms.ToolStrip.Stretch%2A> vlastnost <xref:System.Windows.Forms.ToolStrip> mít pod kontrolou `true`, ovládací prvek vyplní svého kontejneru od začátku do konce a velikost přizpůsobí svou velikost svého kontejneru. V této konfiguraci, možná bude užitečné k roztahování položku v ovládacím prvku, například <xref:System.Windows.Forms.ToolStripTextBox>, aby vyplnil dostupné místo a pro změnu velikosti při změní velikost ovládacího prvku. Tato roztažení je užitečné, například, pokud chcete dosáhnout vzhled a chování podobný panelu Adresa v aplikaci Microsoft® Internet Explorer.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu obsahuje třídu odvozenou z <xref:System.Windows.Forms.ToolStripTextBox> volá `ToolStripSpringTextBox`. Tato třída přepíše <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> metodu pro výpočet dostupná šířka nadřazené <xref:System.Windows.Forms.ToolStrip> řídit po odečtení kombinované šířku všechny ostatní položky. Tento příklad kódu také poskytuje <xref:System.Windows.Forms.Form> třídy a `Program` třídy, na které si předvedeme nové chování.  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Odkazy na sestavení systému, System.Drawing a System.Windows.Forms.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [Architektura ovládacího prvku ToolStrip](toolstrip-control-architecture.md)
- [Postupy: Interaktivní používání vlastnosti Spring v prvku StatusStrip](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
