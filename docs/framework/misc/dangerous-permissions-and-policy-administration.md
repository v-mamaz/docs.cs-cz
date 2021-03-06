---
title: Správa nebezpečných oprávnění a zásad
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 281582b04aabd8a18af8bf17091979385d009ee8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536539"
---
# <a name="dangerous-permissions-and-policy-administration"></a>Správa nebezpečných oprávnění a zásad
Některé z chráněné operace, pro které rozhraní .NET Framework poskytuje oprávnění potenciálně může mít systém zabezpečení obcházení. Tato nebezpečných oprávnění by se měly provádět jenom pro důvěryhodného kódu a pouze v případě potřeby. Je obvykle žádnou obranu proti škodlivým kódem Pokud jsou udělena tato oprávnění.  
  
> [!NOTE]
>  V [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], byly důležité změny v modelu zabezpečení rozhraní .NET Framework a terminologii. Další informace o těchto změnách najdete v tématu [změny zabezpečení](../../../docs/framework/security/security-changes.md).  
  
 Nebezpečná oprávnění jsou vysvětlené v následující tabulce.  
  
|Oprávnění|Potenciální riziko|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|Umožňuje spravovanému kódu volat nespravovaný kód, který je často nebezpečné.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|Bez ověřování kód dělat cokoli.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|Neplatná legitimace může oklamat zásady zabezpečení.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|Možnost upravit zásady zabezpečení můžete zakázat zabezpečení.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|Použití serializace může obejít mechanismy usnadnění. Podrobnosti najdete v tématu [zabezpečení a serializace](../../../docs/framework/misc/security-and-serialization.md).|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|Možnost nastavit aktuální objekt zabezpečení můžou přimět zabezpečení na základě rolí.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|Manipulace s vlákny je nebezpečné z důvodu stavu zabezpečení související s vlákny.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|Můžete použít soukromé členy k překonání mechanismů usnadnění.|  
  
## <a name="see-also"></a>Viz také:
- [Pokyny pro zabezpečené kódování](../../../docs/standard/security/secure-coding-guidelines.md)
