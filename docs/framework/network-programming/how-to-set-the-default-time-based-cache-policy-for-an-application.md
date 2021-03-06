---
title: 'Postupy: Nastavení výchozích zásad mezipaměti na základě času pro aplikaci'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
ms.openlocfilehash: d40b0ffbe514429ed24eaa5d0c2ce2d52c80d37d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608950"
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a>Postupy: Nastavení výchozích zásad mezipaměti na základě času pro aplikaci
Umožňuje aplikaci mít své mezipaměti chování definované hlavičky posílané s prostředkem v mezipaměti a chování mezipaměti definované v části 13 a 14 k dispozici v dokumentu RFC 2616 výchozích zásad mezipaměti na základě času [(Internet Engineering Task Force Sdružení IETF)](https://www.ietf.org/) webu. Toto je chování mezipaměti vhodné pro většinu aplikací.  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a>Chcete-li nastavit automatické výchozí zásady pro aplikace  
  
1.  Vytvořte objekt výchozí zásady založené na čase.  
  
2.  Nastavte jako výchozí pro doménu aplikace objektu zásad.  
  
## <a name="example"></a>Příklad  
 Tyto dva příklady v této části vytvořit identickými zásadami.  
  
 Následující příklad vytvoří výchozí zásady založené na čase a nastaví jej jako výchozí pro doménu aplikace.  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 Můžete také vytvořit pomocí zásad mezipaměti na základě času výchozí <xref:System.Net.Cache.RequestCachePolicy> třídy, jak je znázorněno v následujícím příkladu:  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
## <a name="see-also"></a>Viz také:
- [Správa mezipaměti pro síťové aplikace](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [Zásady mezipaměti](../../../docs/framework/network-programming/cache-policy.md)
- [Zásady mezipaměti na základě místa](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [Zásady mezipaměti na základě času](../../../docs/framework/network-programming/time-based-cache-policies.md)
- [\<requestCaching – > – Element (nastavení sítě)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
