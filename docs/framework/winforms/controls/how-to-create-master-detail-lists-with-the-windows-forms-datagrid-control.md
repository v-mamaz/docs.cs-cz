---
title: 'Postupy: Vytvořit hlavní podrobných seznamů pomocí ovládacího prvku Windows Forms DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: 8f247fb3e61abe46b3bb9c74a3b984310d2b99b3
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715461"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Postupy: Vytvoření hlavního/podrobného seznamu pomocí ovládacího prvku Windows Forms DataGrid
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> Ovládací prvek nahradí a přidá funkce, které <xref:System.Windows.Forms.DataGrid> řízení; však <xref:System.Windows.Forms.DataGrid> ovládací prvek se zachovává kvůli zpětné kompatibilitě a budoucí použití, pokud se rozhodnete. Další informace najdete v tématu [rozdíly mezi Windows Forms DataGridView a DataGrid – ovládací prvky](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Pokud vaše <xref:System.Data.DataSet> obsahuje řadu souvisejících tabulek, můžete použít dvě <xref:System.Windows.Forms.DataGrid> ovládacích prvků pro zobrazení dat ve formátu hlavního záznamu/podrobností. Jeden <xref:System.Windows.Forms.DataGrid> je určen jako hlavní mřížky, a druhý je určený být mřížku podrobnosti. Když vyberete položku v seznamu hlavních, všechny související podřízené položky jsou uvedeny v seznamu podrobnosti. Například pokud vaše <xref:System.Data.DataSet> obsahuje tabulku zákazníků a související tabulku Orders, zadali byste na hlavní mřížka tabulky Zákazníci a být mřížku podrobnosti o objednávkách. Když je zákazník vybrán z hlavní mřížky, všech objednávek tohoto zákazníka v tabulce objednávky přidružené by zobrazí v mřížce podrobností.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>Chcete-li nastavit vztah záznamů master/detail prostřednictvím kódu programu  
  
1.  Vytvořit dvě nové <xref:System.Windows.Forms.DataGrid> ovládací prvky a nastavte jejich vlastnosti.  
  
2.  Přidání tabulek do datové sady.  
  
3.  Deklarovat proměnnou typu <xref:System.Data.DataRelation> k vyjádření vztahu, kterou chcete vytvořit.  
  
4.  Zadejte název pro relaci a určením tabulky, sloupce a položku, která bude tyto dvě tabulky spojit vytvořit instanci relace.  
  
5.  Přidat vztah k <xref:System.Data.DataSet> objektu <xref:System.Data.DataSet.Relations%2A> kolekce.  
  
6.  Použití <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodu <xref:System.Windows.Forms.DataGrid> pro každý z mřížky pro vazbu <xref:System.Data.DataSet>.  
  
     Následující příklad ukazuje, jak nastavit záznamů master/detail relace mezi tabulkami Zákazníci a objednávky v dříve vytvořenou <xref:System.Data.DataSet> (`ds`).  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a>Viz také:
- [Ovládací prvek DataGrid](datagrid-control-windows-forms.md)
- [Přehled ovládacího prvku DataGrid](datagrid-control-overview-windows-forms.md)
- [Postupy: Vytvoření vazby ovládacího prvku Windows Forms DataGrid ke zdroji dat](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
