---
title: 'Postupy: Dědit ze třídy Control'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
ms.openlocfilehash: cf1b3c7d7d530710c4c7e0fbd137667c3598500a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702968"
---
# <a name="how-to-inherit-from-the-control-class"></a>Postupy: Dědit ze třídy Control
Pokud chcete vytvořit zcela vlastní ovládací prvek na formuláři Windows používat, musí dědit z <xref:System.Windows.Forms.Control> třídy. Při dědění z <xref:System.Windows.Forms.Control> třídy vyžaduje, můžete provést další plánování a implementace, také poskytuje největší škálu možností. Při dědění z <xref:System.Windows.Forms.Control>, zdědíte velmi základní funkce, která provádí ovládací prvky fungují. Vyplývajících z funkce <xref:System.Windows.Forms.Control> třída zpracovává vstupu uživatele prostřednictvím klávesnici a myš, definují hranice a velikost ovládacího prvku, poskytuje popisovačů systému windows a poskytuje zpracování zpráv a zabezpečení. Sestavené všechny Malování, který v tomto případě je skutečná vykreslování ovládacího prvku grafického rozhraní, ani nemá začlenit funkce interakce konkrétního uživatele. Je nutné zadat všechny tyto aspekty prostřednictvím vlastního kódu.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-custom-control"></a>Chcete-li vytvořit vlastní ovládací prvek  
  
1.  Vytvořte nový **aplikace Windows** nebo **Knihovna ovládacích prvků Windows** projektu.  
  
2.  Z **projektu** nabídce zvolte **přidat třídu**.  
  
3.  V **přidat novou položku** dialogové okno, klikněte na tlačítko **vlastní ovládací prvek**.  
  
     Nový vlastní ovládací prvek se přidá do vašeho projektu.  
  
4.  Stisknutím klávesy F7 otevřít **Editor kódu** pro vlastní ovládací prvek.  
  
5.  Vyhledejte <xref:System.Windows.Forms.Control.OnPaint%2A> metodu, která bude prázdný s výjimkou volání <xref:System.Windows.Forms.Control.OnPaint%2A> metody základní třídy.  
  
6.  Upravte kód začlenit vlastní vykreslení obsahu, které chcete pro ovládací prvek.  
  
     Informace o psaní kódu pro vykreslení grafiky pro ovládací prvky najdete v tématu [vlastní ovládací prvek Malování a vykreslování](custom-control-painting-and-rendering.md).  
  
7.  Implementujte všechny vlastní metody, vlastnosti nebo události, které bude obsahovat váš ovládací prvek.  
  
8.  Uložit a testování ovládacího prvku.  
  
## <a name="see-also"></a>Viz také:
- [Typy vlastních ovládacích prvků](varieties-of-custom-controls.md)
- [Postupy: Dědit ze třídy UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Postupy: Dědění z existujících Windows Forms ovládacích prvků](how-to-inherit-from-existing-windows-forms-controls.md)
- [Postupy: Autor ovládacích prvků Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Řešení potíží s obslužnými rutinami zděděných událostí v jazyce Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Vývoj ovládacích prvků Windows Forms v době návrhu](developing-windows-forms-controls-at-design-time.md)
