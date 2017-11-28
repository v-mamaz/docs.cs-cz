---
title: "LINQ a souborové adresáře (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 470ad8e783eb05cc56949982b2d2d79d5aaefdc2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="linq-and-file-directories-visual-basic"></a><span data-ttu-id="a2e78-102">LINQ a souborové adresáře (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2e78-102">LINQ and File Directories (Visual Basic)</span></span>
<span data-ttu-id="a2e78-103">Mnoho operace souborového systému jsou v podstatě dotazy a jsou proto vhodné řešení pro LINQ přístup.</span><span class="sxs-lookup"><span data-stu-id="a2e78-103">Many file system operations are essentially queries and are therefore well-suited to the LINQ approach.</span></span>  
  
 <span data-ttu-id="a2e78-104">Všimněte si, že dotazy v této části jsou bez destruktivní.</span><span class="sxs-lookup"><span data-stu-id="a2e78-104">Note that the queries in this section are non-destructive.</span></span> <span data-ttu-id="a2e78-105">Nejsou používány k změnit obsah původní soubory nebo složky.</span><span class="sxs-lookup"><span data-stu-id="a2e78-105">They are not used to change the contents of the original files or folders.</span></span> <span data-ttu-id="a2e78-106">To odpovídá pravidlo, že dotazy by nemělo způsobit žádné vedlejší účinky.</span><span class="sxs-lookup"><span data-stu-id="a2e78-106">This follows the rule that queries should not cause any side-effects.</span></span> <span data-ttu-id="a2e78-107">Obecně platí kód (včetně dotazů, které provádějí vytvořit / aktualizovat / odstranit operátory), který mění data zdroj by měl být udržovány odděleně od kód, který se právě dotazuje data.</span><span class="sxs-lookup"><span data-stu-id="a2e78-107">In general, any code (including queries that perform create / update / delete operators) that modifies source data should be kept separate from the code that just queries the data.</span></span>  
  
 <span data-ttu-id="a2e78-108">Tato část obsahuje následující témata:</span><span class="sxs-lookup"><span data-stu-id="a2e78-108">This section contains the following topics:</span></span>  
  
 [<span data-ttu-id="a2e78-109">Postupy: dotaz pro soubory s konkrétním atributem či názvem (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2e78-109">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 <span data-ttu-id="a2e78-110">Ukazuje, jak hledat soubory kontrolou jedné nebo více vlastností jeho <xref:System.IO.FileInfo> objektu.</span><span class="sxs-lookup"><span data-stu-id="a2e78-110">Shows how to search for files by examining one or more properties of its <xref:System.IO.FileInfo> object.</span></span>  
  
 [<span data-ttu-id="a2e78-111">Postupy: seskupování souborů podle přípony (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2e78-111">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 <span data-ttu-id="a2e78-112">Ukazuje, jak vrátit skupiny <xref:System.IO.FileInfo> objektu podle přípony názvu souboru.</span><span class="sxs-lookup"><span data-stu-id="a2e78-112">Shows how to return groups of <xref:System.IO.FileInfo> object based on their file name extension.</span></span>  
  
 [<span data-ttu-id="a2e78-113">Postupy: dotaz na celkový počet bajtů v sadě složek (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2e78-113">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 <span data-ttu-id="a2e78-114">Ukazuje, jak vracet celkový počet bajtů na všechny soubory v zadané adresářovém stromu.</span><span class="sxs-lookup"><span data-stu-id="a2e78-114">Shows how to return the total number of bytes in all the files in a specified directory tree.</span></span>  
  
 <span data-ttu-id="a2e78-115">[Postupy: porovnání obsahu dvou složek (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span><span class="sxs-lookup"><span data-stu-id="a2e78-115">[How to: Compare the Contents of Two Folders (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span></span>  
 <span data-ttu-id="a2e78-116">Ukazuje, jak vrátit všechny soubory, které se nacházejí v dvě zadané složky a také všechny soubory, které se nacházejí v jedné složce, ale ne na druhou.</span><span class="sxs-lookup"><span data-stu-id="a2e78-116">Shows how to return all the files that are present in two specified folders, and also all the files that are present in one folder but not the other.</span></span>  
  
 [<span data-ttu-id="a2e78-117">Postupy: dotazování na největší soubor či soubory v adresářovém stromu (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2e78-117">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 <span data-ttu-id="a2e78-118">Ukazuje, jak vrátit souboru nejvyšší nebo nejnižší nebo zadaný počet soubory v adresářovém stromu.</span><span class="sxs-lookup"><span data-stu-id="a2e78-118">Shows how to return the largest or smallest file, or a specified number of files, in a directory tree.</span></span>  
  
 [<span data-ttu-id="a2e78-119">Postupy: dotazu na duplicitní soubory v adresářovém stromu (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2e78-119">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 <span data-ttu-id="a2e78-120">Ukazuje, jak do skupiny pro všechny názvy souborů, které se vyskytují ve více než jedno umístění ve stromu zadaný adresář.</span><span class="sxs-lookup"><span data-stu-id="a2e78-120">Shows how to group for all file names that occur in more than one location in a specified directory tree.</span></span> <span data-ttu-id="a2e78-121">Také ukazuje, jak provádět složitější porovnání založené na vlastní porovnávací funkci.</span><span class="sxs-lookup"><span data-stu-id="a2e78-121">Also shows how to perform more complex comparisons based on a custom comparer.</span></span>  
  
 [<span data-ttu-id="a2e78-122">Postupy: dotazu na obsah souborů ve složce (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2e78-122">How to: Query the Contents of Files in a Folder (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 <span data-ttu-id="a2e78-123">Ukazuje, jak k iteraci v rámci složky ve stromu, každý soubor otevřete a dotaz na jeho obsah.</span><span class="sxs-lookup"><span data-stu-id="a2e78-123">Shows how to iterate through folders in a tree, open each file, and query the file's contents.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="a2e78-124">Komentáře</span><span class="sxs-lookup"><span data-stu-id="a2e78-124">Comments</span></span>  
 <span data-ttu-id="a2e78-125">Součástí procesu vytváření zdroje dat, který přesně reprezentuje obsah systému souborů a řádně ošetřuje výjimky je některé složitost.</span><span class="sxs-lookup"><span data-stu-id="a2e78-125">There is some complexity involved in creating a data source that accurately represents the contents of the file system and handles exceptions gracefully.</span></span> <span data-ttu-id="a2e78-126">Příklady v této části vytvořit snímek kolekce <xref:System.IO.FileInfo> objekty, které představuje všechny soubory v zadané kořenové složce a jejích podsložkách.</span><span class="sxs-lookup"><span data-stu-id="a2e78-126">The examples in this section create a snapshot collection of <xref:System.IO.FileInfo> objects that represents all the files under a specified root folder and all its subfolders.</span></span> <span data-ttu-id="a2e78-127">Skutečný stav jednotlivých <xref:System.IO.FileInfo> může změnit v době mezi při zahájení a ukončení provádění dotazu.</span><span class="sxs-lookup"><span data-stu-id="a2e78-127">The actual state of each <xref:System.IO.FileInfo> may change in the time between when you begin and end executing a query.</span></span> <span data-ttu-id="a2e78-128">Například můžete vytvořit seznam <xref:System.IO.FileInfo> objekty, které chcete použít jako zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="a2e78-128">For example, you can create a list of <xref:System.IO.FileInfo> objects to use as a data source.</span></span> <span data-ttu-id="a2e78-129">Pokud se pokusíte přístup `Length` vlastnost v dotazu, <xref:System.IO.FileInfo> objekt se pokusí o přístup a aktualizujte hodnotu v systému souborů `Length`.</span><span class="sxs-lookup"><span data-stu-id="a2e78-129">If you try to access the `Length` property in a query, the <xref:System.IO.FileInfo> object will try to access the file system to update the value of `Length`.</span></span> <span data-ttu-id="a2e78-130">Pokud soubor již existuje, zobrazí se <xref:System.IO.FileNotFoundException> v dotazu, i když jste nejsou systému souborů přímým dotazováním.</span><span class="sxs-lookup"><span data-stu-id="a2e78-130">If the file no longer exists, you will get a <xref:System.IO.FileNotFoundException> in your query, even though you are not querying the file system directly.</span></span> <span data-ttu-id="a2e78-131">Některé dotazy v této části použijte samostatné metodu, která využívá tyto konkrétní výjimky v určitých případech.</span><span class="sxs-lookup"><span data-stu-id="a2e78-131">Some queries in this section use a separate method that consumes these particular exceptions in certain cases.</span></span> <span data-ttu-id="a2e78-132">Další možností je udržovat dynamicky aktualizují v modulu zdroje dat <xref:System.IO.FileSystemWatcher>.</span><span class="sxs-lookup"><span data-stu-id="a2e78-132">Another option is to keep your data source updated dynamically by using the <xref:System.IO.FileSystemWatcher>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e78-133">Viz také</span><span class="sxs-lookup"><span data-stu-id="a2e78-133">See Also</span></span>  
 [<span data-ttu-id="a2e78-134">LINQ na objekty (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2e78-134">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)