---
title: 'Postupy: Oříznutí a změna měřítka obrázků'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 95343ad2c7bc6a83bc4d935f33712ab910d658ff
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705815"
---
# <a name="how-to-crop-and-scale-images"></a>Postupy: Oříznutí a změna měřítka obrázků
<xref:System.Drawing.Graphics> Třída poskytuje několik <xref:System.Drawing.Graphics.DrawImage%2A> metody, některé z nich mají zdrojové a cílové parametry obdélníku, které slouží k oříznutí a změna měřítka obrázků.  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří <xref:System.Drawing.Image> objekt ze souboru na disku Apple.gif. Kód v původní velikost nakreslí obrázek celý apple. Kód poté volá <xref:System.Drawing.Graphics.DrawImage%2A> metodu <xref:System.Drawing.Graphics> objektů pro kreslení část obrázku apple v cílového obdélníku, který je větší než původní obrázek apple.  
  
 <xref:System.Drawing.Graphics.DrawImage%2A> Metoda určuje, jaká část apple k vykreslení zobrazením zdrojového obdélníku, který je určený třetí, čtvrtý, pátý a šestý argument. V takovém případě je apple ořízne na 75 procent šířku a výšku 75 procent.  
  
 <xref:System.Drawing.Graphics.DrawImage%2A> Metoda určuje, kde stanovit oříznutý apple a jak velký aby oříznutý apple zobrazením cílového obdélníku, který je zadaný v druhém argumentu. V tomto případě cílového obdélníku je 30 procent širší a vyšší než původní obrázek 30 procent.  
  
 Následující obrázek znázorňuje původní apple a škálovanou, oříznuté apple.  
  
 ![Crop & Scale](./media/cscropscale1.png "csCropScale1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 V předchozím příkladu je určený k použití pomocí Windows Forms a vyžaduje <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.Control.Paint> obslužné rutiny události. Nezapomeňte nahradit `Apple.gif` název souboru bitové kopie a cestu, která jsou platné ve vašem systému.  
  
## <a name="see-also"></a>Viz také:
- [Obrázky, rastrové obrázky a metasoubory](images-bitmaps-and-metafiles.md)
- [Práce s obrázky, rastrovými obrázky, ikonami a metasoubory](working-with-images-bitmaps-icons-and-metafiles.md)
