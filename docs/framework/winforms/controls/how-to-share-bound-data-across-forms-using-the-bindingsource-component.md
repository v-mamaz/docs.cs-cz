---
title: 'Postupy: Sdílení vázaných dat mezi formuláři pomocí komponenty BindingSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: b01c07208d796044e015b9c64e6414519862d4fb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709026"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a>Postupy: Sdílení vázaných dat mezi formuláři pomocí komponenty BindingSource
Data můžete jednoduše sdílet mezi formuláři pomocí <xref:System.Windows.Forms.BindingSource> komponenty. Chcete třeba zobrazit jeden formulář jen pro čtení, která shrnuje data zdroje dat a jiné Upravitelný formulář, který obsahuje podrobné informace o aktuálně vybrané položky ve zdroji dat. Tento příklad ukazuje tento scénář.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak sdílet <xref:System.Windows.Forms.BindingSource> a vázaných dat mezi formuláři. V tomto příkladu, sdílený <xref:System.Windows.Forms.BindingSource> je předán konstruktoru podřízeného formuláře. Podřízený formulář umožňuje uživateli upravit data pro aktuálně vybrané položky v hlavním formuláři.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.BindingSource.BindingComplete> Událost pro <xref:System.Windows.Forms.BindingSource> komponenta je zpracována v příklad k zajištění toho, že dvě různými formami zůstaly synchronizované. Další informace o tom, proč se to, najdete v článku [jak: Zajištění více ovládacích prvků vázaných ke stejnému zdroji dat zůstalo synchronizovaných](../multiple-controls-bound-to-data-source-synchronized.md).  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Odkazy na sestavení systému, System.Windows.Forms, System.Drawing, System.Data a System.Xml.  
  
 Informace o vytváření tento příklad z příkazového řádku pro Visual Basic nebo Visual C# najdete v tématu [sestavení z příkazového řádku](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) nebo [sestavení pomocí příkazového řádku csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Tento příklad v sadě Visual Studio můžete také vytvořit vložením kódu do nového projektu.  
  
## <a name="see-also"></a>Viz také:
- [Komponenta BindingSource](bindingsource-component.md)
- [Windows Forms – datová vazba](../windows-forms-data-binding.md)
- [Postupy: Zpracování chyb a výjimek, ke kterým dochází s datovou vazbou](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
