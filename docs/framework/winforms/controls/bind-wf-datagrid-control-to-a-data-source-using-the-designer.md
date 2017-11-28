---
title: "Postupy: Vytvoření vazby ovládacího prvku Windows Forms DataGrid ke zdroji dat pomocí Návrháře"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 378f1d80392ae7b2058d5c3b2d987e4810cbd07b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="0f23d-102">Postupy: Vytvoření vazby ovládacího prvku Windows Forms DataGrid ke zdroji dat pomocí Návrháře</span><span class="sxs-lookup"><span data-stu-id="0f23d-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="0f23d-103"><xref:System.Windows.Forms.DataGridView> Řízení nahrazuje a přidá funkce <xref:System.Windows.Forms.DataGrid> řízení; však <xref:System.Windows.Forms.DataGrid> řízení se zachovává kvůli zpětné kompatibilitě a budoucí použití, pokud si zvolíte.</span><span class="sxs-lookup"><span data-stu-id="0f23d-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="0f23d-104">Další informace najdete v tématu [rozdíly mezi systému Windows Forms DataGridView a DataGrid – ovládací prvky](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="0f23d-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="0f23d-105">Windows Forms <xref:System.Windows.Forms.DataGrid> ovládací prvek je určená speciálně pro zobrazení informací ze zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="0f23d-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="0f23d-106">Vytvoření vazby ovládacího prvku v době návrhu nastavením <xref:System.Windows.Forms.DataGrid.DataSource%2A> a <xref:System.Windows.Forms.DataGrid.DataMember%2A> vlastnosti, nebo v době běhu voláním <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="0f23d-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="0f23d-107">I když můžete zobrazit data z různých zdrojů dat, některé běžné zdroje jsou datové sady a data zobrazení.</span><span class="sxs-lookup"><span data-stu-id="0f23d-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
 <span data-ttu-id="0f23d-108">Pokud je zdroj dat dostupný v době návrhu – například, pokud tento formulář obsahuje instanci datové sady nebo zobrazení dat – mřížky můžete vázat na zdroj dat v době návrhu.</span><span class="sxs-lookup"><span data-stu-id="0f23d-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="0f23d-109">Potom můžete zobrazit náhled vzhled data v mřížce.</span><span class="sxs-lookup"><span data-stu-id="0f23d-109">You can then preview what the data will look like in the grid.</span></span>  
  
 <span data-ttu-id="0f23d-110">Můžete také navázat mřížky prostřednictvím kódu programu, v době běhu.</span><span class="sxs-lookup"><span data-stu-id="0f23d-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="0f23d-111">To je užitečné, pokud chcete nastavit zdroj dat na základě informací, které máte v době běhu.</span><span class="sxs-lookup"><span data-stu-id="0f23d-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="0f23d-112">Aplikace může například umožní uživateli zadání názvu tabulky. Chcete-li zobrazit.</span><span class="sxs-lookup"><span data-stu-id="0f23d-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="0f23d-113">Je také nutné v situacích, kde se zdroji dat neexistuje v době návrhu.</span><span class="sxs-lookup"><span data-stu-id="0f23d-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="0f23d-114">To zahrnuje zdroje dat jako pole, kolekce, netypové datové sady a čtečky dat.</span><span class="sxs-lookup"><span data-stu-id="0f23d-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>  
  
 <span data-ttu-id="0f23d-115">Následující postup vyžaduje **aplikace Windows** projekt pomocí formuláře obsahující <xref:System.Windows.Forms.DataGrid> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="0f23d-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="0f23d-116">Informace o nastavení tohoto projektu najdete v tématu [postupy: vytvoření projektu aplikace Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) a [postupy: Přidání ovládacích prvků do formulářů Windows](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0f23d-116">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="0f23d-117">V [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> ovládací prvek není součástí **sada nástrojů** ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="0f23d-117">In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="0f23d-118">Informace o přidání najdete v tématu [postupy: Přidání položky do sady nástrojů](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0).</span><span class="sxs-lookup"><span data-stu-id="0f23d-118">For information about adding it, see [How to: Add Items to the Toolbox](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0).</span></span> <span data-ttu-id="0f23d-119">Kromě toho v [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], můžete použít **zdroje dat** okna pro vázání dat v době návrhu.</span><span class="sxs-lookup"><span data-stu-id="0f23d-119">Additionally in [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="0f23d-120">Další informace najdete v části [vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="0f23d-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f23d-121">Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.</span><span class="sxs-lookup"><span data-stu-id="0f23d-121">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0f23d-122">Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky.</span><span class="sxs-lookup"><span data-stu-id="0f23d-122">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0f23d-123">Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="0f23d-123">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="0f23d-124">Pro data-bind DataGrid – ovládací prvek pro jednotlivé tabulky v Návrháři</span><span class="sxs-lookup"><span data-stu-id="0f23d-124">To data-bind the DataGrid control to a single table in the designer</span></span>  
  
1.  <span data-ttu-id="0f23d-125">Nastavte ovládacího prvku <xref:System.Windows.Forms.DataGrid.DataSource%2A> vlastnost, která má objekt obsahující data položky, které chcete vytvořit vazbu.</span><span class="sxs-lookup"><span data-stu-id="0f23d-125">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="0f23d-126">Pokud zdroj dat je datová sada, nastavte <xref:System.Windows.Forms.DataGrid.DataMember%2A> vlastnost na název tabulky pro vazbu.</span><span class="sxs-lookup"><span data-stu-id="0f23d-126">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>  
  
3.  <span data-ttu-id="0f23d-127">Pokud je zdroj dat datové sady nebo zobrazení dat na základě datové sady tabulky, přidejte kód pro formulář k vyplnění datové sady.</span><span class="sxs-lookup"><span data-stu-id="0f23d-127">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="0f23d-128">Přesný kód, který používáte, závisí na kterém je datová sada získávání dat.</span><span class="sxs-lookup"><span data-stu-id="0f23d-128">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="0f23d-129">Pokud se datová sada je právě nezadají přímo z databáze, obvykle volání `Fill` metoda adaptér pro data, jako v následujícím příkladu kódu, který naplní datovou sadu s názvem `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="0f23d-129">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  <span data-ttu-id="0f23d-130">(Volitelné) Přidejte příslušné tabulce styly a styly sloupců do mřížky.</span><span class="sxs-lookup"><span data-stu-id="0f23d-130">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>  
  
     <span data-ttu-id="0f23d-131">Pokud neexistují žádné tabulky styly, zobrazí se v tabulce, ale s minimálním formátování a všechny sloupce, které jsou viditelné.</span><span class="sxs-lookup"><span data-stu-id="0f23d-131">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="0f23d-132">Pro data-bind ovládacího prvku DataGrid k několika tabulkám v datové sadě v Návrháři</span><span class="sxs-lookup"><span data-stu-id="0f23d-132">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>  
  
1.  <span data-ttu-id="0f23d-133">Nastavte ovládacího prvku <xref:System.Windows.Forms.DataGrid.DataSource%2A> vlastnost, která má objekt obsahující data položky, které chcete vytvořit vazbu.</span><span class="sxs-lookup"><span data-stu-id="0f23d-133">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="0f23d-134">Pokud datová sada obsahuje související tabulky (to znamená, pokud obsahuje objekt relace), můžete nastavit <xref:System.Windows.Forms.DataGrid.DataMember%2A> vlastnost na název v nadřazené tabulce.</span><span class="sxs-lookup"><span data-stu-id="0f23d-134">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>  
  
3.  <span data-ttu-id="0f23d-135">Napište kód pro vyplnění datové sady.</span><span class="sxs-lookup"><span data-stu-id="0f23d-135">Write code to fill the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f23d-136">Viz také</span><span class="sxs-lookup"><span data-stu-id="0f23d-136">See Also</span></span>  
 [<span data-ttu-id="0f23d-137">Přehled ovládacího prvku DataGrid</span><span class="sxs-lookup"><span data-stu-id="0f23d-137">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [<span data-ttu-id="0f23d-138">Postupy: přidání tabulek a sloupců do ovládacího prvku Windows Forms DataGrid – ovládací prvek</span><span class="sxs-lookup"><span data-stu-id="0f23d-138">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [<span data-ttu-id="0f23d-139">DataGrid – ovládací prvek</span><span class="sxs-lookup"><span data-stu-id="0f23d-139">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="0f23d-140">Windows Forms – datová vazba</span><span class="sxs-lookup"><span data-stu-id="0f23d-140">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="0f23d-141">Přístup k datům v sadě Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0f23d-141">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)