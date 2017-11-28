---
title: "Postupy: Řazení a filtrování dat ADO.NET pomocí součásti Windows Forms BindingSource"
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
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 46947e314394d56b5ef0439f33910bb493012db3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="215d7-102">Postupy: Řazení a filtrování dat ADO.NET pomocí součásti Windows Forms BindingSource</span><span class="sxs-lookup"><span data-stu-id="215d7-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="215d7-103">Můžete vystavit řazení a filtrování funkce <xref:System.Windows.Forms.BindingSource> ovládat prostřednictvím <xref:System.Windows.Forms.BindingSource.Sort%2A> a <xref:System.Windows.Forms.BindingSource.Filter%2A> vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="215d7-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="215d7-104">Jednoduché řazení, pokud je základní zdroj dat můžete použít <xref:System.ComponentModel.IBindingList>, a můžete použít filtrování a rozšířené řazení, pokud je zdroj dat <xref:System.ComponentModel.IBindingListView>.</span><span class="sxs-lookup"><span data-stu-id="215d7-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="215d7-105"><xref:System.Windows.Forms.BindingSource.Sort%2A> Vlastnost vyžaduje standardní [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] syntaxe: následuje řetězec představující název sloupce dat ve zdroji dat `ASC` nebo `DESC` indikující, zda v seznamu musí být seřazeny ve vzestupném nebo sestupném pořadí.</span><span class="sxs-lookup"><span data-stu-id="215d7-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="215d7-106">Můžete nastavit pokročilé řazení nebo více sloupci řazení oddělením každý sloupec s oddělovačem čárkami.</span><span class="sxs-lookup"><span data-stu-id="215d7-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="215d7-107"><xref:System.Windows.Forms.BindingSource.Filter%2A> Vlastnost trvá řetězcového výrazu.</span><span class="sxs-lookup"><span data-stu-id="215d7-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="215d7-108">Ukládání citlivé informace, jako jsou hesla, v připojovacím řetězci může ovlivnit zabezpečení vaší aplikace.</span><span class="sxs-lookup"><span data-stu-id="215d7-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="215d7-109">Bezpečnější způsob, jak řídit přístup k databázi, je ověřování systému Windows (označované také jako integrované zabezpečení).</span><span class="sxs-lookup"><span data-stu-id="215d7-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="215d7-110">Další informace najdete v tématu [chrání informace o připojení](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="215d7-110">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="215d7-111">K filtrování dat pomocí BindingSource</span><span class="sxs-lookup"><span data-stu-id="215d7-111">To filter data with the BindingSource</span></span>  
  
-   <span data-ttu-id="215d7-112">Nastavte <xref:System.Windows.Forms.BindingSource.Filter%2A> vlastnost, která má výraz, který chcete.</span><span class="sxs-lookup"><span data-stu-id="215d7-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="215d7-113">V následujícím příkladu kódu je výraz název sloupce, za nímž následuje hodnotu, která chcete použít pro sloupec.</span><span class="sxs-lookup"><span data-stu-id="215d7-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="215d7-114">Řazení dat pomocí BindingSource</span><span class="sxs-lookup"><span data-stu-id="215d7-114">To sort data with the BindingSource</span></span>  
  
1.  <span data-ttu-id="215d7-115">Nastavte <xref:System.Windows.Forms.BindingSource.Sort%2A> vlastnost na název sloupce, který chcete, za nímž následuje `ASC` nebo `DESC` k označení vzestupném nebo sestupném pořadí.</span><span class="sxs-lookup"><span data-stu-id="215d7-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2.  <span data-ttu-id="215d7-116">Více sloupců oddělte čárkou.</span><span class="sxs-lookup"><span data-stu-id="215d7-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="215d7-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="215d7-117">Example</span></span>  
 <span data-ttu-id="215d7-118">Následující příklad kódu načte data z tabulky Zákazníci ukázková databáze Northwind do <xref:System.Windows.Forms.DataGridView> řídit a filtry a seřadí zobrazená data.</span><span class="sxs-lookup"><span data-stu-id="215d7-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="215d7-119">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="215d7-119">Compiling the Code</span></span>  
 <span data-ttu-id="215d7-120">Pro spuštění tohoto příkladu, vložte kód do formuláře, který obsahuje <xref:System.Windows.Forms.BindingSource> s názvem `BindingSource1` a <xref:System.Windows.Forms.DataGridView> s názvem `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="215d7-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="215d7-121">Zpracování <xref:System.Windows.Forms.Form.Load> události pro formulář a volání `InitializeSortedFilteredBindingSource` v obslužná rutina události zatížení.</span><span class="sxs-lookup"><span data-stu-id="215d7-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="215d7-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="215d7-122">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>  
 <xref:System.Windows.Forms.BindingSource.Filter%2A>  
 [<span data-ttu-id="215d7-123">Postupy: Instalace ukázkových databází</span><span class="sxs-lookup"><span data-stu-id="215d7-123">How to: Install Sample Databases</span></span>](http://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)  
 [<span data-ttu-id="215d7-124">BindingSource – komponenta</span><span class="sxs-lookup"><span data-stu-id="215d7-124">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)