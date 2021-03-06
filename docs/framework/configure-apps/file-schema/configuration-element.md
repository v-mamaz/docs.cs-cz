---
title: <configuration> – element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 9a7b25c74763c020c0e19c3f6099db9001acf773
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675046"
---
# <a name="configuration-element"></a>\<Konfigurace > – element

Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.

**\<configuration>**

## <a name="syntax"></a>Syntaxe

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>Atributy

Žádná

## <a name="parent-element"></a>Nadřazený element

Žádná

## <a name="child-elements"></a>Podřízené prvky

|     | Popis |
| --- | ----------- |
| [**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | Určuje zásady vazeb sestavení na úrovni konfigurace.|
| [**\<Po spuštění >** schéma nastavení](~/docs/framework/configure-apps/file-schema/startup/index.md) | Všechny elementy ve schématu nastavení spuštění. |
| [**\<modul runtime >** schéma nastavení](~/docs/framework/configure-apps/file-schema/runtime/index.md) | Všechny prvky v schéma nastavení běhového prostředí. |
| [**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Všechny elementy ve schématu nastavení vzdálené komunikace. |
| [**\<system.Net>** Settings Schema](~/docs/framework/configure-apps/file-schema/network/index.md) | Všechny elementy ve schématu nastavení sítě. |
| [**\<cryptographySettings – >** schéma nastavení](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | Všechny elementy ve schématu kryptografických nastavení. |
| [**\<Konfigurace >** schéma oddílů](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | Všechny elementy ve schématu oddílu nastavení konfigurace. |
| [Trasování a ladění schématu nastavení](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | Všechny elementy ve schématu nastavení trasování a ladění. |
| [Schéma konfigurace nastavení ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Všechny elementy ve schématu konfigurace technologie ASP.NET, které zahrnuje prvky pro konfiguraci technologie ASP.NET webové stránky a aplikace. Použít v *Web.config* soubory. |
| [**\<webové služby >** schéma nastavení](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Všechny elementy ve schématu nastavení webových služeb. |
| [Schéma nastavení webu](~/docs/framework/configure-apps/file-schema/web/index.md) | Všechny elementy ve schématu nastavení webu, který obsahuje prvky pro konfiguraci spolupráce rozhraní ASP.NET s hostitelskou aplikací, například službou IIS. Použít v *aspnet.config* soubory. |

## <a name="remarks"></a>Poznámky

Každý konfigurační soubor musí obsahovat přesně jeden  **\<konfigurace >** elementu.

## <a name="see-also"></a>Viz také:

- [Schéma konfiguračního souboru pro rozhraní .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
