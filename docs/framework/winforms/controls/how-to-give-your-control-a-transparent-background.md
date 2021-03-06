---
title: 'Postupy: Zadejte svůj ovládací prvek průhledné pozadí'
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: 5a54b76eb92c7d3f518b9bf13e154e6faf58de63
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718165"
---
# <a name="how-to-give-your-control-a-transparent-background"></a>Postupy: Zadejte svůj ovládací prvek průhledné pozadí
V dřívějších verzích rozhraní .NET Framework, ovládací prvky nepodporoval nastavení transparentní backcolors bez první nastavení <xref:System.Windows.Forms.Control.SetStyle%2A> metoda v konstruktoru formulářích. V aktuální verzi rozhraní framework backcolor pro většinu ovládacích prvků lze nastavit na <xref:System.Drawing.Color.Transparent%2A> v **vlastnosti** okno v době návrhu nebo v kódu v konstruktoru formuláře.  
  
> [!NOTE]
>  Ovládací prvky Windows Forms nepodporují true průhlednost. Na pozadí ovládacího prvku Windows Forms transparentní kresleno svého nadřazeného objektu.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Button> Ovládací prvek nepodporuje průhlednou barvu backcolor i v případě <xref:System.Windows.Forms.ButtonBase.BackColor%2A> je nastavena na <xref:System.Drawing.Color.Transparent%2A>.  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a>Poskytnout průhlednou barvu backcolor ovládacího prvku  
  
-   V okně Vlastnosti zvolte <xref:System.Windows.Forms.ButtonBase.BackColor%2A> vlastnost a nastavte ho na <xref:System.Drawing.Color.Transparent%2A>  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Drawing.Color.FromArgb%2A>
- [Vývoj vlastních ovládacích prvků Windows Forms pomocí rozhraní .NET Framework](developing-custom-windows-forms-controls.md)
- [Použití spravovaných grafických tříd](../advanced/using-managed-graphics-classes.md)
- [Postupy: Kreslení neprůhledných a poloprůhledných čar](../advanced/how-to-draw-opaque-and-semitransparent-lines.md)
