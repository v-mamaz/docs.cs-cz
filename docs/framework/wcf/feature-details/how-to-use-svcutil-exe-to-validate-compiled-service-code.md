---
title: 'Postupy: Ověření zkompilovaného kódu služby pomocí nástroje Svcutil.exe'
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: a06cf57fce883753af4686b294396d6d6da73a13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531925"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a>Postupy: Ověření zkompilovaného kódu služby pomocí nástroje Svcutil.exe
Můžete použít [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) kvůli zjištění chyb v implementacemi služeb a konfigurace bez, který je hostitelem služby.  
  
### <a name="to-validate-a-service"></a>K ověření služby  
  
1.  Zkompilujte služby do spustitelného souboru a jeden nebo více závislých sestavení.  
  
2.  Otevřete příkazový řádek sady SDK  
  
3.  Na příkazovém řádku spusťte nástroje Svcutil.exe v následujícím formátu. Další informace o různých parametrů, najdete v článku Služba Validationsection z [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tématu.  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     Je nutné použít `/serviceName` možnost určíte název konfigurace služby, kterou chcete ověřit.  
  
     `assemblyPath` Argument určuje cestu ke spustitelnému souboru pro službu a jedno nebo více sestavení, které obsahují typy, které služba má být ověřen. Spustitelný soubor sestavení musí mít přidružený konfiguračního souboru a zadejte konfiguraci služby. Můžete použít standardní zástupné znaky příkazového řádku k poskytování více sestavení.  
  
## <a name="example"></a>Příklad  
 Následující příkaz myServiceName služby implementované ve spustitelném souboru myServiceHost.exe.  Konfigurační soubor služby (myServiceHost.exe.config) je automaticky načíst.  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a>Viz také:
- [Nástroj metadat modelu služby (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
