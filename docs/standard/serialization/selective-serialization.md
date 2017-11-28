---
title: "Selektivní serializace"
ms.date: 08/07/2017
ms.prod: .net
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f583c0c7f2895b16ac0aea883dd98b4768179127
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="selective-serialization"></a><span data-ttu-id="f5bde-102">Selektivní serializace</span><span class="sxs-lookup"><span data-stu-id="f5bde-102">Selective serialization</span></span>
<span data-ttu-id="f5bde-103">Třída často obsahuje pole, která nesmí být serializován.</span><span class="sxs-lookup"><span data-stu-id="f5bde-103">A class often contains fields that shouldn't be serialized.</span></span> <span data-ttu-id="f5bde-104">Můžete například předpokládat, že třída uchovává ID vlákna v členské proměnné.</span><span class="sxs-lookup"><span data-stu-id="f5bde-104">For example, assume a class stores a thread ID in a member variable.</span></span> <span data-ttu-id="f5bde-105">Pokud je třída deserializovat, vlákno uložené ID pro když byl serializován třída můžou už běžet; proto serializaci tato hodnota nemá smysl.</span><span class="sxs-lookup"><span data-stu-id="f5bde-105">When the class is deserialized, the thread stored the ID for when the class was serialized might no longer be running; so serializing this value doesn't make sense.</span></span> <span data-ttu-id="f5bde-106">Členské proměnné můžete zabránit jejich s označením serializována [NonSerialized](xref:System.NonSerializedAttribute) atribut následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="f5bde-106">You can prevent member variables from being serialized by marking them with the [NonSerialized](xref:System.NonSerializedAttribute) attribute as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

<span data-ttu-id="f5bde-107">Přesvědčte se, pokud je to možné, objekt, který by mohl obsahovat nonserializable data citlivá na zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="f5bde-107">If possible, make an object that could contain security-sensitive data nonserializable.</span></span> <span data-ttu-id="f5bde-108">Pokud objekt musí být serializované, budou použity `NonSerialized` atribut konkrétních polí, které obsahují citlivá data.</span><span class="sxs-lookup"><span data-stu-id="f5bde-108">If the object must be serialized, apply the `NonSerialized` attribute to specific fields that store sensitive data.</span></span> <span data-ttu-id="f5bde-109">Pokud tato pole není vyloučit z serializace, mějte na paměti, které uchovávají data jsou viditelné na kód, který má oprávnění k serializaci.</span><span class="sxs-lookup"><span data-stu-id="f5bde-109">If you don't exclude these fields from serialization, be aware that the data they store are exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="f5bde-110">Další informace o psaní kódu Zabezpečte Serializační najdete v tématu [zabezpečení a serializace](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="f5bde-110">For more information about writing secure serialization code, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="f5bde-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="f5bde-111">See also</span></span>  
 [<span data-ttu-id="f5bde-112">Binární serializace</span><span class="sxs-lookup"><span data-stu-id="f5bde-112">Binary Serialization</span></span>](binary-serialization.md)  
 [<span data-ttu-id="f5bde-113">XML a serializace protokolu SOAP</span><span class="sxs-lookup"><span data-stu-id="f5bde-113">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)  
 [<span data-ttu-id="f5bde-114">Zabezpečení a serializace</span><span class="sxs-lookup"><span data-stu-id="f5bde-114">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)