---
title: Chybná délka záznamu
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 37d9da67656ec4821903d8ba67a27ef10f1a437d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728858"
---
# <a name="bad-record-length"></a>Chybná délka záznamu
Mezi možné příčiny této chyby patří:  
  
-   Délka záznamu proměnná, zadaný v `FileGet`, `FileGetObject`, `FilePut` nebo `FilePutObject` příkazu se liší od délka zadaná v odpovídající `FileOpen` příkazu.  
  
-   Proměnné v `FilePut` nebo `FilePutObject` je příkaz nebo obsahuje řetězec s proměnnou délkou.  
  
-   Proměnné v `FilePut` nebo `FilePutObject` je nebo zahrnuje `Variant` typu.  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Ujistěte se, že součet velikostí proměnné pevné délky v uživatelem definovaný typ definuje typ záznamu proměnná je stejná jako hodnota uvedená v `FileOpen` příkazu `Len` klauzuli.  
  
2.  Pokud proměnnou v `FilePut` nebo `FilePutObject` příkazu nebo obsahuje řetězec s proměnnou délkou, ujistěte se, že je kratší než délka záznamu určená v aspoň 2 znaky řetězce proměnné délky `Len` klauzuli `FileOpen` příkaz.  
  
3.  Pokud proměnné v `FilePut` nebo `FilePutObject` není nebo obsahuje `Variant` Ujistěte se, že řetězce proměnné délky je kratší než délka záznamu určená v alespoň 4 bajty `Len` klauzuli `FileOpen` příkaz.  
  
## <a name="see-also"></a>Viz také:
- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
