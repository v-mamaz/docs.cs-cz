---
title: Konfigurace aplikací pomocí konfiguračních souborů
ms.date: 03/30/2017
f1_keywords:
- AutoGeneratedOrientationPage
helpviewer_keywords:
- security configuration files
- end tags
- configuration files [.NET Framework], application
- machine configuration files
- .NET Framework application configuration, configuration files
- applications [.NET Framework], configuration files
- application configuration files, security
- application configuration files, format
- configuration files [.NET Framework]
- hosts, application
- application configuration files, machine
- ASP.NET, configuring
- configuration files [.NET Framework], security
- application configuration files, about
- application configuration files
- <runtime> element
- start tags
- configuration files [.NET Framework], machine
- configuration files [.NET Framework], format
ms.assetid: 86bd26d3-737e-4484-9782-19b17f34cd1f
ms.openlocfilehash: 184be04c963116906c1dc2c0a5803814402ea8e0
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826431"
---
# <a name="configuring-apps-by-using-configuration-files"></a>Konfigurace aplikací pomocí konfiguračních souborů
Rozhraní .NET Framework, prostřednictvím konfiguračních souborů, poskytuje vývojářům a správcům kontrolu a flexibilitu nad způsobem aplikace spouštět. Konfigurační soubory jsou soubory XML, které lze změnit podle potřeby. Správce může ovládat, můžete přístup k aplikaci, která chránila prostředky, které verze sestavení může aplikace používat a kde jsou umístěny objekty a vzdálené aplikace. Vývojáři mohou umístit nastavení konfiguračních souborů, takže odpadá potřeba znovu zkompilovat aplikaci pokaždé, když se změní nastavení. Tato část popisuje, co lze konfigurovat a proč konfigurace aplikace může být užitečné.  
  
> [!NOTE]
>  Spravovaný kód může použít třídy v <xref:System.Configuration> obor názvů pro čtení nastavení z konfiguračních souborů, ale nikoli k zápisu nastavení do těchto souborů.  
  
 Toto téma popisuje syntaxi konfiguračních souborů a obsahuje informace o třech typech konfiguračních souborů: souborů počítače, aplikací a zabezpečení.  
  
## <a name="configuration-file-format"></a>Formát konfiguračního souboru  
 Konfigurační soubory obsahují prvky, které představují logické datové struktury, jež nastavují informace o konfiguraci. V konfiguračním souboru je možné použít značky pro označení začátku a konce prvku. Například `<runtime>` element se skládá z `<runtime>` *podřízené prvky*`</runtime>`. Prázdný element by byla zapsána jako `<runtime/>` nebo `<runtime></runtime>`.  
  
 Stejně jako u všech souborů XML rozlišuje syntaxe v konfiguračních souborech velká a malá písmena.  
  
 Je možné určit nastavení konfigurace pomocí předdefinovaných atributů, kterými jsou páry název/hodnota uvnitř počáteční značky prvku. Následující příklad určuje dva atributy (`version` a `href`) pro `<codeBase>` element, který určuje, kde modul runtime vyhledá sestavení (Další informace najdete v tématu [určení umístění sestavení](../../../docs/framework/configure-apps/specify-assembly-location.md)).  
  
```xml  
<codeBase version="2.0.0.0"  
          href="http://www.litwareinc.com/myAssembly.dll"/>  
```  
  
## <a name="machine-configuration-files"></a>Konfigurační soubory počítače  
 Konfigurační soubor počítače Machine.config obsahuje nastavení, které platí pro celý počítač. Tento soubor je umístěn ve složce %*cesta pro instalaci modulu runtime*%\Config adresáře. Machine.config obsahuje nastavení konfigurace pro celý počítač sestavení vazby, integrované [kanálů řízení vzdálené komunikace](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dkfd3wha(v=vs.100))a technologií ASP.NET.  
  
 Konfigurační systém nejprve hledá v konfiguračním souboru počítače [  **\<appSettings >** element](~/docs/framework/configure-apps/file-schema/appsettings/index.md) a další oddíly konfigurace, které může vývojář definovat. Poté hledá v konfiguračním souboru aplikace. Pro zachování udržovatelnosti souboru konfigurace počítače je vhodné umístit tato nastavení do konfiguračního souboru aplikace. Avšak díky vložení nastavení do konfiguračního souboru počítače lze provádět jednodušší údržbu vašeho systému. Například při použití komponenty třetí strany, kterou používá aplikace klienta i serveru, je jednodušší umístit nastavení této komponenty do jednoho místa. V tomto případě je konfigurační soubor počítače vhodným místem pro umístění nastavení, jelikož nebudete mít stejné nastavení ve dvou různých souborech.  
  
> [!NOTE]
>  Nasazení aplikace pomocí příkazu XCOPY nezkopíruje nastavení z konfiguračního souboru počítače.  
  
 Další informace o tom, jak modul common language runtime používá konfigurační soubor počítače pro vazby sestavení naleznete v tématu [jak modul Runtime vyhledává sestavení](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
## <a name="application-configuration-files"></a>Konfigurační soubory aplikace  
 Konfigurační soubor aplikace obsahuje nastavení specifické pro aplikaci. Tento soubor obsahuje nastavení konfigurace, které čte modul CLR (Common Language Runtime) (například zásady vazeb sestavení, objekty vzdálené komunikace a tak dále) a nastavení, které může číst aplikace.  
  
 Název a umístění konfiguračního souboru aplikace závisí na hostiteli aplikace, což může být jeden z následujících:  
  
-   Spustitelná-hostovaná aplikace.  
  
     Tyto aplikace mají dva konfigurační soubory: zdrojový konfigurační soubor, který je upraven vývojářem během vývoje, a výstupní soubor, který je distribuován spolu s aplikací.  
  
     Při vývoji v sadě Visual Studio umístěte zdrojový konfigurační soubor pro vaši aplikaci v adresáři projektu a nastavte jeho **kopírovat do výstupního adresáře** vlastnost **vždy Kopírovat** nebo **kopírovat, pokud je novější** . Název konfiguračního souboru je název aplikace s příponou .config. Například aplikace s názvem myApp.exe by měla mít zdrojový konfigurační soubor s názvem myApp.exe.config.  
  
     Sada Visual Studio automaticky zkopíruje zdrojový konfigurační soubor do adresáře, kde je zkompilováno sestavení, a vytvoří výstupní konfigurační soubor, který je nasazen spolu s aplikací. V některých případech se může Visual Studio Upravit výstupní konfigurační soubor Další informace najdete v tématu [přesměrování verze sestavení na úrovni aplikace](../../../docs/framework/configure-apps/redirect-assembly-versions.md#BKMK_Redirectingassemblyversionsattheapplevel) část [přesměrování verze sestavení](../../../docs/framework/configure-apps/redirect-assembly-versions.md) článku.  
  
-   Aplikace hostovaná technologií ASP.NET.  
  
     Další informace o konfiguračních souborech technologie ASP.NET najdete v tématu [nastavení konfigurace ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)).
  
-   Aplikace hostovaná pomocí prohlížeče Internet Explorer.  
  
     Pokud má aplikace hostovaná v aplikaci Internet Explorer konfigurační soubor, je v zadané umístění tohoto souboru `<link>` značky s následující syntaxí:  
  
     \<link rel="*ConfigurationFileName*" href="*location*">  
  
     V této značce `location` je adresa URL do konfiguračního souboru. Tím dojde k nastavení základní cesty aplikace. Konfigurační soubor musí být umístěn na stejné webové stránce jako aplikace.  
  
## <a name="security-configuration-files"></a>Konfigurační soubory zabezpečení  
 Konfigurační soubory zabezpečení obsahují informace o hierarchii skupiny kódu a sady oprávnění přidružené k úrovním zásad. Důrazně doporučujeme používat [nástroj Code Access Security Policy (Caspol.exe)](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md) změnit zásady zabezpečení, aby se tyto zásady změny nenarušily konfigurační soubory zabezpečení.  
  
> [!NOTE]
>  Počínaje [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], konfigurační soubory zabezpečení jsou k dispozici pouze v případě, že došlo ke změně zásad zabezpečení.  
  
 Konfigurační soubory zabezpečení jsou umístěny zde:  
  
-   Konfigurační soubor zásad podnikové: %*runtime-install-path*%\Config\Enterprisesec.config  
  
-   Konfigurační soubor zásad počítače: %*runtime-install-path*%\Config\Security.config  
  
-   Konfigurační soubor zásad uživatele: %USERPROFILE%\Application data\Microsoft\CLR security config\v*xx.xx*\Security.config  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: Vyhledání sestavení pomocí mechanismu DEVPATH](../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)  
 Popisuje, jak řídit modul runtime pro použití proměnné prostředí DEVPATH při hledání sestavení.  
  
 [Přesměrování verzí sestavení](../../../docs/framework/configure-apps/redirect-assembly-versions.md)  
 Popisuje, jak zadat umístění sestavení a kterou verzi sestavení, které chcete použít.  
  
 [Určení umístění sestavení](../../../docs/framework/configure-apps/specify-assembly-location.md)  
 Popisuje, jak určit, kde by měl modul runtime vyhledat sestavení.  
  
 [Konfigurace šifrovacích tříd](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 Popisuje, jak namapovat název algoritmu na kryptografickou třídu a identifikátor objektu na kryptografický algoritmus.  
  
 [Postupy: Vytváření zásad vydavatele](../../../docs/framework/configure-apps/how-to-create-a-publisher-policy.md)  
 Popisuje, kdy a jak by měl přidat zásadu vydavatele pro zadání sestavení kódu a přesměrování základní nastavení.  
  
 [Schéma konfiguračního souboru](../../../docs/framework/configure-apps/file-schema/index.md)  
 Popisuje hierarchii schématu pro spuštění, runtime, síť a další typy nastavení konfigurace.  
  
## <a name="see-also"></a>Viz také:
- [Schéma konfiguračního souboru](../../../docs/framework/configure-apps/file-schema/index.md)
- [Určení umístění sestavení](../../../docs/framework/configure-apps/specify-assembly-location.md)
- [Přesměrování verzí sestavení](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
- [Správa webu technologie ASP.NET](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6hy1xzbw(v=vs.90))
- [Správa zásad zabezpečení](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c1k0eed6(v=vs.100))
- [Caspol.exe (nástroj zásad zabezpečení přístupu kódu)](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md)
- [Sestavení v modulu CLR (Common Language Runtime)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
