---
title: 'Postupy: Čtení z textových souborů ve více formátech v jazyce Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, reading from a file
- TextFieldType enumeration
- My.Computer.FileSystem.WriteAllText method, parsing structured text files
- WriteAllText method [Visual Basic], parsing structured text files
- PeekChars method [Visual Basic], determining format of text
- reading text files [Visual Basic], multiple formats
- I/O [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
ms.openlocfilehash: 589b5f94358cf9ce58e47a8a0eaec187aface98d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56964744"
---
# <a name="how-to-read-from-text-files-with-multiple-formats-in-visual-basic"></a>Postupy: Čtení z textových souborů ve více formátech v jazyce Visual Basic
<xref:Microsoft.VisualBasic.FileIO.TextFieldParser> Objekt poskytuje způsob, jak snadno a efektivně analýza strukturovaných textových souborů, jako jsou protokoly. Můžete zpracovat soubor ve více formátech s použitím `PeekChars` metoda určit formát každý řádek v souboru.  
  
### <a name="to-parse-a-text-file-with-multiple-formats"></a>Analyzovat textového souboru ve více formátech  
  
1.  Přidání textového souboru s názvem testfile.txt do vašeho projektu. Do textového souboru přidejte následující obsah.  
  
    ```  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2.  Definování očekávaný formát a použít, když dojde k chybě. Poslední položka v každé pole je -1, proto poslední pole je předpokládá se, že proměnné šířky. K tomu dojde, když poslední položky v poli je menší než nebo rovna 0.  
  
     [!code-vb[VbFileIORead#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#4)]  
  
3.  Vytvořte nový <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> objekt definováním šířku a formátu.  
  
     [!code-vb[VbFileIORead#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#5)]  
  
4.  Projít řádky testování formát před čtením.  
  
     [!code-vb[VbFileIORead#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#6)]  
  
5.  Chyby zápisu do konzoly.  
  
     [!code-vb[VbFileIORead#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#7)]  
  
## <a name="example"></a>Příklad  
 Následuje Úplný příklad, který čte ze souboru `testfile.txt`.  
  
 [!code-vb[VbFileIORead#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a>Robustní programování  
 Následující podmínky mohou způsobit výjimku:  
  
-   Řádek nelze analyzovat pomocí určeného formátu (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). Zpráva o výjimce určuje řádek, který způsobil výjimku, a <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> vlastnost je přiřazena k obsažené v řádku textu.  
  
-   Zadaný soubor neexistuje (<xref:System.IO.FileNotFoundException>).  
  
-   Stav částečným vztahem důvěryhodnosti, ve kterém uživatel nemá dostatečná oprávnění pro přístup k souboru. (<xref:System.Security.SecurityException>).  
  
-   Cesta je příliš dlouhá (<xref:System.IO.PathTooLongException>).  
  
-   Uživatel nemá dostatečná oprávnění pro přístup k souboru (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Viz také:
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>
- <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>
- [Postupy: Čtení z textových souborů s oddělovačem čárkou](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [Postupy: Čtení z souborů s pevnou šířkou](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [Analýza textových souborů pomocí objektu TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
