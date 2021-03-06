---
title: CorAssemblyFlags – výčet
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f99fb7a693c47b257abe9c0b783856179fc9f0eb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582370"
---
# <a name="corassemblyflags-enumeration"></a>CorAssemblyFlags – výčet
Obsahuje hodnoty, které popisují metadata u sestavení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|`afPublicKey`|Označuje, že odkaz na sestavení obsahuje úplnou nezašifrované veřejný klíč.|  
|`afPA_None`|Označuje, že neurčená na architektuře procesoru.|  
|`afPA_MSIL`|Označuje, že je na architektuře procesoru neutrální (PE32).|  
|`afPA_x86`|Označuje, že je na architektuře procesoru x86 (PE32).|  
|`afPA_IA64`|Označuje, že je architektura procesorů Itanium (PE32 +).|  
|`afPA_AMD64`|Označuje, že je architektura procesorů AMD X64 (PE32 +).|  
|`afPA_ARM`|Označuje, že je na architektuře procesoru ARM (PE32).|  
|`afPA_NoPlatform`|Označuje, že sestavení je odkaz na sestavení; To znamená platí pro všechny architektury ale nelze je spustit na libovolné architektury. Díky tomu se příznak je stejný jako `afPA_Mask`.|  
|`afPA_Specified`|Označuje, že příznaky architektura procesoru by mělo být předáno `AssemblyRef` záznamu.|  
|`afPA_Mask`|Maska, která popisuje architekturu procesoru.|  
|`afPA_FullMask`|Určuje, že je součástí popis architektury procesoru.|  
|`afPA_Shift`|Označuje počet posunů v příznacích architekturu procesoru, na a z indexu.|  
|`afEnableJITcompileTracking`|Určuje odpovídající hodnotu z <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> z <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afDisableJITcompileOptimizer`|Určuje odpovídající hodnotu z <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> z <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afRetargetable`|Označuje, že sestavení můžete v době běhu změněn na cíl sestavení z jiného vydavatele.|  
|`afContentType_Mask`|Maska, která popisuje typ obsahu.|  
|`afContentType_Default`|Určuje výchozí typ obsahu.|  
|`afContentType_WindowsRuntime`|Označuje, [!INCLUDE[wrt](../../../../includes/wrt-md.md)] typ obsahu.|  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorHdr.h  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [Výčty pro metadata](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
