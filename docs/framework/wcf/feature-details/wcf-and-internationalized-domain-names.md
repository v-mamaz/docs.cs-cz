---
title: WCF a mezinárodní názvy domén
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: 83c6f3c2afec0f2b6b8fccca4bd8252e9ab35400
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571584"
---
# <a name="wcf-and-internationalized-domain-names"></a>WCF a mezinárodní názvy domén
Byla přidána podpora pro služby WCF s mezinárodní názvy domén (IDN). Mezinárodní název domény je název domény, který obsahuje jiné znaky než ASCII. Tato podpora zahrnuje možnost pro hostování služby WCF pomocí názvu IDN a klienta WCF ke komunikaci s webovou službu s názvem IDN.  
  
## <a name="systemuri-and-idn"></a>System.Uri a IDN  
 <xref:System.Uri> má dvě vlastnosti <xref:System.Uri.Host%2A> a <xref:System.Uri.DnsSafeHost%2A>. Tyto vlastnosti obsahovat Unicode nebo kódování Punycode hodnoty v závislosti na nastavení konfigurace IDN.  
  
 V konfiguračním souboru aplikace pomocí následující kód XML je povoleno IDN  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 \<Idn > prvku obsahuje atribut enabled, které můžete nastavit na jedno z následujících hodnot:  
  
1.  "None"  
  
2.  "AllExceptIntranet"  
  
3.  "Vše"  
  
 Když je IDN nastavená na hodnotu "None", žádný převod se provádí Uri.Host nebo Uri.DnsSafeHost. Když je IDN nastavená na "Vše", identifikátor uri. Hostitel zůstává kódování Unicode a identifikátor uri. DnsSafeHost je převede na kódování Punycode. Když je IDN nastavená na "AllExceptIntranet", identifikátor uri. DnsSafeHost je převede na kódování Punycode u internetových adres a zůstane Unicode pro adres v podnikové síti. Toto nastavení je důležité pro správný překlad názvů DNS. Všimněte si, že toto nastavení není potřeba nakonfigurovat pro Windows 8 a novější verze.  
  
> [!WARNING]
>  Měli byste nikdy pevně zakódovat adresu pomocí kódování Punycode. WCF převede za vás na základě nastavení konfigurace, které použijete.  
  
> [!WARNING]
>  Při přidávání znaky Unicode do applicationHost.exe.config, uložte soubor pomocí kódování UTF-8.  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Uri?displayProperty=nameWithType>
