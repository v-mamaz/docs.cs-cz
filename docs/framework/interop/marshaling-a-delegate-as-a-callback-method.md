---
title: Zařazování delegáta jako metody zpětného volání
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23079343244c8471f9ae5ff0a7613d0d8a84242b
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219734"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a>Zařazování delegáta jako metody zpětného volání
Tato ukázka předvádí, jak předat delegáti nespravovaná funkce očekává ukazatele na funkce. Delegát je třída, která může obsahovat odkaz na metodu a je ekvivalentní ukazatele na funkci zajišťující bezpečnost typů nebo zpětného volání funkce.  
  
> [!NOTE]
>  Při použití delegáta uvnitř volání, modul common language runtime chrání delegáta je uvolněna z paměti po dobu trvání tohoto volání. Nicméně pokud nespravovaná funkce ukládá delegáta pro použití po dokončení volání, je nutné ručně zabránit uvolňování paměti až do dokončení nespravovanou funkci s delegátem. Další informace najdete v tématu [handleref – ukázka](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hc662t8k(v=vs.100)) a [GCHandle – ukázka](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/44ey4b32(v=vs.100)).  
  
 Ukázka zpětného volání používá následující nespravované funkce zobrazené s původní deklarací funkce:  
  
-   **TestCallBack** exportovaná z knihovny PinvokeLib.dll.  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   **TestCallBack2** exportovaná z knihovny PinvokeLib.dll.  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 [Knihovny PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) je vlastní nespravovaná knihovna, která obsahuje implementace dříve uvedených funkcí.  
  
 V této ukázce `LibWrap` třída obsahuje spravované prototypy pro `TestCallBack` a `TestCallBack2` metody. Obě metody předat jako parametr delegáta funkce zpětného volání. Signatura delegáta musí odpovídat signatuře metody, na které odkazuje. Například `FPtr` a `FPtr2` delegáty mají podpisy, které jsou stejné jako `DoSomething` a `DoSomething2` metody.  
  
## <a name="declaring-prototypes"></a>Deklarace prototypů  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a>Volání funkcí  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a>Viz také:
- [Různé ukázky zařazování](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))
- [Datové typy vyvolání platformy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ac7ay120(v=vs.100))
- [Vytváření prototypů ve spravovaném kódu](creating-prototypes-in-managed-code.md)
