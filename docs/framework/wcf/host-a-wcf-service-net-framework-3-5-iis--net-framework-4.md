---
title: "Postupy: Hostování služby WCF napsané pomocí .NET Framework 3.5 v IIS a běžící pod .NET Framework 4"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e2c9dbf92ddaf1c23cb09184f046cb536717015
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-host-a-wcf-service-written-with-net-framework-35-in-iis-running-under-net-framework-4"></a>Postupy: Hostování služby WCF napsané pomocí .NET Framework 3.5 v IIS a běžící pod .NET Framework 4
Při hostování [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] služby napsané pomocí [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] na počítač se systémem [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], může dojít <xref:System.ServiceModel.ProtocolException> s následujícím textem.  
  
```Output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8). If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly. The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 Nebo pokud se pokusíte vyhledat soubor .svc služby, mohou se zobrazit chybová stránka s následujícím textem.  
  
```Output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 K těmto chybám, protože je spuštěna služba IIS je spuštěna v rámci domény aplikace [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] a služby WCF je očekáván běh [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. Toto téma vysvětluje změny vyžadované k získání službu spustit.  
  
 Poté vyhledejte <`compilers`> elementu a změňte možnost zprostředkovatele CompilerVersion s hodnotou 4.0. Ve výchozím nastavení, jsou uvedeny dvě <`compiler`> elementů v rámci <`compilers`> elementu. Možnost poskytovatele CompilerVersion pro obě jak je znázorněno v následujícím příkladu je nutné aktualizovat.  
  
```xml  
<system.codedom>  
      <compilers>  
        <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                  type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
        <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                  type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="OptionInfer" value="true"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
      </compilers>  
    </system.codedom>  
```  
  
### <a name="add-the-required-targetframework-attribute"></a>Přidat atribut vyžaduje targetFramework  
  
1.  Otevřete soubor Web.config služby a podívejte se <`compilation`> elementu.  
  
2.  Přidat `targetFramework` atribut <`compilation`> elementu, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <compilation debug="false"  
            targetFramework="4.0">  
  
            <assemblies>  
              <add assembly="System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Xml.Linq, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35"/>  
              <add assembly="System.Data.DataSetExtensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
            </assemblies>  
  
          </compilation>  
    ```  
  
3.  Najít <`compilers`> elementu a změňte možnost zprostředkovatele CompilerVersion s hodnotou 4.0. Ve výchozím nastavení, jsou uvedeny dvě <`compiler`> elementů v rámci <`compilers`> elementu. Možnost poskytovatele CompilerVersion pro obě jak je znázorněno v následujícím příkladu je nutné aktualizovat.  
  
    ```xml  
    <system.codedom>  
          <compilers>  
            <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                      type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
            <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                      type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="OptionInfer" value="true"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
          </compilers>  
        </system.codedom>  
    ```