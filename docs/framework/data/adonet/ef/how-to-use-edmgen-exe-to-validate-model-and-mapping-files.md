---
title: 'Postupy: Použití EdmGen.exe pro ověření modelu a souborů mapování'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 12258236c904c70d6d94490e3d1c6af2457bbe0c
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827884"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Postupy: Použití EdmGen.exe pro ověření modelu a souborů mapování
Toto téma ukazuje, jak používat [generátor EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) nástroje pro ověření modelu a souborů mapování. Další informace najdete v tématu [modelu Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Ověření modelu School pomocí EdmGen.exe  
  
1.  Vytvoření databáze školy. Další informace najdete v tématu [vytvoření ukázkové databáze školy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2.  Generování modelu školy. Další informace najdete v tématu [jak: Použití EdmGen.exe pro generování modelu a souborů mapování](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Na příkazovém řádku spusťte následující příkaz bez konce řádků:  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>Viz také:
- [Postupy: Ruční konfigurace projektu v Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Datový Model Entity ADO.NET nástroje](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Postupy: Předběžně generovat zobrazení pro zlepšení výkonu dotazů](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Postupy: Použití EdmGen.exe pro generování kódu na objektové vrstvě](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
