---
title: 'Postupy: Poskytnutí dialogového okna průběhu pro operace se soubory – C# Průvodce programováním'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: 462da68313fea19e5b89a9e2f5221f6659338e98
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975040"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a>Postupy: Poskytnutí dialogového okna průběhu pro operace se soubory (C# Průvodce programováním v)
Můžete zadat standardní dialogové okno, který znázorňuje průběh operací se soubory ve Windows, pokud použijete <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> metodu <xref:Microsoft.VisualBasic?displayProperty=nameWithType> oboru názvů.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a>Chcete-li přidat odkaz v sadě Visual Studio  
  
1.  V panelu nabídky zvolte **projektu**, **přidat odkaz**.  
  
     **Správce odkazů** zobrazí se dialogové okno.  
  
2.  V **sestavení** oblasti, zvolte **Framework** Pokud není již vybrána.  
  
3.  Vyberte v seznamu názvů **Microsoft.VisualBasic** zaškrtněte políčko a klikněte na tlačítko **OK** tlačítka zavřete dialogové okno.  
  
## <a name="example"></a>Příklad  
 Následující kód zkopíruje adresář, který `sourcePath` určuje do adresáře, který `destinationPath` určuje. Tento kód také poskytuje standardní dialogové okno zobrazující odhadovanou výši zbývajícího času před dokončením operace.  
  
 [!code-csharp[csFilesandFolders#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#11)]  
  
## <a name="see-also"></a>Viz také:

- [Systém souborů a registr (C# Programming Guide)](../../../csharp/programming-guide/file-system/index.md)
