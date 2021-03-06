---
title: Základní ovládací prvky
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: eb6db63806c4a0e024fcf1c7759a2c7f4487f713
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703067"
---
# <a name="constituent-controls"></a>Základní ovládací prvky
Ovládací prvky, které tvoří uživatelský ovládací prvek nebo *základní ovládací prvky* jsou označovány jako, jsou relativně nepřizpůsobitelným při rozhodování o vykreslování grafiky vlastní. Všechny ovládací prvky Windows Forms zpracovávat své vlastní vykreslování prostřednictvím vlastní <xref:System.Windows.Forms.Control.OnPaint%2A> metody. Vzhledem k tomu, že tato metoda je chráněný, není přístupná pro vývojáře a proto ji nelze zabránit spuštění při vykreslení ovládacího prvku. To neznamená, ale, že nemůžete přidat kód pro vliv na vzhled základních ovládacích prvků. Další vykreslování dosáhnete tak, že přidáte obslužné rutiny události. Předpokládejme například, že byly pro vytváření <xref:System.Windows.Forms.UserControl> s tlačítkem `MyButton`. Pokud jste si přáli mít další vykreslování nad rámec je zadán <xref:System.Web.UI.WebControls.Button>, by přidejte kód do vašeho uživatelského ovládacího prvku podobný následujícímu:  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
>  Ovládací prvky některé formulářů Windows, jako například <xref:System.Windows.Forms.TextBox>, jsou přímo kresleno Windows. V těchto případech <xref:System.Windows.Forms.Control.OnPaint%2A> se nikdy nevolá metodu, a proto výše uvedeném příkladu již nikdy nebudou voláni.  
  
 Tím se vytvoří metodu, která se spustí pokaždé, když `MyButton.Paint` spustí událost, a tím přidáte další grafické vyjádření do ovládacího prvku. Všimněte si, že tím byste nezabránili provádění `MyButton.OnPaint`, a proto všechny Malování obvykle provádí tlačítko bude stále provádět kromě vlastního vykreslování. Podrobnosti o rozhraní GDI + technologie a vlastního vykreslování, najdete v článku [grafické vytváření obrázků pomocí GDI +](../advanced/how-to-create-graphics-objects-for-drawing.md). Pokud budete chtít mít jedinečné reprezentace vašeho ovládacího prvku, je vaší nejlíp zděděný ovládací prvek a napsat kód pro vlastní vykreslování pro něj. Podrobnosti najdete v tématu [ovládací prvky User-Drawn](user-drawn-controls.md).  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Ovládací prvky vykreslované uživatelem](user-drawn-controls.md)
- [Postupy: Vytváření grafických objektů pro kreslení](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Typy vlastních ovládacích prvků](varieties-of-custom-controls.md)
