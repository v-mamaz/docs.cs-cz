---
title: Příkaz GetSchema a kolekce schémat
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: e067e5c6e108a27ecaf9e4b0e3e6a33938ad0b59
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562988"
---
# <a name="getschema-and-schema-collections"></a>Příkaz GetSchema a kolekce schémat
**Připojení** třídami implementace spravovaného zprostředkovatele .NET Framework **GetSchema** metodu, která se používá k načtení informací o schématu databáze, která je aktuálně připojena, a informace o schématu vrácených **GetSchema** metoda je k dispozici ve formě <xref:System.Data.DataTable>. **GetSchema** je metoda přetížená metoda, která poskytuje volitelných parametrů pro určení kolekce schématu pro vrácení a omezit množství vrácených informací.  
  
## <a name="specifying-the-schema-collections"></a>Určení kolekce schémat  
 První nepovinný parametr **GetSchema** metody je název kolekce, který je zadán jako řetězec. Existují dva typy kolekce schémat: společné kolekce schémat, které jsou společné pro všechny poskytovatele a kolekce určité schéma, které jsou specifické pro každého zprostředkovatele.  
  
 Můžete dát dotaz na zprostředkovatele rozhraní .NET Framework spravované určit seznam kolekcí nepodporuje schéma voláním **GetSchema** metody bez argumentů nebo názvem kolekce schématu "MetaDataCollections". Vrátí <xref:System.Data.DataTable> seznam kolekcí nepodporuje schéma, počet omezení, které každá podporují a počet identifikátor částí, které používají.  
  
### <a name="retrieving-schema-collections-example"></a>Načítání kolekcí příkladu schématu  
 Následující příklady ukazují, jak používat <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> metoda zprostředkovatele dat .NET Framework pro SQL Server <xref:System.Data.SqlClient.SqlConnection> třídy pro načtení schématu informace o všech tabulek, které jsou součástí **AdventureWorks**ukázkovou databázi:  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,    
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
   End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
   Console.WriteLine("Press any key to continue.");  
   Console.ReadKey();  
   }  
 }  
  
  private static string GetConnectionString()  
  {  
   // To avoid storing the connection string in your code,  
   // you can retrieve it from a configuration file.  
   return "Data Source=(local);Database=AdventureWorks;" +  
      "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="see-also"></a>Viz také:
- [Načítání informací o databázovém schématu](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [ADO.NET spravovaných zprostředkovatelích a datové sady pro vývojáře](https://go.microsoft.com/fwlink/?LinkId=217917)
