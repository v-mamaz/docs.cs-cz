---
title: SqlClient pro Entity Framework
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: 5b47b035932062b859d470716903e826b2bb6f3d
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903845"
---
# <a name="sqlclient-for-the-entity-framework"></a>SqlClient pro Entity Framework
Tato část popisuje zprostředkovatele dat .NET Framework pro SQL Server (SqlClient), která umožňuje rozhraní Entity Framework pracovat prostřednictvím systému Microsoft SQL Server.  
  
## <a name="provider-schema-attribute"></a>Atribut schématu poskytovatele  
 `Provider` je atribut `Schema` prvek store schema definition language (SSDL).  
  
 Použití SqlClient přiřadit řetězec "System.Data.SqlClient" `Provider` atribut `Schema` elementu.  
  
## <a name="providermanifesttoken-schema-attribute"></a>Atribut ProviderManifestToken schématu  
 `ProviderManifestToken` je povinný atribut `Schema` prvek SSDL. Tento token se používá k načtení manifestu zprostředkovatele pro scénáře v režimu offline. Další informace o `ProviderManifestToken` atributu naleznete v tématu [Element schématu (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).  
  
 SqlClient slouží jako zprostředkovatel dat pro různé verze systému SQL Server. Tyto verze mají různé možnosti. Například [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] nepodporuje `varchar(max)` a `nvarchar(max)` typy, které byly představeny s nástrojem [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].  
  
 SqlClient vytváří a přijímá následující tokeny manifestu zprostředkovatele pro různé verze systému SQL Server.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|-|-|-|  
|2000|2005|2008|  
  
> [!NOTE]
>  Od verze Visual Studio 2010, [ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) nepodporuje SQL Server 2000.  
  
## <a name="provider-namespace-name"></a>Název zprostředkovatele Namespace  
 Všichni poskytovatelé musí zadat obor názvů. Tato vlastnost říká rozhraní Entity Framework, která předpona je používá zprostředkovatel pro konkrétní konstrukce, jako jsou typy a funkce. Obor názvů pro manifesty poskytovatelů SqlClient je `SqlServer`. Další informace o oborech názvů najdete v tématu [obory názvů](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).  
  
## <a name="types"></a>Typy  
 Zprostředkovatelem SqlClient pro Entity Framework obsahuje informace o mapování mezi typy konceptuálních modelů a typy serveru SQL Server. Další informace najdete v tématu [SqlClient pro typy Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
## <a name="functions"></a>Funkce  
 Zprostředkovatelem SqlClient pro Entity Framework definuje seznam funkcí podporována zprostředkovatelem. Seznam podporovaných funkcí najdete v tématu [SqlClient pro funkce Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [SqlClient pro funkce Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [SqlClient pro typy Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [Známé problémy v SqlClient pro Entity Framework](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Viz také:
- [Jazyk Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [Referenční dokumentace jazyka](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
- [Známé problémy v zprostředkovatelem SqlClient pro Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
