---
title: Mapování identifikátorů objektů na algoritmy šifrování
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
ms.openlocfilehash: 000d5d94b19907dfed40ac03f3172b9b8449c6f2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083445"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Mapování identifikátorů objektů na algoritmy šifrování
Digitální podpisy Ujistěte se, že data bez dozoru při odeslání z jedné aplikace do jiného. Obvykle digitální podpis je vypočítán s použitím matematické funkce hash data, která mají být podepsán. Při formátování hodnoty hash podepsat, některé algoritmy digitálního podpisu připojí ASN.1 identifikátor objektu (OID) v rámci operace formátování. Identifikátor OID Určuje algoritmus, který byl použit pro výpočet hodnoty hash. Algoritmy můžete namapovat na identifikátory objektů rozšířit mechanismus kryptografie na vlastní algoritmy. Následující příklad ukazuje, jak namapovat identifikátor objektu na nový algoritmus hash.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 [ \<Oidentry – > element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) obsahuje dva atributy. **OID** atribut je identifikátor objektu. **Název** atribut je hodnota **název** atribut z [ \<nameEntry > element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md). Musí existovat mapování z název algoritmu na třídu před identifikátor objektu lze mapovat na jednoduchý název.  
  
## <a name="see-also"></a>Viz také:
- [Konfigurace šifrovacích tříd](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [Kryptografické služby](../../../docs/standard/security/cryptographic-services.md)
